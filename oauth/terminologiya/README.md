# Terminologiya

### Ümumi terminlər

> **`Grant types:`**` ``Authentication usage scenarios supported by OAuth 2.0` - Grant types (icazə hüquqları) OAuth tərəfindən tərtib edilən müxtəlif avtorizasiya senarilərini təyin edir. Grant növlərini növbəti bölmələrdə daha ətraflı qeyd edəcəyik.&#x20;

> **`Client IDs and client secrets:`**` ``used to identify and authenticate apps` - Tətbiqləri identifikasiya və autentifikasiya etmək üçün **Client ID** və **Client secret** dəyərndən istifadə olunur.&#x20;
>
> Məsələn, əvvəlki bölmədə qeyd etdiyimiz **Rapid** saytı **Google** vasitəsilə girişi tətbiq edən zaman, ilk öncə Google-da qeydiyyatdan keçib öz platformasın tanıtmış və **Google** **Rapid** platformasına **Client ID** və **Client Secret** təqdim etmişdir.&#x20;

{% hint style="info" %}
Google-da bunların alternativi müvafiq olaraq **Client ID** kimi **Consumer key**, **Client secret** kimi isə **Consumer secret** dəyərləridir.
{% endhint %}

> **`Scopes:`**` ``Limit the access for a given token` - Token üzrə verilmiş icazənin əhatə dairəsi. Məsələn hansı sorğuları göndərib cavabın ala bilər və s.

#### TLS/SSL/HTTPS

> **`TLS:`**` ``All OAuth 2.0 traffic must be sent encrypted via TLS` -&#x20;
>
> Siz çox güman ki, **TLS**-i **SSL** və ya **Secure Sockets Layer** və ya **HTTPS** kimi tanıyırsınız. **TLS** **SSL**-in davamçısıdır və **SSL** artıq istifadə edilməməlidir.
>
> **TLS** vasitəsilə **API** sorğuları və cavabları client (Rapid) və server (Google) arasında ötürülərkən şifrələrnir. OAuth-un ciddi tələbi var ki, bütün OAuth trafiki, o cümlədən token-ə malik istənilən API sorğusu şifrələnsin. Şifrələmə tokenləri, **Client ID** və **Client secret**-ləri 3-cü tərəflərin əlinə keçməsindən qoruyur.

### Tətbiq növləri

{% hint style="warning" %}
Tətbiq dedikdə - saytlar, mobil tətbiqlər və digər proqram təminatları nəzərdə tutulur&#x20;
{% endhint %}

> Tətbiqlər **konfidensial** və ya konfidensial olmayan (bundan sonra - **public**) ola bilər.&#x20;
>
> Konfidensial tətbiqlər məxfi məlumatları konfidensial olaraq saxlayır. Bu o anlama gəlir ki, **token**-lər və **Client secret**-ləri elə saxlanılır ki, onları əldə etmək mümkün olmur.&#x20;
>
> **Public** tətbiqlər isə konfidensial olmayan tətbiqlərdir.&#x20;
>
> Məxfi məlumatlar **public** tətbiqlərdə saxlanılmır, çünki bu məlumatlar qorunmur.&#x20;

> Tətbiqlər güvənilən (bundan sonra - **trusted**) və ya güvənilməyən (bundan sonra - **untrusted**) qruplara bölünür.
>
> Sizin şifrələr tətbiqə məlum olursa bu **trusted** tətbiq olur əks halda **untrusted**.
>
> Trusted tətbiqlər sizin daxil etdiyiniz məxfi məlumatları saxlayan tətbiqlərdir (məsələn, **Google** - **gmail**)
>
> 3-cü tərəfin tətbiqləri isə hər zaman **untrusted** tətbiqlər olur.&#x20;

> Məsələn, yuxarıda da qeyd etdiyimiz kimi, siz [Rapid API saytında ](https://rapidapi.com/)qeydiyyatdan keçən zaman sizə `"Sign up with Google"` təklifi çıxır. Burada **Rapid API** saytı 3-cü tərəf, yəni `untrusted`, `public` **Google** isə `trusted` və `konfidensial` tətbiqdir.
>
> Burada siz Google seçimi seçdikdən sonra yazdığınız istifadəçi adı və şifrə və ya yaddaşda olan bu məlumatlar **Rapid API** platformasına məlum olmur. Bir sözlə siz öz giriş məlumatlarınızı sayt ilə paylaşmırsınız. Bu səbəbdən də, bu kimi 3-cü tərəf platformalar hər zaman **untrusted** hesab edilir.

![](<../../.gitbook/assets/vk\_swiftshader\_icd.json (1).png>)

> Giriş ilə bərabər, OAuth 3-cü tərəf platformalara Google-da artıq mövcud olan bir sıra məlumatları da təqdim etməyə icazə verir. Siz artıq rastlaşmısınızsa bu formada qeydiyyatdan keçəndə [razılıq verirsiniz](../../oauth-grant-noevl-ri/authorization-code/#icaz) və avtomatik olaraq gmail-də qeyd etdiyiniz ad və soyad 3 cü tərəf saytda əks olunur. Bu məlumat paylaşmasıda OAuth ilə həyata keçirilir.
>
> Biz bu haqda növbəti bölmələrdə daha geniş danışacağıq.

{% hint style="danger" %}
Siz API Dizayn edərkən, yaradılan tətbiqin public və ya konfidensial, trusted və ya untrusted təyin etməlisiniz. Bu sizə düzgün OAuth grant növlərini seçməyə imkan verəcəkdir.
{% endhint %}
