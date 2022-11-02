# Step 1: The openapi object (OpenAPI tutorial)

Ümumi olaraq bildirim ki, bizim Open API mövzumuz aşaıdakı məsələlərə görə unikaldır.

* Burada bizə əvvəldən tanış olan Travel API ları üzrə Open API konteksti ilə tanış olacaqğıq
* Yenə də bizə tanış olan platofmralarda (Stoplight və Svagger Uİ) də Open API necə hazırlanır ona baxacağıq
* Bizim mövzumuz Open API speki üzrə bütün bölmələri əhatə etmir. Yalnız lazımlı hissələri əlavə etmişəm.
* Bizim mövzumuz hazırda ən çox istifadə olunan və Svagger tərəfindən ən sonuncu versiya kimi təsdiqlənən 3.0 Open API specin əhatə edir.&#x20;

### The root-level objects in OpenAPI spec <a href="#the-root-level-objects-in-openapi-spec" id="the-root-level-objects-in-openapi-spec"></a>

> Open API spesifikasiyanın nüvəsi 8 əsas obyektdən ibratədir. Bu obyektlərində daxilində bir neçə nested obyekt vardır amma əsas parent objectlər bunlardır.

* [`openapi`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#oasObject)
* [`info`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#infoObject)
* [`servers`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#serverObject)
* [`paths`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#pathsObject)
* [`components`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#componentsObject)
* [`security`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#securityRequirementObject)
* [`tags`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#tagObject)
* [`externalDocs`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#externalDocumentationObject)

> "root level" dedikdə mən Open API spesifikasiyanın əsas səviyyələrin nəzərdə tuturam. Bu levellər həmçinin də Global level adlanır (əgər fikir vermisinizsə Stoplight da vardır), çünki bəzi object lər burada qeyd olunur (məsələn `servers` və `security)` və bütün obyketlərə şamil olunur (əgər aşağı səviyyədə başqası qeyd edilməyibsə.

> Bütün spesifikasiya (yəni bu 8 root level obyektlərdən ibarət olan) [OpenAPI documen](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#oasDocument) adlanır. Fayl extension isə yaml məsələn openapi.**yaml** adlandırılır.

{% hint style="info" %}
Yadınızda saxlayın - OpenAPI spesifikasiyaya istinad edir, “Swagger” Open API spesifikasiyanı dəstəkləyən və onun üzərində işləri görməyə imkan verən tool və ya platformadır və SmartBear kompaniyası tərəfindən idarə edilir.
{% endhint %}

> OpenAPI sənədi üzrə dərsliyi bir çox varaintda hazırlamaq olar. Mən qedy etdiyim root level obyektləri əsasında bu dərsliyi hazırlamışam.&#x20;
>
> Siz burada iki yanaşma əsasında izah görəcəksiz
>
> 1. Kod səviyyəsində işləyən Swagger-dən,&#x20;
> 2. digəri isə istifadəçi interfeysində işləyən Stoplight Studio-dan istifadə .

### Swagger <a href="#swagger" id="swagger"></a>

> Kodlaşdırmaya keçməmişdən əvvəl, baxaki kodlaşdırmanı harada edəcəksiniz və nə kimi seçiləriniz vardır
>
>

#### Where to write your spec code

> Kodlaşırmanın ən sadə yolu online [Swagger Editor](https://swagger.io/swagger-editor/) istifadə etməkdir. Swagger Editor split viyu təqdim edir, yəni sol tərəfdə kodlaşdırma edirsinz və sağ tərəfdə yazdığınız kodun necə görünməsini real rejimdə izləyirsiniz. Hətta Displaydə dəyişiklik etdikdə kodda da bunun dərhal nəzərə alındığını görə bilərsiniz.

> &#x20;[Swagger Editor](https://swagger.io/swagger-editor/) yazdığınız kodu real vaxt rejimində yoxlayacaq və siz spesifikasiya sənədini kodlamağı bitirənə qədər xətalar varsa onları göstərəcəkdir. Üzərində işlədiyiniz kodda X işarələrini görməyincə xətalardan narahat olmayın. Çünki bir çox tövsiyyə xətalarıda qarşımıza çıxacaqdır.

> Mən adətən text editordan (Sublime Text kimi mətn redaktorundan istifadə etməklə) istifadə etməklə öz spesifikasiyamı komputerimdə saxlayıram. Amma onun üzərində işi online olaraq  [Swagger Editor](https://swagger.io/swagger-editor/) vasitəsilə edir. İşimi bitirdikdən sonra yenədə eyni qaydada kopyalayıb Sublime textdə saxlayıra.&#x20;
>
> Amma bir məsələnidə deyimki  [Swagger Editor](https://swagger.io/swagger-editor/) bizim spesifikasıyımızı brauzerin cach-də saxlayır. Siz cahsi təmizləmədikcə spesifikasıyımız orada qalacaqdır. &#x20;
>
> Əvvəl xatırlayırdınızsa demişdik ki Swagger HUB cloudda saxlay;r
>
> If you want to purchase a subscription to [SwaggerHub](https://idratherbewriting.com/learnapidoc/pubapis\_swaggerhub\_smartbear.html), you could keep your spec content in the cloud (SwaggerHub has an editor almost identical to Swagger UI) associated with your personal login. SwaggerHub is the premium tooling for the open-source and free Swagger Editor.

> Another option to work locally is to use [Visual Studio Code](https://code.visualstudio.com/) with two extensions: [openapi-lint](https://marketplace.visualstudio.com/items?itemName=mermade.openapi-lint) and [Swagger Viewer](https://marketplace.visualstudio.com/items?itemName=Arjun.swagger-viewer). These extensions let you work locally and preview a live version of Swagger. You can also download and run the [Swagger Editor locally](https://swagger.io/tools/swagger-editor/).

> Sadə və rahat olsun deyə biz bu dərslikdə online Swagger Editor dan istifadə edəcəyik

#### Add the openapi object

> From the [Swagger Editor](https://editor.swagger.io/) and go to **File > Clear editor**. Keep this tab open throughout the OpenAPI tutorial, as you’ll be adding to your specification document with each step.
>
> Add the first root-level property for the specification document: `openapi`. In the [openapi](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#oasObject) object, indicate the version of the OpenAPI spec to validate against. The latest version is `3.0.2`.

```yaml
openapi: "3.0.2"
```

> Until you add more information in here, you’ll see error messages and notes such as “No operations defined in spec!” To avoid these errors, add some placeholder info here like this:

```yaml
openapi: 3.0.2
info:
  title: Travelpayouts API
  version: v3
paths: {}
```

> The editor renders the display as follows.

![](<.gitbook/assets/image (2).png>)

Əgər çətinliyiniz olsa buradakı Yaml dan istifadə edərsiniz.

<details>

<summary>Travelpayouts.yaml</summary>

```yaml
openapi: 3.0.0
x-stoplight:
  id: 76s9h4g291j6r
info:
  title: Travelpayouts API
  version: '3'
  description: |-
    Returns the cheapest tickets for specific dates. This sample Swagger file covers the `current` endpoint only from the Travelpayouts API. <br/><br/>  
    > All parameters are optional, you must select at least `destination` or `origin` parameter. By default this endpoint retrieves **chepeast ticket**.
  contact:
    name: Support
    url: 'https://support.travelpayouts.com/'
    email: someone@gmail.com
  termsOfService: 'https://support.travelpayouts.com/hc/en-us/articles/360004162111-Terms-of-the-Travelpayouts-Travel-Affiliate-Network'
  license:
    name: 'License (MIT, Apache 2.0, etc): Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)'
    url: 'https://creativecommons.org/licenses/by-sa/4.0/'''
servers:
  - url: 'https://api.travelpayouts.com/aviasales/v3'
    description: Production
paths:
  /prices_for_dates:
    get:
      summary: Get the cheapest ticket
      tags:
        - Flight
      responses:
        '200':
          description: OK
          content:
            application/json:
              schema:
                type: object
                properties:
                  success:
                    type: boolean
                  data:
                    type: array
                    items:
                      type: object
                      properties:
                        origin:
                          type: string
                        destination:
                          type: string
                        origin_airport:
                          type: string
                        destination_airport:
                          type: string
                        price:
                          type: integer
                        airline:
                          type: string
                        flight_number:
                          type: string
                        departure_at:
                          type: string
                        return_at:
                          type: string
                        transfers:
                          type: integer
                        return_transfers:
                          type: integer
                        duration:
                          type: integer
                        link:
                          type: string
                x-examples:
                  Example 1:
                    success: true
                    data:
                      - origin: LON
                        destination: BCN
                        origin_airport: DME
                        destination_airport: BCN
                        price: 3001
                        airline: IO
                        flight_number: '675'
                        departure_at: '2022-01-21T22:30:00+03:00'
                        return_at: '2022-02-03T06:25:00+03:00'
                        transfers: 0
                        return_transfers: 0
                        duration: 175
                        link: /search/LON2101BCN03021?t=IO16427934001642798800000090DMEBCN16438587001643863800000085BCNVKO_9a6898092e218d1d1a374ecdd20a7fc6_3001&search_date=27122021&expected_price_uuid=bccbd9bf-69dc-49e2-a09b-c7bb6414fde5&expected_price_currency=rub
              examples:
                example-1:
                  value:
                    success: true
                    data:
                      - origin: LON
                        destination: BCN
                        origin_airport: DME
                        destination_airport: BCN
                        price: 3001
                        airline: IO
                        flight_number: '675'
                        departure_at: '2022-01-21T22:30:00+03:00'
                        return_at: '2022-02-03T06:25:00+03:00'
                        transfers: 0
                        return_transfers: 0
                        duration: 175
                        link: /search/LON2101BCN03021?t=IO16427934001642798800000090DMEBCN16438587001643863800000085BCNVKO_9a6898092e218d1d1a374ecdd20a7fc6_3001&search_date=27122021&expected_price_uuid=bccbd9bf-69dc-49e2-a09b-c7bb6414fde5&expected_price_currency=rub
      operationId: get-prices_for_dates
      description: ''
      parameters:
        - $ref: '#/components/parameters/currency'
        - schema:
            type: string
          in: query
          name: origin
          description: An IATA code of a city or an airport of the origin
        - schema:
            type: string
          in: query
          name: destination
          description: 'An IATA code of a city or an airport of the destination (if you don''t specify origin parameter, you must set destination)'
        - schema:
            type: string
            pattern: YYYY-MM or YYYY-MM-DD
          in: query
          name: departure_at
          description: 'the departure date '
        - schema:
            type: string
          in: query
          name: return_at
          description: the return date. For one-way tickets do not specify it
        - schema:
            type: boolean
            default: false
          in: query
          name: direct
          description: 'non-stop tickets, `true` or `false`'
        - schema:
            type: string
            default: ru
          in: query
          name: market
          description: sets the market of the data source
        - schema:
            type: string
            default: '30'
            maxLength: 1000
          in: query
          name: limit
          description: the total number of records on a page
        - schema:
            type: string
          in: query
          name: page
          description: 'a page number, is used to skip some massive of results. For example, if we want to get the entries from *100* to *150*, we need to set `page=3`, and `limit=50`'
        - schema:
            type: string
            enum:
              - price
              - route
            default: price
          in: query
          name: sorting
          description: 'the assorting of prices. <br/><br/>  *price* — by the price (the default value). For the directions, only city — city assorting by the price is possible <br/><br/>  *route* — by the popularity of a route.'
        - schema:
            type: boolean
            default: false
          in: query
          name: unique
          description: 'returning only unique routes, if only origin is specified, `true` or `false`'
    parameters: []
components:
  schemas: {}
  securitySchemes:
    3c63416a24d3b969da6df9271faa9d6e:
      type: apiKey
      in: query
      name: token
  parameters:
    currency:
      name: currency
      in: query
      required: false
      schema:
        type: string
        default: RUB
      description: the currency of prices
x-internal: false
security:
  - 3c63416a24d3b969da6df9271faa9d6e: []
```

</details>

> Hazırda Svagger 3.0.n variantını dəstəkləyir. Nümunədə olan v3 API ın versiyasın göstərir, open API nin deyilı. Bunu qarışdırmayın.

> `openapi obyektində versiyalardan əlavə bölmələr yer almır. OpenAPİ versiyaları ilə buradan tanış ola bilərsiniz.` (see [Version History](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#appendix-a-revision-history)). Hələki platformalar və online tool-lar əsasən 3.0.n versiyaya fokuslanıblar. Siz həmçinin müxtəlif versiyalar arasında konvertasiya edə bilərsiniz. [https://www.apimatic.io/transformer/](https://www.apimatic.io/transformer/)

![](<.gitbook/assets/image (4).png>)

\
