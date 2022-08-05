---
description: Designed for the registration of new merchants.
---

# Merchant Onboarding API

## <mark style="color:blue;">Merchant registration</mark>

{% swagger baseUrl="https://dev.multibank.az/qr/v1" method="post" path="/merchant" summary="Merchant registration" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="entityName" required="true" type="String (up to 25)" %}
Merchant name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" required="true" type="String " %}
EMAIL –format: localpart@domain, character set of local part: [A-Z], [a-z], [.!#$%&"*+/-=?^_`{|}~], [0-9]; character set of domain: [A-Z], [a-z], [.-], [0-9]);
{% endswagger-parameter %}

{% swagger-parameter in="body" name="webhookUrl" required="true" type="URL" %}
Merchant Webhook URL where status will be send
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tin" type="String (10) " %}
Merchant’s Tax Identification Number
{% endswagger-parameter %}

{% swagger-parameter in="header" name="content-type" required="true" %}
application/json
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
}
      “apiKey”: “9baac6ad-8dc3-43af-a121-c281e1c8f71d”
      “merchantId”:  “454632”,
      “webHookUrl”:  “https://qrapi.portofino.az/v1/qr/{rrn}/status”
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
  "timestamp": "2022-05-20T12:10:53.805+00:00",
  "status": 400,
  "error": "Bad Request",
  "message": "Validation failed for argument [0] in public az.ingress.qr.generator.dto.MerchantResponseDto az.ingress.qr.generator.controller.MerchantController.generateQrcode(az.ingress.qr.generator.dto.MerchantRequestDto) with 2 errors: [Field error in object 'merchantRequestDto' on field 'webHookUrl': rejected value [null]; codes [NotNull.merchantRequestDto.webHookUrl,NotNull.webHookUrl,NotNull.java.lang.String,NotNull]; arguments [org.springframework.context.support.DefaultMessageSourceResolvable: codes [merchantRequestDto.webHookUrl,webHookUrl]; arguments []; default message [webHookUrl]]; default message [must not be null]] [Field error in object 'merchantRequestDto' on field 'entityName': rejected value [AZ71UBAZ01299566041010AZN001]; codes [Size.merchantRequestDto.entityName,Size.entityName,Size.java.lang.String,Size]; arguments [org.springframework.context.support.DefaultMessageSourceResolvable: codes [merchantRequestDto.entityName,entityName]; arguments []; default message [entityName],25,0]; default message [size must be between 0 and 25]] ",
  "errors": [
    {
      "property": "webHookUrl",
      "message": "must not be null"
    },
    {
      "property": "entityName",
      "message": "size must be between 0 and 25"
    }
  ],
  "path": "/qr/v1/merchant"
}
```
{% endswagger-response %}
{% endswagger %}

#### Request example

{% tabs %}
{% tab title="JSON" %}
```json
{
  "email": "info@ingress.az",
  "entityName": "Ingress Group",
  "tin": 3884683,
  "webHookUrl": "https://www.ingress.az/payments/status"
}
```
{% endtab %}

{% tab title="cURL" %}
```
curl --location --request POST 'localhost:8088/qr/v1/merchant' \
--header 'Content-Type: application/json' \
--data-raw '{
    "entityName":"Ingress Group",
    "email":"info@ingress.az",
    "tin":"3884",
    "webHookUrl":"https://www.ingress.az/payments/status",
}'
```


{% endtab %}
{% endtabs %}

#### Response example

{% tabs %}
{% tab title="JSON" %}
```json
{ 
"apiKey": "3382a836-fbec-4ad5-bf23-74c691f8f222", 
"id": 10040, 
"webHookUrl": "https://www.ingress.az/payments/status/qr/{rrn}/status" 
}
```

| Field                                      | Type    | Required | Description                                                 |
| ------------------------------------------ | ------- | -------- | ----------------------------------------------------------- |
| <mark style="color:red;">apiKey</mark>     | String  | True     | Merchant unique ApiKey for generation QR (security purpose) |
| <mark style="color:red;">id</mark>         | Integer | True     | Unique Merchant ıd                                          |
| <mark style="color:red;">webHookUrl</mark> | URL     | True     | Callback URL where status will be sent                      |
{% endtab %}
{% endtabs %}

{% hint style="info" %}
For business processes refer to [Merchant Registration](../process-overview/merchant-onboarding-overview/merchant-registration.md)
{% endhint %}

## <mark style="color:blue;">Branch registration</mark>

{% swagger method="post" path="/branch" baseUrl="https://dev.multibank.az/qr/v1" summary="Branch registration" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="merchantId" type="Integer" %}
Received id from merchant registration
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="String (up to 25)" required="true" %}
Branch name

**Default - Main Office**
{% endswagger-parameter %}

{% swagger-parameter in="body" name="city" type="String (up to 15)" %}
Merchant's city
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" type="String" %}
Merchant's address
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "id": 10008,
  "name": "Main Office",
  "city": "Baku",
  "address": "Bulbul pr. 56A, ABU Park"
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
  "timestamp": "2022-05-16T12:14:15.981+00:00",
  "status": 404,
  "error": "Not Found",
  "message": "Merchant with the id 1001189 not found",
  "errors": [],
  "path": "/qr/v1/merchant/%7BmerchantId%7D/branch"
}
```
{% endswagger-response %}
{% endswagger %}

#### Request example

{% tabs %}
{% tab title="JSON" %}
```json
{ 
"address": "Bulbul pr. 56A, ABU Park", 
"city": "Baku", 
"name": "Main Office" 
}
```


{% endtab %}

{% tab title="cURL" %}
```
curl --location -g --request POST 'localhost:8088/qr/v1/merchant/{merchantId}/branch?merchantId=10007
' \
--header 'Content-Type: application/json' \
--data-raw '{
  "address": "Bulbul pr. 56A, ABU Park",
  "city": "Baku",
  "name": "Main Office"
}'
```


{% endtab %}
{% endtabs %}

**Response example**

{% tabs %}
{% tab title="JSON" %}
```json
{
  "address": "Bulbul pr. 56A, ABU Park",
  "city": "Baku",
  "id": 12309,
  "name": "Main Office"
}
```

| Field                                   | Type    | Required | Description    |
| --------------------------------------- | ------- | -------- | -------------- |
| <mark style="color:red;">address</mark> | String  | False    | Branch address |
| <mark style="color:red;">city</mark>    | String  | False    | Branch city    |
| <mark style="color:red;">id</mark>      | Integer | True     | Branch id      |
| <mark style="color:red;">name</mark>    | String  | True     | Branch name    |


{% endtab %}
{% endtabs %}

{% hint style="info" %}
For business processes refer to [Branch Registration](../process-overview/merchant-onboarding-overview/branch-registration.md)
{% endhint %}

## <mark style="color:blue;">Terminal registration</mark>

{% swagger method="post" path="/terminal" baseUrl="https://dev.multibank.az/qr/v1" summary="Terminal registration" %}
{% swagger-description %}
<mark style="color:red;">

****

</mark>
{% endswagger-description %}

{% swagger-parameter in="body" name="iban" type="" %}
Merchant's account number
{% endswagger-parameter %}

{% swagger-parameter in="query" name="branchID" required="true" type="Integer" %}
Received id from branch registration
{% endswagger-parameter %}

{% swagger-parameter in="body" name="terminalType" type="Enum" %}
Terminal type

**Default value - WEB\_PAGE**

<mark style="color:red;">Available values:</mark>

`PHYSICAL_PRINTING`

`POS_TERMINAL`

`SELF_SERVICE`&#x20;

`ATM`&#x20;

`WEB_PAGE`

`MOBILE_APP`&#x20;

`OTHER`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="terminalNumber" type="String (up to 25)" %}
Terminal number

**Default value - WEB-SITE-0001**
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deliveryChannel" type="Integer (3)" %}
Delivery channel types

&#x20;**1st value**&#x20;

“0” - Print – Sticker at the entity

“1” - Print – Invoice

“2”- Print – Journal&#x20;

“3”- Print – other

“4”- Screen – POS/ATM

“5”- Screen – Website

“6”- Screen – App

“7”- Other



&#x20;**2nd value**

&#x20;“0”- At the address of the entity presenting the AZQR Code

“1” - Not at the address of the entity presenting the AZQR Code (for ex., mobile)&#x20;

“2”- Remote trading (e-commerce)

“3”- Other

\
**3rd value**

“0”- Operation with the participation of a cashier, operator or representative of the business entity&#x20;

“1”- Self-service operation without participation of a representative of the entity presenting the AZQR Code.

“2”- Operation completed with a partial participation of a representative of the business entity presenting the AZQR Code.

“3”- Other

**Default value - 523 (E commerce)**
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantCategoryCode" type="Integer (4)" %}
[Merchant Category Codes](https://docs.google.com/spreadsheets/d/1xiOzfcSfkUsCoEAnsS-lRC-BRVz9V4up/edit?usp=sharing\&ouid=102637542479077781442\&rtpof=true\&sd=true)

**Default value - 5732 (E-commerce)**
{% endswagger-parameter %}

{% swagger-parameter in="body" name="qrDefaultLifetime" type="Integer (6)" %}
Validity of QR time (seconds).

**Default value - 600**
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "id": 10005,
  "branch": {
    "id": 10011,
    "name": "Main Office",
    "city": "Baku",,
    "address": "Bulbul pr. 56A, ABU Park"
  },
  "terminalNumber": "WEB-SITE-0001",
  "terminalType": "WEB_PAGE"
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
  “timestamp”: “2022-05-16T13:34:56.344+00:00”,
  “status”: 404,
  “error”: “Not Found”,
  “message”: “Branch with the id 100114 not found”,
  “errors”: [],
  “path”: “/qr/v1/branch/%7BbranchId%7D/terminal”
}
```
{% endswagger-response %}
{% endswagger %}

**Request example**

{% tabs %}
{% tab title="JSON" %}
```json
{
  "terminalType": "WEB_PAGE",
  "terminalNumber": “WEB-SITE-0001",
  "iban": “AZ71UBAZ01299566041010AZN001",
  "deliveryChannel": 400,
  "merchantCategoryCode": 5732,
  "qrDefaultLifetime": 600
}
```


{% endtab %}

{% tab title="cURL" %}
```
curl --location -g --request POST 'localhost:8088/qr/v1/merchant/{merchantId}/branch?merchantId=10007
' \
--header 'Content-Type: application/json' \
--data-raw '{
  "terminalType": "WEB_PAGE",
  "terminalNumber": “WEB-SITE-0001",
  "iban": “AZ71UBAZ01299566041010AZN001",
  "deliveryChannel": 400,
  "merchantCategoryCode": 5732,
  "qrDefaultLifetime": 600
}'
```


{% endtab %}
{% endtabs %}

**Response example**

{% tabs %}
{% tab title="JSON" %}
```json
{
  "id": 10005,
  "branch": {
    "id": 10011,
    "name": "Main Office",
    "city": "Baku",,
    "address": "Bulbul pr. 56A, ABU Park"
  },
  "terminalNumber": "WEB-SITE-0001",
  "terminalType": "WEB_PAGE"
}
```

| Field          | Type    | Required | Description                                                                                                                                                                                                                                                                               |
| -------------- | ------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id             | Integer | True     | Terminal id                                                                                                                                                                                                                                                                               |
| branch         | Array   | False    | Branch information                                                                                                                                                                                                                                                                        |
| id             | Integer | True     | Branch id                                                                                                                                                                                                                                                                                 |
| name           | String  | True     | Branch name                                                                                                                                                                                                                                                                               |
| city           | String  | False    | Branch city                                                                                                                                                                                                                                                                               |
| address        | String  | False    | Branch address                                                                                                                                                                                                                                                                            |
| terminalNumber | String  | True     | Terminal number                                                                                                                                                                                                                                                                           |
| terminalType   | Enum    | True     | <p>Terminal types <mark style="color:red;">Available values:</mark></p><p><code>PHYSICAL_PRINTING</code></p><p><code>POS_TERMINAL</code></p><p><code>SELF_SERVICE</code> </p><p><code>ATM</code> </p><p><code>WEB_PAGE</code></p><p><code>MOBILE_APP</code> </p><p><code>OTHER</code></p> |
|                |         |          |                                                                                                                                                                                                                                                                                           |
{% endtab %}
{% endtabs %}

{% hint style="info" %}
For business processes refer to [Terminal Registration](../process-overview/merchant-onboarding-overview/terminal-registration.md)
{% endhint %}

## <mark style="color:blue;">Merchant Details Modification API</mark>

![](../.gitbook/assets/Soon.png)

