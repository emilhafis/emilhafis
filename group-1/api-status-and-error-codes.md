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

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

> Bəzən status kodların düzgün tətbiq etməyəndə, səhvin harda olduğunu anlamaq olmur. Buna görədə düzgün status kodlar təyin etməliyik ki, API-mız üzrə qayıdan xətalar dərhal aydın olsun.

> You can see a list of common [REST API status codes here](http://www.restapitutorial.com/httpstatuscodes.html) and a [general list of HTTP status codes here](https://en.wikipedia.org/wiki/List\_of\_HTTP\_status\_codes). Although it’s probably good to include a few standard status codes, comprehensively documenting _all standard_ status codes, especially if rarely triggered by your API, is unnecessary.
>
> [REST API status codes here](http://www.restapitutorial.com/httpstatuscodes.html) buradan REST API üzrə ümumi istifadə edilən kodları görə bilərsiniz. Həmçinin də ümumi list ilə buradan tanış ola bilərsiniz -  [general list of HTTP status codes here](https://en.wikipedia.org/wiki/List\_of\_HTTP\_status\_codes)
>
> Burdakı bütün kodları nəzərə almağınıza ehtiyac yoxdur. REST API üzrə ulduz qoyulan kodlar ən geniş istifadə olunanlardır. bunları istifadə etsəniz bəs edər.

### TOP 10 HTTP status code

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### Where to list the HTTP response and error codes

> Most APIs should have a general page listing response and error codes across the entire API. A standalone page listing the status codes (rather than including these status codes with each endpoint) allows you to expand on each code with more detail without crowding the other documentation. It also reduces redundancy and the sense of information overload.
>
> On the other hand, if some endpoints are prone to triggering certain status and error codes more than others, it makes sense to highlight those status and error codes on same API reference pages. One strategy might be to call attention to any particularly relevant status or error codes for a specific endpoint, and then link to the centralized “Response and Status Codes” page for full information.

\


