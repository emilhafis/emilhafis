# Getting started tutorial: Using Stoplight Studio to create an OpenAPI specification document

> OpenAPI spesifikasiyası bir neçə yol ilə hazırlana bilər:
>
> 1. Source code-lardan avto generate edilməklə
> 2. Editor-lardan istifadə etməklə (məsələn Swagger Editor) manual kodlaşdırmaqla
> 3. GUI editordan (məsələn Stoplight) istifadə etməklə.
>
> Hazırda biz 3 variantda bildirdiyimiz GUİ editor olan Stoplight vasitəsilə API dizayn edəcəyik. Yəni, əvvəlki mövzularda travelpayouts üzrə göstərdiyimiz real API-ları daxili istifadə üçün APı First yanaşması tətbiq edəcəyik.

> For a higher-level introduction to the Open API, see [Introduction to the OpenAPI specification](https://idratherbewriting.com/learnapidoc/pubapis\_openapi\_intro.html). For a more conceptual introduction to Stoplight Studio is available here: [Stoplight — visual modeling tools for creating your OpenAPI spec](https://idratherbewriting.com/learnapidoc/pubapis\_stoplight.html).

### Using a visual editor <a href="#using-a-visual-editor" id="using-a-visual-editor"></a>

> Before we get started, let’s address an initial question about the approach we’re taking. When creating your OpenAPI specification document, why should you use a visual/GUI editor, which hides the code (unless you toggle the view open) instead of coding every detail of the spec by hand?
>
> All approaches have their merits. But if you don’t work with the OpenAPI specification enough to remember all the fields and syntax for each property, or if you’re learning it for the first time, trying to get the syntax valid in the raw code can be challenging. Coding by hand leads to many errors and forces you to spend a lot of time troubleshooting invalid syntax.
>
> Using an editor helps you avoid these errors and focus instead on the content. The less time you spend fiddling with syntax and more time working on content, the better the outcome of the documentation. For more on the philosophy of not getting lost in the syntactical details of the spec, but instead focusing on content, read this post by Phil Sturgeon, who says Stoplight Studio is “an absolute game changer for API Design, and something I’ve been waiting for since I found out about it somewhere in 2018” ([Reinventing API Design with Stoplight Studio](https://phil.tech/2019/08/22/reinventing-api-design-stoplight-studio/)).
>
> As a technical writer who likes working in Markdown and other raw formats, I can see the appeal of working directly in the code. But the OpenAPI syntax is quite complex, and YAML is fussy. I’d rather be worrying more about the content than addressing syntax questions. But even so, Stoplight lets you switch into the code view to work in that mode when you want, and switch back into the visual view when you want. Changes you make in one mode sync to the other. This gives you the best of both world

### Before we begin <a href="#before-we-begin" id="before-we-begin"></a>

>
>
> Before we begin the tutorial, note the following:
>
> * Stoplight Studio isn’t the only GUI editor for creating OpenAPI specifications. You can also use [OpenAPI-GUI](https://mermade.github.io/openapi-gui/), [Apibldr](https://apibldr.com/), [SwaggerHub’s visual editor](https://app.swaggerhub.com/help/ui/visual-editor), and others. (However, I think Stoplight’s editor is one of the most mature and user-friendly.)
> * Although Stoplight has a commercial offering, their editor and documentation publishing are free (the [free tier](https://stoplight.io/pricing/) includes 2 projects and 3 authors). But in general, just because you’re using the Stoplight Studio editor here, it doesn’t mean you’re wed to their documentation outputs. You can use the Stoplight Studio editor to create a valid specification, export it, and then choose the tool you want to use to render it (e.g., Stoplight, Redoc, Spectacle, Swagger UI, or some other display framework).
> * Stoplight’s platform gives you a nice path toward more comprehensive documentation, including not only API reference content but also [conceptual documentation](https://idratherbewriting.com/learnapidoc/docconceptual.html) and [tutorial content](https://idratherbewriting.com/learnapidoc/docapiscode.html). In short, you can create Markdown files [similar to Stoplight Studio’s documentation](https://meta.stoplight.io/docs/studio/README.md). Their platform lets you create a more seamless documentation experience for your readers across many different types of content, providing you with a complete publishing solution — not just a way to create reference content. (This tutorial will only cover creating API reference content, though.)
> * This tutorial should take about 30 minutes to an hour. No special technical knowledge is required.

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

> Stoplight provides a variety of options for working with projects — desktop editor versus web editor, and syncing from GitHub or saving directly to a Stoplight workspace. In this tutorial, I take the simplest path: using the web editor and saving to the Stoplight workspace. But recognize that you have more options for how you approach projects. See [Working with Projects](https://meta.stoplight.io/docs/studio/docs/Basics/01-working-with-projects.md) for more details.

### Step 1: Set up a project in Stoplight Studio <a href="#setup" id="setup"></a>

>
>
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
> 5\. In the New API dialog box, name your API (e.g., “openweathermap”), and click **Create**. By default, the editor will use OpenAPI v3 and YAML.
>
> 6\. Stoplight Studio creates an OpenAPI (OAS) specification file called, in this case, openweathermap.v1.yml and loads it as follows:



<figure><img src=".gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

7\. Stoplight lets you toggle between a form and code editor. The above screenshot shows the Form view. Click the **Code** button in the upper-right corner to see the code automatically created.

<figure><img src=".gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

> (The code includes some sample content for some fictitious user endpoints called `/users/{userid}` and `/user`.)
>
> You could simply paste in a valid OpenAPI spec into the Code view, and it would populate the Form view. But presumably you don’t already have an OpenAPI spec to paste into the code — this is why you’re using the editor, to build out the specification document.

> You can seamlessly switch between Form and Code views. Try adding a word in the Form view, switch to the Code view and find it, then remove it from the Code view and see how it updates in the Form view. Here’s a short video clip showing this:

{% embed url="https://youtu.be/ngTq3aGZFVA" %}

Click the **Preview** button in the upper-right corner to see what the content would look like when published:

<figure><img src=".gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

The ability to switch views between Form, Code, and Preview gives you a lot of authoring power.

> 9\. Click the **Form** button to switch back to the Form view.

### Step 2: Enter the API overview information <a href="#overview" id="overview"></a>

> To get started, populate the fields in the API Overview section (this includes the version, name, description, security, contact, license, and other general details). For this tutorial, I’ve prepared sample information for you to easily insert into the Stoplight Editor. (Note that, in the sample information in the orange expandable buttons, for fields that don’t have names, I put the assumed titles of these fields in \[brackets].)

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

To populate the API overview:

> 1. In the Stoplight Studio sidebar, click **API Overview.**
> 2. Enter information in each of the form fields using information provided in the orange button below:

<details>

<summary>Sample API Overview information</summary>

API Overview information:

* _1.0 \[Version]_: 3
* _\[Name]_: Travelpayouts API
* _Description …_: Returns the cheapest tickets for specific dates. This sample Swagger file covers the `current` endpoint only from the OpenWeatherMap API. All parameters are optional, but you must select at least `destination` or `origin` parameter. By default this endpoint retrieves **chepeast ticket**.

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
* _Contact Url_: [https://openweathermap.org/api](https://support.travelpayouts.com/)
* _Contact Email_: someone@gmail.com
* _Terms of Service URL_: [https://openweathermap.org/terms](https://support.travelpayouts.com/hc/en-us/articles/360004162111-Terms-of-the-Travelpayouts-Travel-Affiliate-Network)

**License**

* _License (MIT, Apache 2.0, etc)_: Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)
* _License URL_: https://creativecommons.org/licenses/by-sa/4.0/

</details>

{% hint style="info" %}
**Note**: The Markdown source formatting in the sample text is intentional. When you copy and paste in the source, Stoplight will convert the Markdown into HTML when displaying the published page. Also note that Stoplight allows you to use [Stoplight-flavored Markdown](https://github.com/stoplightio/studio-demo/blob/master/docs/markdown/stoplight-flavored-markdown.md). This Markdown version allows all the same tags as [CommonMark](https://commonmark.org/) but also includes some special tags for callouts, alerts, and other formatting.


{% endhint %}

Bitirdikd'n sonra yuxar; soldak; Publish etməyi unutmayın

When finished, the form should look like this:

![](<.gitbook/assets/image (3).png>)

3\. Now that you entered information for the first section, check out how it looks. Click the **Preview** button in the upper-right corner. It should look as follows:

![](<.gitbook/assets/image (1).png>)

4\. Return to the Form view by clicking the **Form** button again.

### Step 3: Enter the path and parameter information <a href="#endpoints" id="endpoints"></a>

> Now enter the path and parameter information:
>
> 1. In the sidebar, right-click the **Paths** folder and select **New Path**.

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

You can remove the default `/users/{userid}` and `/user` and endpoints. Right-click each endpoint and select **Delete Path**.

By default Stoplight creates a GET operation for the weather endpoint. In our case, this works out great because this endpoint has a GET endpoint. But if not, you could just click the other operations available to create details for those operations.



2\. Travelpayouts-da istifadə edəcəyimiz endpointin adını yazaq - **prices\_for\_dates**

By default Stoplight creates a GET operation for the weather endpoint. In our case, this works out great because this endpoint has a GET endpoint. But if not, you could just click the other operations available to create details for those operations.

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
*

    <figure><img src=".gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

</details>

Yekunda Stoplight bu formada görünəcəkdir

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

You don’t need to add security for this endpoint because you already configured global security in the previous section. However, if this endpoint had unique security method, you could override the global security here by clicking the + Security button.

### Step 4: Learn how to re-use parameters <a href="#reuse" id="reuse"></a>
