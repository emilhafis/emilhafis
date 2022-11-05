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
Replace `APIKEY` with your actual API key.
{% endhint %}

\


