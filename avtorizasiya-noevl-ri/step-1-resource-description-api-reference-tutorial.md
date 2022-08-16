# Addım 1: Resursun təsviri



| Step I ->                                                                                                                                                                                       | Step II ->                                                                                                                                                                                                                                                                                                                                                                            | Step III ->                                     | Step IV ->                                           | Step V                                                                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------- | ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <mark style="color:orange;">****</mark>[<mark style="color:orange;">**Resoursun təsviri**</mark>](step-1-resource-description-api-reference-tutorial.md)<mark style="color:orange;">****</mark> | <p><mark style="color:blue;"><strong></strong></mark><a href="step-2-endpoints-and-methods-api-reference-tutorial.md"><mark style="color:blue;"><strong>Endpoint</strong></mark> </a></p><p><a href="step-2-endpoints-and-methods-api-reference-tutorial.md"><mark style="color:blue;"><strong>və metodlar</strong></mark> </a><mark style="color:blue;"><strong></strong></mark></p> | <mark style="color:blue;">**Parameters**</mark> | <mark style="color:blue;">**Request example**</mark> | <p><mark style="color:blue;"><strong>Response</strong></mark> </p><p><mark style="color:blue;"><strong>example and</strong></mark> </p><p><mark style="color:blue;"><strong>schema</strong></mark></p> |

> “Resources” API-dan qayıdan məlumatlara deyilir. Bir çox API-larda müxtəlif kateqoriyalı məlumatlar cə ya müxtəlif resurslar qayıda bilər.
>
> Resursun təsviri qısa olur (1-3 cümləlik) və adətən feil ilə başlayır. Adətən resurslara giriş üçün resurslar üzrə müxxtəlif endpoint-lər olur və hər mir endpoint üzrə də bir neçə metodlarlar mövcud olur.&#x20;
>
> Adətən 1 səhifədə resurslara giriş üçün istifadə olunan enpoint-lər ümumi resursun təsviri ilə birgə göstərilir.&#x20;

### Examples of resource descriptions

> Aşağıda Mailchimp API’s [Campaigns resource](https://developer.mailchimp.com/documentation/mailchimp/reference/campaigns/) üzrə nümunə göstərilmişdir.

![](<../.gitbook/assets/mailchimp (1).png>)

> Adətən API-larda eyni resurs daxilində bir çox endpoint-lər olur. Bu senaridə ümumir resurs (Campaingns) və resurs üzrə endpoint-lər göstərilmişdir. Yəni Campaings resursu daxilində bir neçə enpoint vardır.

{% code lineNumbers="true" %}
```javascript
POST /campaigns
GET /campaigns
GET /campaigns/{campaign_id}
PATCH /campaigns/{campaign_id}
DELETE /campaigns/{campaign_id}
POST /campaigns/{campaign_id}/actions/cancel-send
POST /campaigns/{campaign_id}/actions/pause
POST /campaigns/{campaign_id}/actions/replicate
POST /campaigns/{campaign_id}/actions/resume
POST /campaigns/{campaign_id}/actions/schedule
POST /campaigns/{campaign_id}/actions/send
POST /campaigns/{campaign_id}/actions/test
POST /campaigns/{campaign_id}/actions/unschedule
```
{% endcode %}

#### [YouTube](https://developers.google.com/youtube/v3/docs/comments)

![](../.gitbook/assets/youtube\_api.PNG)

#### [Trello](https://developer.atlassian.com/cloud/trello/rest/api-group-cards/#api-group-cards)

![](../.gitbook/assets/trello.PNG)

```java
POST /1/cards
GET /1/cards/{id}
PUT /1/cards/{id}
DELETE /1/cards/{id}
GET /1/cards/{id}/{field}
GET /1/cards/{id}/actions
və digərləri
```

>
>
> The Relationships resource isn’t described but rather acts as a container for relationship endpoints. Descriptions are added for each of the resources grouped within the Relationships resource:
>
> * GET `/users/self/followsGet`
> * GET `/users/self/followed-byGet`
> * GET `/users/self/requested-byList`
> * GET `/users/user-id/relationshipGet`
> * POST `/users/user-id/relationshipModify`

> Although the Events resource isn’t described here, descriptions are added for each of the Events endpoints. The Events resource contains all of these endpoints:

> For the Membership resource (or “object,” as they call it), there are 7 different endpoints or methods you can call. The Box API describes the Membership resource and each of the endpoints that lets you access the resource.
>
> Sometimes the general resource isn’t described; instead, it just groups the endpoints. The bulk of the description appears in each endpoint. For example, in the Eventbrite API, here’s the Events resource:

> For another example of an API with resources and endpoints, check out the [Trello API](https://developers.trello.com/v1.0/reference#introduction)

{% hint style="info" %}
The description of the resource is likely something you’ll re-use in different places — product overviews, tutorials, code samples, quick references, etc. As a result, put a lot of effort into crafting it. Consider storing the description in a re-usable snippet in your authoring tool so that you can list it without resorting to copy/paste methods in your [quick start guide](https://idratherbewriting.com/learnapidoc/docapis\_doc\_quick\_reference.html).
{% endhint %}

### Terminology for describing the resource <a href="#terminology-for-describing-the-resource" id="terminology-for-describing-the-resource"></a>

> The exact terminology for referring to _resources_ varies. The “things” that you access using a URL can be referred to in a variety of ways, but “resource” is the most common term because you access them through a URL, or uniform _resource_ locator. Other than “resources,” you might see terms such as _API calls_, _endpoints_, _API methods_, _calls_, _objects_, _services_, and _requests_. Some docs get around the situation by not calling them anything explicitly except “Reference.”
>
> Despite the variety with terminology, generally an API has various “resources” that you access through “endpoints.” The endpoints give you access to the resource. (But terminology isn’t standard, so expect variety.)
>
> For more on how API terminology varies, see [The difference between resources, endpoints, objects, and items in the bunq API documentation](https://medium.com/bunq-developers-corner/the-difference-between-resources-endpoints-objects-and-items-in-the-bunq-api-documentation-6b774473542).
>
>
>
>

### Recognize the difference between reference docs versus user guides <a href="#recognize-the-difference-between-reference-docs-versus-user-guides" id="recognize-the-difference-between-reference-docs-versus-user-guides"></a>

> Resursun təsviri (həmçinin də endpoint təsviri) adətən qısa olur və 1-3 cümlə ilə göstərilir. Bəs 3 cümlə ilə bütün fikri tam izah edə bilməyəndə və daha çox detalların əlavə edilməsi lazım olanda nə edə bilərik? Belə olduqda bilinki, bunun üçün user guide-lar/tutorial-lar mövcuddur. Gəlin Reference sənədləşməsi ilə userguides/tutorials arasında nə fərqlər var baxaq.
>
> * **Reference documentation:** Proqramçıların oxuyaraq ümumi mənzərəni, resursun nəyi ifadə etməsini dərhal başa düşəcəyi prinsipləri özündə saxlayır. Məsələn, [YouTube](step-1-resource-description-api-reference-tutorial.md#undefined) nümunəsində  ümumi olaraq `Comment` resursunun nəyə xidmət etdiyi göstərilir amma API-dan necə istifadə edilməlidir, autentifikasiya metodları hansılardır və digər istifadə qaydaları göstərilmir.
> * **User guides/tutorials**:  Bu bölməyə addım-addım təlimatlar, kod nümunələri, konsepsiyalar və prosedurlar daxil olmaqla API-dən necə istifadə olunacağına dair ətraflı məlumatlar qeyd olunur. Bunun haqqında növbəti bölmələrdə daha geniş danışacağıq və başa düşəcəyik ki, bu səndələşməni hansı formada daha effektiv etmək olar.
>
> API refrens bölməsinin təsviri resursun ehtiva etdiyi məlumatın 1-3 cümləlik xülasəsini təqdim etsə də,  **User guides/tutorials-da** bu barədə daha ətraflı məlumat verə bilərsiniz. Siz Referens bölməsində **User guides/tutorials**-a link verərək daha detaaalı məlumatın alınması üçün şərait yarada bilərsiniz.&#x20;

```
// Some code
```

### Get account balance endpointi üçün resurs təsviri <a href="#resource-description-for-the-surfreport-endpoint" id="resource-description-for-the-surfreport-endpoint"></a>

> Let’s review the [surf report wiki page](https://idratherbewriting.com/learnapidoc/docapis\_new\_endpoint\_to\_doc.html#surf\_report\_api) (which contains the information about the resource) and try to describe the resource in 1-3 sentences. Here’s my approach:
>
> Gəlin bir daha Get account balans wiki page (ümumi təsviri verilən hissəsinə) və 1-3 cümlə ilə resursu təsvir etməyə çalışaq. Aşağıda nümunə əlavə edirəm.

{% hint style="success" %}
## Get account balance

Hesab üzrə balansın əldə olunmasını əhatə edir. Həmçinin də, bu API-dan istifadə edərək hesabın valyutasını, kredit xətti üzrə limiti, istifadə olunmuş balansı, overdraft xəttin və s. təyin etmək mümkündür.
{% endhint %}

> Now it’s time to list out the [endpoints and methods](https://idratherbewriting.com/learnapidoc/docapis\_resource\_endpoints.html) for the resource.

\
