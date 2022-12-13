# Access/Refresh Token

### Access token nədir?

{% hint style="info" %}
OAuth **Access token** (giriş token) müəyyən bir müddət ərzində xüsusi resurslara məhdud girişə icazə vermək üçün verilir və icazə verən istifadəçi və ya token-i verən server tərəfindən ləğv edilə bilər.&#x20;
{% endhint %}

> Yuxarıdakı qeydi aydınlaşdırmağa çalışaq.
>
> **Access token** (və ya **token**) xüsusi resurslara məhdud girişə icazə vermək üçün generasiya edilir.
>
> Biz [**Rapid API** saytında qeydiyyatdan keçən zaman](overview.md#rapid-api-platformasi) **Google** üzərindən autentifikasiyanı seçiriksə, bu zaman Google bizdən gmail accountu üçün `şifrə:parol` istəyir. Biz düzgün məlumatları daxil etdikdən sonra, Google **Rapid** saytına bizə bağlı `Access token` verir. Sonradan **Rapid** saytı bu `Access token` ilə müraciət edib bizim icazə verdiyimiz məlumatları (məsələn, ad,soyad) **Google**-dan götürə bilər.
>
> Xüsusi resurslara məhdud giriş (limited access) isə o deməkdir ki, istifadəçinin resurslarına/məlumatlarına tam girişə ehtiyac olmur. `Access tokenlər`i də məhdud zaman üçün etibarlı olur. `Access token` üçün etibarlılıq müddətinin təyin olunması təhlükəsizlik effektini yüksəldir.
>
> Access token-lər ləğv edilə bilər, belə olduqda artıq onlar ilə giriş uğurlu olmayacaqdır. Bu ləğv etmə tokeni verən server tərəfindən və ya istifadəçi tərəfindən həyata keçirilə bilər.&#x20;

{% hint style="info" %}
**Google** OAuth **Access token**ləri "`opaque strings`"-dir. Yəni token hər hansı bir məlumat əsasında şifrələnmiş, encode edilmiş dəyər deyil, sadəcə ixtiyari dəyərlərdən formalaşır. Bunun əsas üstünlüyü odur ki, tokeni formalaşdırmaq üçün lazım olan bütün məlumatlar avtorizasiya serverində saxlanılır. Yəni, digər serverə məlumat üçün müraciət edilmir (məsələn, istifadəçi məlumatları).
{% endhint %}

{% hint style="warning" %}
Əgər siz tech writer kimi access token istifadə etməyə qərar vermisinizsə, o zaman bu dəyəri Authorisation header-də istifadə edərək, "bearer token" kimi göndərilməsini qeyd edin.
{% endhint %}

> The `Authorization: <type> <credentials>` pattern was introduced by the W3C in [HTTP 1.0](https://www.rfc-editor.org/rfc/rfc1945), and has been reused in many places since. Many web servers support multiple methods of authorization. In those cases sending just the token isn't sufficient.
>
> Sites that use the
>
> ```
> Authorization : Bearer cn389ncoiwuencr
> ```
>
> format are most likely implementing OAuth 2.0 [bearer tokens](https://www.rfc-editor.org/rfc/rfc6750).The [OAuth 2.0 Authorization Framework](https://www.rfc-editor.org/rfc/rfc6749) sets a number of other requirements to keep authorization secure, for instance requiring the use of HTTPS/TLS.
>
> If you're integrating with a service that is using OAuth 2.0 it is a good idea to get familiar with the framework so that the flow you're using is implemented correctly, and avoiding unnecessary vulnerabilities. There are a number of good tutorials available online.

### Access token necə əldə edilir?

> İlk öncə, tətbiq avtorizasiya serveri ilə autentifikasiya edilməlidir. OAuth protokolunda bu proses **Client ID** və **Client secret** dən istifadə edilməklə həyata keçirilir.&#x20;

> Daha sonra, resursun sahibi (istifadəçi), avtorizasiya serverində öz məlumatları ilə autentifikasiya olunmalıdır.&#x20;
>
> Bundan əvvəl bildirdiyim kimi, [Rapid API](https://rapidapi.com/) saytında istifadəçi (resurs sahibi) qeydiyyat zamanı `Sign up with Google` seçimi seçdikdən sonra, öz gmail hesabının `username:password` nu daxil edib orada autentifikasiyadan keçir. Bununla istifadəçi təsdiq edir ki, resursun sahibi (gmail) həqiqətəndə odur və sayta daxil olmağı təsdiq edir. Nəticədə **Google** **Rapid**-ə **Access token** verir.

> İstəyə bağlı olaraq `Access token`-ə məhdud yerlərə giriş icazələri verilə bilər. Bu, token üçün icazə verilməli olan giriş səviyyəsini təyin edəcəkdir. Yəni token üçün sorğu göndərilərkən bu token-lə hansı məlumatları əldə etmək və ya hansı əməliyyatları etmək istənildiyi göstərilir. Token-i verən resurs yoxlama nəticəsində görsə ki, həqiqətəndə bu icazələr verilə bilər o zaman sorğuya uyğun cavabı qaytarır.

### Refresh token

> **Refresh token** etibarlılıq müddəti bitmiş **Access token**-i yenidən almaq üçün istifadə olunur. Yəni, bu proses arxa fonda gedir və istifadəçinin bundan xəbəri olmur. **Refresh token** olmasa gərək istifadəçi etibarlılıq müddəti bitmiş **Access token** üçün hər dəfə öz məlumatlarını (credentials) daxil edib prosesi yenidən başlatsın.

### Refresh token istifadəsi

> Yeni **Access token** əldə etmək üçün **Refresh token**-dən necə istifadə edilir?
>
> Yeni **Access token** almaq üçün, tətbiq yalnız özünün **Client ID** və **Client secret**-ni autentifikasiya olunmaq üçün autentifikasiya serverinə (məsələn Google) göndərir.&#x20;

{% hint style="info" %}
Rapid misalında - Rapid `Client ID` və `Client secret` dəyərini Google-da qeydiyyatdan keçərkən alır.

Burada çox dayanmayın, növbəti bölmələrdə sizə tam aydın olacaq.
{% endhint %}

> Burada istifadəçi məlumatlarından (şifrə, parol və ya yenidən Google üzərindən onu autentifikasiya etmək) istifadə olunmur. Bunun əvəzinə **Refresh token** istifadə olunur.
>
> Bu məlumatlar ilə sorğu göndərildikdə **Access token** yenidən generasiya edilib qaytarılır və istifadəçinin işlərində hansısa dayanma olmur.
>
> Bir sözlə istifadəçinin öz istifadəçi adını və şifrəsini yazaraq yenidən Google üzərindən autentifikasiyasına ehtiyac qalmır. &#x20;

{% hint style="info" %}
Edilə biləcək hər hansı bir təhlükənin qarşısını almaq üçün **Access token**-nin etibarlılıq müddəti olur.

**Access token** üçün qəbul edilmiş ümumi bitmə müddəti 5 dəqiqədir. Təsəvvür edə bilrisinizmi, **Refresh token** olmasa idi, hər 5 dəqiqədən bir istifadəçilər öz istifadəçi adını və şifrələrini daxil etməyə məcbur olacaqdılar. Bu səbəbdən də biz **Refresh token**-dən istifadə edirik.
{% endhint %}

> Adətən **Refresh token** istifadə edildikdə yenisi yaradılaraq **Access token** ilə birgə göndərilir.
