---
description: Task
---

# Raw data

### Sənədləşdirmək üçün məlumat

> ### <mark style="color:orange;">Get account balance API</mark>
>
> Yeni Endpointimiz budur   /accounts/{AccountId}/balances. Bu endpoint 3-cü tərəf təşkilatlar və ya banklar üçün nəzərdə tutulmuşdur. {AccountId} həmin hesab üzrə balansı qaytarır.
>
> Mandatory parameter-lər:
>
> * AccountId:&#x20;
> * Receiver-Participant-Code:&#x20;
> * PSU-Device-ID
> * Consent-ID
>
> Optional parameter-lər.
>
> * Sender-Participant-Code
>
> Response nümunəsi aşağıdakı kimidir.
>
> Autentifikasiya kimi Basic Auth-dan istifadə olunur.
>
> {"Data": {    "Balance": \[{"AccountId": "AZ29VTBA00000000000160209170", "Amount": "Amount": "1230.00","Currency": "AZN"},"CreditDebitIndicator": "Credit","Type": "InterimAvailable","DateTime": "2017-04-05T10:43:07+00:00", "CreditLine": \[ {"Included": true, "Amount": {   "Amount": "1000.00",   "Currency": "AZN" }, "Type": "Pre-Agreed"  }] } \}}
>
> Cavab bu elementlərdən ibarətdir.
>
> Data/Balance&#x20;
>
> AccountId
>
> CreditDebitIndicator
>
> Type
>
> DateTime
>
> CreditLine
>
>

Bu məlumatları Travelpayouts və ya ev tapşırığınızdakı API məlumatları ilə müqaisə etsəniz, görərsiniz ki, bunları loru dildə desəm "adam içinə çıxarmaq olmaq"

> _**Bunun üçün nələr etməlisiniz, ümumiyyətlə məsələyə necə yanaşmalısınız?**_&#x20;

{% hint style="warning" %}
Addım addım bütün prosesin üzərindən keçəcəyik və sonda **API** prinsiplərini mənimsəmiş olacağıq. Hazırda yalnız ümumi olaraq tanış olun və başa düşməyə çalışın ki, bu **API** nəyə xidmət edəcəkdir.
{% endhint %}

> Gördüyünüz kimi, buradakı məlumatlar **struktsuzdur** və dərhal anlamaq **çətindir**.&#x20;
>
> Əlavə olaraq, bir çox məlumatların proqramçıların hardan əldə edəcəkləri haqqında da məlumat yoxdur.
>
> Deməli burada iki işimiz olacaqdır:
>
> 1 . Məlumatları tam dəqiqləşdirmək;
>
> 2\. Məlumatları API best practice-ə uyğun strukturlaşdırmaq, yəni dizayn etmək.&#x20;

{% hint style="info" %}
Növbəti mövzularımızda artıq biznes tələblərini analiz edərək sıfırdan **API Dizayn**-nı (yəni sıfırdan sona kimi bütün məlumatları) özümüz hazırlayacağıq.&#x20;
{% endhint %}

### Növbəti addım

>
