# Tapşırıq

> Gəlin indi güman edək ki, siz **Tech Writer**-siz və **Bankda** **Payment team** ilə işləyirsiniz.&#x20;
>
> Komandanıza tapşırılıb ki, bank müştərilərinin məlumatların 3-cü tərəf təşkilatlara vermək üçün **PSD2 standartı** əsasında **Open Banking** yaradın.
>
> Hazırda bu formatlı standart Mərkəzi Bank tərəfindən **Ani Ödənişlər Sistemində** yaradılmışdır. Amma, bizə sırf bankda yaradılmış mərkəzləşdirilmiş Open Banking lazımdır ki, onu istədyimiz formada hazırlayaq.
>
> Komandanız sizə bildirir ki, API tələblərin artıq digər **API Tech** writer-lər hazırlanmış, yeni **endpoint proqramlaşdırılmışdır** və **** onu sənədləşdirmək lazımdır.&#x20;

{% hint style="info" %}
Çox vaxt, **endpoint** yerinə **API**-da deyilir.
{% endhint %}

> Aşağıda sizə yeni API `Get account balance API` haqqında məlumatları təqdim edirlər.

### Sənədləşdirmək üçün məlumat

> ### <mark style="color:blue;">Get account balance API</mark>
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
> Autentifikasiya kimi Basic AUTh-dan istifadə olunur.
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

> Gördüyünüz kimi sizə verilən məlumatlar dağınıq formada və nizamsız düzülüşdədir.
>
> Bir çox **Tech writer**-lər layihə üzrə sıfırdan sənədləşmələri etmirlər. Arxitektlər adətən vacib məlumatları özləri üçün qeyd götürürlər və ya görüşlər zamanı uzun uzadı müzakriələr nəticəsində lazımı məlumatları alırlar və sonda özləridə bir çox məlumatları sənədləşmələrə əlavə edirlər. Bu məlumatlarda çox vaxt tam olmur və bu səbəbdən də **development** zamanı <mark style="color:red;">problemlər çox olur</mark>.&#x20;
>
> Yekunda hazırlanmış məlumatlar dağınıq olur, dərhal başa düşmək olmur və ya həssas daxili məsələlər (məsələn, database scheme, test login və s) sənədləşmələrin tərkbində yer alır.
>
> Nəticədə, bu məlumatlar ilə tanış olmayan proqramçılar nəyi necə edəcəklərin bilmirlər.
>
> **Tech writer** kimi bizim işimiz həmin məlumatları auditoriyamıza tam, dəqiq, səliqəli və faydalı məlumat kimi çatdırmaqdan ibratədir.&#x20;

> _**Bunun üçün nələr etməlisiniz, ümumiyyətlə məsələyə necə yanaşmalısınız?**_&#x20;

{% hint style="warning" %}
Məlumatlar sizi qorxutmasın. Addım addım hamsının üzərindən keçəcəyik və sonda **API** prinsiplərin mənimsəmiş olacağıq. Hazırda yalnız ümumi olaraq tanış olun və başa düşməyə çalışınki bu **API** nəyə xidmət edəcəkdir.
{% endhint %}

> Gördüyünüz kimi,buradakı məlumatlar **struktsuzdur** və dərhal anlamaq **çətindir**.&#x20;
>
> Əlavə olaraq, bir çox məlumatları proqramçılar hardan əldə edəcək onun haqqında da məlumat yoxdur.
>
> Deməli burada iki işimiz olacaqdır:
>
> 1 . Məlumatları tam dəqiqləşdirmək;
>
> 2\. Məlumatları API best practice-ə uyğun strukturlaşdırmaq, yəni dizayn etmək.&#x20;

{% hint style="info" %}
Növbəti mövzularımızda artıq biznes tələblərin analiz edərək sıfırdan **API Dizayn**-nı (yəni sıfırdan sona kimi bütün məlumatları) özümüz hazırlayacağıq.&#x20;
{% endhint %}

### Növbəti addım

> Növbəti [bölmədə](../api-reference-tutorial/api-reference-tutorial-overview.md) API üzrə qeyd etdiyimiz 5 əsas hissə ilə tanış olacağıq.&#x20;