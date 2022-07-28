# Client Credentials

![](../.gitbook/assets/Clent\_crd\_grant.png)

## Nədir?

> **Client credentials grant** növü əsasən sistemlər arası yəni machine-to-machine (M2M) və ya system-to-system əlaqələrində istifadə olunur. Sistem - istifadəçiləri deyil, digər tətbiqləri, sistemləri autentifikasiya edir.&#x20;
>
> Bu senaridə ənənəvi autentifikasiya sxemi olan istifadəçi adı + şifrə, sosial şəbəkədəki giriş məlumatlarından istifadə məna kəsb etmir.
>
> Qorunan istifadəçinin məxfi məlumatlarına giriş imkanı olan servislərdə bu **grant** növündən istifadə edilməməlidir. Bu **grant** növü hər hansı bir istifadəçi credential-ları toplamır, ona görə də istifadəçinin autentifikasiya etmək və ya məlumatlara giriş əldə edən proqrama razılıq vermək kimi bir imkanı olmur.

### Necə işləyir?

![](../.gitbook/assets/Client\_credentials2.png)

> Yuxarıdakı sxemə uyğun olaraq **proses** aşağıdakı formada həyata keçirilir:
>
> 1. 3-cü tərəf **application** (məs, hər hansı bir sayt **Google map**-dən istifadə etmək istəyir. Burada sayt - M2M App-dır) **API Gateway / Auth server**- də autentifikasiya olunmaq üçün özünün **Client ID** və **Client Secret**-indən istifadə edir.
> 2. **API Gateway / Auth server** **Client ID** və **Client Secret**-in həqiqiliyini yoxlayır.
> 3. Yoxlama uğurlu olduqda **API Gateway / Auth server** **Access token** generasiya edib qaytarır.
> 4. **Application** access token-dən istifadə edərək lazımı məlumatı əldə etmək üçün sorğu göndərir.
> 5. **API Gateway / Auth server** token-i yoxlayır.&#x20;
> 6. Token etibarlı olarsa **API Gateway / Auth server** sorğunu **Backend API / Backend Servis**-ə göndərir.
> 7. **Backend API / Backend Servis** lazımı məlumatları **API Gateway / Auth server**-nə qaytarır.
> 8. **API Gateway / Auth server** məlumatları **Application**-a göndərir.

{% hint style="info" %}
**Client ID** və **Client Secret** dəyərləri tətbiqi **Google**-da qeydiyyatdan keçirərkən verilir.
{% endhint %}

{% hint style="info" %}
Digər **grant** növlərindən fərqli olaraq **Client credential grant** növündə adətən [**Refresh token**](../oauth/access-refresh-token.md#refresh-token) qaytarılmır.&#x20;

Belə ki, **Refresh token** istifadəçinin məxfi məlumatlarını təkrar təkrar göndərməsinin qarşısını almaq üçün istifadə olunduğundundan və burada da istifadəçi məlumatları olmadığından [**Resfresh token**](../oauth/access-refresh-token.md#refresh-token-istifad-si)-in istifadəsi zəruri olmur.
{% endhint %}

## <mark style="color:blue;">Google Apigee nümunəsi</mark>

> Bu bölmədə **Google**-da **Client credentials grant** növü üzrə proses necə gedir onu qısa olaraq göstərməyə çalışacam.

### [Access tokenin](../oauth/access-refresh-token.md#access-token-n-dir) yaradılması

> Nəzərə almaq lazımdır ki, Google-da və bir çox digər sxemlərdə **Backend servis**i tokenin yaradılmasında iştirak etmir.
>
> Aşağıda ümumi sxem təsvir olunmuşdur. Sxem üzrə addımlar ilə detallı tanış olacağıq.

### Access token sorğusu

![](../.gitbook/assets/Token\_creation\_1.png)

> 1. **Client** (burada müxtəlif **Application**-lar nəzərdə tutulur) token endpoint-nə (**API Gateway / Auth server -** Burada Google üzrə **Apigee** adlandırılıb) **Client credentials grant** növü ilə **POST** sorğusu göndərir. Sorğuya **Application**-nun `Client ID` və `Client secret`-də əlavə edilir.

{% hint style="info" %}
Bu keysdə Google token sorğusunun əldə olunması üçün **POST** metodundan istifadə edir.

Amma bəzi senarilərdə bunun üçün GET metodundan istifadə olunduğunuda görürük. GET sorğuları bookmark və ya cach-də saxlana bilər və belə olduqda bu token sorğusu üçün uyğun olmur. Belə ki, OAuth token yaradılma funksionallığı digər tətbiqin backend servislərinin müraciət etdiyi servisdə yox digər servislərdə idarə olunur.&#x20;
{% endhint %}

> 2\. **Apigee** `Client ID` və `Client secret` yoxlayır.&#x20;
>
> 3\. Əgər etibarlı olarsa **Access token**-i, **Token** üzrə bitmə tarixini göndərir.

{% hint style="warning" %}
Qeyd edtdiyimiz kimi, burada da istifadəçi məlumatları (credentials) istifadə olunmadığı üçün [**Refresh token**](../oauth/access-refresh-token.md#refresh-token) **** generasiya edilmir.
{% endhint %}

### Google API Request və Response nümunəsi

![](<../.gitbook/assets/Apigee get token.png>)

> Nümunədə **API** sorğusu və cavabı üzrə əks olunan dəyərlər qeyd olunur. Bu sorğu Google servisinə **Client credentials grant** növündə **POST** metodu ilə göndərilmişir.&#x20;

### Basic Authentication

![](<../.gitbook/assets/Apigee get token 2.png>)

> `Client ID` və `Client Secret` `Authorisation header`-də [encode](../avtorizasiya-noevl-ri/basic-auth.md#base-64-encode-v-decode) olunaraq göndərilir.&#x20;
>
> Google autnetifikasiya üsulu kimi [basic authentication](../avtorizasiya-noevl-ri/basic-auth.md)-dan istifadə edir.
>
> **Application**-nun credential məlumatları olan `Client ID` və `Client Secret` encode olunmuş  [**Base64**](../avtorizasiya-noevl-ri/basic-auth.md#base-64-encode-v-decode) formatında `Header` dəyəri kimi göndərilir.

{% hint style="warning" %}
Bir daha qyed edək ki, [`base64 encoding`](../avtorizasiya-noevl-ri/basic-auth.md#base-64-encode-v-decode) `` şifrələmə demək deyil. Siz base64 formatına konvertasiya olunmuş məlumatı əvvəlki dəyərnə qaytara bilərsiniz.
{% endhint %}

> Göründüyü kimi, **Google** App credential-larını (`Client ID` və `Client Secret )` yalnız **encode** edir yəni **şifrələmir**.&#x20;
>
> Qeyd edirlər ki, biz [TLS (SSL)](../oauth/terminologiya/#tls-ssl-https) vasitəsilə sorğu və cavabı encrypt etdiyimiz üçün məlumat mübadiləsində bütün məlumatlar qorunur.

### Access token bitmə tarixi

![](<../.gitbook/assets/Apigee Get Token 4.png>)

> Application üçün **Access token**in bitmə tarixini bilmək çox vacibdir.
>
> Bu səbəbdəndə **Google** **Tokeni** **Application**-a qaytararkən onun bitmə tarixini və digər parametrləridə göstərir.

### Token istifadəsi

![](<../.gitbook/assets/Apigee use token.png>)

> **Google** **Token**-nin `Authorization header`-də göndərilməsini tələb edir. Şəkildə `Bearer` qarşısında gördüyünüz **Token** nümunəsidir.
>
> Google OAuthV2 siyasətinə uyğun olaraq Tokeni yoxlayır.
>
> Yoxlama bu formada həyata keçirilir - ilk öncə tokenin etibarlı və istifadə müddəti yoxlanılır, əgər yoxlama uğurlu olarsa sorğulanan resursa (məsələn burada **items**) token-in icazəsinin olub olmaması yoxlanılır. Əgər icazə olmazsa, `401 Unauthorized` qaytarılır, əks halda uğurlu cavab ilə istənilən məlumatlar qaytarılır.&#x20;
