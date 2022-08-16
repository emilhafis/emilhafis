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
