---
description: Qəbul etdiyimiz tapşırıq nümunəsi
---

# Endpoint dizayn

### Yeni Endpointin sənədləşdirilməsi

> Qeyd etdiyimiz kimi, Layihə meneceri / Product Owner sizə bildirir ki, növbəti reliz üçün yeni **endpoint** hazırlanıb onu sənədləşdirmək lazımdır.&#x20;

{% hint style="info" %}
Çox vaxt, **endpoint** yerinə **API**-da deyilir.
{% endhint %}

> Və sizə detalları əks etdirən məlumatları təqdim edirlər. Buradakı məlumatlar dağınıq formada və nizamsız düzülüşdədir.
>
> Bir çox **Tech writer**-lər layihə üzrə sıfırdan sənədləşmələri etmirlər. Arxitektlər adətən vacib məlumatları özləri üçün qeyd götürürlər və ya görüşlər zamanı uzun uzadı müzakriələr nəticəsində lazımı məlumatları alırlar və sonda özləridə bir çox məlumatları sənədləşmələrə əlavə edirlər. Bu məlumatlarda çox vaxt tam olmur və bu səbəbdən də **development** zamanı <mark style="color:red;">problemlər çox olur</mark>.&#x20;
>
> Yekunda hazırlanmış məlumatlar dağınıq olur, dərhal başa düşmək olmur və ya həssas daxili məsələlər (məsələn, database scheme, test login və s) sənədləşmələrin tərkbində yer alır.
>
> Nəticədə, bu məlumatları bu layihədə iştirak etməyən proqramçılara yönlədirmək lazım olur və bu proqramçılarda nəyə necə başlayacaqlarını bilmirlər.
>
> **Tech writer** kimi bizim işimiz həmin məlumatları auditoriyamıza tam, dəqiq, səliqəli və faydalı məlumat kimi çatdırmaqdan ibratədir.&#x20;

### Yeni Endpoint üzrə məlumatlar

> Təsəvvür edək ki, bizə aşağıdakı kimi məlumatları təqdim ediblər.
>
> Buna qədər API tələblərin artıq digər API Tech writer-lər hazırlayıb, bizim vəzifəmiz isə həmin məlumatları çeşidləmək və ondan sənədləşmə hazırlamaqdır.  &#x20;

{% hint style="info" %}
Növbəti mövzularımızda artıq biznes tələblərin analiz edərək sıfırdan API Dizayn-nı (yəni sıfırdan sona kimi bütün məlumatları) özümüz hazırlayacağıq.&#x20;
{% endhint %}

> Məlumatları başa düşmək üçün gəlin aşağıdakı **"Get account balance API"** bölməsinə baxaq.&#x20;

{% hint style="danger" %}
Məlumatlar sizi qorxutmasın. Addım addım hamsının üzərindən keçəcəyik və sonda API prinsiplərin mənimsəmiş olacağıq. Hazırda yalnız ümumi olaraq tanış olun və başa düşməyə çalışınki bu API nəyə xidmət edəcəkdir.
{% endhint %}

### Get account balance API nümunəsi

{% hint style="info" %}
### <mark style="color:blue;">Get account balance API</mark>

Yeni Endpointimiz budur   /accounts/{AccountId}/balances. Bu endpoint 3-cü tərəf təşkilatlar və ya banklar üçün nəzərdə tutulmuşdur. {AccountId} həmin hesab üzrə balansı qaytarır.

Mandatory parameter-lər:

* AccountId:&#x20;
* Receiver-Participant-Code:&#x20;
* PSU-Device-ID
* Consent-ID

Optional parameter-lər.

* Sender-Participant-Code

Response nümunəsi aşağıdakı kimidir.

Autentifikasiya kimi Basic AUTh-dan istifadə olunur.

{"Data": {    "Balance": \[{"AccountId": "AZ29VTBA00000000000160209170", "Amount": "Amount": "1230.00","Currency": "AZN"},"CreditDebitIndicator": "Credit","Type": "InterimAvailable","DateTime": "2017-04-05T10:43:07+00:00", "CreditLine": \[ {"Included": true, "Amount": {   "Amount": "1000.00",   "Currency": "AZN" }, "Type": "Pre-Agreed"  }] } \}}

Cavab bu elementlərdən ibarətdir.

Data/Balance&#x20;

AccountId

CreditDebitIndicator

Type

DateTime

CreditLine


{% endhint %}

> Gördüyünüz kimi,buradakı məlumatlar struktsuzdur və dərhal anlamaq çətindir.&#x20;
>
> Əlavə olaraq, bir çox məlumatları proqramçılar hardan əldə edəcək onun haqqındada məlumat yoxdur.
>
> Deməli burada iki işimi zolacaqdır:
>
> 1 . Məlumatları tam dəqiqləşdirmək
>
> 2\. Məlumatları API best practice-ə uyğun strukturlaşdırmaq&#x20;

### Növbəti addım

> Növbəti [bölmədə](api-reference-tutorial-overview.md) API üzrə qeyd etdiyimiz 5 əsas hissə ilə tanış olacağıq.&#x20;
