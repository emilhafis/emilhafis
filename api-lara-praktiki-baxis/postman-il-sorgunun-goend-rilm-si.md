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

>
>
> In this exercise, you’ll use Postman to make a request using OpenWeatherMap’s [current weather data API endpoint](https://openweathermap.org/current). To make the request:
>
> 1. If you haven’t already done so, download and install the Postman app at [https://www.getpostman.com/downloads/](https://www.getpostman.com/downloads/). (Make sure you download the app and not the deprecated Chrome extension.)
> 2. Start the Postman app and sign in when prompted. Close any welcome screens so you can make a request.
> 3. Insert the following endpoint into the box next to **GET**: `https://api.openweathermap.org/data/2.5/weather`
> 4.  Click the **Params** tab (below the box where you inserted the endpoint) and then add the following three parameters in the **key** and **value** rows:
>
>     * key: `zip` / value: `95050`
>     * key: `units` / value: `imperial`
>     * key: `appid`/ value: \<insert your own API key>
>
>     For the value for `appid`, use your own API key. (If you didn’t [get an API key](https://idratherbewriting.com/learnapidoc/docapis\_get\_auth\_keys.html), use [one of the keys here](http://idratherbewriting.site/apikeys).) Your Postman UI should look like this:
