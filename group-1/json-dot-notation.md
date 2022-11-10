# JSON Dot notation

## Inspect the JSON from the response payload

> Xatırlayırsınızsa ilk dərsdə kiçik bir sayt düzəltmişdik və aviabilet üzrə nəticə tarixə görə syatda əks olunurdur. Əslində bu frontned developerlərin işidir. Beləki onlar backenddən aldıqları JSOn response un fieldlərin lazımı xanalarda çıxarmalıdırlar.
>
> Amma bizim məqsədimiz developer gözü ilə məsələlərə baxmaq və prosesləri başa düşməkdir. Ona görə ilk dərsdə göstərdiyimiz nümunənin necə ərsəyə gəlməsinə baxaq.

### &#x20;Activity: Make an API request on a web page

> Burada biz JavaScript dən istifadə edərək API response-dan qayıdan cavabları web page də göstərəcyik. Konkret olaraq seçdiyimiz tarix üzrə Bakı - İstanbul biletinin qiymətinə baxacağıq.&#x20;
>
> 1. Gəlin Text editorda yeni HTML faylımızı yaradaq və adını `flight_test.html` adlandıraq və içərisinə göstərdiyimiz kodu əlavə edək

{% hint style="warning" %}
Sizcə biz API request üçün JavaScript kodun hardan əldə edə bilərik? API Request JSON da bizə məlumdur
{% endhint %}



```html
<html>
   <meta charset="UTF-8">
   <head>
      <title>Sample page</title>
      <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
      <script>
      POSTMAN CODE GOES HERE
      </script>
   </head>
   <body>
      <h1>Sample Page</h1>
      flight_price: <span id="flightPrice"></span>
   </body>
</html>
```

> Burada gördüyümüz sadə HTML səhifəsidir. Bunu İnternetdə açsanız görünüş bu formada olacaqdır.

![](../.gitbook/assets/image.png)

> 2\. ABildirdiyimiz kimi postman bizə lazım olan kodu götürürük (Java Script)
>
> 3\. Bunun üçün Postmanda Code blokun açıb **JavaScript - jQuery seçirik**:

<figure><img src="https://lh4.googleusercontent.com/UH8Yy4R6DdJOAMyz3Ko16JRMLUxJB_6gLEec9mhDOJ3J7cF_24wjD_Lxru_SabKT7ofYVbmsMyg9g0cxlBeSYZHnR9BJj9NrTxM5k6frB828XT5QGmuueiURqYKFuc9O-vzlqilH3r1XrZZ-Ta350X4EE80jPS6CVdCm1UqeR3-mTDzBuQpjn3OuEzV1McB95OM" alt=""><figcaption></figcaption></figure>

```javascript
var settings = {
  "url": "https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-26&unique=false&sorting=price&direct=false&currency=rub&limit=30&page=1&one_way=true&token=3c63416a24d3b969da6df9271faa9d6e",
  "method": "GET",
  "timeout": 0,
  "headers": {
    "X-Access-Token": "3c63416a24d3b969da6df9271faa9d6e"
  },
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

1. Kodu kopyalayıb `POSTMAN CODE GOES HERE` deyilən hissəyə əlavə edirik.
2.  `console.log(response);`altına bu sətri artırırıq

    ```
    var content = response.wind.speed;
    $("#windSpeed").append(content);
    ```

\


\
