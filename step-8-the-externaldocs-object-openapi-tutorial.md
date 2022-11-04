# Step 8: The externalDocs object (OpenAPI tutorial)

The [`externalDocs` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#external-documentation-object) lets you link to external documentation. You can also provide links to external docs in the `paths` object.

### Example externalDocs object

> Here’s an example of an `externalDocs` object:

```
externalDocs:
  description: API Documentation
  url: https://support.travelpayouts.com/hc/en-us/articles/203956163-Travel-insights-with-Aviasales-Data-API
```

> Note that this documentation should relate to the API as a whole. To link a specific parameter to more documentation, you can add an `externalDocs` object to the operation object, as noted in [Operation objects](https://idratherbewriting.com/learnapidoc/pubapis\_openapi\_step4\_paths\_object.html#operation-objects) section in Step 4: The paths object.

{% hint style="info" %}
If you get stuck, see the [sample OpenAPI spec here](https://idratherbewriting.com/learnapidoc/docs/openapi\_spec\_and\_generated\_ref\_docs/openapi\_openweathermap.yml) for the fully working sample. This will help you spot and troubleshoot indentation or other errors
{% endhint %}

### &#x20;View the Appearance in Swagger UI

Add the above code to the root level of your OpenAPI document in Swagger UI.

When you do, in the Swagger UI, a link appears after the API description along with other info about the API:\


<figure><img src=".gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
At this point, you can probably anticipate some challenges with integrating Swagger UI with the rest of your documentation. It seems that you will likely have two outputs and a semi-fragmented user experience. The `externalDocs` object at least gives you a predictable place to link back to your other [conceptual topics](https://idratherbewriting.com/learnapidoc/docconceptual.html). See [Integrating Swagger UI with the rest of your docs](https://idratherbewriting.com/learnapidoc/pubapis\_combine\_swagger\_and\_guide.html) for more information on integration strategies.
{% endhint %}

### &#x20;Seeing the finished result

> Now that we’ve completed all the steps in the tutorial, we’re finished building our OpenAPI specification document.
>
> You can see the complete specification document here:&#x20;
>
> Here’s the specification document rendered by Swagger UI:

<details>

<summary>travelpayouts.yaml</summary>

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
security:
- app_id: []
externalDocs:
  description: API Documentation
  url: https://support.travelpayouts.com/hc/en-us/articles/203956163-Travel-insights-with-Aviasales-Data-API

tags:
  - name: Flight
    description: "Get the cheapest ticket"

paths:
  /prices_for_dates:
    get:
      tags: 
        - "Flight"
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

  /dates:
    get:
      tags: 
        - "Dates"
      summary: Get the cheapest ticket
      description: Get the cheapest ticket by date
      operationId: for_dates
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
  securitySchemes:
    app_id:
      type: apiKey
      description: API key to authorize requests.
      name: token
      in: query       
        
          
```

</details>

> Sorğunu icra edib nəticəsinə baxın. Sonra saytda bileti axtarın. Görün uyğun nəticələrdirmi? Ən azından azından origin query parametri kimi GYD yazmalısız

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
You can insert any valid path to an OpenAPI specification document in the “Explore” box in Swagger UI (assuming the version of Swagger UI supports your OpenAPI version), and it will display the API documentation. For example, you could insert `https://petstore.swagger.io/v2/swagger.json` (then click **Explore**) and it would show the Petstore API.
{% endhint %}



\


\
