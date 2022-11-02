# Step 4: The paths object (OpenAPI tutorial)

The [`paths` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#pathsObject) contains the meat of your API information. The `paths` object has several sub-objects: a [path items object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#pathItemObject), an [operations object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#operationObject), and more.

{% hint style="info" %}
Əvvəlki 3 mövzunu asta keçdik və bütün obyektlər ilə tanış olduq. Burada isə sürətli keçəcəyik. İlk dəfədən başa düşməsəniz problem yoxdur, hazır mən təqdim etdiyim kod üzərində işləyərsiniz və sonra lazım olduqda geriq ayıdıb baxarsınız.

Hər zaman hər şeyi yadda saxlamaq yox nəyi haradan tapacağınızı bilmək önəmlidir.
{% endhint %}

### Paths objects

> Bu bizim bildiyimiz endpointdir. open API spesifikasiyasında endpoint path adlandırılır deyə burada da Path deyəcəyik.

> `path`  obeykti daxilindəki Path item obyektləri  daxilinə HTTP metodları da daxildir.  (GET, POST, Delete və PUt haqqında bundan əvvəlki mövzuda danışmışıq)  &#x20;
>
> Gəlin indi, path endpoint) qeyd edib onlar üzrə metodu təyin edək. Flight endpoint i üçün bir path-a (/[prices\_for\_dates](https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates?origin=string\&destination=BCN\&departure\_at=string\&return\_at=string\&unique=false\&sorting=price\&direct=false\&currency=rub\&limit=30\&page=1\&one\_way=true\&token=PutYourTokenHere)) baxmışdıq. Və bunun metodu `GET` idi.

```
paths:
  /prices_for_dates:
    get:
```

> The operation object (`get` in the code above) contains various properties and objects:
>
> Yuxarıda göstərilən **get** üzrə operation obyektlər bir neçə xassədən və obyektlərdən ibarətdir.&#x20;
>
> * `tags`:  Endpointləri qruplaşdırmaq üçün istifadə edilir. Yadınızdadırsa Stoplight da demişdim. Svagge Uİ təyin etdiyiniz tag altında endpointləri quruplaşdırır
> * `summary`: path üzrə qısa təsvir. Svagger UI təsviri path in yanında göstərir. Təsvir üçün limit 5-10 sözdən ibarət olmaldıır. Çalışın qısa və lokanik edin. Təsvir endpointlər collapse olduqda belə görünür
> * `description`: path üzrə tam təsvir. Burada artıq detallı məlumat yaza bilərsiniz. Svagger Uİ də description üçün kifayət qədər yer olur. Burada həmçinində Markdown dili dəstəklənir.
> * [`externalDocs`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#externalDocumentationObject) (object): path üzrə əlavə məlumat əldə etmək üçün, kənar sənədləşməyə link
> * `operationId`: path üzrə unikal id. Spesifikasiya daxilində
>
>
>
> * [`parameters`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#parameterObject) (object):  Əvvəlki mövzuda bildirdiyimiz kimi son versiyalarda Reqeust body parametr kimi nəzərə alınmadığından ayrıca obyekt kimi göstərilir. parametr obyketinə həmçinində [reference object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#requestBodyObject) daxildir və bu `components` object nə istnad edir (bu step 5 də izah ediləcək)
>
>
>
> * [`requestBody`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#requestBodyObject) (object): path üçün request body detalları. `requestBody` obyektinə də həmçinin compnenet obyektinə istinad edən r[eference object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#referenceObject) daxildir. (You can find an example of a `requestBody` parameter in the [Swagger Petstore demo](https://petstore.swagger.io/#/pet/addPet). The `/pet` endpoint submits a request body when adding a pet. Check out the `requestBody` YAML syntax in [petstore-expanded.yml](https://github.com/OAI/OpenAPI-Specification/blob/master/examples/v3.0/petstore-expanded.yaml) — look at `post` under `/pets`. Also see [Describing Request Body](https://swagger.io/docs/specification/describing-request-body/).)
>
>
>
> * [`responses`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#responsesObject) (object): Request nəticəsində qayıdan Responsu göstərir. Response obyektinə də reference obyekti daxildir. Response standart status codelarından istifadə edir. [status codes](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#http-status-codes).&#x20;
>
>
>
> * [`callbacks`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#callbackObject) (object): Callback details to be initiated by the server if desired. Callbacks are operations performed after a function finishes executing. The `callbacks` object can also include a [reference object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#referenceObject) that contains a pointer to the description in the `components` object.
>
>
>
> * `deprecated`: Whether the path is deprecated. Omit unless you want to indicate a deprecated field. Boolean. path artıq müxtəlif səbəblərdən istifadəyə yararsız. Əgər bu fieldi mütləq göstərmək istəyirsənizsə və path işləkdirsə onda dəyərin false edin
>
>
>
> * [`security`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#securityRequirementObject) (object): Security authorization method used with the operation. Include this object at the path level only if you want to overwrite the `security` object at the root level. The name is defined by the `securitySchemes` object in the `components` object. More details about this are provided in the [security object](https://idratherbewriting.com/learnapidoc/pubapis\_openapi\_step6\_security\_object.html).
> *
> * [`servers`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#serverObject) (object): Server obyketi global server obyektindən fərqli olduqda qeyd edilir. Yadınızdadırsa 3 cü addımda bildirdimki hə rendpoint üzrə server fərqli ola bilər.
>
>
>
> Göstərilən hyperlinkli olanlar obyektlər dir. yəni onlar daxilində fieldlər olur. Onların dəyərləri sadə string deyir, hər xassəsəinə uyğun məlumatlar təşkil edir.

{% hint style="warning" %}
You’ll undoubtedly need to consult the [OpenAPI spec](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md) to see what details are required for each of the values and objects here. I can’t replicate all the details you need, nor would I want to. I’m just trying to introduce you to the OpenAPI properties at a surface level.
{% endhint %}

> Gəlin bu obyektləri məlumatların kodumuza əlavə edək\
>

```yaml
paths:
  /weather:
    get:
      tags:
      summary:
      description:
      operationId:
      externalDocs:
      parameters:
      responses:
      deprecated:
      security:
      servers:
      requestBody:
      callbacks:
```

{% hint style="info" %}
At this point, if you paste this content into the Swagger Editor, you will get errors until some additional properties are added.
{% endhint %}

> Now we can remove a few unnecessary fields that we don’t need for our OpenWeatherMap API documentation:
>
> Bizim travel API mız üçün lazım olmayan bir necə fieldi çıxaraq
>
> * &#x20;[`requestBody` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#requestBodyObject)  daxil etməyə ehtiyac yoxdur çünki API mızda request body yoxdur sorğulara path parametrləri ilə alınır
> * [`servers` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#serverObject) daxil etməyə ehtiyac yoxdur çünki bizim bir server URL miz var və biz onu Global mənimsətmişik
> * [security](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#securityRequirementObject) obyektindəndə həmçinin, bütün path larimiz üçün eyni formaları təhlükəzilik olacaq. biz bunu növbəti stepdə baxacağıq. Deyə bilərsinizmi travel də avtorizaisya necə həyata keçirdi? Hamı şəxsiyə yazsın
> * endpintimiz işlək olduğu üçün depreciated lazım deyik
> * `callbacks` istifadə edirikmi burda? Lazım deyil
> * Nəticədə aşağıdakı fieldlər qaldı:

```yaml
paths:
  /prices_for_dates:
    get:
    tags:
    summary:
    description:
    operationId:
    externalDocs:
    parameters:
    responses:
```

> Operation obyektinin bir çox obyekti ya sadə string istəyir ya da nested obyekt olaraq öz daxilində bir neçə sadə field yazılmasın tələb edir.&#x20;
>
> Burada ən detallı nested obyektlər  [`parameters` object](https://idratherbewriting.com/learnapidoc/pubapis\_openapi\_step4\_paths\_object.html#parameters) and the [`responses` object](https://idratherbewriting.com/learnapidoc/pubapis\_openapi\_step4\_paths\_object.html#responses).

### **Parameters object**

> The [`parameters` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#parameterObject) array olmaqla aşağıdakı fieldlərdən ibarətdir:
>
> * `name`: Parameter adı.
> * `in`: Where the parameter appears. Possible values are `header`, `path`, `query`, or `cookie`. (Request bodies are not described here.)
> * `description`: Description of the parameter.
> * `required`: Whether the parameter is required.
> * `deprecated`: Whether the parameter is deprecated.
> * `allowEmptyValue`: Boş dəyər göndərməyə imkan verir yoxsa yox, onu təyin edir
> * `style`: Məlumatların göndərilməsi zamanı onların byte-lara çevrildiyi bilmək üçün istifadə edilir. Bu çox nadir halda qarşınıza çıxacaqdır
> * `explode`: Advanced parameter related to arrays.
> * `allowReserved`: Whether reserved characters are allowed.
> * [`schema`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#schemaObject) (object): The schema or model for the parameter. The schema defines the input or output data structure. Note that the `schema` can also contain an `example` object.
> * `example`: An example of the media type. If your `examples` object contains examples, those examples appear in Swagger UI rather than the content in the `example` object.
> * [`examples`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#exampleObject) (object): An example of the media type, including the schema.
>
> Here’s the `paths` object that includes the `parameters` details:

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
      #externalDocs:
      parameters:
      - name: currency
        in: query
        description: "The currency of **prices**"
        schema:
          type: string
          default: "RUB"
          
      - name: departure_at
        in: query
        description: "The departure date"
        schema:
          type: string
      
      - name: return_at
        in: query
        description: "Non-stop tickets"
        schema:
          type: string      
 
      - name: direct
        in: query
        description: "The return date. For one-way tickets do not specify it"
        schema:
          type: boolean 
          
      - name: limit
        in: query
        description: "The total number of records on a page `max 1000`"
        schema:
          type: integer
          default: 30
 
      - name: market
        in: query
        description: "Sets the market of the data source"
        schema:
          type: string
          default: ru
 
      - name: page
        in: query
        description: "A page number, is used to skip some massive of results. For example, if we want to get the entries from `100 to 150`, we need to `set page=3`, and `limit=50`"
        schema:
          type: string
          
      - name: origin
        in: query
        description: "[An IATA code](https://www.nationsonline.org/oneworld/IATA_Codes/airport_code_list.htm#:~:text=The%20International%20Air%20Transport%20Association's,it%2C%20New%20York's%20John%20F.) of a city or an airport of the origin"
        schema:
          type: string

      - name: sorting
        in: query
        description: "The assorting of prices"
        schema:
          type: string
          enum: [price, route]
          default: price
          
      - name: unique
        in: query
        description: "Returning only unique routes, if only origin is specified, `true` or `false`"
        schema:
          type: boolean
          default: false


```

{% hint style="info" %}
If you get stuck, see the [sample OpenAPI spec here](https://idratherbewriting.com/learnapidoc/docs/openapi\_spec\_and\_generated\_ref\_docs/openapi\_openweathermap.yml) for the fully working sample. This will help you spot and troubleshoot indentation or other errors.
{% endhint %}

**Responses object**

> Digər operation obyektində əhəmiyyətli property [`responses` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#responsesObject). Response property üçün siz demək olar ki,  componenets obyektinə istinad edirsiniz. Biz response a 5-ci addında baxacağıq, çünki bu addımda çox məlumat oldu.
>
> Hazırda Svagerrin yazdığımız code validate etməsi və error olmaması üçün example response əlavə edək

```yaml
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

See [Describing Parameters](https://swagger.io/docs/specification/describing-parameters/) in Swagger’s OpenAPI documentation for more details.

### Paths object code

Now let’s combine the above two code blocks (both `parameters` and `responses`) for our `paths` object. You can paste the following code into the Swagger Editor — add this `paths` object below the `openapi`, `info`, and `servers` code you added in the previous tutorials.\


### &#x20;View the Appearance in Swagger UI

Swagger UI displays the `paths` object like this:

\


<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

> Expand the Current Weather Data section to see the details. When you click **Try it out**, you’ll notice that the field populates with the description. If you want the field to populate with a value, add a `default` property under `schema` (as shown with the `mode` parameter in the code above).
>
> However, with this API, the parameters can’t all be passed with the same request — you use only the parameters you want for the request you’re making. (For example, you can’t pass zip code _and_ city name _and_ lat/long, etc. in the same request.) As a result, it wouldn’t make sense to use defaults for each parameter because the user would then need to remove most of them.

{% hint style="info" %}
Swagger’s UI collapses each path by default. You can set whether the initial display is collapsed or open using the [`docExpansion` parameter in Swagger UI](https://github.com/swagger-api/swagger-ui#parameters). This `docExpansion` parameter is for Swagger UI and not part of the OpenAPI spec. Swagger UI has more than [20 different parameters](https://github.com/swagger-api/swagger-ui#parameters) of its own that control the display. For example, if you don’t want the `Models` section to appear, add the parameter `defaultModelsExpandDepth: -1` in your Swagger UI file.
{% endhint %}

### Note about parameter dependencies

\
The OpenAPI specification doesn’t allow you to declare dependencies with parameters, or mutually exclusive parameters. According to the Swagger OpenAPI documentation,

> OpenAPI 3.0 does not support parameter dependencies and mutually exclusive parameters. There is an open feature request at [https://github.com/OAI/OpenAPI-Specification/issues/256](https://github.com/OAI/OpenAPI-Specification/issues/256). What you can do is document the restrictions in the parameter description and define the logic in the 400 Bad Request response. ([Parameter Dependencies](https://swagger.io/docs/specification/describing-parameters/#parameter-dependencies-19))

In the case of the weather endpoint with the OpenWeatherMap, most of the parameters are mutually exclusive. You can’t search by City ID _and_ zip code simultaneously. Although the parameters are optional, you must use at least one parameter. Also, if you use the `lat` parameter, you must also use the `lon` parameter because they’re a pair. The OpenAPI spec can’t programmatically reflect that structured logic, so you have to explain it in the `description` property or in other more conceptual documentation.

\


>

### &#x20;
