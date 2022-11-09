# HTTP

> Bir çox mövuzlarda HTTP işlətmişik. REST API HTTP protokolu üzərindən məlumat mübadiləsi aparır, HTTP erro, status code, HTTP metodlar.
>
> Bəs bu HTTP protokolu nədir?

### What is HTTP protocol?

> Məqsədimiz məlumat mübadiləsini başa düşməkdir. Ona görə də HTTP protokolunun dərinliyinə girməyəcəyik.

> **HTTP** açılışı **Hyper Text Transfer Protocol-dur.**&#x20;
>
> Hazırda bizim istifadə etdiyimiz veb brauzerlər bu protokoldan (www) istifadə edir.
>
> Bizim komputerimiz ilə veb server arasındakı əlaqə HTTP Request və Response əsasında həyata keçir.

### World Wide Web Communication

> WWW dediyimiz World Wide Web  web client (məsələn bizim brauzer) və web serverlər (məsələn bizim açdığımız travelpayouts serveri) arasındakı əlaqəni HTTP protokolu üzərindən təmin edir.
>
> **Client** dediyimiz **** adətən **** bizim brauzerlər (Chrome, Mozilla və s) nəzərdə tutulur amma bu istənilən proqram təminatı və ya qurğusu ola bilər. Məsələn biz cUrl-dən və ya Postmandan sorğu ediriksə biz burada clientik.
>
> Server isə məlumatları emal edib onlara cavabı qaytarandır, \
>

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### HTTP Request / Response

> Client və server arasındakı məlumat mübadiləsi bildiyimiz kimi reqeust və response-a əsaslanaır. Məsələn,
>
> 1. Client (brauzer) serverə (saytın yerləşdiyi server, cloud və s.) **HTTP request** göndərir
> 2. Server sorğunu qəbul edir
> 3. Server sorğunu emal edir
> 4. Serer brazuerə **HTTP response** (output) qaytarır
> 5. Client (brazuer) sorğunu qəbul edir

### The HTTP Request Circle

> A typical HTTP request / response circle:
>
> 1. The browser requests an HTML page. The server returns an HTML file.
> 2. The browser requests a style sheet. The server returns a CSS file.
> 3. The browser requests an JPG image. The server returns a JPG file.
> 4. The browser requests JavaScript code. The server returns a JS file
> 5. The browser requests data. The server returns data (in XML or JSON).\
>

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

> HTTP HTML documentləri kimi resursların alınması üçün protokoldur. O, İnternetdə hər hansı məlumat mübadiləsinin əsasını təşkil edir və client -server protokoludur, yəni sorğular client, çox vaxt Veb brauzer tərəfindən başlanır. Tam sənəd əldə edilən müxtəlif sub-sənədlərdən, məsələn, mətn,şəkillər, videolar, skriptlər və sairdən əsasında qurulur. Yəni biz bir veb sayta girəndə arxada müxtəlif sorğular gedərək alınan nəticələr birləşdirili və bizə göstərilir.



{% hint style="info" %}
## Protocol

A **protocol** is a system of rules that define how data is exchanged within or between computers. Communications between devices require that the devices agree on the format of the data that is being exchanged. The set of rules that defines a format is called a protocol.
{% endhint %}



![](<../.gitbook/assets/image (9).png>)

> Once again here's the client server interaction associated with HTTP consisting of a request followed by a response. So, what is the request all about? Well, the client is requesting some resource from the server. Once the server receives the request it may be able to provide this resource directly. It may need to create it. It may need to retrieve it from some other server. Or it may not be able to satisfy the request at all. Whatever might be the case, the server's job is to respond accordingly. So let's take a closer look at this.

> The resources delivered as a part of this protocol typically include Hypertext, Cascading Style Sheets, Hypermedia, and Scripts. So Hypertexts, these are just texts that's marked-up using HTML, or HyperText Mark-up Language and it could be styled with CSS and it may contain references. In other words, hyperlinks to other resources. These hyperlinks are to other resources that the reader's able to immediately access via a mouse click.

> Hypermedia, this is just Just a logic extension of hypertext to graphics, audio, and visual. Hyperlinks, these are references to other hyper media and if you think about it they actually define the structure of the world wide web. Indeed, this is the structure that Google uses to determine the relevance of the hyperlinks that are returned to you when you do a search. And lastly, you could have scripts as an HTTP resource. Nowadays this is typically JavaScript so this is code that's returned to your browser and then executed in your browser.

![](<../.gitbook/assets/image (5).png>)

> The HTTP protocol is extremely right weight and simple. Indeed that's one of the main reasons for its success. Initially, with HTTP/0.9 a client could only issue what are called GET requests so ask for a resource from the server and that's it. Here's what it might look like. GET and then from the root of the application welcome.html. This would cause the server to return the contents of the whatever the HTML was contained inside the file welcome dot HTML. With HTTP one point o, which was introduced a little bit later in 1996 this HTTP protocol was extended to include additional headers with additional requests methods as well.

![](<../.gitbook/assets/image (10).png>)

### HTTP Request

> Here are the specific pieces of an HTTP request. It consists of three parts. There's a Request line, a Header, and then a Message body. We'll now consider each of these parts in turn



![](<../.gitbook/assets/image (19).png>)

> Let's look at the Request Line. It identifies the resource that's being requested and the desired action, sometimes this is called request, verb or method instead of action, that you'd like to apply to that resource. The resource is identified by a Universal Resource Identifier, more specifically, a Uniform Resource Locator, sometimes you'll hear this referred to as URL, very common, is a specific type of a URI. Now there are nine request types that can be specified and I'm going to list each of them.

```bash
curl --include GET 'https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-26&unique=false&sorting=price&direct=false&currency=rub&limit=30&page=1&one_way=true&token=3c63416a24d3b969da6df9271faa9d6e' \
--header 'X-Access-Token: 3c63416a24d3b969da6df9271faa9d6e'
```

```bash
curl --include GET 'https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-26&unique=false&sorting=price&direct=false&currency=rub&limit=30&page=1&one_way=true&token=3c63416a24d3b969da6df9271faa9d6e' \
--header 'X-Access-Token: 3c63416a24d3b969da6df9271faa9d6e'
curl: (6) Could not resolve host: GET
HTTP/2 200 
server: nginx
date: Wed, 09 Nov 2022 06:55:57 GMT
content-type: application/json; charset=utf-8
content-length: 500
vary: Accept-Encoding
x-krakend: Version undefined
x-krakend-completed: false
x-request-id: 99a5d8a0af5e046bcec232828a295f29
x-robots-tag: noindex

{"success":true,"data":[{"origin":"BAK","destination":"IST","origin_airport":"GYD","destination_airport":"SAW","price":8967,"airline":"TK","flight_number":"7703","departure_at":"2023-03-26T05:15:00+04:00","transfers":0,"return_transfers":0,"duration":185,"link":"/search/BAK2603IST2?t=TK16797933001679804400000185GYDSAW_d8b41db8fd891a5f27e406371756c862_17934\u0026search_date=06112022\u0026expected_price_uuid=3d5f4ee6-0303-4e73-9b58-44fc59546b99\u0026expected_price_currency=rub"}],"currency":"rub"}% 
```

![](<../.gitbook/assets/image (18).png>)

> Bunlardan birincisi **HEAD** requestdir. Normal sorğularda bildiyimiz kimi HEAD response-da görünmür. Amma onu bildirdiyimi zkimi sorğulasaq görünəcəkdir.
>
> Digəri isə ən geniş istifadə olunan **GET** metodudur.&#x20;

{% hint style="danger" %}
GET metodu nədir?

POST nədir?

PUT nədir?

DELETE nədir?

(The POST, PUT, and DELETE methods, they can cause side effects. They're changing the resource. So therefore they're not called safe methods. The PUT and DELETE methods, what you'd like is for them to be idempotent. What this means, if you do multiple identical requests, they should have the same effect as a single request. So if you put a resource multiple times, it should continue to override it. If you delete a resource multiple times, it should be deleted the first time. And after that it shouldn't change what's on the server side.  So the safe methods, if you think about, since they don't change the state of the server, are therefore by definition also idempotent.)

Idempotency nədir (So a couple of things about these types of requests. The HEAD, GET, OPTIONS and TRACE are referred to as safe methods. What this means is that they do not produce side effects on the server. So if you do a GET request, for example, it'll get the resource but it does not change it on the server side. So no side effects. If a GET method is implemented in a safe way, then think about this, a browser can make an arbitrary number of GET requests without modifying the state of a web application. )
{% endhint %}



![](<../.gitbook/assets/image (11).png>)

> DELETE is the next one, this allows you to delete a resource. TRACE echoes back a received response. OPTIONS returns the HTTP methods that the server supports for that specific resource. CONNECT converts the request connection to a TCP/IP tunnel. This is what's used to facilitate a TSL or SSL encrypted communication to HTTPS. And then finally PATCH allows you to apply a partial modification to a resource.

![](<../.gitbook/assets/image (17).png>)



![](<../.gitbook/assets/image (8).png>)

>

![](<../.gitbook/assets/image (15).png>)

> On the client side, let's talk about now the header. Again, we talked about there's a request line, a header, and then a message body, so this is the second piece. The HTTP message header is the primary part of the request. Here's a typical syntax. There's a field\_name: and then the value for that field. Here's an example, you might see something the header that looks like Accept: text/plain. This is saying that the browser can accept just plain text

![](<../.gitbook/assets/image (13).png>)

> An HTTP message header must be separated from the message body by a blank line. So after the header, blank line, and then here comes the third part, the body. So the message body is optional. Doesn't have to appear in a request. It's typically included if there's user-entered data that needs to be uploaded to the server side. If an HTTP request includes a body, there are usually header fields that describe what is up in the body. So, for example, you might see something like Content-Type is text/html or the Content-Length is 3495 bytes. So these things are describing the body itself. So these are the three parts of the request, the request line, the header, and then the message body.



![](<../.gitbook/assets/image (14).png>)

> So the message body is optional. Doesn't have to appear in a request. It's typically included if there's user-entered data that needs to be uploaded to the server side. If an HTTP request includes a body, there are usually header fields that describe what is up in the body. So, for example, you might see something like Content-Type is text/html or the Content-Length is 3495 bytes. So these things are describing the body itself. So these are the three parts of the request, the request line, the header, and then the message body. To make this a little bit more concrete, let me pull up a website.



So here's The New York Times, and I'm going to use Chrome in this case, and I'm going to select > View > Developer > Developer Tools. So, again, all of the browsers have these. So, here's the Developer Tools and I'm going to go ahead and hit reload, so you can see the request that is made here. And so here it is. Let's select Network and then I can look at the requests, and a lot of stuff happened here but the initial request was www.newyorktimes.com and you'll see that it was a get request, it returned status 200. We're going to talk about that in the next video, but let's take a look at this request itself. And I'm going to select the headers here. And I want to see the actual request since that's what we're talking about. I'm going to select View Source and if you look at this, you'll see that it was a GET request and it used HTTP/1.1. And here you see the headers. So there's host, so the field name, and then the value, Connection: keep-alive, Cache-Control, maximum age. Accept: text, so this is saying what the browser can accept, so on and so forth. So, everything here are headers. There's no body to this and at the very end, you'll see a big, massive cookie. So again, provide as a header. So the header field and then the actual value is specified here. So this is a GET request. Let's go to our blog application and let's enter a new post. And so I'm going to create a new post and again I'm going to turn on the Developer Tools, so that we can see what happens. And so we'll create a new post and let's just call it Test and Test. We're going to create that post and let me look here, and we'll see that this post is actually using the post method. Again we can take a look at this and we can see that the Request Header was of type POST and it used the route called POST. This is what was added to the end of the URL here, then it was using HTTP/1.1. You'll see in this case that the Header Field and down below there's actually a body associated with this as well and it's in this Form Data. So the form data contains the body.

### [Travelpayouts example ](https://app.travelpayouts.com/dashboard)

![](../.gitbook/assets/image.png)

