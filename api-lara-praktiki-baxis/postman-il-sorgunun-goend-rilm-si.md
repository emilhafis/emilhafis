---
description: Postman ilə sorğunun göndərilməsi
---

# Postman

Hazırda bir neçə REST GUI klientləri (proqram təminatları) vardır ki, onlar ilə rahatlıqla endpoint-ləri (yəni API-ləri) və onların parametrlərin yoxlamaq olar. Siz həmçinin cURL (növbəti dərslərin mövzularından biri olacaqdır) istifadə edə bilərsiniz. Amma GUI klientləri ilə REST API testləşdirmələri daha sadədir.

{% hint style="info" %}
**GUI - G**raphical **U**ser **I**nterface. Qrafik istifadəçi interfeysi (məsələn [Postman](https://www.getpostman.com/), [Advanced REST Client](https://chrome.google.com/webstore/detail/advanced-rest-client/hgmloofddffdnphfgcellkdfbfbjeloo))
{% endhint %}

### Nə üçün GUI klient?

> Siz GUI REST klinet ilə:
>
> * Sorğularınızı saxlayıb daha sonra rahat formada istifadə edə bilərsiniz
> * Düzgün formatda məlumatları rahatlıqla daxil edə bilərsiniz
> * Qayıdan cavabları strukturlaşdırılmış JSON formatında görüb analiz edə bilərsiniz
> * Rahatlıqla parametləri əlavə edə bilərsiniz

### Məşhur GUI klientləri

> * [Postman](https://www.getpostman.com/)
> * [Insomnia](https://insomnia.rest/)
> * [Paw](https://luckymarmot.com/paw)
> * [Advanced REST Client](https://chrome.google.com/webstore/detail/advanced-rest-client/hgmloofddffdnphfgcellkdfbfbjeloo) (Chrome browser extension)
>
> bu proqram təminatlarının arasında Postman fikrimcə ən yaxşı seçimdir. Çünki o bizə sorğu göndərmək, cavabı almaq müxtəlif əməliyyatları pulsuz formada keçirməyə imkan verir. Həmçinin də müxtəlif əməliyyat sistemlərini (MAC,  Windows, Ubuntu) dəstəkləyir.

{% hint style="info" %}
Bizim örəndiyimiz ənənəvi metod ondan ibarətdir ki, biz ilk öncə öyrənəcəyimiz mövzunun və ya hansısa prosesi ilk öncə nəzərəiyyəsi ilə tanış olub sonradan onun təcrübə tərəfinə keçirik. Amma mən bu kursda bildirdiyim kimi təcrübədən nəzərəiyyəyə keçəcəm ki, həm başa düşmək rahat olsun, həm də çoxlu informasiya ilə sizi yükləməyim.

Məsələn burada istifadə etdiyimiz GET metodunu və ya endpoint nədir sualına cavab axtarmayacağıq, bunun üçün xüsusi mövzumuz olacaqdır - API endpoint-lərinin dokumentasiyası
{% endhint %}

### Activity. Postman ilə sorğunun göndərilməsi&#x20;

> Burada biz Postman-dən istifadə edərək verilmiş tarix və aeroportlar üzrə [travelpayouts aviabilet API](https://support.travelpayouts.com/hc/en-us/articles/203956163-Travel-insights-with-Aviasales-Data-API)-larını yoxlayayıb qiymətlərini öyrənəcəyik. Sorğu göndərmək üçün:
>
> 1. Əgər sizdə Postman yoxdursa o zaman onu yükləyib quraşdırmaq lazımdır ( [https://www.getpostman.com/downloads](https://www.getpostman.com/downloads/)). Əmin olun ki, Chrome extension yox, Postman applikasiyasın yükləmisiniz.
> 2. Postman app-ı start edib qeydiyyatdan keçin.&#x20;
> 3. Göstərilmiş endpoint-i **GET** sorğusunun yanındakı xanaya daxil edin: [`https://api.travelpayouts.com/aviasales/v3/prices_for_dates`](https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates)``
> 4.  Click the **Params** tab (below the box where you inserted the endpoint) and then add the following three parameters in the **key** and **value** rows:
>
>     * key: `zip` / value: `95050`
>     * key: `units` / value: `imperial`
>     * key: `appid`/ value: \<insert your own API key>
>
>     For the value for `appid`, use your own API key. (If you didn’t [get an API key](https://idratherbewriting.com/learnapidoc/docapis\_get\_auth\_keys.html), use [one of the keys here](http://idratherbewriting.site/apikeys).) Your Postman UI should look like this:
