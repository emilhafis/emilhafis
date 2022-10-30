# Getting started tutorial: Using Stoplight Studio to create an OpenAPI specification document

> OpenAPI spesifikasiyası bir neçə yol ilə hazırlana bilər:
>
> 1. Source code-lardan avto generate edilməklə
> 2. Editor-lardan istifadə etməklə (məsələn Swagger Editor) manual kodlaşdırmaqla
> 3. GUI editordan (məsələn Stoplight) istifadə etməklə.
>
> Hazırda biz 3 variantda bildirdiyimiz GUİ editor olan Stoplight vasitəsilə API dizayn edəcəyik. Yəni, əvvəlki mövzularda travelpayouts üzrə göstərdiyimiz real API-ları daxili istifadə üçün APı First yanaşması tətbiq edəcəyik.

### Using a visual editor <a href="#using-a-visual-editor" id="using-a-visual-editor"></a>

> Başlamamışdan əvəvl aydınlıq gəitərək ki, GUİ ilə işləməyin üstünlüyü nədir
>
> Göstərdiyimiz hər 3 yanaşmanın hamısın bir birinə nəzərə n mənfi və müsbət tərəfləri var.
>
> Open API ilə siz ilk dəfə işləyirsinizsə GUİ dən istifadə sizin üçün çox rahat gələcəkdir. Əlavə olaraq əl ilə kodlaşdırma texniki səhvlərə yol aça bilər və sizin xeyli vaxtınız gedə bilər.&#x20;
>
> Editordan istifadə sizə bu xətalardan yayınmaq imkanı verir. Sizə error düzəltmək əvəzinə analitika aparırsınız.&#x20;
>
> baxacağımız Stoplight bizə hər iki imkanı təqdim edir, həm GUi vasitəsilə, həmdə code editordan özümüz dəyişikliklər edə bilərik.

### &#x20;<a href="#before-we-begin" id="before-we-begin"></a>

### What you’ll build <a href="#what-youll-build" id="what-youll-build"></a>

> Bildirdiyim kimi, burada biz [travelpayouts API](https://support.travelpayouts.com/hc/en-us/articles/203956163-Travel-insights-with-Aviasales-Data-API)-nı öz developerlərimizə tapşırıq vermək üçün API First dizayn edəcəyik. Xatırlayırsınızsa ilk dərsimizdə nümunəni bu platforma üzərində göstərmişdim.
>
> Here’s the [documentation output](https://idratherbewriting.stoplight.io/docs/openweathermap4/YXBpOjExMTIxODY3-open-weather-map-api) that you’ll build in this tutorial:

### The tutorial has the following steps:

>
>
> * [Step 1: Set up a project in Stoplight Studio](https://idratherbewriting.com/learnapidoc/pubapis\_openapis\_quickstart\_stoplight.html#setup)
> * [Step 2: Enter the API overview information](https://idratherbewriting.com/learnapidoc/pubapis\_openapis\_quickstart\_stoplight.html#overview)
> * [Step 3: Enter the path and parameter information](https://idratherbewriting.com/learnapidoc/pubapis\_openapis\_quickstart\_stoplight.html#endpoints)
> * [Step 4: Learn how to re-use parameters](https://idratherbewriting.com/learnapidoc/pubapis\_openapis\_quickstart\_stoplight.html#reuse)
> * [Step 5: Enter the responses and response schema information](https://idratherbewriting.com/learnapidoc/pubapis\_openapis\_quickstart\_stoplight.html#responses)
> * [Step 6: Preview, test, and publish the output](https://idratherbewriting.com/learnapidoc/pubapis\_openapis\_quickstart\_stoplight.html#preview)



### Step 1: Set up a project in Stoplight Studio <a href="#setup" id="setup"></a>

> * [https://stoplight.io/studio/](https://stoplight.io/studio/) göstərilən linkə keçid edək Getting started for free və ya On the Web bölməsin seçək
> * instruksiyaya əsasən workspace yaradaq və daxil olaq
> * Follow the on-screen instruction to create a workspace, and then sign into it, authenticating with one of the ID options.
> * Click the **+** button ![Add project button](https://s3.us-west-1.wasabisys.com/idbwmedia.com/images/api/stoplight\_plus\_button.png) at the top to add a new project. Give the project a name, and then click

<figure><img src=".gitbook/assets/image (3) (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (6) (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (4) (2).png" alt=""><figcaption></figcaption></figure>

> 4\. Click the **API** button in the sidebar.
>
> 5\. In the New API dialog box, and click **Create**. By default, the editor will use OpenAPI v3 and YAML.
>
> 6\. Stoplight Studio creates an OpenAPI (OAS) specification file called, in this case, travel.v1.yml and loads it as follows:



<figure><img src=".gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

7\. Stoplight sizə forma və kod editor arasında keçid etməyə imkan verir. Yuxarıdakı ekran görüntüsü Form görünüşünü göstərir. Avtomatik yaradılmış kodu görmək üçün yuxarı sağ küncdəki Kod düyməsini klikləyin.

<figure><img src=".gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

> (Bu kodda bəzi sample məlumat qeyd olunub `/users/{userid}` and `/user`.)
>
> Siz əlinizdə olan Open api specini sadəcə bura copy past etməklə vizual nəticəni ala biləris. Amma hazırda Open API spek olmadığından gəlin onu yaradaq.

Click the **Preview** button in the upper-right corner to see what the content would look like when published:

<figure><img src=".gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

The ability to switch views between Form, Code, and Preview gives you a lot of authoring power.

> 9\. Form klik edərək qayıdaq Form-a

### Step 2: Enter the API overview information <a href="#overview" id="overview"></a>

> To get started, populate the fields in the API Overview section (this includes the version, name, description, security, contact, license, and other general details). For this tutorial, I’ve prepared sample information for you to easily insert into the Stoplight Editor. (Note that, in the sample information in the orange expandable buttons, for fields that don’t have names, I put the assumed titles of these fields in \[brackets].)

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

To populate the API overview:

> 1. In the Stoplight Studio sidebar, click **API Overview.**
> 2. Enter information in each of the form fields using information provided in the orange button below:

{% hint style="info" %}
**Note**: The Markdown source formatting in the sample text is intentional. When you copy and paste in the source, Stoplight will convert the Markdown into HTML when displaying the published page. Also note that Stoplight allows you to use [Stoplight-flavored Markdown](https://github.com/stoplightio/studio-demo/blob/master/docs/markdown/stoplight-flavored-markdown.md). This Markdown version allows all the same tags as [CommonMark](https://commonmark.org/) but also includes some special tags for callouts, alerts, and other formatting.


{% endhint %}

Bitirdikd'n sonra yuxar; soldak; Publish etməyi unutmayın

When finished, the form should look like this:

<figure><img src=".gitbook/assets/image (3) (3).png" alt=""><figcaption></figcaption></figure>

3\. Now that you entered information for the first section, check out how it looks. Click the **Preview** button in the upper-right corner. It should look as follows:

<figure><img src=".gitbook/assets/image (1) (3) (1).png" alt=""><figcaption></figcaption></figure>

4\. Return to the Form view by clicking the **Form** button again.

<details>

<summary>Sample API Overview information</summary>



API Overview information:

* _1.0 \[Version]_: 3
* _\[Name]_: Travelpayouts API
* _Description …_: Returns the cheapest tickets for specific dates. This sample Swagger file covers the `current` endpoint only from the Travelpayouts API. All parameters are optional, but you must select at least `destination` or `origin` parameter. By default this endpoint retrieves **chepeast ticket**.

**Servers +**

* __[_https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates_](https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates)__
* _Name (optional)_: Production

**Security schemes +**

* _left drop-down menu_: apiKey
* _key_: 3c63416a24d3b969da6df9271faa9d6e
* _name_: token
* _right drop-down menu_: query

**Global security +**

* Select **key**

**Contact**

* _Contact Name_: Support
* _Contact Url_: [https://support.travelpayouts.com/](https://support.travelpayouts.com/)
* _Contact Email_: someone@gmail.com
* _Terms of Service URL_: [https://support.travelpayouts.com/hc/en-us/articles/360004162111-Terms-of-the-Travelpayouts-Travel-Affiliate-Network](https://support.travelpayouts.com/hc/en-us/articles/360004162111-Terms-of-the-Travelpayouts-Travel-Affiliate-Network)

**License**

* _License (MIT, Apache 2.0, etc)_: Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)
* _License URL_: https://creativecommons.org/licenses/by-sa/4.0/

</details>

### Step 3: Enter the path and parameter information <a href="#endpoints" id="endpoints"></a>

> Now enter the path and parameter information:
>
> 1. In the sidebar, right-click the **Paths** folder and select **New Path**.

<figure><img src=".gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

You can remove the default `/users/{userid}` and `/user` and endpoints. Right-click each endpoint and select **Delete Path**.

By default Stoplight creates a GET operation for the weather endpoint. In our case, this works out great because this endpoint has a GET endpoint. But if not, you could just click the other operations available to create details for those operations.

2\. Travelpayouts-da istifadə edəcəyimiz endpointin adını yazaq - **prices\_for\_dates**

3\. “Your GET endpoint” dəyişib - Get the chepeast ticket edək

4\. Click the Tags button ![Stoplight tags button](https://s3.us-west-1.wasabisys.com/idbwmedia.com/images/api/tags\_button\_stoplight2.png) in the upper-left corner and add a tag called “Flight endpoints.”

This tag will group the endpoints in the sidebar by this tag into a collapsed section called “Weather endpoints.” This is how you build navigation hierarchy for your endpoints.

5\. In the Description field, add the description for this endpoint. Expand the orange button below to get a description to paste here.

<details>

<summary>Sample path information</summary>

Paths:

* _/_prices\_for\_dates
* _\[Operation]_: GET
* _Operation ID_: get-prices\_for\_dates
* _Description_: Access current weather data for any location on Earth including over 200,000 cities! Current weather is frequently updated based on global models and data from more than 40,000 weather stations.

</details>

{% hint style="danger" %}
Kim deyə bilər ki, burada hansı parametrlər istifadə olunub və nədən bildiniz?

[https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates?origin=LON\&destination=BCN\&departure\_at=2022-01\&return\_at=2022-02\&unique=false\&sorting=price\&direct=false\&currency=rub\&limit=30\&page=1\&one\_way=true\&token=PutYourTokenHere ](https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates?origin=LON\&destination=BCN\&departure\_at=2022-01\&return\_at=2022-02\&unique=false\&sorting=price\&direct=false\&currency=rub\&limit=30\&page=1\&one\_way=true\&token=PutYourTokenHere)
{% endhint %}

6\. In Stoplight Studio, click the **+ Query Param** button to expand the query parameters options. (Note that our sample API has query parameters only, no path parameters.) Expand the orange button below for sample query parameter information. Then populate all the query parameter information into the Stoplight Studio editor.

<details>

<summary>Sample query parameter information</summary>

* **currency** — the currency of prices. The default value is RUB
* **origin** — An IATA code of a city or an airport of the origin
* **destination** — An IATA code of a city or an airport of the destination (if you don't specify origin parameter, you must set destination)
* **departure\_at** — the departure date (`YYYY-MM` or `YYYY-MM-DD`)
* **return\_at** — the return date. For one-way tickets do not specify it
* **direct** — non-stop tickets, `true` or `false`. By default:  `false`
* **market** — sets the market of the data source (by default, ru)
* **limit** — the total number of records on a page. The default value — 30. The maximum value — 1000
* **page** — a page number, is used to skip some massive of results. For example, if we want to get the entries from 100 to 150, we need to set `page=3`, and `limit=50`
* **sorting** — the assorting of prices:
  * **price** — by the price (the default value). For the directions, only city — city assorting by the price is possible
  * **route** — by the popularity of a route.
* **unique** — returning only unique routes, if only `origin` is specified, `true` or `false`. By default: `false`
* **token** — your API token.

</details>

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Yekunda Stoplight bu formada görünəcəkdir

<figure><img src=".gitbook/assets/image (16) (1).png" alt=""><figcaption></figcaption></figure>

You don’t need to add security for this endpoint because you already configured global security in the previous section. However, if this endpoint had unique security method, you could override the global security here by clicking the + Security button.

### Step 4: Learn how to re-use parameters <a href="#reuse" id="reuse"></a>

The OpenAPI spec allows to re-use parameters by storing the information in the [`components`](https://idratherbewriting.com/learnapidoc/pubapis\_openapi\_step5\_components\_object.html) property. In the Stoplight Studio editor, you reuse parameters by entering the parameter information in the Parameters section in the sidebar. (In the code behind the scenes, this information gets stored in `components`.)

To understand how this works, let’s re-use one of the query parameters.

To re-use a parameter:

1.  Right-click **Parameters** in the lower-left corner of the sidebar and select **New Query Parameter**.

    A parameter section similar to the query parameter sections you just populated appears.
2. Populate the `currency` parameter here using the same information as before.
3. Return to the previous query parameters section where you entered the `currency` parameter, and click the Reference button ![Reference button](https://s3.us-west-1.wasabisys.com/idbwmedia.com/images/api/stoplight\_link\_button.png) for this parameter.
4. Search for “currency” and select it.

<figure><img src=".gitbook/assets/image (3) (4).png" alt=""><figcaption></figcaption></figure>

When you link the parameter to the reference like this, the icon turns red: ![Reference button turns red when linked](https://s3.us-west-1.wasabisys.com/idbwmedia.com/images/api/stoplight\_link\_button\_red6.png)

5\. Switch to the Code editor and search for `cuurency`. You’ll now see a reference to a component:

```yaml
     parameters:
        - $ref: '#/components/parameters/currency'
```

You don’t need to do anything in the code here — I’m just pointing out what changed behind the scenes. You can use this same technique to re-use other parameters as well as other types of content, such as responses.

6\. Preview your updates. The preview should look like this:

<figure><img src=".gitbook/assets/image (1) (4) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
This endpoint in the travelpayouts API doesn’t have any path, header, or body parameters, so you can skip those elements.
{% endhint %}

### Step 5: Enter the responses and response schema information <a href="#responses" id="responses"></a>

As a final step for this endpoint, you need to enter the response information. The response includes not only an example response but also the schema describing the response. The schema describes all possible values in the response, their data types, and whether the values are required.

To enter the response information in Stoplight Studio:

1. Below the parameter section for the endpoint, click the **+ Response** button. Then click the **+ Add Body** button that appears within this expanded Response section.
2.  On the Schema tab, click **Generate from JSON**.

    Here you’ll experience one of the coolest features in the Stoplight Studio editor, and one reason why I like this editor so much. The editor will automatically build out the response schema from a sample JSON response.
3. Expand the orange button below and copy the sample response.

<details>

<summary>Sample response</summary>



```
{"success": true,
"data": [
{
"origin": "LON",
"destination": "BCN",
"origin_airport": "DME",
"destination_airport": "BCN",
"price": 3001,
"airline": "IO",
"flight_number": "675",
"departure_at": "2022-01-21T22:30:00+03:00",
"return_at": "2022-02-03T06:25:00+03:00",
"transfers": 0,
"return_transfers": 0,
"duration": 175,
"link": "/search/LON2101BCN03021?t=IO16427934001642798800000090DMEBCN16438587001643863800000085BCNVKO_9a6898092e218d1d1a374ecdd20a7fc6_3001&search_date=27122021&expected_price_uuid=bccbd9bf-69dc-49e2-a09b-c7bb6414fde5&expected_price_currency=rub"
}]
}
```

</details>



4\. Paste in the copied JSON into the gray area where it says “Paste or write a JSON example below…” (Remove the empty curly braces `{}` first, and then paste in your sample.) HTTP 200 uğurlu savab seçiril

5\. Click **Generate from JSON**.&#x20;

6\. Add some more detail about the response elements:

1. Click the **Description** button ![Description button](https://s3.us-west-1.wasabisys.com/idbwmedia.com/images/api/stoplight\_description\_button.png) next to each property and add a description.
2. Click the **Other Properties** ![Other properties](https://s3.us-west-1.wasabisys.com/idbwmedia.com/images/api/stoplight\_other\_properties\_button2.png) button and add an example in the **example** field.

For the description and examples, expand the orange button below and copy over the information.

<details>

<summary>Sample description and examples</summary>



* **origin** — the point of departure
* **destination** — the point of destination
* **origin\_airport** — the IATA of the origin airport
* **destination\_airport** — the IATA of the destination airport
* **price** — price of the ticket
* **airline** — the IATA of the airline
* **flight\_number** — flight number
* **departure\_at** — departure date
* **return\_at** — return date
* **transfers** — number of stops on the way to the destination
* **return\_transfers** — number of stops on the way back
* **duration** — the flight duration in minutes
* **link** — the ticket link. Add the code to the URL [https://www.aviasales.com/](https://www.aviasales.com/search/) to open the search results on the given route on Aviasales. Use our [link generator](https://support.travelpayouts.com/hc/en-us/articles/360027634052-How-to-create-a-link-to-any-page-of-the-travel-brand-s-website) to create your partner link out of the resulting link
* **currency** — the currency of prices.

</details>



### Before we begin <a href="#before-we-begin" id="before-we-begin"></a>

>
>
> Before we begin the tutorial, note the following:
>
> * Stoplight Studio isn’t the only GUI editor for creating OpenAPI specifications. You can also use [OpenAPI-GUI](https://mermade.github.io/openapi-gui/), [Apibldr](https://apibldr.com/), [SwaggerHub’s visual editor](https://app.swaggerhub.com/help/ui/visual-editor), and others. (However, I think Stoplight’s editor is one of the most mature and user-friendly.)
> * Although Stoplight has a commercial offering, their editor and documentation publishing are free (the [free tier](https://stoplight.io/pricing/) includes 2 projects and 3 authors). But in general, just because you’re using the Stoplight Studio editor here, it doesn’t mean you’re wed to their documentation outputs. You can use the Stoplight Studio editor to create a valid specification, export it, and then choose the tool you want to use to render it (e.g., Stoplight, Redoc, Spectacle, Swagger UI, or some other display framework).
> * Stoplight’s platform gives you a nice path toward more comprehensive documentation, including not only API reference content but also [conceptual documentation](https://idratherbewriting.com/learnapidoc/docconceptual.html) and [tutorial content](https://idratherbewriting.com/learnapidoc/docapiscode.html). In short, you can create Markdown files [similar to Stoplight Studio’s documentation](https://meta.stoplight.io/docs/studio/README.md). Their platform lets you create a more seamless documentation experience for your readers across many different types of content, providing you with a complete publishing solution — not just a way to create reference content. (This tutorial will only cover creating API reference content, though.)
> * This tutorial should take about 30 minutes to an hour. No special technical knowledge is required.
