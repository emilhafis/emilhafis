# Ümumi proses

Bütün grant növləri demək olar ki, **ümumi modelə əsaslanır** və aşağıdakı sxemə uyğun proseslər həyata keçir.

Belə ki, tətbiq (sxemdə Client) tokenə ehtiyacı müəyyən edir, yeni [**Access token**](../oauth/access-refresh-token.md#access-token-n-dir) tələb edir və nəhayət qorunan resursa daxil olmaq üçün tokendən istifadə edir.



![](<../.gitbook/assets/Common\_process 2.PNG>)

> Sxemdə 3 istinad nöqtəsi göstərilmişdir.
>
> 1. Tətbiqdən sorğu göndərən **Client** (burada Client qismində istifadəçi+tətbiq birlikdə göstərilmişdir)
> 2. **API Gateway** və ya **Authorsation server.** Token bu serverdə yaradılır və yoxlanılır.&#x20;
> 3. Məlumatları təmin edən **Backend API** və ya **Backend servis.**

![](../.gitbook/assets/common\_token\_creation.png)

> İlk öncə, **Client** token əldə etmək üçün müraciət edir.&#x20;
>
> Bu proses hər bir grant növünə görə fərqli olur və biz növbəti bölmələrdə bunu əhatə edəcəyik.

![](../.gitbook/assets/common\_get\_resource.png)

> Yeni token əldə edildikdən sonra **Client** lazım olan məlumatın alınması üçün **API Gateway/ Auth server** - nə müraciət edir.
>
> **API Gateway/ Auth server token**-in etibarlılığını yoxlayır, etibarlı olduğu təqdirdə sorğunu icra etmək üçün **Backend API** və ya **Backend servisi**nə göndərir.&#x20;
>
> **Backend servis**i sorğuya uyğun cavabı qaytarır.

{% hint style="info" %}
Bəzi digər proseslərdə Token alındıqdan sonra **API Gateway/ Auth server**-nə deyil, birbaşa **Backend API** və ya **Backend servisi-**nə token ilə müraciət göndərilib lazımı məlumatlar istənilir.&#x20;

Tövsiyə olunandır ki, bütün sorğular ilk öncə **API Gateway/ Auth server** göndərilsin və burada token yoxlanılsın. Əgər proses uğurlu olarsa bu servis özü **Backend API** və ya **Backend servisi-**nə müraciət göndərsin.

Bu sxemlərdə göstərdiklərim **Google**-da hazırlanan arxitekturaya əsaslanır.
{% endhint %}

![](../.gitbook/assets/common\_token.PNG)

> **Client** vaxtı keçmiş və ya etibarlı olmayan token ilə müraciət etdikdə **API Gateway/ Auth server token**-i yoxlayaraq `401 Unauthorized` xətası qaytarır. Belə olduqda resursa giriş üçün sorğu **Backend API** və ya **Backend servisi**nə göndərilmir.
>
> Bu halda tətbiq istifadəçinin xəbəri olmadan bundan əvvəl qeyd etdiyimiz [**Refresh token**](../oauth/access-refresh-token.md#refresh-token) ilə müraciət edərək yeni **Access token** əldə edir.
>
> **Token**-nin bu etapda və ya yeni yaranan zaman formalaşması eyni formada aparılır.
