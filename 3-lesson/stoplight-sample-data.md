# Stoplight sample data

### Travelpayouts

<details>

<summary>API Overview</summary>

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

<details>

<summary>Path information</summary>

Paths:

* _/_prices\_for\_dates
* _\[Operation]_: GET
* _Operation ID_: get-prices\_for\_dates
* _Description_: Access current weather data for any location on Earth including over 200,000 cities! Current weather is frequently updated based on global models and data from more than 40,000 weather stations.

</details>

<details>

<summary>Sample query parameter</summary>



* **currency** — the currency of prices. The default value is RUB

<!---->

* **origin** — An IATA code of a city or an airport of the origin

<!---->

* **destination** — An IATA code of a city or an airport of the destination (if you don't specify origin parameter, you must set destination)

<!---->

* **departure\_at** — the departure date (`YYYY-MM` or `YYYY-MM-DD`)

<!---->

* **return\_at** — the return date. For one-way tickets do not specify it

<!---->

* **direct** — non-stop tickets, `true` or `false`. By default:  `false`

<!---->

* **market** — sets the market of the data source (by default, ru)

<!---->

* **limit** — the total number of records on a page. The default value — 30. The maximum value — 1000

<!---->

* **page** — a page number, is used to skip some massive of results. For example, if we want to get the entries from 100 to 150, we need to set `page=3`, and `limit=50`

<!---->

* **sorting** — the assorting of prices:
  * **price** — by the price (the default value). For the directions, only city — city assorting by the price is possible
  * **route** — by the popularity of a route.

<!---->

* **unique** — returning only unique routes, if only `origin` is specified, `true` or `false`. By default: `false`

<!---->

* **token** — your API token.

</details>

<details>

<summary>Sample response info</summary>

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

{% embed url="https://support.smartbear.com/swaggerhub/docs/integrations/api-auto-mocking.html" %}

{% embed url="https://support.smartbear.com/swaggerhub/docs/organizations/index.html" %}
