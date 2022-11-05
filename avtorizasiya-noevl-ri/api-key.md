# API Key

### API Key nədir

> Bir çox şirkətlər, onların API-larındən istifadə etmək üçün `API Key` üçün qeydiyyatdan keçməyi tələb edirlər.&#x20;
>
> `API Key` **** uzun dəyərlərdən (long string) ibarət olur və adətən `URL` və ya `Request header`-ə əlavə edilir. `API Key` API sorğu edəni autentifikasiya etmək, yəni təyin etmək üçün istifadə edilir.&#x20;
>
> `API Key` həmçinində proqram təminatının xüsusi bir komponeneti ilə əlaqələndirilə bilər və yalnız ora giriş icazəsini təmin edə bilər. Yəni, API üzrə 5 fərqli məlumat almaq mümkündürsə, ola bilər ki, bizə onun yalnız 2-nə icazə verilir.

{% hint style="warning" %}
API development zamanı **URL**-də olan bütün məlumatlar loglanır. Yəni, log məlumatı kimi yadda saxlanılır və lazım olarsa araşdırma zamanı istifadə edilir. Əgər biz **API Key dəyərini** `query parameter` kimi (**URL**-də göndərilsə) təyin etsək, o zaman çox güman ki, bu dəyər də loglanmalarda əks olunacaqdır. Belə olduqda **API Key**-in əldə edilməsi asanlaşır.&#x20;

Qəbul olunmuş ən yaxşı təcrübə bu dəyərin `header parameter` kimi göndərilməsidir, çünki header məlumatları əsasən loglanmır.

Bu səbəbdən də, **API Dizayn** hazırlayarkən **API Key** dəyərini `headerparameter` kimi sənədləşdirin.
{% endhint %}

![API Key](../.gitbook/assets/api\_key.png)

> Bir çox API dokumentasiya saytlarına qeydiyyatdan keçib daxil olduqdan sonra, sizin `API Key` dəyəriniz avtomatik formalaşdırılır və sizə təqdim olunur.&#x20;
>
> Məsələn, aşağıda [avia bilet API-ları təmin edən platformada](https://www.travelpayouts.com/) qeydiyyatdan keçdikdən sonra avtomatik olaraq bizim üçün **API Key** formalaşır.

#### Travelpayouts API Key

![](<../.gitbook/assets/api\_key\_edit 2.png>)
