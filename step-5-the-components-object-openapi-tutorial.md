# Step 5: The components object (OpenAPI tutorial)

> `components` obyekti Open API spesifikasiyasında digər obeyektlərdən xüsusidir. Çünki siz burada bir neçə yerdə istifadə edilə bilən məlumatlar yaradıb öz spesifikasiyanızın müxtəlif yerində ondan istifadə edə bilər. Hər dəfə eyni məlumatları yazmağa ehtiyac qalmadan.
>
> Bizim APı snearimizdə `parameters` və `responses` obyekti üzrə detalları `components` də daxlayacağıq.

> Parametrlərinizin təfərrüatlarını təsvir etmək və mürəkkəb response scheme sxemini təsvir etmək OpenAPI spesifikasiyasının ən çətin aspektləri ola bilər.&#x20;
>
> `parameters` və `responses` birbaşa `parameters` və `responses` obyektlərində müəyyən edə bilsəniz də, adətən iki səbəbə görə onları siyahıya salmırsınız:
>
> * Bu definitions hissələrini digər requests və ya responses yenidən istifadə etmək istəyə bilərsiniz. API-də bir neçə yerdə eyni parametr və ya response istifadə etmək adi haldır. `components` obyekti vasitəsilə OpenAPI sizə eyni definitions bir neçə yerdə təkrar istifadə etməyə imkan verir.
> * You might not want to clutter up your `paths` object with too many parameter and response details, since the `paths` object is already somewhat complex with several levels of objects.
> * Siz `paths` obyektinizi həddən artıq çox parameter və response təfərrüatları ilə qarışdırmaq istəməyə bilərsiniz, çünki `paths` obyekti artıq bir neçə səviyyəli obyektlərlə bir qədər mürəkkəbdir.
>
> Daha mürəkkəb sxemlər üçün (və ya bir neçə əməliyyatda və ya `paths` da yenidən istifadə olunan sxemlər üçün) requests və responses üçün sxemi `paths` obyektində siyahıya almaq əvəzinə, adətən siz [reference object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#referenceObject) dən (referenced with `$ref`) xüsusi [`components` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#componentsObject) definitina müraciət etmək üçün istifadə edirsiniz (For more details on `$ref`, see [Using $ref](https://swagger.io/docs/specification/using-ref/).)
>
>

> Think of the `components` object like a document appendix where the re-usable details are provided. If multiple parts of your spec have the same schema, you point each of these references to the same object in your `components` object, and in so doing you single source the content. The `components` object can even be [stored in a separate file](http://apihandyman.io/writing-openapi-swagger-specification-tutorial-part-8-splitting-specification-file/) if you have a large API and want to organize the information that way. (However, with multiple files, you wouldn’t be able to use the online Swagger Editor to validate the content.)

### Objects in components

You can store a lot of different re-usable objects in the `components` object. The [`components` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#componentsObject) can contain these objects:

* [`schemas`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#schemaObject)
* [`responses`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#responses-object)
* [`parameters`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#parameterObject)
* [`examples`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#examples-object)
* [`requestBody`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#requestBodyObject)
* [`headers`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#headerObject)
* [`securitySchemes`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#securitySchemeObject)
* [`links`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#linkObject)
* [`callbacks`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#callbackObject)

> `components` daxilindəki hər bir obyektin properties OpenAPI spesifikasiyasının digər hissələrində eyni formada istifadə edilir. Bunun reference işarəsindən (`$ref`) istifadə olunaraq `components` obyektinə istinad edilir. `$ref` stands for [`reference` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#referenceObject) and is part of JSON.
>
>

### Re-using parameters across multiple paths

> Bundan əvəvlki stepdə biz bütün parametrləri birbaşa olaraq `parameters` obyektinin daxilində yaratmışdır. Eyni parametrlərin digər paths da təkrar istifadəsi üçün `parameters`  `components` saxlayaq.

Replace the existing `paths` object in the Swagger Editor with the above code sample, include the new `components` object, and observe that the rendered display still looks the same.

<details>

<summary>Re-using parameters</summary>

```
openapi: 3.0.3
info:
  title: Travelpayouts API
  version: v3
  description: "Aviasales Data API — the way to get travel insights for your site or blog. Get flight price trends and find popular destinations for your customers. <p> 
  
    Data is transferred from the cache, which is formed on the basis of searches of users of sites Aviasales for the last 48 hours. So it is recommended that you use them to generate static pages. <p>
  
    For developers, documentation is available with examples of requests and answers in various programming languages, as well as a link to Postman.<p>

    >**Please note**: *API methods use limits, which are described in the article API rate limits.*<p>

  This documentation is for the public Aviasales API of the same name.
    To access the API, you must pass your `token` in the `X-Access-Token header` or in the token parameter. To obtain a  token for the Data Access API, go to the [Dashboard](https://www.travelpayouts.com/programs/100/tools/api)"
  license: 
    name: "License (MIT, Apache 2.0, etc): Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) License"
    url: https://creativecommons.org/licenses/by-sa/4.0/'
  termsOfService: "https://support.travelpayouts.com/hc/en-us/articles/360004162111-Terms-of-the-Travelpayouts-Travel-Affiliate-Network"
  contact:
    name: "Travelpayouts support"
    url: https://support.travelpayouts.com/hc/en-us
    email: someone@gmail.com
servers:
  - url: "https://api.travelpayouts.com/aviasales/v3/"
    description: "Production Server"
  - url: "https://test.travelpayouts.com/aviasales/v3/"
    description: "Test server"
paths:
  /prices_for_dates:
    get:
      tags: 
      - Flight
      summary: Get the cheapest ticket
      description: Get the cheapest ticket by date
      operationId: get-prices_for_dates
      parameters:
        - $ref: '#/components/parameters/currency'
        - $ref: '#/components/parameters/departure_at'
        - $ref: '#/components/parameters/return_at'
        - $ref: '#/components/parameters/direct'
        - $ref: '#/components/parameters/limit'
        - $ref: '#/components/parameters/market'
        - $ref: '#/components/parameters/page'
        - $ref: '#/components/parameters/origin'
        - $ref: '#/components/parameters/sorting'
        - $ref: '#/components/parameters/unique'


      #externalDocs:
      
          
      responses:
        200:
          description: Successful response
          content:
            application/json:
              schema:
                title: Sample
                type: object
                properties:
                  placeholder:
                    type: string
                    description: Placeholder description

        404:
          description: Not found response
          content:
            text/plain:
              schema:
                title: Weather not found
                type: string
                example: Not found


components:
  parameters:
    currency:
      name: currency
      in: query
      description: "The currency of **prices**"
      schema:
        type: string
        default: "RUB"
    
    departure_at:  
      name: departure_at
      in: query
      description: "The departure date"
      schema:
        type: string
  
    return_at:
      name: return_at
      in: query
      description: "Non-stop tickets"
      schema:
        type: string      
  
    direct:
      name: direct
      in: query
      description: "The return date. For one-way tickets do not specify it"
      schema:
        type: boolean 
     
    limit:  
      name: limit
      in: query
      description: "The total number of records on a page `max 1000`"
      schema:
        type: integer
        default: 30
  
    market:
      name: market
      in: query
      description: "Sets the market of the data source"
      schema:
        type: string
        default: ru
   
    page:
      name: page
      in: query
      description: "A page number, is used to skip some massive of results. For example, if we want to get the entries from `100 to 150`, we need to `set page=3`, and `limit=50`"
      schema:
        type: string
      
    origin:
      name: origin
      in: query
      description: "[An IATA code](https://www.nationsonline.org/oneworld/IATA_Codes/airport_code_list.htm#:~:text=The%20International%20Air%20Transport%20Association's,it%2C%20New%20York's%20John%20F.) of a city or an airport of the origin"
      schema:
        type: string
  
    sorting:
      name: sorting
      in: query
      description: "The assorting of prices"
      schema:
        type: string
        enum: [price, route]
        default: price
      
    unique:
      name: unique
      in: query
      description: "Returning only unique routes, if only origin is specified, `true` or `false`"
      schema:
        type: boolean
        default: false
```

</details>

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
If you get stuck, see the [sample OpenAPI spec here](https://idratherbewriting.com/learnapidoc/docs/openapi\_spec\_and\_generated\_ref\_docs/openapi\_openweathermap.yml) for the fully working sample. This will help you spot and troubleshoot indentation or other errors.
{% endhint %}

###

> \
> 4-cü addımda path obyektin izah edərkən biz responses obyektini path obyekti kimi təsvir etdik hətta sadə formada ora response artırdıq.we used a [`schema`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#schemaObject) object to describe the model for the request or response. The `schema` refers to the data structure (the fields, values, and hierarchy of the various objects and properties of a JSON or YAML object — see [What is a schema?](https://spacetelescope.github.io/understanding-json-schema/about.html#what-is-a-schema)).

> Gəlin indi detallı baxaq ki `responses` obyektində scheme properties necə işləyir. Biz həmçinində bu məlumatları `componenets` də saxlayacağıq və sənədin digər yerlərində istifadə etmək mümkün olacaq. Əgər 4 cü addıma baxsaq bizim ordakı nümunə `response` bu formada görünürdü

```
paths:
  //prices_for_dates:
    get:
      parameters:

      ...

      responses:
        200:
          description: Successful response
          content:
            application/json:
              schema:
                title: Sample
                type: object
                properties:
                  placeholder:
                    type: string
                    description: Placeholder description

        404:
          description: Not found response
          content:
            text/plain:
              schema:
                title: Weather not found
                type: string
                example: Not found

```

Now let’s move the `schema` description for the `200` response into the `components` object:

<figure><img src=".gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

Then in `components/schemas`, we’ll define the `200` schema.

Before we describe the response in the `components` object, it might be helpful to review what the `weather` response from the OpenWeatherMap API looks like. The JSON response contains multiple nested objects at various levels.

```json
{
    "success": true,
    "data": [
        {
            "origin": "BAK",
            "destination": "IST",
            "origin_airport": "GYD",
            "destination_airport": "SAW",
            "price": 8777,
            "airline": "",
            "flight_number": "7703",
            "departure_at": "2023-03-26T05:15:00+04:00",
            "transfers": 0,
            "return_transfers": 0,
            "duration": 185,
            "link": "/search/BAK2603IST1?t=TK16797933001679804400000185GYDSAW_772e0eb34e7755ce3c2a74565fa76f90_143&search_date=01112022&expected_price_uuid=ac8a8c14-d565-45c2-b959-8ecb2bc80587&expected_price_currency=usd"
        }
    ],
    "currency": "rub"
}
```

> Responsu təsvir etmək üçün bir neçə yol vardır. Siz ierarxiya ilə uzun təsvir düzəldə bilərsiniz . Bu varaintlardan biridir amma bütün səviyyələri düzgün formada nizamlamaq çətindir. Çünki çoxlu nested obyektlər olanda bu dah da çətinləşəcəkdir. Həmçinin də səhv etmək çox asan olur.  Ən pisi isə siz bundan yenidən istifadə edə bilmirsiz (yəni referens). This undercuts one of the main reasons for storing this object in `components` in the first place.
>
> Digər yanaşma isə hər bir obyekt üçün `components` öz enetitisin yaratmaqdır. Hər hansı obyekt nested olduqda obyektin içində obyekt olduqda `$ref` əlavə edərək  onu yeni obyektə yönəltmək olar. Beləliklə, obyektlər saadə qalır (çox səviyyəli nesting olmaq əvəzinə) və siz qarışıq alt səviyyələr dənizində itməyəcəksiniz. (Əgər alt obyekt yoxdursa, $ref istifadə etmədən təsviri birbaşa təqdim edə bilərsiz).
>
> Burada `200` response descriptionu price\_for\_date göstərmişəm. Həmçinin də `paths` tag əlavə edəərk ümumi kontektsi saxlamışam\
> ``

**Responses object with components documentation:**

<details>

<summary>Response scheme</summary>

```
openapi: 3.0.3
info:
  title: Travelpayouts API
  version: v3
  description: "Aviasales Data API — the way to get travel insights for your site or blog. Get flight price trends and find popular destinations for your customers. <p> 
  
    Data is transferred from the cache, which is formed on the basis of searches of users of sites Aviasales for the last 48 hours. So it is recommended that you use them to generate static pages. <p>
  
    For developers, documentation is available with examples of requests and answers in various programming languages, as well as a link to Postman.<p>

    >**Please note**: *API methods use limits, which are described in the article API rate limits.*<p>

  This documentation is for the public Aviasales API of the same name.
    To access the API, you must pass your `token` in the `X-Access-Token header` or in the token parameter. To obtain a  token for the Data Access API, go to the [Dashboard](https://www.travelpayouts.com/programs/100/tools/api)"
  license: 
    name: "License (MIT, Apache 2.0, etc): Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) License"
    url: https://creativecommons.org/licenses/by-sa/4.0/'
  termsOfService: "https://support.travelpayouts.com/hc/en-us/articles/360004162111-Terms-of-the-Travelpayouts-Travel-Affiliate-Network"
  contact:
    name: "Travelpayouts support"
    url: https://support.travelpayouts.com/hc/en-us
    email: someone@gmail.com
servers:
  - url: "https://api.travelpayouts.com/aviasales/v3/"
    description: "Production Server"
  - url: "https://test.travelpayouts.com/aviasales/v3/"
    description: "Test server"
paths:
  /prices_for_dates:
    get:
      tags: 
      - Flight
      summary: Get the cheapest ticket
      description: Get the cheapest ticket by date
      operationId: get-prices_for_dates
      parameters:
        - $ref: '#/components/parameters/currency'
        - $ref: '#/components/parameters/departure_at'
        - $ref: '#/components/parameters/return_at'
        - $ref: '#/components/parameters/direct'
        - $ref: '#/components/parameters/limit'
        - $ref: '#/components/parameters/market'
        - $ref: '#/components/parameters/page'
        - $ref: '#/components/parameters/origin'
        - $ref: '#/components/parameters/sorting'
        - $ref: '#/components/parameters/unique'
      #externalDocs:
      responses:
        "200":
          description: Successful response
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/200'
        "404":
          description: Not found response
          content:
            text/plain:
              schema:
                title: Weather not found
                type: string
                example: Not found


components:
  parameters:
    currency:
      name: currency
      in: query
      description: "The currency of **prices**"
      schema:
        type: string
        default: "RUB"
    
    departure_at:  
      name: departure_at
      in: query
      description: "The departure date"
      schema:
        type: string
  
    return_at:
      name: return_at
      in: query
      description: "Non-stop tickets"
      schema:
        type: string      
  
    direct:
      name: direct
      in: query
      description: "The return date. For one-way tickets do not specify it"
      schema:
        type: boolean 
     
    limit:  
      name: limit
      in: query
      description: "The total number of records on a page `max 1000`"
      schema:
        type: integer
        default: 30
  
    market:
      name: market
      in: query
      description: "Sets the market of the data source"
      schema:
        type: string
        default: ru
   
    page:
      name: page
      in: query
      description: "A page number, is used to skip some massive of results. For example, if we want to get the entries from `100 to 150`, we need to `set page=3`, and `limit=50`"
      schema:
        type: string
      
    origin:
      name: origin
      in: query
      description: "[An IATA code](https://www.nationsonline.org/oneworld/IATA_Codes/airport_code_list.htm#:~:text=The%20International%20Air%20Transport%20Association's,it%2C%20New%20York's%20John%20F.) of a city or an airport of the origin"
      schema:
        type: string
  
    sorting:
      name: sorting
      in: query
      description: "The assorting of prices"
      schema:
        type: string
        enum: [price, route]
        default: price
      
    unique:
      name: unique
      in: query
      description: "Returning only unique routes, if only origin is specified, `true` or `false`"
      schema:
        type: boolean
        default: false
        
  schemas:
    "200":
      title: Successful response
      type: object
      properties:
        success:
          type: boolean
          description: Success request
          example: true
        data:
          type: array
          items:
            $ref: '#/components/schemas/Data'
          description: (more info Weather condition codes)
    Data:
      title: Data
      type: object
      properties:
        trip_class:
          type: string
          enum: ["0","1","2"]
          description: "the flight class: `0 — Economy class` `1 — Business class` `2 — First`"
        depart_date:
          type: string
          description: "the date of departure"
          example: 12-03-2022
        value:
          type: string
          description: "the cost of a flight, in the **currency specified**"
          
        
          
```

</details>

> Növbəti bölmədə response fieldləri və responsu necə təsvir etmək lazımdır onu görəcəyik. Bu nümunədən siz gördünüz ki `$ref` properties spesifikasiyanız fərqli yerində işlətmə yanaşı componenets bölməsindədə işlədə bilirsiz.

{% hint style="info" %}
Notice how the schema definition includes an `example` property for each element? Swagger UI will take this `example` and use it to dynamically build a full code sample in the Responses section in the Swagger UI output. Thus, you don’t need big chunks of code for the sample responses in your spec. Instead, these sample responses get built automatically from the schema. It’s one of the neat things about Swagger UI. This way, your schema documentation and sample response remain consistent.
{% endhint %}

### Describing a schema

\


These [data types](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#data-types) are also available:

* `integer`
* `long`
* `float`
* `double`
* `string`
* `byte`
* `binary`
* `boolean`
* `date`
* `dateTime`
* `password`

When you start documenting your own schema, start by looking in the OpenAPI’s [schema object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#schemaObject), and then consult the [JSON Schema](https://tools.ietf.org/html/draft-wright-json-schema-00) if something isn’t covered.\


Additionally, look at some example schemas. You can view [3.0 examples here](https://github.com/OAI/OpenAPI-Specification/tree/master/examples/v3.0). I usually find a spec that resembles what I’m trying to represent and mimic the same properties and structure.

### A way to cheat – automatically generate the schema from JSON using Stoplight

Describing a JSON response can be complicated and confusing. Fortunately, there’s a somewhat easy workaround. To be honest, this is the approach I use when I’m documenting JSON responses. With the Stoplight Studio Editor, you can automatically generate the specification schema syntax from a sample response. Bundan əvvəl Stoplightda buna baxmışdır.



### Using GUI editors to work with the specification code

At this point, you’re probably thinking how impractical and error-prone it’s going to be as you work directly in the YAML code like this. For this reason, several companies have developed GUI editors to make it easier to work with the specification code. In particular, check out [Stoplight](https://idratherbewriting.com/learnapidoc/pubapis\_stoplight.html), which provides an editor that lets you toggle between code and a GUI display. Smartbear also offers [SwaggerHub](https://idratherbewriting.com/learnapidoc/pubapis\_swaggerhub\_smartbear.html), which doesn’t necessarily provide a GUI but which gives you inline commenting and versioning tools

### View the Appearance in Swagger UI

In the Response section, observe how the Example Value code has been dynamically built from the `example` values in the schema to show a sample response.

Also, click the **Model** link to see how the descriptions of each element appear in an expandable/collapsible way:

> Response bölməsinə nəzər salıb example value-ların necə göründüyünə baxaq. Həmçinin də Model ə klik edərək hər bir element üzrə açılan bağlanan görünüşdə dəyərləri görə bilərik.

![](<.gitbook/assets/image (1).png>)

>

### The Models section – why it exists, how to hide it

\
You’ll also notice another “Models” section below all the other paths:

![](https://lh6.googleusercontent.com/8UzOtjzirtc3QHwXm3cGeVCQ0hWkVWjFcibtxbTif8pONl1f9bvetrKTr1bV6NBy1nHxUsTqU9IEsDM4sEkx7a3ggEZnjwV3Fzuao\_3D4lXOoTSTUGSiS0BPjuYfy0VPClhFw-VbEbJ6UUq4JxHgZR3m8WdEV7rugijg8DE5Utza\_gAzkgm5XrEl19ty7\_tE4i4)

By default, Swagger UI displays each object in `components` in a section called “Models” at the end of your Swagger UI display. If you consolidate all schemas into a single object, without using the `$ref` property to point to new objects, you will see just one object in Models. If you split out the objects, then you see each object listed separately, including the object that contains all the references.

Because I want to re-use objects, I’m going to define each object in `components` separately. As a result, the Models section looks like this:

Why is there a Models section here? Apparently, it was added by popular request because the online Swagger Editor showed the display, and many users asked for it to be incorporated into Swagger UI.

You don’t need this Models section in Swagger UI because both the request and response sections of Swagger UI provide a “Model” link that lets the user toggle to this view.

To hide the Models section, you can add the parameter `defaultModelsExpandDepth: -1` parameter in your Swagger UI project. I provide a [Swagger UI tutorial](https://idratherbewriting.com/learnapidoc/pubapis\_swagger.html#create\_swaggerui) in an upcoming section in this course, with details about the [Swagger UI parameters](https://github.com/swagger-api/swagger-ui/blob/master/docs/usage/configuration.md#parameters) where you could configure this parameter.

### Security definitions

> `components` obyektinə həmçinin də hər bir path üzrə avtorizaisya metodunu təyin edən [`securitySchemes` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#securitySchemeObject) də daxildir. Bu mövzuda danışmaq çox olar deyə onu növbəti bölmədə danışacam.

\


\
\


\


\


> Replace the existing `paths` object in the Swagger Editor with the above code sample, include the new `components` object, and observe that the rendered display still looks the same.
>
> Mövcud `paths` obeyktini Üvagger Editorda kodda göstərilən nümunə ilə əvəz edək və `components`  obyektin əlavə edək. Görəcəyik ki, nəticə eyni oldu.

{% hint style="info" %}
If you get stuck, see the [sample OpenAPI spec here](https://idratherbewriting.com/learnapidoc/docs/openapi\_spec\_and\_generated\_ref\_docs/openapi\_openweathermap.yml) for the fully working sample. This will help you spot and troubleshoot indentation or other errors.
{% endhint %}
