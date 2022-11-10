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

