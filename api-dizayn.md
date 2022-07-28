---
description: Bu bölmədə API sənədləşmədə istifadə olunan autentifikasiyadan danışacağıq
---

# API Dizayn

{% hint style="info" %}
**API Dizayn** dedikdə - API sənədləşməsi və "API-First approach" nəzərdə tutulur. Yəni, developerlər üçün API üzrə tam detallı sənədin hazırlanması.
{% endhint %}

### API autentifikasiya sənədləşmədə

> **API** sənədləşməsində autentifikasiya metodunun necə işlədiyini detallı göstərməyə **ehtiyac yoxdur.**&#x20;
>
> **API**-dan sui-istifadə hallarının qarşısını almaq üçün autentifikasiya prosesinin daxili təfərrüatlarını izah etməmək ən düzgün yoldur.

### Nələr göstərilməlidir?

> Qeyd edilənlərə baxmayaq, siz **API Dizayn** hazırlayarkən bir neçə məlumatı göstərməli və onlardan necə istifadə edilməsini aydın qeyd etməlisiniz. Məsələn:
>
> * ****[**API Key** ](avtorizasiya-noevl-ri/api-key.md)necə əldə olunur.
> * Sorğular necə **autentifikasiya** olunur.
> * Uğursuz autentifikasiya üzrə **error** mesajları nələr olur.
> * Autentifikasiya məlumatlarında **məxfilik** (sensitivity) məlumatları hansılar olur.
> * **Token** bitmə tarixi nə vaxt olur.

> Əgər sizin **API**-larda həm `public`, həm də `private key` olarsa, siz göstərməlisiniz ki, bunlar harda istifadə olunur və qeyd etməlsiniz ki, `private key`-lər paylaşılmamalıdır.&#x20;
>
> Müxtəlif **API** sorğularını çağırmaq üçün müxtəlif lisenziya səviyyələrindən **(`license tier)`** istifadə edilərsə, bunlar haqqında məlumat sizin **autentifikasiya** bölmənizdə və ya digər yerdə açıq şəkildə göstərilməlidir.
>
> Developerlər-in **API**-dən istifadə etmələri üçün [**API Key**](avtorizasiya-noevl-ri/api-key.md) **** onlar üçün zəruri olduğundan, bu dəyərin necə alınması adətən gözəçarpan yerdə, məsələn **Help** başlığının əvvəlində göstərilir.

### Nümunələr

Müxtəlif platformaların  autentifikasiya və ya avtorizasiya bölmələri üzrə bəzi nümunələr ilə aşağıda tanış ola bilərsiniz.&#x20;

### [Twitter](https://developer.twitter.com/en/docs/authentication/oauth-2-0)

> Siz Twitter-dən istifadə edərək autentifikasiya-nı həyata keçirə bilərsiniz.&#x20;
>
> Twitter OAuth 2.0 protokolundan istifadə edir və [öz saytlarında](https://developer.twitter.com/en/docs/authentication/oauth-2-0) bu haqda detallı məlumatları qeyd etmişlər.

![](.gitbook/assets/twitter\_auth.png)

### [Ebay](https://developer.ebay.com/api-docs/static/oauth-tokens.html)

> Həmçinində Ebay OAuth 2.0 protokolundan istifadə edir və [developer bölmədə](https://developer.ebay.com/api-docs/static/oauth-tokens.html) istifadə üzrə detallı təfərrüatları qeyd etmişlər.

![](.gitbook/assets/ebay\_oauth.PNG)

### [Google identitiy](https://developers.google.com/identity/protocols/oauth2)

> Bundan əvvəl nümunələrdə tanış olduğumuz kimi OAuth 2.0 protokolundan istifadə edən böyük platformalardan biridə Google-dur və istifadə qaydaların [detallı göstərmişlər.](https://developers.google.com/identity/protocols/oauth2)

![](.gitbook/assets/google\_oauth.png)
