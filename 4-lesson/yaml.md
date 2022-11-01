# Yaml

For details on other differences between JSON and YAML, see [Learn YAML in Minutes](http://learnxinyminutes.com/docs/yaml/). To learn more about YAML, see this [YAML tutorial](http://rhnh.net/2011/01/31/yaml-tutorial).

<details>

<summary>Travelpayouts Yaml</summary>

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
