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

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

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

![](<../.gitbook/assets/image (5) (2).png>)

> The HTTP protocol is extremely right weight and simple. Indeed that's one of the main reasons for its success. Initially, with HTTP/0.9 a client could only issue what are called GET requests so ask for a resource from the server and that's it. Here's what it might look like. GET and then from the root of the application welcome.html. This would cause the server to return the contents of the whatever the HTML was contained inside the file welcome dot HTML. With HTTP one point o, which was introduced a little bit later in 1996 this HTTP protocol was extended to include additional headers with additional requests methods as well.

![](<../.gitbook/assets/image (10) (1).png>)

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



![](<../.gitbook/assets/image (8) (2).png>)

>

![](<../.gitbook/assets/image (15).png>)

> On the client side, let's talk about now the header. Again, we talked about there's a request line, a header, and then a message body, so this is the second piece. The HTTP message header is the primary part of the request. Here's a typical syntax. There's a field\_name: and then the value for that field. Here's an example, you might see something the header that looks like Accept: text/plain. This is saying that the browser can accept just plain text

![](<../.gitbook/assets/image (13).png>)

> An HTTP message header must be separated from the message body by a blank line. So after the header, blank line, and then here comes the third part, the body. So the message body is optional. Doesn't have to appear in a request. It's typically included if there's user-entered data that needs to be uploaded to the server side. If an HTTP request includes a body, there are usually header fields that describe what is up in the body. So, for example, you might see something like Content-Type is text/html or the Content-Length is 3495 bytes. So these things are describing the body itself. So these are the three parts of the request, the request line, the header, and then the message body.



![](<../.gitbook/assets/image (14).png>)

> So the message body is optional. Doesn't have to appear in a request. It's typically included if there's user-entered data that needs to be uploaded to the server side. If an HTTP request includes a body, there are usually header fields that describe what is up in the body. So, for example, you might see something like Content-Type is text/html or the Content-Length is 3495 bytes. So these things are describing the body itself. So these are the three parts of the request, the request line, the header, and then the message body. To make this a little bit more concrete, let me pull up a website.



### [Travelpayouts example ](https://app.travelpayouts.com/dashboard)

![](<../.gitbook/assets/image (2).png>)

> Gəlin nümunə üzərindən baxaq ki, arxa fonda nələr baş verir. Travelpayouts saytın açaq. Sonra Chrome-da Settings > More tools > Developer Tools seçək. Bütün brauzerlərdə Developer tool vardır. Yerləri settingsdə fərqli ola bilər.&#x20;
>
> Sorğunu veririk və görürük ki,xeyli sayda məlumatlar gəldi. İndi Network seçib göndərilən sorğulara baxaq. Burada gördüyünüz kimi çox saylı sorğular göndərilir. Gördüynüz kimi burada GET requestdən istifadə olunub və 200 HTTP status code qayıdıb və əməliyyatımızın uğurlu olduğunu bildirir.&#x20;

![](<../.gitbook/assets/image (10).png>)



> Siz burada real request görürüsünüz. Gördüyümüz kimi bu GET requestdir. Və response tab-a keçəndə artıq bizə `content-type: text/html` HTML göndərildiyini görürük.

![](<../.gitbook/assets/image (20).png>)

<pre class="language-bash"><code class="lang-bash"><strong>General
</strong><strong>Request URL: https://app.travelpayouts.com/dashboard
</strong>Request Method: GET
Status Code: 200 
Remote Address: 172.255.224.36:443
Referrer Policy: strict-origin-when-cross-origin

Response header
content-encoding: br
content-type: text/html
date: Wed, 09 Nov 2022 08:15:55 GMT
last-modified: Wednesday, 09-Nov-2022 08:15:55 GMT
server: nginx
x-request-id: 4078a867c2b86503e021293c973f850e

Request header
:authority: app.travelpayouts.com
:method: GET
:path: /dashboard
:scheme: https
accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
accept-encoding: gzip, deflate, br
accept-language: en-US,en;q=0.9,az;q=0.8
cookie: locale=en; app_referer=https://www.google.com/; regpage=mainpage; _ym_uid=1666552879338889828; _ym_d=1666552879; uxs_uid=df550180-5307-11ed-9d36-e1ae213eb832; _fbp=fb.1.1666552880189.337540356; promotion_code=; _ga_XC952XPR7M=GS1.1.1666552879.1.1.1666552895.0.0.0; _iidt=F8Ho8Y9D/YMP0AukQxUhT6UTrr0uIjTS6NDxTWxqcCc0BSSjpLiN7ikz7hma4rlyBCvbT8sHRpl0amVcAMn3tAlYMw==; _vid_t=He520iosYNGaWnqKW9AfwbZe11qB9B7WprB8kzI9VfUnEaB+s7PdLopnXh2ssUZln1lQ+hk613Dil6/dL9FE0QlYuw==; refresh_token=EBe-7qFHG8VN-yMzbwjJPq-QxX0DM85aJdvKQuHuAbq15_HdlrACfA; marker=direct; _hjSessionUser_302269=eyJpZCI6ImI4YWNkNWI0LTM1NDEtNWZlYy04M2M1LTkxZmM5YzhmNmVhYiIsImNyZWF0ZWQiOjE2NjY1NTI4OTMyNzUsImV4aXN0aW5nIjp0cnVlfQ==; mindboxDeviceUUID=5550fda9-2619-4cf7-b6b5-dc20769bcf17; directCrm-session=%7B%22deviceGuid%22%3A%225550fda9-2619-4cf7-b6b5-dc20769bcf17%22%7D; partners_marker=368030; ad_source=support_en; ad_content=articles+203956163-Travel-insights-with-Aviasales-Data-API; tp_referrer=app.gitbook.com/s/n8Zzef3LcIaitPYhMJp0/~/changes/4rRSMEr0x2EzSXWvvEBD/api-dizayn/sorgu-nuemun-si; _hjSessionUser_302666=eyJpZCI6IjRlMGE4N2RhLTkyNjQtNTIzZS1iNGRkLTVjMDE1NmFmODlhZSIsImNyZWF0ZWQiOjE2NjY1NTI5NDM1NDcsImV4aXN0aW5nIjp0cnVlfQ==; _ga_1WLL0NEBEH=GS1.1.1667670655.6.0.1667670655.60.0.0; app_locale=en; _sp_ses.2042=*; _hjSession_302269=eyJpZCI6IjA4YTA5MDg3LTU0ZGQtNDY5Zi1hZGNkLTBkYTQ1YzI0M2M2MiIsImNyZWF0ZWQiOjE2Njc5ODA2OTQyOTUsImluU2FtcGxlIjp0cnVlfQ==; _hjAbsoluteSessionInProgress=0; access_token=eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6InI2Ukl1WEdiV1o0b2o5VmxMNWNEVDRhLW1TZyJ9.eyJhdWQiOiJiMGUwMmZjYy0wYWI0LTRiMmMtYTE2NC03NDI3NjI3ODNhNGUiLCJleHAiOjE2Njc5ODE1OTMsImlhdCI6MTY2Nzk4MDY5MywiaXNzIjoidHJhdmVscGF5b3V0cy5jb20iLCJzdWIiOiIzMzlkZGU1Zi01MTQ5LTRhOGItOGJmOS00YjFjMjI5MjZlNDAiLCJqdGkiOiJlMDZiZGViYi0zZjAyLTQwOWMtYjJlZC1lNjM3MjA3YjE3MTUiLCJhdXRoZW50aWNhdGlvblR5cGUiOiJSRUZSRVNIX1RPS0VOIiwiZW1haWwiOiJlLmguYWJiYXNvdkBnbWFpbC5jb20iLCJlbWFpbF92ZXJpZmllZCI6ZmFsc2UsInByZWZlcnJlZF91c2VybmFtZSI6ImUuaC5hYmJhc292QGdtYWlsLmNvbSIsInJvbGVzIjpbIlBBUlRORVIiXSwiYXBwbGljYXRpb25JZCI6ImIwZTAyZmNjLTBhYjQtNGIyYy1hMTY0LTc0Mjc2Mjc4M2E0ZSJ9.TVigKvwenuFtCOr153IBns1Z9Vkbbtz74rBefYu93BCua92BqxyIMXzjd6k7q9EfuCrl4K1REIjCIWSuRkmSe0kUEZ3VTqjhUKEfASOdy9p0fNIEg82CczXzzljsz2I4iUZ5YQISZVetRR3kicu0W-1pN4GUojZlnssFqMRAcrpo2SAnP9ZHRiz3nhIqPYWWrSWhz5SPXSmAfSJ3Ir0r6RZ8B0ibO1LkqsZYa8RHnrBFaEOB7QA9eShfxXU6xO9SYLWMBTem_lLGUVfhptwdOLP3wIc-ibV7j-AuLVi6-56sxmWwUnZcJm0CSLKuOXj7jM9-OU0smGqduY54lWR2LA; daily_logged_in=true; tp_session=true; _ga=GA1.2.1625802743.1666552879; _gid=GA1.2.1920764687.1667980695; _ym_isad=2; _ym_visorc=w; _sp_id.2042=ac0fb207-849f-4ee3-93e1-1005540e2d3e.1666552879.5.1667980699.1667414002.41549885-1cc5-40f8-b290-c6db5fbfe192; _ga_Y3REWYRN9K=GS1.1.1667980695.4.1.1667981349.0.0.0
if-modified-since: Wednesday, 09-Nov-2022 07:58:11 GMT
sec-ch-ua: "Google Chrome";v="107", "Chromium";v="107", "Not=A?Brand";v="24"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "macOS"
sec-fetch-dest: document
sec-fetch-mode: navigate
sec-fetch-site: none
sec-fetch-user: ?1
upgrade-insecure-requests: 1
user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36ba</code></pre>

