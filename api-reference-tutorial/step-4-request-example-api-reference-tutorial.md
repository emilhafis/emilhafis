# Step 4: Request example (API reference tutorial)

|   |   |   |
| - | - | - |
|   |   |   |
|   |   |   |
|   |   |   |

> Request nümunəsinə Endpoint-də daxil olmaqla istifadə edilmiş parametrlər konfiqurasiyanı göstərir. Sorğu nümunəsi adətən bütün mümkün parametr konfiqurasiyaların göstərmir amma mümkün qədər parametrləri göstərmək lazımdır.
>
> Sorğu nümunələrində çox vaxt müxtəlif dillərdə həmin hazırlanmış kod nümunələrini (code snipets) də göstərirlər. cURL kod nümunələri ilə birgə göstərilir və demək olarki bütün sorğu nümunələrində cURL dən istifadə olunur. Bu qeyd etdiklərimiz sorğu nümunəsində göstərmək vacib deyil amma olarsa çox yaxşı olar.

### Sorğu nümunələri

> Aşağıdakı nümunə [Stripe-ın göstərdiyi sorğu](https://stripe.com/docs/api/customer\_bank\_accounts/create) nümunəsidir.

![](../.gitbook/assets/Stripe\_request\_example.PNG)

> The design of this API doc site arranges the sample requests and responses in the right column of a three-column layout. The request is formatted in curl, which we explored earlier in [Make a curl call](https://idratherbewriting.com/learnapidoc/docapis\_make\_curl\_call.html).
>
> Gördüyünüz kimi burada API dizayn 3 hissəli təsvir edilmişdir. Sol tərəfdə Resurs və resurs üzrə əməliyyatlar, ortada Parametrlər, sağda isə request və response nümunəsi.&#x20;

{% hint style="info" %}
Bu formada dizaynı ilk dəfə Stripe gətirmişdir. Mənim bu dizayn çox xoşuma gəlir. API documenting üçün istifadə olunan ReDoc platformasının da dizaynı buna çox oxşardır.
{% endhint %}

> Sorğu nümunəsi cURL-də göstərilmişdir. cURL-i daha dərindən növbəti mövzularda müzakirə edəcəyik.
>
> İndi isə cURL nədir və nə üçün sorğuları cURL-də göstərirlər gəlin ümumi olaraq baxaq

### cURL qısa təsviri

> One of the advantages of REST APIs is that you can use almost any programming language to call the endpoint. The endpoint is simply a resource located on a web server at a specific path.
>
> Each programming language has a different way of making web calls. Rather than exhausting your energies trying to show how to make web calls in Java, Python, C++, JavaScript, Ruby, and so on, you can just show the call using curl
>
> curl provides a generic, language-agnostic way to demonstrate HTTP requests and responses. Users can see the format of the request, including any headers and other parameters. Your users can translate this into the specific format for the language they’re using.
>
> curl is a common format to show requests for several reasons:
>
> * curl is language agnostic, so it’s not specific to one particular programming language.
> * curl shows the header information required in the request.
> * curl shows the method used with the request.
>
> In general, use curl to show your sample request.&#x20;

### Multiple request examples <a href="#multiple-request-examples" id="multiple-request-examples"></a>

#### [Travelpayouts](https://support.travelpayouts.com/hc/en-us/articles/203956163-Travel-insights-with-Aviasales-Data-API)

> Other API doc sites might use the full resource URL, such as this plain example from Twitter:

{% hint style="info" %}
nədir travel
{% endhint %}

> If you have a lot of parameters, consider including several request examples. In the CityGrid Places API, the [`where` endpoint](http://docs.citygridmedia.com/display/citygridv2/Places+API#PlacesAPI-WhereSearchHTTPSEndpoint) is as follows:

![](../.gitbook/assets/travel-request\_example.PNG)

```javascript
https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&token=3c63416a24d3b969da6df9271faa9d6e
```

> However, there are [literally 17 possible query string parameters](http://docs.citygridmedia.com/display/citygridv2/Places+API#PlacesAPI-WhereSearchRequest) you can use with this endpoint. As a result, the documentation includes several sample requests that show various parameter combinations:

> The resource URL includes both the base path and the endpoint. One problem with showing the full resource URL is that it doesn’t indicate if any header information needs to be passed to authorize the request. (If your API consists of GET requests only and doesn’t require authorization, great, but few APIs are set up this way.) curl requests can easily show any header parameters.

> Adding multiple request examples makes sense when the parameters wouldn’t usually be used together. For example, there are few cases where you might actually include all 17 parameters in the same request, so any sample will be limited in what it can show.
>
> This example shows how to “Find hotels in Boston, viewing results 1-5 in alphabetical order”:
>
> ```
> https://api.citygridmedia.com/content/places/v2/search/where?what=hotels&where=boston,ma&page=1&rpp=5&sort=alpha&publisher=test&format=json
> ```
>
> If you [click the link](https://api.citygridmedia.com/content/places/v2/search/where?what=hotels\&where=boston,ma\&page=1\&rpp=5\&sort=alpha\&publisher=test\&format=json), you can see the response directly. In the [responses topic](https://idratherbewriting.com/learnapidoc/docapis\_doc\_sample\_responses\_and\_schema.html#dynamic\_responses), I get into more detail about dynamically showing the response when users click a request.
>
> How many different requests and responses should you show? There’s probably no easy answer, but probably no more than a few. You decide what makes sense for your API. Users will usually understand the pattern after a few examples.

### Requests in various languages <a href="#requests-in-various-languages" id="requests-in-various-languages"></a>

> Bildiyimiz kimi REST API "language agnostic"-dir, yəni proqramlaşdırma dili deyil, istifadə edilən protokoldur. Müxtəlif proqramlaşdırma dilləri üzrə istifadə olunan protokoldur. Proqramçılar öz tətbiqlərin istənilən dildə (Java, Ruby, Python və s) yaza bilərlər. Proqramçılar istifadə etdikləri proqramlaşdırma dili vasitəsilə API ları sorğulayıb onlar üzrə cavabları ala bilərlər. Cavablar JSON və ya XML formatında olur.&#x20;
>
> Yazdıqlarımızın məntiqi nəticəsi olaraq biz proqramçıların hansı dildən istifadə edəcəyini tam olaraq bilməyəcəyimiz üçün, proqramlaşdırma dillərində kod nümunələri təqdim etməyimiz bir növ nəticəsizdir. Bir çox API-larda sorğu və cavab nümunələri təqdim olunur və proqramçıların özləri bilir ki, yazdılqları dildə hansı formada HTTP requests göndərə bilərlar.
>
> Buna baxmayaraq əksər API-lar bir neçə fərqli proqramlaşdırma dillərində nümunələr təqdim edirlər:
>
> Məsələn aşağıda [Stripe üzrə](https://stripe.com/docs/api/customer\_bank\_accounts/object?lang=python) görə bilərsiniz ki, bir neçə seçim imkanı verilir.

![](../.gitbook/assets/stripe\_code\_snip.png)

> You can select which language you want for the sample request: C#, curl, Java, Node.js, PHP, Python, or Ruby.

> You can see the request in Shell (curl), Ruby, Node, or Python. Developers can easily copy the needed code into their applications, rather than figuring out how to translate the curl request into a particular programming language.
>
> However, don’t feel so intimidated by this smorgasbord of code samples. Some API doc tools (such as [Readme.com](https://readme.com/) or [SwaggerHub](https://idratherbewriting.com/learnapidoc/pubapis\_swaggerhub\_smartbear.html)) can automatically generate these code samples because the patterns for making REST requests in different programming languages follow a common template.

{% hint style="info" %}
Many times, product managers know which programming languages the target users develop applications with. If you know the target audience’s preferred programming language, you can focus your code samples on that language only.
{% endhint %}

### Auto-generating code samples

> If you’re not using an authoring tool that auto-generates code examples, and you want to provide these code snippets, you can auto-generate code samples from both Postman and Paw, if desired.
>
> Əgər siz API doc platformalarından istifadə etmirsinizsə və qeyd etdiyimiz kimi fərqli dillərdə kod nümunələri vermək istəyirsinizsə narahat olmayan bunun sadə yolu var. Belə ki, API testing üçün geniş istifadə olunan Postman-dan istifadə edərək cURL və müxtəlif proqramlaşdırma dilləri üzrə kod nümunələri generasiya edə bilərsiniz.



> Postman-da göndərəcyiniz sorğuları qeyd edirsiniz və şəkildə göstərilən bölməyə daxil olub isiyahını açırsınız.

![](<../.gitbook/assets/Screenshot from 2022-08-16 16-20-29 (1).png>)

> Siyahıdan Python seçilən zaman, bizə Pythona uyğun kod nümunəsi təqdim olunur.

![](<../.gitbook/assets/postman\_python (1).png>)

> Hazırda bizə sənədləşmədə göstərmək üçün cURl lazımdır, ona görə də cURL üzrə nümunəni də götürək.

![](<../.gitbook/assets/postman\_cUrl (1).png>)

test

```javascript
curl --location --request GET 'http://obank-test.example.az:50000/api/obis/v1.0/accounts/AZ83MOSZ00000000000019988155/balances' \
--header 'Sender-Participant-Code: AZERAZ20' \
--header 'Receiver-Participant-Code: MOSZAZ20' \
--header 'PSU-Device-ID-Type: IMEI' \
--header 'PSU-Device-ID: 43437437347347' \
--header 'PSU-IP-Address: 333' \
--header 'Consent-ID: qwer3456tzui7890' \
--header 'Authorization: Basic QVpFUkFaMjBBWFhYOjE='
```

{% hint style="danger" %}
Although these code generators are probably helpful, they may or may not work for your API. Always review code samples with developers. In most cases, developers supply the code samples for the documentation, and technical writers briefly comment on the code samples.
{% endhint %}

{% hint style="info" %}
Postman, cURL, API doc platformaları (SwaggerHub, ReDoc və s) üzrə ayrıca mövzularımız olacaqdır.
{% endhint %}

### Request example for the surfreport endpoint <a href="#request-example-for-the-surfreport-endpoint" id="request-example-for-the-surfreport-endpoint"></a>

> Let’s return to the `surfreport/{beachId}` endpoint in our [sample scenario](https://idratherbewriting.com/learnapidoc/docapis\_new\_endpoint\_to\_doc.html) and create a request example for it. Here’s my approach:
>
> İndi isə bizə verilən taska qayıdaq və&#x20;

{% hint style="info" %}
### <mark style="color:blue;">**Sorğu nümunəsi**</mark>

```javascript
curl --location --request GET 'http://obank-test.example.az:50000/api/obis/v1.0/accounts/AZ83MOSZ00000000000019988155/balances' \
--header 'Sender-Participant-Code: AZERAZ20' \
--header 'Receiver-Participant-Code: MOSZAZ20' \
--header 'PSU-Device-ID-Type: IMEI' \
--header 'PSU-Device-ID: 43437437347347' \
--header 'PSU-IP-Address: 333' \
--header 'Consent-ID: qwer3456tzui7890' \
--header 'Authorization: Basic QVpFUkFaMjBBWFhYOjE='
```

(In the above code, replace `APIKEY` with your actual API key.)
{% endhint %}







\
