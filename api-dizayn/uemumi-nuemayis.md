# Ümumi nümayiş

> Üzərində işlədiyimiz müxtəlif hissələri tam nümayiş etdirmək üçün onları bir yerə yığaq.

### <mark style="color:blue;">Resursun təsviri (Resurce description)</mark>

**`Balans`** resursu 1 hesab üzrə balansı əldə etmək üçün istifadə edilir. Həmçinin də, bu API-dan istifadə edərək hesabın valyutasını, kredit xətti üzrə limiti, istifadə olunmuş balansı, overdraft xəttin və s. öyrənmək mümkündür.

### <mark style="color:blue;">**Endpoint və metod**</mark>

<mark style="color:blue;">**GET**</mark>\*\* /accounts/{AccountId}/\*\***balances**

Hesab üzrə balansı əldə et (Request to get account balance)

### <mark style="color:blue;">Sorğu nümunəsi (Request example)</mark>

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

### <mark style="color:blue;">Cavab nümunəsi (Response example)</mark>

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

### <mark style="color:blue;">Cavabın sxemi (Response scheme)</mark>

|   |   |   |
| - | - | - |
|   |   |   |
|   |   |   |
|   |   |   |

|   |   |   |
| - | - | - |
|   |   |   |
|   |   |   |
|   |   |   |
