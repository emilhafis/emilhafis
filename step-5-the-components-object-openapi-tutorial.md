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

```yaml
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

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
If you get stuck, see the [sample OpenAPI spec here](https://idratherbewriting.com/learnapidoc/docs/openapi\_spec\_and\_generated\_ref\_docs/openapi\_openweathermap.yml) for the fully working sample. This will help you spot and troubleshoot indentation or other errors.
{% endhint %}



\


\


\
