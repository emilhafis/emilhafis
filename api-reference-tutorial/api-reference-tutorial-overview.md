# Overview

> Tapşırığıa keçməmişdən öncə **REST API üzrə əsas bölmələrə nəzər salaq.**
>
> Burada biz REST API Dizaynı üçün əsas olan 5 bölməyə baxacağıq: _resursun təsviri_, _enpoint_ və _metodlar_, _parametrlər_, _sorğu nümunəsi_ və _cavab nümunəsi/sxemi_. API dizayn etmək üçün hər bölmədə lazımlı məlumatlar ilə tanış olub "**best practice**" nümunələrə baxacağıq.

### REST API dizaynında 5 əsas bölmə

> Demək olar ki, bütün API-larda bu 5 bölmə iştirak edir.

#### [Resursun təsviri](../avtorizasiya-noevl-ri/step-1-resource-description-api-reference-tutorial.md)

Resurslar API tərəfindən qaytarılan məlumatlara deyilir. Ümumiyyətlə bizim yazdığımız API hansı məlumatları qaytarırsa, hansı resursa aid məlumatları qaytarırsa biz o resursun təsvirin veririk. Məsələn travelpayoutsda API bilet resursu üzrə məlumat qaytarırdı.

#### [Endpoint və metodlar](../avtorizasiya-noevl-ri/step-2-endpoints-and-methods-api-reference-tutorial.md)

**Endpoint** resursa necə giriş əldə edə biləcəyimizi, **metod** isə resurs üzərində hansı əməliyyatları (`GET`, `POST`, `DELETE` və s) icra edə biləcəyimizi göstərir.

#### [Parametrlər](../api-dizayn/parametrl-r.md)

**Parameter**-lər **Endpoint** ilə göndərə biləcəyimiz dəyərlərdir. Bu dəyərlər qayıdan cavabda (bundan sonra **Response**) hansı dəyərlərin olmasını və ya **Response**-un formatını təyin edir.&#x20;

#### [Sorğu nümunəsi](../api-dizayn/sorgu-nuemun-si.md)

**Sorğu nümunəsi** **Endpoint** də daxil olmaqla istifadə edilmiş `parametrlər konfiqurasiyanı` göstərir.&#x20;

#### [Cavab nümunəsi və sxemi](../api-dizayn/cavab-nuemun-si-v-sxemi.md)

Cavab nümunəsi sorğu nümunəsinə əsaslanan nümunə cavabı göstərir; **cavab sxemi** isə cavabın bütün mümkün elementlərini müəyyən edərək onların təsvirini verir.

{% hint style="info" %}
Biz işlərimizi sadə formada heç bir avtomatlaşdırılımış **API doc platformalarından** istifadə etmədən görəcəyik. Həmçinin, bilin ki, bu işləri görmək üçün müxtəlif Avtomatlaşdırılmış **API platformalar** vardır və biz onlar ilə növbəti məqalələrimizdə tanış olacağıq.

Amma sonda sizə hazırladığım **API**-ın həmin platformaların birində necə göründüyünü göstərəcəm.
{% endhint %}

### Növbəti addım

Növbəti [bölmədə Resursun təsviri](../avtorizasiya-noevl-ri/step-1-resource-description-api-reference-tutorial.md) ilə tanış olacağıq.&#x20;
