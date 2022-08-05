# QR Payment API

## <mark style="color:blue;">Generate QR</mark>

{% swagger method="post" path="/qr-generate" baseUrl="https://dev.multibank.az/qr/v1" summary="Generate QR" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="content-type" type="String" required="true" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="Array" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="query" name="qrType" type="String" required="false" %}
Terminal type

**Default value - BASE64\_IMAGE**

<mark style="color:red;">Available values:</mark>

`BASE64_IMAGE`

`STRING`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="Number (10,2)" required="true" %}
Transaction amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ccy" type="Currency" required="true" %}
Transaction currency

**Default - AZN**
{% endswagger-parameter %}

{% swagger-parameter in="body" name="terminalNumber" type="String" %}
Terminal number
{% endswagger-parameter %}

{% swagger-parameter in="header" name="apiKey" type="String" %}
Merchant's API Key
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "rrn": "214016116754",
  "qrTxt": "iVBORw0KGgoAAAANSUhEUgAAAMgAAADIAQAAAACFI5MzAAADUklEQVR4Xu3WPRKcIBQAYGzkCtLI1aCRK0AD2ugVpIGrQQNXkAaCm5lEM2HXNpml5HOQv/ceoLQa+LPjV/vKV872lX9aMoAB2YDdKLu0E6CeiAoEbwZF1/l5YPmREHbQzXCWXKfd1D+TiR4EZZxxMv1TYSu0AYBBebuEZ6LCxPk4yAnguMX7eloC+ul3u+9bS87m484lyhwdr/6PkgHpJUAHmMSWe6SfCV6WEjo3qE2nIJ5IOUA/EJVZ6IUDKKgHktU+DTBTh1eAkkOvrz8J9XkkqNidblmq62hNKZmz5Ty5uthRhPGJZNJtWx5HFmh0UO9PpOgsacDaiZ3pYq7/aUpG0S4zsjarFCS8rqctZBgkC8qNAxFpSWffRxFzNytT94WltYvX0ZpSbB4l3EVAjgzI8SeS1UzqKaRd4ngM7HbaLSk1PdTI6tyo6sWKy6vvozgyMmtYDfoA7SWy3sgqRbFex3LU3fH21fdBMmArDvVWOVHCRJ16IqIY6F9R4nWKt1NoSYmxjqYydud6b7N+IzunqWhvc91Xh199HyRzQFeqD8DrVCRgjwRIQHUAcsDrKCV8JDWrCl+OiaUYwHS98U0psxR6WyfZGVQOec0uTckEADUjA0a6zD24RXBTuhT9FpTBaeaSXTNfU2p6nVXUep7gts1s/T1aW7KUaNkMqUmCjPh6cm0pKzsIwQc12M7UX//TlpqOmA1QGxXw0V1n3ZQMV+pQFjH0I+nW6+40pSy27s1mvU0HCvCa+drioBNm4BNQ0Qg3PRJTK7N30Aw1wZRblLyRnu1sruOcNZoZ9UBq+Uc6GbrZtdaNW45vSgk0T0wfbO+2LPw1izUlM4P8mYuKXnHy/vX1J+n7XmR88IEuAdCfNf2TKDPA4kaoa9Tb/RolbeGgFzPaWe5soLO8jNYWbKNhAdsd1xKzXGfdlOK6slODZsLiDOh135qSe7WteOVKa7/UEvpIujDys5xLtpgBXG5VW6pBW6+7xMVnfss7TamvtIFFIyfS2T9ekG1RtfDBWAtgLQS7vFXNppAaH65OnON62vf89kbq/rgu1FnvYrne+HfCcbTJnk806J/J+cja6uWwhou0PZP6upW1Ji0HLaZO5Yn8tX3lK2f7yv8nPwCpAst0Ac9eGgAAAABJRU5ErkJggg=="
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
  "timestamp": "2022-05-20T12:18:30.198+00:00",
  "status": 400,
  "error": "Bad Request",
  "message": "Merchant not found for the api key",
  "errors": [],
  "path": "/qr/v1/qr-generate"
}
```
{% endswagger-response %}
{% endswagger %}

#### Request example

{% tabs %}
{% tab title="JSON" %}
```json
{
  "amount": {
    "amount": 488.45,
    "currency": "AZN"
  },
  "terminalNumber": "WEB-SITE-0001"
  }
```


{% endtab %}

{% tab title="cURL" %}


```uri
curl --location --request POST 'https://dev.multibank.az/qr/v1/qr-generate?qrType=STRING'
--header 'apiKey: 29f0f292-b356-4124-8437-f88795a8bffa'
--header 'Content-Type: application/json'
--data-raw '{ "amount": { "amount": 488.45, "currency": "AZN" } }'
```


{% endtab %}
{% endtabs %}

{% hint style="warning" %}
If you do not send terminal number then QR will be generated for default terminal
{% endhint %}

#### Response example

{% tabs %}
{% tab title="JSON" %}
```json
{
  "rrn": "214016116754",
  "qrTxt": "iVBORw0KGgoAAAANSUhEUgAAAMgAAADIAQAAAACFI5MzAAADUklEQVR4Xu3WPRKcIBQAYGzkCtLI1aCRK0AD2ugVpIGrQQNXkAaCm5lEM2HXNpml5HOQv/ceoLQa+LPjV/vKV872lX9aMoAB2YDdKLu0E6CeiAoEbwZF1/l5YPmREHbQzXCWXKfd1D+TiR4EZZxxMv1TYSu0AYBBebuEZ6LCxPk4yAnguMX7eloC+ul3u+9bS87m484lyhwdr/6PkgHpJUAHmMSWe6SfCV6WEjo3qE2nIJ5IOUA/EJVZ6IUDKKgHktU+DTBTh1eAkkOvrz8J9XkkqNidblmq62hNKZmz5Ty5uthRhPGJZNJtWx5HFmh0UO9PpOgsacDaiZ3pYq7/aUpG0S4zsjarFCS8rqctZBgkC8qNAxFpSWffRxFzNytT94WltYvX0ZpSbB4l3EVAjgzI8SeS1UzqKaRd4ngM7HbaLSk1PdTI6tyo6sWKy6vvozgyMmtYDfoA7SWy3sgqRbFex3LU3fH21fdBMmArDvVWOVHCRJ16IqIY6F9R4nWKt1NoSYmxjqYydud6b7N+IzunqWhvc91Xh199HyRzQFeqD8DrVCRgjwRIQHUAcsDrKCV8JDWrCl+OiaUYwHS98U0psxR6WyfZGVQOec0uTckEADUjA0a6zD24RXBTuhT9FpTBaeaSXTNfU2p6nVXUep7gts1s/T1aW7KUaNkMqUmCjPh6cm0pKzsIwQc12M7UX//TlpqOmA1QGxXw0V1n3ZQMV+pQFjH0I+nW6+40pSy27s1mvU0HCvCa+drioBNm4BNQ0Qg3PRJTK7N30Aw1wZRblLyRnu1sruOcNZoZ9UBq+Uc6GbrZtdaNW45vSgk0T0wfbO+2LPw1izUlM4P8mYuKXnHy/vX1J+n7XmR88IEuAdCfNf2TKDPA4kaoa9Tb/RolbeGgFzPaWe5soLO8jNYWbKNhAdsd1xKzXGfdlOK6slODZsLiDOh135qSe7WteOVKa7/UEvpIujDys5xLtpgBXG5VW6pBW6+7xMVnfss7TamvtIFFIyfS2T9ekG1RtfDBWAtgLQS7vFXNppAaH65OnON62vf89kbq/rgu1FnvYrne+HfCcbTJnk806J/J+cja6uWwhou0PZP6upW1Ji0HLaZO5Yn8tX3lK2f7yv8nPwCpAst0Ac9eGgAAAABJRU5ErkJggg=="
}
```

| Field                                 | Type    | Required | Description                     |
| ------------------------------------- | ------- | -------- | ------------------------------- |
| <mark style="color:red;">rrn</mark>   | Integer | True     | Qr reference number             |
| <mark style="color:red;">qrTxt</mark> | String  | True     | Generated QR (base64 or string) |
{% endtab %}
{% endtabs %}

{% hint style="info" %}
For business processes refer to [QR Generation Overview](../process-overview/qr-payment-overview/qr-generation-overview.md)
{% endhint %}

## <mark style="color:blue;">Cancel QR</mark>

{% swagger method="put" path="/qr/{rrn}/cancel" baseUrl="https://dev.multibank.az/qr/v1" summary="Cancel QR" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="content-type" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="path" name="rrn" type="Integer (12)" %}
QR reference
{% endswagger-parameter %}

{% swagger-response status="204: No Content" description="" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
  "timestamp": "2022-05-20T12:24:59.676+00:00",
  "stavtus": 400,
  "error": "Bad Request",
  "message": "QrCode not found with given rrn 21401672184",
  "errors": [],js
  "path": "/qr/v1/qr/21401672184/cancel"
}
```
{% endswagger-response %}
{% endswagger %}

#### Request example

{% tabs %}
{% tab title="cURL" %}
curl --location --request PUT 'https://dev.multibank.az/qr/v1/qr/214016116754/cancel'
{% endtab %}
{% endtabs %}

{% hint style="info" %}
For business processes refer to [QR Cancel Overview](../process-overview/qr-payment-overview/qr-cancel-overview.md)
{% endhint %}

## <mark style="color:blue;">Investigate QR</mark>

{% swagger method="get" path="/qr/{rrn}/status" baseUrl="https://dev.multibank.az/qr/v1" summary="Investigate QR" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="content-type" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="query" name="rrn" type="Integer (12)" %}
QR reference
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{ 
   “status“: “incompleted“,
   “description“: “AM04	InsufficientFunds“,
   “iban“: “AZ71UBAZ01299566041010AZN001“,
   “amount“: “1000.00“
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
  "timestamp": "2022-05-26T11:05:56.496+00:00",
  "status": 400,
  "error": "Bad Request",
  "message": "QrCode not found with given rrn 456",
  "errors": [],
  "path": "/qr/v1/qr/456/status"
}
```
{% endswagger-response %}
{% endswagger %}

#### Request example

{% tabs %}
{% tab title="cURL" %}
```
curl --location --request GET 'https://dev.multibank.az/qr/v1/qr/214016116754'
```
{% endtab %}
{% endtabs %}

#### Response example

{% tabs %}
{% tab title="JSON" %}
```json
{
  "rrn": "214016116754",
  "status": "CANCELED",
  "description": null,
  "aliasValue": "AZ71UBAZ01299566041010AZN001",
  "amount": 488.45
}
```

| Field                                       | Type          | Required | Description                                                                 |
| ------------------------------------------- | ------------- | -------- | --------------------------------------------------------------------------- |
| <mark style="color:red;">rrn</mark>         | Integer       | True     | Qr reference number                                                         |
| <mark style="color:red;">status</mark>      | Enum          | True     | Available values -`expired,   canceled, inprogress, completed, incompleted` |
| <mark style="color:red;">description</mark> | String        | False    | Used with `incomplete` status for detailed information                      |
| <mark style="color:red;">aliasValue</mark>  | String        | True     | Merchant’s bank account number                                              |
| <mark style="color:red;">amount</mark>      | Number (10,2) | True     | Value of amount                                                             |
{% endtab %}
{% endtabs %}

{% hint style="info" %}
For business processes refer to [QR Investigation Overview](../process-overview/qr-payment-overview/qr-investigation-overview.md)
{% endhint %}

## <mark style="color:blue;">Status QR via Webhook</mark>

{% swagger method="put" path="/qr/{rrn}/status" baseUrl="https://www.ingress.az/payments/status" summary="Status QR via Webhook" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="rrn" type="Integer (12)" required="true" %}
QR reference
{% endswagger-parameter %}

{% swagger-parameter in="header" name="contentType" type="String" required="true" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="apiKey" type="String" required="true" %}
QR API Service Provider's Api Key
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="Enum" required="true" %}
Transaction status.

Available values:&#x20;

<mark style="color:red;">`read,`</mark>

<mark style="color:red;">`paid,`</mark>

<mark style="color:red;">`canceled,`</mark>

<mark style="color:red;">`expired,`</mark>

<mark style="color:red;">`completed,`</mark>

<mark style="color:red;">`incompleted`</mark>
{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" type="String" %}
Used with the 

<mark style="color:red;">

`incomplete`

</mark>

 status for detailed information.
{% endswagger-parameter %}

{% swagger-response status="204: No Content" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

#### Request example

{% tabs %}
{% tab title="JSON" %}
```json
{
  "description": "Amount insufficient",
  "status": "incompleted"
}
```
{% endtab %}

{% tab title="cURL" %}
```
curl --location --request GET 'localhost:8088/qr/v1/qr/213817883355' \
--header 'Content-Type: application/json' \
--data-raw '{
  "description": "Amount insufficient",
  "rrn": "214016116754",
  "status": "incompleted"
}'
```
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
Merchant should implement Webhook URL for receiving QR Payment Status
{% endhint %}

{% hint style="info" %}
For business processes refer to [QR Webhook Status Overview](../process-overview/qr-payment-overview/qr-webhook-status-overview.md)
{% endhint %}
