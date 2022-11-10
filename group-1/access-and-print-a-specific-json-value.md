# Access and print a specific JSON value

>
>
> Burada mövzumuzun davamı olaraq, response payload-dan yəni qayıdan cavabdan dəyərlərin necə əgötürələrək ekrana verilməsini göstərir. Flight sample page-də gördük ki, cavablar developer console-a gəlir amma ekranda görünmür. Ekranda görünməsi üçün dot notation və javaScript dən istifadə edib JSON dəyərlərini əldə etməliyik və əldə etidyimizi ekranda çap etməli yəni nümayiş etdirməliyik.&#x20;
>
> Nəzərə alın ki, bu bölmədə bir az JavaScriptdən istifadə edəcəyik. Sizin təşkilatdakı rolunuzdan asılı olaraq, bu tipli kodları ola bilsin sənədləşmədə istifadə etmədiniz amma bunları bilmək lazımdır, ki prosesi tm təsəvvür edək.

### Getting a specific property from a JSON response object

> JSON wouldn’t be very useful if you always had to print out the entire response. Instead, you select the exact property you want and pull that out through dot notation. The dot (`.`) after `response` (the name of the JSON payload, as defined arbitrarily in the jQuery AJAX function) is how you access the values you want from the JSON object.
>
> As an example, this is the full response from the [request made previously](https://idratherbewriting.com/learnapidoc/docapis\_analyze\_json.html):
>
> Əgər siz qayıdan bütün cavabı print etmək istəsəniz burada JSOn sizin üçün yararlı olmayacaqdı. əgər siz konkret bir dəyəri götürmək istəyirsinizsə onda siz dot notationdan istifadə edib həmin ddəyərə gedib çıxmalısınız. The dot (`.`) after `response` (the name of the JSON payload, as defined arbitrarily in the jQuery AJAX function) is how you access the values you want from the JSON object.
>
> Numunədə qayıdan tam cavabı göstərirəm.

```json
{
    "success": true,
    "data": [
        {
            "origin": "BAK",
            "destination": "IST",
            "origin_airport": "GYD",
            "destination_airport": "SAW",
            "price": 8967,
            "airline": "TK",
            "flight_number": "7703",
            "departure_at": "2023-03-26T05:15:00+04:00",
            "transfers": 0,
            "return_transfers": 0,
            "duration": 185,
            "link": "/search/BAK2603IST2?t=TK16797933001679804400000185GYDSAW_d8b41db8fd891a5f27e406371756c862_17934&search_date=06112022&expected_price_uuid=3d5f4ee6-0303-4e73-9b58-44fc59546b99&expected_price_currency=rub"
        }
    ],
    "currency": "rub"
}
```

Bura da da console-a gələn cavabı görə bilərik

<figure><img src="https://lh4.googleusercontent.com/DY4opU8Sp9-t6PNQWiaqvmlsZiVv46a4Wm7oQj9KKBoUjwpVMIADiRZNaI4xE9QDX6w7UYgEi3V-sw5_8U82raQ7EbF43Rplz078ehaXktsYWs9KBoPS0f8Keh_ugGv5ORQTeUPHvRPedXV6jGTxo_DihxCD-euutFZP8cA7PMX-lSi8fbBQ_J9M6LgUQaWgSdo" alt=""><figcaption></figcaption></figure>

> Bizim senarimizdə biz ucuz bilet qiyməti ilə maraqlnırdırdıq, yəni bizə lazım olan `price` dəyəridir.
>
> bu dəyərə gedib çıxamaq üçün isə bu formada dot notation istifadə etməliyik

```
response.currency
```

> JSOn response-dan `currency` əldə etmək və onu JavaScript Console da print etmək üçün, aşağıda göstəriləni  `console.log(response)`  altına əlavə edək.

```
console.log("flight-price: " + response.currency);
```

```html
<!DOCTYPE html>
 <html>
   <head>
      <script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>
      <meta charset="utf-8">
      <link rel="stylesheet"  href='https://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap.min.css' rel='stylesheet' type='text/css'>
      <title>travelpayouts Integration</title>
   </head>
   <body>
      <script>
        {
          var settings = {
             "url": "https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-26&unique=false&sorting=price&direct=false&currency=azn&limit=30&page=1&one_way=true&token=3c63416a24d3b969da6df9271faa9d6e",
             "method": "GET",
             "timeout": 0,
};
           $.ajax(settings)
           .done(function (response) {
             console.log(response);
             console.log("currency: " + response.currency)
         });
         }
      </script>
      
   </body>
</html>
```

> Refresh your Chrome browser and see the information that appears in the console:

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
CORS söndürməyi unutmayın
{% endhint %}

### Printing a JSON value to the page

> Let’s say you wanted to print part of the JSON (the wind speed data) to the page, not just the console. (By “print,” I mean make the value appear on the page, not send it to a printer.) Printing the value involves a little bit of JavaScript (or jQuery to make it easier).
>
> I’m assuming you’re starting with the [same code](https://idratherbewriting.com/learnapidoc/assets/files/weather-plain.html) from the [previous tutorial](https://idratherbewriting.com/learnapidoc/docapis\_json\_console.html). That code looks like this:
>
> İndi isə baxaq ki, JSOn value-nu (flight-price) səhifədə necə print edirik (print dedikdə printer nəzərdə tutumuruq, ekranda göstərməyi deyirəm).&#x20;
>
> Deməli bizim kodumuz hazırda bu formadadır.\
>

```html
<!DOCTYPE html>
 <html>
   <head>
      <script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>
      <meta charset="utf-8">
      <link rel="stylesheet"  href='https://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap.min.css' rel='stylesheet' type='text/css'>
      <title>travelpayouts Integration</title>
  
      <script>
        {
          var settings = {
             "url": "https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-26&unique=false&sorting=price&direct=false&currency=azn&limit=30&page=1&one_way=true&token=3c63416a24d3b969da6df9271faa9d6e",
             "method": "GET",
             "timeout": 0,
};
           $.ajax(settings)
           .done(function (response) {
             console.log(response);
             console.log("flight-price: " + response.currency)
         });
         }
      </script>
   </head>
     <body>
     </body>
</html>
```

{% hint style="info" %}
(In the above code, replace `APIKEY` with your actual API key.)
{% endhint %}

### İstənilən dəyərin print edilməsi üçün

> 1. Add the following inside the `ajax` function:

```javascript
$.ajax(settings).done(function (response) {
console.log(response);

var content = response.currency;
$("#currency").append(content);

});
```

```
      <h1>Sample Page</h1>
      <div id="currency">Price: </div>
```



> Kodumuz bu formadda görünəcəkdir

```html
<!DOCTYPE html>
 <html>
   <head>
      <script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>
      <meta charset="utf-8">
      <link rel="stylesheet"  href='https://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap.min.css' rel='stylesheet' type='text/css'>
      <title>travelpayouts Integration</title>
  
      <script>
           {
             var settings = {
                "url": "https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-26&unique=false&sorting=price&direct=false&currency=azn&limit=30&page=1&one_way=true&token=3c63416a24d3b969da6df9271faa9d6e",
                "method": "GET",
                "timeout": 0,
            };
              $.ajax(settings)
              .done(function (response) {
                console.log(response);
               
            var content = response.currency;
            $("#currency").append(content);

            });
            }
      </script>
   </head>
     <body>

       <h1>Sample Page</h1>
      <div id="currency">Məzənnə: </div>
      
     </body>
</html>
```

>

> 2\. Səhifəni yeniləyək və görəcəyik ki, qiymət ekranda çap edildi.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

### Biz burada nə etdik?

\
Gəlin baxaq.

Inside the tags of the AJAX `done` method, we pulled out the value we wanted into a variable, like this:

```
var settings = {
                "url": "https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-26&unique=false&sorting=price&direct=false&currency=azn&limit=30&page=1&one_way=true&token=3c63416a24d3b969da6df9271faa9d6e",
                "method": "GET",
                "timeout": 0,
```

Burada biz API-ya müraciət etdik.

```
  $.ajax(settings)
              .done(function (response)
```

AJAX daxilindəki `done` metodu ilə biz istədiyimiz `currency` dəyəri götürdük

```
var content = response.currency;
```

Sonra biz ekranda görünməsi üçün element əlavə etdik və `Məzənnə` olaraq adlandırdıq.

```
  <div id="currency">Məzənnə: </div>
```

&#x20;Sonra biz JQuery append metodundan istifadə edib `content` dəyərində  götürdüyümüz `currency` dəyərini ekrandakı `currency` dəyərinə mənimsədirik.

```
$("#currency").append(content);
```

### Get the value from an array

In the previous section, you retrieved a value from a JSON object. Now let’s get a value from an array. Let’s get the `main` property from the `weather` array in the response. Here’s what the JSON array looks like:

Biz bundan öncə JSON obyektindəki dəyəri götürüb print etdik. İndi isə bir qədər işimizi qəlizləşdirib array dən dəyərləri götürməyə çalışacaq. Çünki bizə lazım olan digər məlumat data array daxilindədəir. Gəlin qiyməti çıxaraq. Qiymətimiz price adı altındadır. Bir daha nəzərə salaq JSOn muza

```
{
    "success": true,
    "data": [
        {
            "origin": "BAK",
            "destination": "IST",
            "origin_airport": "GYD",
            "destination_airport": "SAW",
            "price": 8967,
            "airline": "TK",
            "flight_number": "7703",
            "departure_at": "2023-03-26T05:15:00+04:00",
            "transfers": 0,
            "return_transfers": 0,
            "duration": 185,
            "link": "/search/BAK2603IST2?t=TK16797933001679804400000185GYDSAW_d8b41db8fd891a5f27e406371756c862_17934&search_date=06112022&expected_price_uuid=3d5f4ee6-0303-4e73-9b58-44fc59546b99&expected_price_currency=rub"
        }
    ],
    "currency": "rub"
}
```

{% hint style="warning" %}
data - nın array olduğun haradan bilirik?

* Mötərizədən
{% endhint %}

data array-dən price dəyərini götürmək üçün bu formada dot notation istifadə etməliyik.

```
response.data[0].price
```



Sonra onu səhifədə çap etmək üçün qeyd etdiyimiz nümunələrə əməl etməliyik.

Obyektlər sizə istədiyiniz dəyərləri götürməyə icazə verirsə də, array tələb edirki siyahı üzrə dəyərin yerləşdiyi siyahını seçməyi tələb edir.

Düzəltdiyimiz nümunə üzrə sample kodumuz

```
<!DOCTYPE html>
 <html>
   <head>
      <script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>
      <meta charset="utf-8">
      <link rel="stylesheet"  href='https://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap.min.css' rel='stylesheet' type='text/css'>
      <title>travelpayouts Integration</title>
  
      <script>
           {
             var settings = {
                "url": "https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-26&unique=false&sorting=price&direct=false&currency=azn&limit=30&page=1&one_way=true&token=3c63416a24d3b969da6df9271faa9d6e",
                "method": "GET",
                "timeout": 0,
            };
              $.ajax(settings)
              .done(function (response) {
                console.log(response);
               
            var content = response.currency;
            $("#currency").append(content);

            var content = response.data[0].price;
            $("#price").append(content);
            });
            }
      </script>
   </head>
     <body>

       <h1>Sample Page</h1>
      <div id="currency">Məzənnə: </div>
      <div id="price">Qiymət: </div>
     </body>
</html>
```

(In the above code, replace `APIKEY` with your actual API key.)
