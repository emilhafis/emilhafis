# API status and error codes

> Statis və error code response header-də olmaqla ümumilikdə cavabı klassifikasiya edir - məsələrən, cavab ya uğurlu olur ( bu halda 200 code-u alınır), server xətası ilə nəticələnir (500) avtorizasiya problemi olur (403) və d. Standart status kodlar üzrə documentasiyada əlavə nələrsə yazmağa ehtiyac yoxdur, çünki bu hamıya məlum olur artıq, amma API nıəz üçün spesifik kodlar işlədirsinizsə bunları göstərməlisiniz.&#x20;
>
> Error code-lar problemi trabulshoout etməyə çox kömək olur. Ona görədə API hazırlayarkən çalışın düzgün kodlar istifadə edin.

{% hint style="info" %}
Troubleshooting - bir problemin aşkarlanaraq aradan qaldırılması
{% endhint %}

### Sample status code in curl header

> Status codes don’t appear in the response body. They appear in the response header, which you might not see by default.
>
> Status code-lar response body-də əks olunmur, onlar response header-də əks olunur və by default siz onları görmürsünüz. Yəni arxa planda emal olunur.
>
> Curl  mövzunda görəcəksinizki, response header-i əldə etmək üçün siz `--include` or `-i` curl request ə əlavə etməlsiziniz.&#x20;

```
curl --include GET 'https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-26&unique=false&sorting=price&direct=false&currency=rub&limit=30&page=1&one_way=true&token=3c63416a24d3b969da6df9271faa9d6e' \
--header 'X-Access-Token: 3c63416a24d3b969da6df9271faa9d6e'
```

> Əgər siz ancaq response header-0in qayıtmasını istəyirsinizə (və başqa heç nə) o zaman `-I` hərfin böüyk göstərin.



```bash
curl -I -X GET 'https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-26&unique=false&sorting=price&direct=false&currency=rub&limit=30&page=1&one_way=true&token=3c63416a24d3b969da6df9271faa9d6e' \
--header 'X-Access-Token: 3c63416a24d3b969da6df9271faa9d6e'
```

{% hint style="info" %}
APIKey-ni öz valid keyniz ilə əvəz edərsiniz. Cavab bu formada olacaqdır:
{% endhint %}

```bash
HTTP/2 200 
server: nginx
date: Sat, 05 Nov 2022 05:58:44 GMT
content-type: application/json; charset=utf-8
content-length: 496
vary: Accept-Encoding
x-krakend: Version undefined
x-krakend-completed: false
x-request-id: 97a82753b4046361f8c3b115117a2f30
x-robots-tag: noindex
```

> İlk sətirdə olan `HTTP/1.1 200 OK` bizə sorğunun stausunun 200 olduğunu bildirir. Əksər REST API-lər response header-dəki standart protokollara əsaslanır. Məsələn 200 travelpayouts developerləri tərəfindən təyin edilən ixtiyari kod deyildir. 200 HTTP sorğuları üçün universal qəbul edilmiş koddur.&#x20;

> GET request edəndə sorğunun uğurlu və ya uğursuz olmasını təyin etmək çox asan olur. Çünki siz ccavabı aldıqda bilirsinizki bu uğurludur.. Amma təsəvvür edinki siz backenddə POST, PUThər hansı məlumatları dəyişirsiniz.  bu halda siz necə biləcəksinzi ki, sorğu uğurlu olmuşdur və lazımı dəyişiklikləri backenddə icra etmişdir? Bu halda HTTP response code sorğunun uğurlu və ya uöursuz olmasını göstərir.
>
> HTTP status code uzun xəta mesajlarınıa aid qısaldılmış kodlardır.

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

> Bəzən status kodların düzgün tətbiq etməyəndə, səhvin harda olduğunu anlamaq olmur. Buna görədə düzgün status kodlar təyin etməliyik ki, API-mız üzrə qayıdan xətalar dərhal aydın olsun.

> You can see a list of common [REST API status codes here](http://www.restapitutorial.com/httpstatuscodes.html) and a [general list of HTTP status codes here](https://en.wikipedia.org/wiki/List\_of\_HTTP\_status\_codes). Although it’s probably good to include a few standard status codes, comprehensively documenting _all standard_ status codes, especially if rarely triggered by your API, is unnecessary.
>
> [REST API status codes here](http://www.restapitutorial.com/httpstatuscodes.html) buradan REST API üzrə ümumi istifadə edilən kodları görə bilərsiniz. Həmçinin də ümumi list ilə buradan tanış ola bilərsiniz -  [general list of HTTP status codes here](https://en.wikipedia.org/wiki/List\_of\_HTTP\_status\_codes)
>
> Burdakı bütün kodları nəzərə almağınıza ehtiyac yoxdur. REST API üzrə ulduz qoyulan kodlar ən geniş istifadə olunanlardır. bunları istifadə etsəniz bəs edər.

### TOP 10 HTTP status code

<figure><img src="../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Where to list the HTTP response and error codes

> Most APIs should have a general page listing response and error codes across the entire API. A standalone page listing the status codes (rather than including these status codes with each endpoint) allows you to expand on each code with more detail without crowding the other documentation. It also reduces redundancy and the sense of information overload.
>
> On the other hand, if some endpoints are prone to triggering certain status and error codes more than others, it makes sense to highlight those status and error codes on same API reference pages. One strategy might be to call attention to any particularly relevant status or error codes for a specific endpoint, and then link to the centralized “Response and Status Codes” page for full information.

### Where to get status and error codes

> Status and error codes may not be readily apparent when you’re documenting your API. You’ll probably need to ask developers for a list of all the status and error codes that are unique to your API. Sometimes developers hard-code these status and error codes directly in the programming code and don’t have easy ways to hand you a comprehensive list (this makes localization problematic as well).
>
> As a result, you may need to experiment a bit to ferret out all the codes. Specifically, you might need to [try to break the API](https://idratherbewriting.com/learnapidoc/testingdocs\_test\_your\_instructions.html) to see all the potential error codes. For example, if you exceed the [rate limit](https://idratherbewriting.com/learnapidoc/docapis\_rate\_limiting\_and\_thresholds.html) for a specific call, the API might return a special error or status code. You would especially need to document this custom code. A troubleshooting section in your API might make special use of the error codes.

### How to list status codes

> You can list your status and error codes in a basic table or definition list, somewhat like this:
>
> Məsələn Bizim hazırladığımız sadə vord sənədində Error kodları bu formada qeyd olunub.



<figure><img src="../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

### Status/error codes can assist in troubleshooting 

> Status və error kodlar bildirdiyimiz kimi troubleshooting zamanı xeyli köməklik göstərir.&#x20;
>
> Bundan əlavə olaraq hər bir sənədləşmənin sonunda mümkün error kodlar və onların mənaları qeyd olunur.&#x20;
>
> Tək status kodla problemin əksər vaxtı nədə olduğunu bilmək olmur. Amma hansı istiqamətə getməli olduğumuza çox kömək edir.

> A section on troubleshooting could list error messages related to the following situations:
>
> * The wrong API keys are used
> * Invalid API keys are used
> * The parameters don’t fit the data types
> * The API throws an exception
> * There’s no data for the resource to return
> * The rate limits have been exceeded
> * The parameters are outside the max and min boundaries of what’s acceptable
> * A required parameter is absent from the endpoint
>
> Where possible, document the exact text of the error in the documentation so that it easily surfaces in searches.

OBİs və real digər servis nümunəsi

### Example of status and error codes

The following are some sample status and error code pages in API documentation.

<figure><img src="https://lh3.googleusercontent.com/38nR7s_ZRJTq7jec30k7vmHiyneQ1QbtlIb1YNQmKy2i09wVCgrKBK_yeod4ruTk0-dngsCO7_z2Hy3VhbeVMqQ-tuetyAzblWAg_TUC-JpHhuo6mjmS5yicDDoclIoH2Pyz7bkt8j6L-FP8tcqirqx4E4M7P-p8nx5hr9Pay5_805bdh4rFf0ciNITsAlefqKE" alt=""><figcaption></figcaption></figure>

> API dizayn edərkən yalnız HTTP error kodlar verməklə kifayətlənmək olmaz. Məsələn Mailchinp nümunəsində olduğu kimi bir çox yaxşı development olunmuş API-lar dəqiq göstərir ki problem haradadır.&#x20;
>
> ```
> HTTP/1.1 405 Method Not Allowed
> ```
>
> &#x20;Mailchimp bununla yanaşı geniş formada JSON response body-də bildiririki problem nədən ibaərtdir.
>
> ```json
> {
>     "type": "https://mailchimp.com/developer/marketing/docs/errors/",
>     "title": "Method Not Allowed",
>     "status": 405,
>     "detail": "The requested method and resource are not compatible. See the Allow header for this resource's available methods.",
>     "instance": "3b4dcb40-0b6b-4820-bfaa-41267b3826ea"
> }
> ```

{% hint style="warning" %}
Error kodların düzgün təqdim edilməsi çox vacibdir. Bu əlavə sualları azaldır və sizin API-zıa inteqraisyanı sürətləndirir.
{% endhint %}

> Most developers will probably be familiar with 200, 400, and 500 codes, so these codes don’t need a lot of explanatory detail. But if your API has unique codes, make sure to describe these adequately.

### [YouTube Error codes](https://developers.google.com/youtube/v3/docs/errors)  ![](<../.gitbook/assets/image (5) (1).png>)

> YouTube da görürük ki, Error code-lar üçün ayrıca səhifə verilib. Orada kod ilə yanaşı Error detail və descriptionda təsvir edilib.
>
> Gördüyünüz kimi böyük şirkətlər error handling məsələsinə çox ciddi yanaşırlar. Təsəvvür edin ki, onların yüz minlərlə istifadəçisi var və development zamanı çıxan problemlər onlara məlum olmasa nələ baş verər...
>
> Bu gün bizim ölkə də də bununla bağlı ciddi problemlər vardır. Əminəmki sizinlə bu məsələlər get gedə optimallaşacaq.

### Startups

#### Open Banking

Məsələn biz özümüz develop etdiyimiz APIyanaşmalarına baxaq.

1. AÖS də yaradılan Open Banking nümunəsi. Burada Hər metodun altında HTTP status kodlar göstərilir və əlavə olaraq, response body də error details aydın formada əks olunur.

<figure><img src="../.gitbook/assets/image (2) (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

### 2. QR Payment

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

Bu yanaşma çox yaxşıdır. Burda xəta ilə bərabər xətanın sırf nədən qaynaqlandığı deyilir.

Ümumiyyətlə error məsələsində developerlərin 2 yanaşması olur

* İlk xəta çıxan kimi prosesi dayandırmaq və geriyə xəta qaytarmaq.&#x20;
* Bütün sorğunu yoxlayıb bütün xətaları qaytarmaq. hazırda biz bu formatdan istifadə edirik və çox gözəl nəticələri olur.

