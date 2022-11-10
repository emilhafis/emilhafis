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
      flight_price: <span id="flight_Price"></span>
   </body>
</html>
```

> Burada gördüyümüz sadə HTML səhifəsidir. Bunu İnternetdə açsanız görünüş bu formada olacaqdır.

![](<../.gitbook/assets/image (6).png>)

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

4\. Kodu kopyalayıb `POSTMAN CODE GOES HERE` deyilən hissəyə əlavə edirik.

5\. `console.log(response);`altına bu sətri artırırıq

```
$("#flight_price").append (response.data[0].price);
```

> 6\. Nəticədə kodumuz bu formada görünəcəkdir

```html
<html>
   <meta charset="UTF-8">
   <head>
      <title>Sample page</title>
      <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
      <script>
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
           var content = response.data[0].price;
         $("#flight_price").append (response.data[0].price);
         });
      </script>
   </head>
   <body>
      <h1>Sample Page</h1>
      flight_price: <span id="flight_Price"></span>
   </body>
</html>
```

> (Kodda API-Keyni öz aktual API Key ilə əvəz edin)
>
> What is this code doing? In a nutshell, when `ajax` (a jQuery function) retrieves the response from the API, it assigns the response to `response`. A variable called `content` is created and set it equal to `response.wind.speed` ([dot notation](https://idratherbewriting.com/learnapidoc/docapis\_diving\_into\_dot\_notation.html) is used to access this value). jQuery’s `append` method inserts `content` after an element called `#windSpeed`on the page. (I realize this is an extremely abbreviated explanation, but explaining JavaScript is beyond the scope of this course. In general, you can learn more by reading about the [jQuery.ajax()](https://api.jquery.com/jquery.ajax/) function.)
>
> Bu kod nə iş görür bəs? Qısa olaraq desək, `ajax` (a jQuery function) API-dan response-u gətirir və onu console-a verir.&#x20;
>
> Query’s `append` methodu response data-dan price-yı əldə edib `#flight_price` adlandırır

> 7\. Chrome işə salıb JavaScript Console açaq
>
> To open the JavaScript Console, on Chrome on a Mac, go to **View > Developer > Javascript Console**; on Windows, click the **menu** button (vertical ellipses) and go to **More tools > Developer tools**. Then click the **Console** tab.
>
> \
> 8\. In Chrome, press **Cmd+O** (Mac) or **Ctrl + O** (Windows) and select your `flight_test.html` file.
>
> The weather response should be logged to the JavaScript Console (due to the `console.log(response)` code in the request). If you expand the object returned to the console, it will look as follows:\
>

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You can view the file here:
{% endhint %}

### The AJAX method from jQuery

\
In this section, I’ll explain a bit more about the `ajax` function you used earlier. This information probably isn’t essential for documenting REST APIs, but it’s good to understand. In the code, here’s the `ajax` script:

```
<script>
   var settings = {
     "async": true,
     "crossDomain": true,
     "url": "https://api.openweathermap.org/data/2.5/weather?zip=95050&appid=APIKEY&units=imperial",
     "method": "GET"
   }

   $.ajax(settings).done(function (response) {
     console.log(response);
   });
</script>
```

(In the above code, replace `APIKEY` with your actual API key.)

If you’re working with JavaScript and APIs, the [`ajax` method from jQuery](https://api.jquery.com/jquery.ajax) can be helpful with code samples. This `ajax` method takes one argument: `settings`.

```
$.ajax(settings)
```

The `settings` argument is an object that contains a variety of key-value pairs.

```
var settings = {

```

Each of the allowed key-value pairs is defined in [jQuery’s ajax documentation](https://api.jquery.com/jquery.ajax/#jQuery-ajax-settings).

Some important values are the `url`, which is the URI or endpoint you are submitting the request to. Another value is `headers`, which allows you to include custom headers in the request.

Look at the code sample you created. The `settings` variable is passed in as the argument to the `ajax` method. jQuery makes the request to the HTTP URL asynchronously, which means it won’t hang up your computer while you wait for the response. You can continue using your application while the request executes.

You get the response by calling the method `done`.

```
$.ajax(settings).done(function (response) {
})
```

In the earlier code sample, `done` contains an anonymous function (a function without a name) that executes when `done` is called. The response object from the `ajax` call is assigned to the `done` method’s argument, which in this case is `response`. (You can name the argument whatever you want.)

You can then access the values from the response object using object notation. In this example, the response is just logged to the console.

If you’re new to JavaScript, this is likely a bit fuzzy right now. If so, don’t worry — code becomes clearer the more you use it.

Notice how difficult it is to explain code? This is one of the challenges of developer documentation. Fortunately, you wouldn’t need to explain much from standard programming languages like JavaScript. But you might need to explain how to work with your API in different languages. I cover this topic in more depth in [Code samples and tutorials](https://idratherbewriting.com/learnapidoc/docapis\_codesamples\_bestpractices.html).

### Logging responses to the console

The line of code that logged the response to the console was simply this:

```
console.log(response);
```

Logging responses to the console can be a useful way to test whether an API response is working (it’s also helpful for debugging or troubleshooting your code). The console collapses each object inside an expandable section. You can inspect the payload in the console to see if contains the values you expect (without printing values to the page).

### &#x20;Inspect the payload

Inspect the payload by expanding each of the sections [returned in the JSON console object](https://idratherbewriting.com/learnapidoc/assets/files/weather-plain.html). Based on the information here, what’s the forecast for today?

I realize the page is blank and unexciting. In the next section, [Access and print a specific JSON value](https://idratherbewriting.com/learnapidoc/docapis\_access\_json\_values.html), we’ll pull out some values and print them to the page.\


\


\
