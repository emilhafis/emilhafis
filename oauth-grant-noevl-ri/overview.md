# Overview

> OAuth **grant** növləri OAuth avtorizasiya senarilərini idarə etmək üçün nəzərdə tutulan müxtəlif icazə senarilərini təyin edir. Biz növbəti bölmələrdə grant növlərinin təfərrüatlarını nəzərdən keçirəcəyik, lakin gəlin onlardan nə vaxt istifadə etməli olduğumuza ümumi nəzər salaq.

![](../.gitbook/assets/OAuth\_common.png)

{% hint style="info" %}
Ən çox istifadə olunan OAuth Grant növləri göstərilmişdir.
{% endhint %}

### Client credentials grant type

> İlk olaraq **Client credentials grant** növünə baxaq.&#x20;
>
> Bu sistemlər arasında (system-to-sytem) əlaqə üçün nəzərdə tutulmuşdur.&#x20;
>
> Məsələn, biz [ticket.az](https://tickets.az/en) saytına daxil olub aviabilet axtaranda (aşağıdakı şəkil), sayt arxa fonda bir neçə aviabilet API-ya müraciət edib ən ucuz bileti tapmağa çalışır. Müraciət etdiyi platformalardan biri də [travelpayouts ](https://www.travelpayouts.com/)platformasıdır. Məhz ticket.az platformasının travelpayouts platformasında autentifikasiya olunması bu növə aiddir. Burada [travelpayouts ](https://www.travelpayouts.com/)API-larına [ticket.az](https://tickets.az/en) müraciət edir, yəni istifadəçi olaraq biz müraciət etmirik. Ona görə də, bizdən hansısa istifadəçi adı və parolu tələb olunmur.

{% hint style="info" %}
[travelpayouts](https://www.travelpayouts.com/)-dan məlumatları əldə etmək üçün orada qeydiyyatdan keçib [**API Key** ](../avtorizasiya-noevl-ri/api-key.md#travelpayouts-api-key)alınmalıdır.&#x20;
{% endhint %}

![Ticket.az](<../.gitbook/assets/Ticket (3).png>)

{% hint style="warning" %}
Bundan sonrakı grant növləri birbaşa istifadəçilər ilə əlaqəlidir.
{% endhint %}

### Password grant type

> İkinci, **Resource owner password grant** növü adlanır (adətən **password grant type** adlandırılır).&#x20;
>
> Bu növ yalnız tətbiq **trusted** olduqda istifadə edilə bilər. Bu grant növündə istifadəçi credential-ları tətbiq üzərindən avtorizasiya serverinə göndərilir. Tətbiqin istifadəçi məlumatlarına icazəsi olduğundan, bu grant növündən yalnız o halda istifadə **məntiqlidir ki,** tətbiq istifadəçi resursları saxlayan şirkət tərəfindən yaradılmış olsun.&#x20;
>
> Əks halda bu növdən istifadə **tövsiyyə edilmir.**

### **Authorization code grant type**

> Üçüncü, **Authorization code grant növüdür** (auth code grant növü də adlandırılır).&#x20;
>
> Bu grant növü tətbiq **untrusted** olduğu zaman istifadə edilir.&#x20;
>
> Növbəti bölmələrdə baxacağıq ki, **auth grant** növü hansı formada istifadəçilərə icazə verir ki, öz məxfi məlumatlarını (credentials) tətbiqə bildirmədən avtorizasiya serverinə ötürsün.
>
> Nümunə kimi əvvəlki bölmələrdə göstərdiyimiz **Rapid API** misalını göstərə bilərik. Burada **Auth grant** avtorizasiya növündən istifadə edilmişdir.

![Rapıd API](../.gitbook/assets/vk\_swiftshader\_icd.json.png)

