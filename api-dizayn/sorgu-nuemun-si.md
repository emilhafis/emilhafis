---
description: Request example
---

# Sorğu nümunəsi

![](../.gitbook/assets/request.png)

> **Sorğu nümunəsi** **Endpoint**-də daxil olmaqla istifadə edilmiş `parametrlər konfiqurasiyanı` göstərir. Sorğu nümunəsi adətən bütün mümkün parametr konfiqurasiyaların göstərmir amma mümkün qədər parametrləri göstərmək lazımdır.
>
> Sorğu nümunələrində çox vaxt müxtəlif dillərdə hazırlanmış kod nümunələrini də `code snipets` göstərirlər. Bunu göstərmək mütləq deyil, amma göstərilməsi daha yaxşıdır.

### Sorğu nümunələri

> Aşağıdakı nümunə [Stripe-ın göstərdiyi sorğu](https://stripe.com/docs/api/customer\_bank\_accounts/create) nümunəsidir.

![](../.gitbook/assets/Stripe\_request\_example.PNG)

> Gördüyünüz kimi burada API dizayn 3 hissəli təsvir edilmişdir. Sol tərəfdə Resurs və resurs üzrə əməliyyatlar, ortada Parametrlər, sağda isə request və response nümunəsi.&#x20;

{% hint style="info" %}
Bu formada dizaynı ilk dəfə **Stripe** gətirmişdir. Mənim bu dizayn çox xoşuma gəlir. API documenting üçün istifadə olunan ReDoc və Stoplight platformasının da dizaynı buna çox oxşardır.
{% endhint %}

> Sorğu nümunəsi default olaraq **cURL**-də göstərilmişdir. **cURL**-i daha dərindən növbəti mövzularda müzakirə edəcəyik. Həmçinində seçim əsnasında digər proqramlaşdırma dillərində nümunələrə baxmaq mümkündür.

#### [Travelpayouts](https://support.travelpayouts.com/hc/en-us/articles/203956163-Travel-insights-with-Aviasales-Data-API)

> Other API doc sites might use the full resource URL, such as this plain example from Twitter:
>
> Digər nümunə isə travelpayouts-dır. Gördüyünüz kimi buraya nümunə üçün tam olaraq sorğunu yerləşdiriblər. Yəni siz hazır sorğunu götürüb ona uyğun qayıdan cavaba baxa bilərsiniz.

{% hint style="info" %}
Travelpayouts-dan müxtəlif aviabilet qiymətləri ilə tanış olub öz platformanıza inteqrasiya edə bilərinsiniz.
{% endhint %}

![](../.gitbook/assets/travel-request\_example.PNG)

> Sorğunu göndərmək üçün sadəcə bizdən `API Key` tələb olunur. `API Key` saytda qeydiyyatdan keçdikdən sonra əldə olunur. Məsələn, mən `API Key` əldə etmişəm. Aşağıdakı [**URL**-i ](https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates?origin=GYD\&token=3c63416a24d3b969da6df9271faa9d6e)sadəcə brazuerdə açaraq qayıdan cavab ilə tanış ola bilərsiniz.

```javascript
https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&token=3c63416a24d3b969da6df9271faa9d6e
```

> Bəzən bu formada bir neçə sorğu nümunələri göstərirlər. Əgər sorğu nümunəsi üçün eyni vaxtda bir neçə parametrin birgə işlədilməsi mümkün olmazsa bu zaman bir neçə sorğu nümunəsinin göstərilməsi məqsədəuyğundur.

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
> İndi isə [bizə verilən taska](../api-reference-tutorial/a-new-endpoint-to-document.md#the-wiki-page-get-account-balance-api) qayıdaq və `/accounts/`<mark style="color:orange;">`{AccountId}/`</mark>`balances` endpointi üçün sorğu nümunəsi hazrılayaq.&#x20;

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

### Növbəti addım

> Now that we’ve created a sample request, the next steps naturally follow — include a sample response that corresponds with the same request. We’ll also document the model or schema of the response in general. Go to [Step 5: Response example and schema (API reference tutorial)](https://idratherbewriting.com/learnapidoc/docapis\_doc\_sample\_responses\_and\_schema.html).
>
> [\
> ](https://www.buymeacoffee.com/learnapidoc)







\
