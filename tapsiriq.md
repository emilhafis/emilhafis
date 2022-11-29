---
description: Task
---

# Tapşırıq

> Prosesi daha yaxşı anlamaq üçün yenədə məsələləri praktika üzərindən edəcəyik. Belə ki, artıq analiz olunmuş məlumat üzərindən Rest API prinsiplərin və sənədləşməsin başa düşməyə çalışacağıq.

> Gəlin indi güman edək ki, siz **Tech Writer**-siniz və **Bankda** **Payment team** ilə işləyirsiniz.&#x20;
>
> Komandanıza tapşırılıb ki, bank müştərilərinin məlumatlarını 3-cü tərəf təşkilatlara vermək üçün **PSD2 standartı** əsasında **Open Banking** yaradın.
>
> Hazırda bu formatlı standart Mərkəzi Bank tərəfindən [**Ani Ödənişlər Sistemində**](https://anipay.az/open-banking) yaradılmışdır. Amma, bizə sırf bankda yaradılmış mərkəzləşdirilmiş Open Banking lazımdır ki, onu istədyimiz formada hazırlayaq.
>
> Komandanız sizə bildirir ki, API tələblərin artıq digər analitiklər analiz etmiş, yəni **endpoint proqramlaşdırılmış** və **** bizə isə **** onu dizayn edib sənədləşdirmək lazım olduğu bildirilir. Bizim sənədləşmədən digər 3-cü tərəflər istifadə edib servisləri öz proqramları ilə inteqrasiya etməlidirlər. 1-ci dərsdəki Travlepayoutsu təsəvvür edinki biz yaradıqır amma burada biz bilet yox bank haqqında məlumatlar qaytaracağıq.

{% hint style="info" %}
Ödəniş Xidmətləri Direktivi İkinci (PSD2) ödəniş xidmətləri təminatçılarını müştərilərin autentifikasiyası proseslərini təkmilləşdirməyə məcbur etmək və həmçinin üçüncü tərəflərin iştirakı ilə bağlı yeni tənzimləmələr gətirmək üçün nəzərdə tutulmuş qanunvericilikdir.

Bizdə də qanunvercilik olacaq və 3 cü tərəflər bank məlumatların ala biləcəklər.
{% endhint %}

{% hint style="info" %}
Çox vaxt, **endpoint** yerinə **API**-da deyilir.
{% endhint %}

> Aşağıda bizə yeni API `Get account balance API` haqqında məlumatları təqdim edirlər.

Bu məlumatları Travelpayouts və ya ev tapşırığınızdakı API məlumatları ilə müqaisə etsəniz, görərsiniz ki, bunları loru dildə desəm "adam içinə çıxarmaq olmaq"
