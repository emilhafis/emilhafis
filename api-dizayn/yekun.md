# Yekun

<mark style="color:green;">**Endpoint**</mark>

<mark style="color:blue;">**GET**</mark>**   /accounts/**<mark style="color:orange;">**{AccountId}/**</mark>**balances**

**Hesab üzrə balansı əldə et (Request to get account balance)**

#### Sorğu nümunəsi

```url
curl --location --request GET 'http://obank-test.example.az:50000/api/obis/v1.0/accounts/AZ83MOSZ00000000000019988155/balances' \
--header 'Sender-Participant-Code: AZERAZ20' \
--header 'Receiver-Participant-Code: MOSZAZ20' \
--header 'PSU-Device-ID-Type: IMEI' \
--header 'PSU-Device-ID: 43437437347347' \
--header 'PSU-IP-Address: 333' \
--header 'Consent-ID: qwer3456tzui7890' \
--header 'Authorization: Basic QVpFUkFaMjBBWFhYOjE='
```

#### <mark style="color:purple;">Cavab nümunəsi</mark>

```javascript
{
   "Data":{
      "Balance":[
         {
            "AccountId":"AZ29VTBA00000000000160209170",
            "Amount":{
               "Amount":"1230.00",
               "Currency":"AZN"
            },
            "CreditDebitIndicator":"Credit",
            "Type":"InterimAvailable",
            "DateTime":"2017-04-05T10:43:07+00:00",
            "CreditLine":[
               {
                  "Included":true,
                  "Amount":{
                     "Amount":"1000.00",
                     "Currency":"AZN"
                  },
                  "Type":"Pre-Agreed"
               }
            ]
         }
      ]
   }
}
```
