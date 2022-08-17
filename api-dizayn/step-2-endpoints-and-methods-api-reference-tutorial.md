# Step 2: Endpoints and methods (API reference tutorial)

|                                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                    |   |
| ----------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | - |
| <mark style="color:blue;">**Resursun təsviri**</mark> | <p><mark style="color:orange;"></mark><a href="step-2-endpoints-and-methods-api-reference-tutorial.md"><mark style="color:orange;"><strong>Endpoint</strong></mark> </a><mark style="color:orange;"></mark></p><p><mark style="color:orange;"></mark><a href="step-2-endpoints-and-methods-api-reference-tutorial.md"><mark style="color:orange;"><strong>və metodlar</strong></mark> </a><mark style="color:orange;"><strong></strong></mark></p> |   |

### Endpoint və metod nədir?

> **Endpoint** resursa necə giriş əldə edə biləcəyinizi, **metod** isə resurs üzərində hansı əməliyyatları (`GET`, `POST`, `DELETE` və s) icra edə biləcəyinizi göstərir.
>
> **Resurslar** müxtəlif **Endpoint**-lərə malik olur. **Endpoint**-lərin müxtəlif **Path (yəni URL-ləri)** və **metodları** olsa da onların hamsı **Resurs** üzrə müxtəlif məlumatları qaytarırlar.&#x20;
>
> **Endpoint**-lərin təsviri adətən ümumi resursun təsvirinə oxşar, lakin daha qısa təsvirlərə malik olur.&#x20;

{% hint style="info" %}
Məsələn, aşağıda **Mailchimp API** üzrə nümunədə görə bilərsiniz ki, ümumi resurs **Campaings** adlanır və onun təsviri belə göstərilir:

<mark style="color:orange;">`Campaigns are how you send emails to your Mailchimp list. Use the Campaigns API calls to manage campaigns in your Mailchimp account.`</mark>

**Campaings** resursunun Endpoint-lərindən biri olan ** `GET /campaigns`** təsviri isə resursa nəzərən qısa olaraq belə göstərilir:

<mark style="color:orange;">`Get all campaigns in an account.`</mark>
{% endhint %}

> Həmçinin, Endpoint bütün Endpoint-lər üçün ümumi olan əsas Path-i (yol) deyil, yalnız resurs URL-in Path-in (yolun) göstərir.
>
> Also, the endpoint shows the end path of a resource URL only, not the base path common to all endpoints.

### Endpointlər üzrə nümunə

#### [Mailchimp](https://mailchimp.com/developer/marketing/api/campaigns/)

> Here’s an example of the endpoints for the Relationships resource in the Instagram API:

![](../.gitbook/assets/mailchimp\_endpoint.PNG)

> Endpoint-lər adətən gözə daha tez çarpması üçün xüsusi dizaynla interfeysdə göstərilir. API sənədləşmələrinin əksəriyyətinin əsas məğzini Endpoint-lər təşkil edir. bu səbəbdəndə sənədləşmənizdə **Endpoint**-ləri xüsusi frmada göstərməyiniz tövsiyyə olunur. &#x20;
>
> Çünki proqramçılar test sorğuları etmək üçün dərhal **Endpoint**-ləri axtaracaqlar.&#x20;

### Represent path parameters with curly braces <a href="#represent-path-parameters-with-curly-braces" id="represent-path-parameters-with-curly-braces"></a>

> Əgər sizin endpoint-də **path parameter** varsa onları _fiqurlu mötərizə_ (_curly braces_) ilə göstərin. Məsələn aşağıda **Mailchimp API** üzrə nümunə göstərilmişdir.

```javascript
POST /campaigns/{campaign_id}/actions/cancel-send
```

{% hint style="warning" %}
If you can, put the path parameter in another color to set it off:

**POST /campaigns/**<mark style="color:orange;">**{campaign\_id}**</mark>**/actions/cancel-send**
{% endhint %}

> Curly braces for path parameters are a convention that users will understand. In the above example, almost no endpoint uses curly braces in the actual path syntax, so the `{campaign_id}` is an obvious placeholder.

> Here’s an example from the Facebook API that colors the path parameter in an easily identifiable way:

#### [OpenWeather API](https://openweathermap.org/api/one-call-3)

![](../.gitbook/assets/Open.PNG)

> When the parameters are described in Facebook’s docs, the same green color is used to set off the parameters, which helps users recognize their meaning.
>
> Bu API-larda da istifadiçilərin dərhal parametrləi anlamaları üçün <mark style="color:orange;">fərqli rənglə</mark> verilmişdir.





> Path parameterlərinin standart təyin edilən bir rəngi yoxdur. Məsələn aşağıda [Amazon API-](step-2-endpoints-and-methods-api-reference-tutorial.md#undefined)larında şahidi oluruq ki, path parametri olan `{eventGroupId}` URL-dəki digər dəyərlərdən seçilmir. &#x20;
>
> Amma siz sənədləşmə edərkən bu parametrlərin dərhal gözə çarpası üçün fərqli formada və fərqli rənglə verilməsini tövsiyyə edirəm. Mən standart olaraq [OpenWeather API](https://openweathermap.org/api/one-call-3)-da olduğu kimi narıncı rəngdən istifadə edirəm.

#### [Amazon API](https://developer-docs.amazon.com/sp-api/docs/finances-api-reference#get-financesv0financialeventgroupseventgroupidfinancialevents)

![](../.gitbook/assets/Amazon.PNG)

### You can list the method next to the endpoint <a href="#you-can-list-the-method-next-to-the-endpoint" id="you-can-list-the-method-next-to-the-endpoint"></a>

> It’s common to list the method (GET, POST, and so on) next to the endpoint. The method defines the operation with the resource. Briefly, each method is as follows:
>
> * GET: Retrieves a resource
> * POST: Creates a resource
> * PUT: Updates or creates within an existing resource
> * PATCH: Partially modifies an existing resource
> * DELETE: Removes the resource
>
> See [Request methods](https://en.wikipedia.org/wiki/Hypertext\_Transfer\_Protocol#Request\_methods) in Wikipedia’s article on HTTP for more details. (There are some additional methods, but they’re rarely used.)

> Since there’s not much to say about the method itself, it makes sense to group the method with the endpoint. Here’s an example from the Box API:

#### Endpointimiz üzrə metodu təyin edək

> Məlumatlarda qeyd edildiyi kimi, 3-cü tərəf təşkilatlar banklardan hesab üzrə balansları əldə edəcəklər. Məlumatın əldə edilməsi üçündə **GET** metodundan istifadə edilir.

{% hint style="success" %}
Endpointimiz üçün metod - <mark style="color:blue;">**GET**</mark>
{% endhint %}

#### [Stripe API](https://stripe.com/docs/api/customer\_bank\_accounts)

![](../.gitbook/assets/Stripe.PNG)

{% hint style="info" %}
Sometimes the method is referred to as the “verb.” GET, PUT, POST, PATCH, and DELETE are all verbs or actions.
{% endhint %}

### The endpoint shows the end path only <a href="#the-endpoint-shows-the-end-path-only" id="the-endpoint-shows-the-end-path-only"></a>

> Endpoint-i göstərdiyiniz zaman yalnız "end path"-i göstərin. "Full path" "Base Path və Endpoint-dən ibarət olur və bunların ümumilikdə resurs URL adlanır.&#x20;
>
> Yuxarıdakı Stripe nümunəmizdə də endpoint  `/v1/customers/:id/sources` kimi göstərilir. Burada Stripe hər dəfə resurs URL-ni tam formada, yəni bu formada `https://api.stripe.com/v1/customers/:id/sources` göstərmir. yuxarıdakı qeydimizi bu nümunə üzrə izah etsək burada `https://api.stripe.com` **Base path** `/v1/customers/:id/sources isə` **Endpoint-dir.**  Bunların ikisi bir yerdə isə `https://api.stripe.com/v1/customers/:id/sources` **Resurs URL-dir.**

{% hint style="warning" %}
Tam resurs URL-nin sənədləşməyə daxil edilməsi, istifadəçilər üçün lazım olan Endpoint-lərə diqqətini yönəltməkdən yayındırır.&#x20;

Adətən resurs URL user guide-dın giriş hissəsində (məsələn, getting starting tutorial) avtorizasiya metodları ilə birgə göstərilir.

Bu səbəbdəndə, hər dəfə Endpoint yazarkən full resurs URL göstərməyiniz lazım deyil.
{% endhint %}

### How to group multiple endpoints for the same resource <a href="#how-to-group-multiple-endpoints-for-the-same-resource" id="how-to-group-multiple-endpoints-for-the-same-resource"></a>

> Another consideration in documenting endpoints and methods is how to group and list the endpoints, particularly if you have a lot of endpoints for the same resource. In [Examples of resource descriptions](https://idratherbewriting.com/learnapidoc/docapis\_resource\_descriptions.html#examples), we looked at a variety of APIs. Many doc sites provide different designs for grouping or listing each endpoint for the resource, so I won’t revisit all the same examples. Group the endpoints in some way that makes sense, such as by method or by the type of information returned.
>
> For example, suppose you have three GET endpoints and one POST endpoint, all of which relate to the same resource. Some doc sites might list all the endpoints for the same resource on the same page. Others might break them into separate pages. Others might create one group for the GET endpoints and another for the POST endpoints. It depends how much you have to say about each endpoint.
>
> If the endpoints are mostly the same, consolidating them on a single page could make sense. But if they’re substantially unique (with different responses, parameters, and error messages), separating them onto different pages is probably better (and easier to manage). Then again, with a more sophisticated website design, you can make lengthy information navigable on the same page.

> In a later section on [design patterns](https://idratherbewriting.com/learnapidoc/pubapis\_design\_patterns.html), I explain that [long pages](https://idratherbewriting.com/learnapidoc/pubapis\_design\_patterns.html#longish\_pages) are common pattern with developer docs, in part because they make content easily findable for developers using Ctrl + F.

### How to refer to endpoints in tutorials <a href="#how-to-refer-to-endpoints-in-tutorials" id="how-to-refer-to-endpoints-in-tutorials"></a>

> In tutorials and other conceptual content, how do you refer to the endpoints within an API reference topic? Referring to the “`/aqi` endpoint” or to the “`/weatherdata`” endpoint doesn’t make a huge difference. But with more complex APIs, using the endpoint to talk about the resource can be tricky.
>
> At one company I worked at, our URLs for the Rewards endpoints looked like this:
>
> \
>

> To say that you could use the rewards resource wasn’t always specific enough, because there were multiple rewards and missions endpoints.
>
> It can get awkward referring to the endpoint. For example, you might have a sentence like this: “When you call `/users/{userId}/rewards/`, you get a list of all rewards. To get a specific reward for a specific mission for a specific user, the `/users/{userId}/rewards/{missionId}` endpoint takes several parameters…”
>
> The longer the endpoint, the more cumbersome the reference becomes. These kinds of descriptions are more common in the [conceptual sections](https://idratherbewriting.com/learnapidoc/docconceptual.html) of your documentation. Generally, there’s not a clear convention about how to refer to cumbersome endpoints. Adopt an approach that makes the most sense for your API.

### Endpoint for surfreport API <a href="#endpoint-for-surfreport-api" id="endpoint-for-surfreport-api"></a>

> Let’s create the Endpoints and methods section for our [fictitious surfreport API](https://idratherbewriting.com/learnapidoc/docapis\_new\_endpoint\_to\_doc.html). Here’s my approach:

{% hint style="success" %}
<mark style="color:green;">**Endpoint**</mark>

<mark style="color:blue;">**GET**</mark>**   /accounts/**<mark style="color:orange;">**{AccountId}/**</mark>**balances**

**Hesab üzrə balansı əldə et (Request to get account balance)**
{% endhint %}

### Next step

> Now that we’ve described the resource and listed the endpoints and methods, it’s time to tackle one of the most important parts of an API reference topic: the [parameters section](https://idratherbewriting.com/learnapidoc/docapis\_doc\_parameters.html).
