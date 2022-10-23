# Demo site



Nümunədə göstərdiyimiz HTML faylı hansı formada bizə məlumatları qaytarıb yekun olaraq ona baxaq.

```html
<!DOCTYPE html>
 <html>
   <head>
      <script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>
      <meta charset="utf-8">
      <link rel="stylesheet"  href='https://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap.min.css' rel='stylesheet' type='text/css'>
      <title>travelpayouts Integration</title>
      <style>
         #origin_airport, #destination_airport, #flight_number, #flight_price {color: red; font-weight: bold;};
         #origin_airport_desc, #destination_airport_desc, #price_ccy {color: darkblue;  font-weight: bold;}
         body {margin:20px;}
         .button {
                background-color: #4CAF50;
                border: none;
                color: white;
                padding: 15px 32px;
                text-align: center;
                text-decoration: none;
                display: inline-block;
                font-size: 16px;
                margin: 4px 2px;
                cursor: pointer;
                border-radius: 12px;
                width: 100%;
                }
      </style>
   </head>
   <body>
      <script>
         function checkFlight() {
          var settings = {
             "url": "https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-23&return_at=2023-03-26&currency=azn&limit=1&token=3c63416a24d3b969da6df9271faa9d6e",
             "method": "GET",
             "timeout": 0,
};
           $.ajax(settings)
           .done(function (response) {
             console.log(response);
         $("#origin_airport").append (response.data[0].origin_airport);
         $("#destination_airport").append (response.data[0].destination_airport);
         $("#flight_number").append (response.data[0].flight_number);
         $("#flight_price").append (response.data[0].price);
         $("#destination_airport_desc").append (" (Istanbul Airport)");
         $("#price_ccy").append (" (AZN)");
         $("#origin_airport_desc").append (" (Heydar Aliyev International Airport)");
         });
         }
      </script>
      <!-- <button type="button" onclick="checkWind()" class="btn btn-success weatherbutton">Axtar</button>  -->
      <input type="button" onclick="checkFlight()" class="button" value="Axtar">
      <h2>İstanbula ən ucuz bilet (İyul 11 2022 gediş - İyul 18 2022 dönüş)</h2>
      <span><b>Gediş aeroportu: </b></span><span id="origin_airport"></span><span id="origin_airport_desc"></span><br/>
      <span><b>Eniş aeroportu: </b></span><span id="destination_airport"></span> <span id="destination_airport_desc"></span><br/>
      <span><b>Qiymət: </b></span><span id="flight_price"></span><span id="price_ccy"></span><br/>
      <span><b>Uçuş nömrəsi: </b></span><span id="flight_number"></span>
   </body>
</html>
```

```html
```

>
