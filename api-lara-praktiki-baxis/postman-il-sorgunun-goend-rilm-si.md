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

### Activity 1. İlkin sorğunun göndərilməsi&#x20;

> Burada biz Postman-dən istifadə edərək Bakıdan (Heydər Əliyev aerorportundan) olan üçuşlarını [travelpayouts aviabilet API](https://support.travelpayouts.com/hc/en-us/articles/203956163-Travel-insights-with-Aviasales-Data-API)-ları vasitəsilə yoxlayıb qiymətlərini öyrənəcəyik. Sorğu göndərmək üçün:
>
> 1. Əgər sizdə Postman yoxdursa o zaman onu yükləyib quraşdırmaq lazımdır ( [https://www.getpostman.com/downloads](https://www.getpostman.com/downloads/)). Əmin olun ki, Chrome extension yox, Postman applikasiyasın yükləmisiniz.
> 2. Postman app-ı start edib qeydiyyatdan keçin.&#x20;
> 3. Göstərilmiş endpoint-i **GET** sorğusunun yanındakı xanaya daxil edin: [`https://api.travelpayouts.com/aviasales/v3/prices_for_dates`](https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates)``
> 4. Params tab-na (endpoint-i daxil etdiyiniz yerin aşağısında) aşağıdakı dəyərləri daxil edin:
>
> &#x20;     **key**: `origin` / **value**: `GYD`
>
> &#x20;     **key**: `token`/ **value**: \<API key - nizi daxil edin>
>
> `token` üçün [əldə etdiyiniz API key-dən](nuemun-nin-yoxlanilmasi.md#activity.-travelpayouts-api-key-ld-olunmasi) istifadə edin. Əgər API key almamısınızsa və ya hər hansı problem varsa [bunlardan birin](nuemun-nin-yoxlanilmasi.md#activity.-travelpayouts-api-key-ld-olunmasi) istifadə edə bilərsiniz.
>
> Yekunda sizin Postman interfeysiniz bu formada görünəcəkdir.&#x20;

![Postman endpoints & params](../.gitbook/assets/Postman\_request.png)

> Siz bu parametrləri əlavə edəndə onlar GET box-da göstərilən endpoint URL-də "query string" kimi əlavə edilir. Məsələn, sizin endpointiniz bu formada görünməlidir:
>
> ``[`https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&token=3c63416a24d3b969da6df9271faa9d6e`](https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates?origin=GYD\&token=3c63416a24d3b969da6df9271faa9d6e) `` (sizin API Key `token` value-dakından fərqli olacaqdır). Query string parametrləri endpoint-də sual  `?` işarəsindən sonra əlavə edilir və bir birindən ampersand `&` işarəsi ilə ayrılır. Query string parametrlərinin sıralamadakı yerlərinin önəmi olmur.&#x20;
>
> Qeyd etmək lazımdır ki, bir çox API sorğularında API key **URL-də** `query string parametri` əvəzinə **`Header`-**də ötürülür. Əgər belə hal olarsa siz **Headers** tab-na klik edib tələb olunan `key-value` məlumatın oraya əlavə etməlisiniz. Bizim keysimizdə travelpayouts API key məlumatını `query string parametr` kimi **URL**-də göndərir.

> 5\. **Send** düyməsinə klik edin.
>
> Cavab Postman-ın aşağı pəncərəsində görünməlidir. Bu formada:

![Postman response](../.gitbook/assets/Postman\_response.png)

> **6. Sorğunun saxlanılması**
>
> 1. Postman-da **Send** düyməsinin üzərində **Save** düyməsinə klik edin. Klik etdikdən sonra dialog box açılacaqdır.
> 2. **Request name** xanasında sorğu üçün özünüzə rahat olan adı daxil edin, məsələn "Travelpayouts Flight check"
> 3. **Request description (Optional)** xanasında sorğuya aid ümumi təsviri qeyd edin, məsələn "Ticket from Baku to Istanbul"
> 4. Aşağıdakı bölmədə **New Collection** klik edib sorğunuzu saxlamaq üçün yeni qovluq yaradın. Qovluğun adını verin, məsələn "Travelpayouts" və **Create** düyməsinə klik edin. Yekunda yaratdığınız qovluğa daxil olun.&#x20;
>
> &#x20; **Collection** yaratdıqdan sonra sorğununun saxlanılması üçün **Save** düyməsi aktivləşəcəkdir.&#x20;
>
> &#x20; Görünüş bu formada olacaqdır.     &#x20;

![Postman save request](../.gitbook/assets/Postman\_collection.png)

> 7\. **Save** düyməsinə klik edin.
>
> Saxlanılmış sorğular Postman interfeysinin sol küncündə görünəcəkdir. Əgər Collection sütunun görmürsünüzsə sol tərəfdə 1-ci sırada duran Collection düməsinə klik edin.&#x20;

![Postman saved request](<../.gitbook/assets/Postman\_save (2).png>)

#### Activity 2. Əlavə parametrlər ilə sorğunun göndərilməsi

Burada daha detallı olaraq Bakıdan (Heydər Əliyev aeroportu) İstanbula (Atatürk aeroportu) seçdiyimiz tarixlər üzrə (məsələn 11.07.2022-18.07.2022) mövcud olan gediş və qayıdış biletləri ilə tanış olacağıq.

> Now instead of getting the current weather, let’s use another OpenWeatherMap endpoint to get the forecast. Enter details into Postman for the [5 day forecast request](https://openweathermap.org/forecast5). In Postman, you can click a new tab, or click the arrow next to Save and choose **Save As**. Then choose your collection and request name.
>
> A sample endpoint for the 5 day forecast, which specifies location by zip code, looks like this:
>
> Qeyd etdiyimiz şərtlərə uyğun [parametrləri](https://support.travelpayouts.com/hc/en-us/articles/203956163-Travel-insights-with-Aviasales-Data-API) Postman-a daxil edin. Postman-da new tab klik edib yeni sorğu yarada bilərsiniz və ya saxladığınız sorğuya [API parametrlərini](https://support.travelpayouts.com/hc/en-us/articles/203956163-Travel-insights-with-Aviasales-Data-API) əlavə edib sorğunu yoxlaya bilərsiniz.&#x20;
>
> Endpointiniz bu formada görünməlidir:
