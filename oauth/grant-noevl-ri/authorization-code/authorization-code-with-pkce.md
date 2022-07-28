# Authorization Code with PKCE

{% hint style="warning" %}
Biz bildirdik ki, hazırda istifadəçi məlumatları (credentials) üçün ən çox istifadə olunan grant növü [**Authorization code**](./)-dur. Bu növdə də, **Client** tərəf, yəni sayt tərəf qeydiyyat zamanı təqdim olunan `Client ID` və `Client Secret` dəyərlərini təhlükəsiz formada saxlamalıdır.

Əgər Client tərəf bunu etmək istəmirsə və ya etmək üçün gücü yoxdursa nə edilməlidir? Belə çıxır ki, [Authorization code grant](./) növüdə etibarlı deyil?
{% endhint %}

### Ümumi məlumat

Qeyd etdiyimiz kimi, Public client-lər (məsələn, [native](authorization-code-with-pkce.md#native-apps) və [single-page applications](authorization-code-with-pkce.md#single-page-apps)) [Auth Code grant növü ](./)əsasında [Access token](../../access-refresh-token.md#access-token-n-dir) üçün sorğu etdikdə, əlavə təhlükəsizlik məsələləri ortaya çıxır. Bunun səbəbləri:

#### **Native apps**

{% hint style="info" %}
**Native application -** xüsusi əməliyyat sistemləri üzrə yazılmış tətbiqlərdir. Məsələn iOS və ya Android üçün yazılmış mobil bankçılıq.
{% endhint %}

> * `Client ID` və`Client Secret`-i təhlükəsiz formada saxlaya bilmir. Tətbiqi decompile (yəni mobil tətbiqin mənbə kodlarının alınması) etdikdə, orada mənbə kodları ilə yanaşı `Client ID` və `Client Secret` dəyərlərinidə əldə etmək olur. Bu dəyərlər isə bildiyimiz kimi bu tətbiqdən istifadə edəcək bütün istifadəçilərə şamil olunur.&#x20;
> * Həmçinində fırıldaqçılıq üçün xüsusi URL sxemdən istifadə edilərək sizin göndərdiyiniz `Authorisation code` əldə edilə bilər.

#### **Single-page apps**

{% hint style="info" %}
**Single Page Application (SPA)** əsasında hazırlanan saytlar browser vasitəsilə backend-dən bir dəfə HTML (yəni veb səhifə) götürür. Bundan sonra istifadəçi başqa səhifəyə keçid edəndə artıq backend-dən yeni HTML götürülmür və yalnız lazım olan məlumatlar JavaScript API-lər ilə gətirilərək müvafiq dəyişikliklər əks olunur.&#x20;

Bir sözlə səhifə yenilənməsinə ehtiyac olmur və belə olduqda sürət əhəmiyyətli dərəcədə artır və istifadəçi "native" tətbiq istifadə etmiş kimi hiss edir.

Hazırda Gmail, Facebook, Trello, Google Maps və başqaları bu mexanizmdən istifadə edir.

Ənənəvi **Multiple-page applications** - da isə hər dəfə səhifə yenilənir. Düzdür hazırda AJAX vasitəsilə bunun iş prinsipi dahada sadələşmişdir.

Hər iki metodun özünə uyğun müsbət və mənfi tərəfləri vardır. [Buradan tanış ola bilərsiniz.](https://medium.com/@NeotericEU/single-page-application-vs-multiple-page-application-2591588efe58)
{% endhint %}

> * `Client ID` və`Client Secret`-i etibarlı şəkildə saxlamaq mümkün deyil, çünki onların bütün mənbəyi brauzer üçün əlçatandır.

### Çıxış yolu

> * Qeyd edilən problemlərin həlli üçün OAuth 2.0 Authorization Code Flow grant növünün yeni versiyası olan **Proof Key for Code Exchange (PKCE)** yaratmışdır.



> The PKCE-enhanced Authorization Code Flow sorğu göndərən Application tərəfindən yaradılan və **API Gateway / Auth server**-nə göndərilən `secret` dəyərini ehtiva edir.&#x20;
>
> Bu `secret`  `Code Verifier` adlanır.&#x20;
>
> Əlavə olaraq sorğunu göndərən Application `Code Verifier` -in mübadiləsi üçün `Code Challenge` adlandırılan dəyər formalaşdırır və [`HTTPS (TLS/SSL)`](../../../avtorizasiya-noevl-ri/basic-auth.md#https) üzərindən `Authorization Code` əldə etmək üçün **API Gateway / Auth server-**nə göndərir. Belə olduqda fırıldaqçılar yalnız `Authorization Code` əldə edə bilərlər və onlar `Code Verifier` olmadan `Authorization Code` ilə [`Access Token`](../../access-refresh-token.md) `` əldə edə bilməzlər.

### Necə işləyir?

{% hint style="info" %}
Bu növ [**Authorization code grant**](./) **** növü ilə demək olar ki, eynilik təşkil edir. Fərq yalnız ondadır ki, Application əldə etdiyi`Client ID` və `Client Secret` əvəzinə proses zamanı özünün generasiya etdiyi`Code Verifier və Code Challenge` dəyərlərindən istifadə edir.
{% endhint %}

![](../../../.gitbook/assets/auth\_pcka-2.png)

> Proses aşağıdakı formada həyata keçirilir:
>
> 1. İstifadəçi tətbiq və ya sayt daxilində **Login** bölməsin seçir.
> 2. App ixtiyari rəqəmlərdən ibarət kriptoqrafik `code_verifier` və bundan isə `code_challenge yaradır.`
> 3. Sayt istifadəçini **API Gateway / Auth server**-nin login və avtorizasiya bölməsinə `code_challenge` ilə birlikdə yönləndirir.
> 4. **API Gateway / Auth server-**in **login** bölməsi isitfadəçiyə çıxarılır ([nümunə](./#pop-up)).
> 5. İstifadəçi göstərilən login metodlarından birini seçir və həmçinində, tələb edilirsə bəzi məlumatlarının götürülməsi üçün icazəni təsdiq edir ([nümunə](./#icaz)).
> 6. **API Gateway / Auth server** `code_challenge` saxlayır və istifadəçini geriyə, tətbiqə `authorization code` ilə birlikdə yönləndirir.
> 7. App bu `authorization code`-u və 2-ci addımda yaradılmış olan `code_verifier` dəyərini **API Gateway / Auth server**-nə **** göndərir.
> 8. **API Gateway / Auth serve** `code_challenge` və `code_verifier` yoxlayır.
> 9. Yoxlama uğurlu olduqda **API Gateway / Auth server** `Access token` (lazım olduqda R**efresh token**) generasiya edib App-a qaytarır.
> 10. **App** `Access token`-dən istifadə edərək lazımı məlumatı əldə etmək üçün sorğu göndərir.
> 11. Token etibarlı olarsa **API Gateway / Auth server** sorğunu **Backend API / Backend Servis**-ə göndərir.
> 12. **Backend API / Backend Servis** lazımı məlumatları **API Gateway / Auth server**-nə qaytarır.
> 13. **API Gateway / Auth server** məlumatları **Application**-a göndərir.
