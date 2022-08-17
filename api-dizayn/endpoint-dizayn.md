# Endpoint Dizayn

>

{% hint style="warning" %}
Əgər qeyd etdiklərim üzrə məlumatınız yoxdursa, Linkedin postunun rəy bölməsində "API-lara proqramçı baxışı" adlı mövzunu məndən istəyin. Mövzu API nədir, API-dan necə istifadə edirlər və s. bölmələri əhatə edir. Real nümunələr ilə başa düşürsünüzki proqramçılar API-lardan necə istifadə edirlər.

Sizə həmin mövzunu göndərəcəm, əgər tələbat çox olarsa online olaraqda görüş keçirərik.
{% endhint %}

> Gəlin indi güman edək ki, siz Tech Writer-siz və Payment team ilə işləyirsiniz. Komandanız sizə bildirir ki, yeni API var onu sənədləşdirmək lazımdır. Bunun üçün nələr etməlisiniz, ümumiyyətlə məsələyə necə yanaşmalısınız?&#x20;

### You have a new endpoint to document

> The project manager calls you over and says the team has a new endpoint for you to document for the next release. (Sometimes teams will also refer to each endpoint as an “API” as well.)

> Qeyd etdiyimiz kimi, Layihə meneceri /Product Owner sizə bildiri ki, növbəti reliz üçün yeni endpoint hazırlanıb onu sənədləşdirmək lazımdır. Yəni, sizin bu&#x20;

{% hint style="info" %}
Çox vaxt, endpoint yerinə API-da deyilir. Yeni API hazırlanıb.
{% endhint %}

> Və sizə detalları əks etdirən məlumatları təqdim edirlər. Buradakı məlumatlar dağınıq formada və nizamsız düzülüşdədir.
>
> Bir çox tech writer-lər layihə üzrə sıfırdan sənədləşmələri etmirlər. Arxitektlər adətən vacib məlumatları özləri üçün note götürürlər və ya görüşlər zamanı uzun uzadı müzakriələr nəticəsində lazımı məlumatları alırlar.
>
> note-lar və ya görüşlər zamanı alınmış məlumatlar çox vaxt tam olmur və bu səbəbdəndə development zamanı problemlər çox olur.&#x20;
>
> Təqdim edilmiş məlumatlar isə dağınıq, dərhal başa düşmək olmur və ya daxili məsələlər (məsələn, database scheme, test login və s) olur.
>
> Nəticədə, bu məlumatları bu layihədə iştirak etməyən proqramçılara yönlədirmək lazım olacaqdır. Tech writer kimi bizim işimiz həmin məlumatları auditoriyamıza tam, dəqiq, səliqəli və faydalı məlumat kimi çatdırmaq olacaqıdr. Artıq bu məlumatlarla işləyən proqramçıların devleopent zamanı artıq heç bir sualları qalmayacaqdırş.

### Wiki page with information about the new endpoint

> İndi sizin vəzifəniz bu mock wiki səhifəsindəki məlumatları çeşidləmək və ondan sənədləşmə hazırlamaqdır. Buna qədər API tələblərin artıq digər Tech writer hazırlayıb, bizim taskımız sadəcə sənədləşmədir. Növbəti mövzularımızda artıq sıfırdan API tələblərində özümüz hazırlayacağıq.&#x20;
>
> Məlumatları başa düşmək üçün aşağıdakı wiki səhifəsinə baxın. Növbəti mərhələlərdə APı refrence topic vasitəsilə hissə hissə necə sənədləşmə lazımdırsa onu öyrənəcəyik.
>
> Sonda isə artıq biz API prinsiplərin başa düşmüş olacağıq.

### The wiki page: "Get account balance API"

{% hint style="info" %}
### <mark style="color:blue;">Get account balance API</mark>

Yeni Endpointimiz budur   /accounts/{AccountId}/balances. Bu endpoint 3-cü tərəf təşkilatlar və ya banklar üçün nəzərdə tutulmuşdur. {AccountId} həmin hesab üzrə balansı qaytarır.

Mandatory parameter-lər:

* AccountId:&#x20;
* Receiver-Participant-Code:&#x20;
* PSU-Device-ID-Type:&#x20;
* PSU-Device-ID
* PSU-IP-Address
* Consent-ID

Optional parameter-lər.

* Sender-Participant-Code

The response-a  will include the surf height, the wind, temp, the tide, and overall recommendation.

Sample endpoint with parameters:

```
https://api.openweathermap.org/com/surfreport/123?&days=2&units=metrics&hour=1400
```
{% endhint %}

{% hint style="info" %}
<pre><code>{
<strong>  "Data": {
</strong>    "Balance": [
      {
        "AccountId": "AZ29VTBA00000000000160209170",
       "Amount": {
          "Amount": "1230.00",
          "Currency": "AZN"
        },
        "CreditDebitIndicator": "Credit",
        "Type": "InterimAvailable",
        "DateTime": "2017-04-05T10:43:07+00:00",
        "CreditLine": [
          {
            "Included": true,
            "Amount": {
              "Amount": "1000.00",
              "Currency": "AZN"
            },
            "Type": "Pre-Agreed"
          }
        ]
      }
    ]
  },
  "Links": {
    "Self": {"href": "/accounts/22289/balances"}
  }
}</code></pre>
{% endhint %}

>
>
> Yeni Endpointimiz budur   /accounts/{AccountId}/balances. Bu endpoint 3-cü tərəf təşkilatlar və ya banklar üçün nəzərdə tutulmuşdur. {AccountId} həmin hesab üzrə balansı qaytarır.
>
> Mandatory parameter-lər:
>
> * AccountId:&#x20;
> * Receiver-Participant-Code:&#x20;
> * PSU-Device-ID-Type:&#x20;
> * PSU-Device-ID
> * PSU-IP-Address
> * Consent-ID
>
> Optional parameter-lər.
>
> * Sender-Participant-Code
>
> The response-a  will include the surf height, the wind, temp, the tide, and overall recommendation.
>
> Sample endpoint with parameters:
>
> ```
> https://api.openweathermap.org/com/surfreport/123?&days=2&units=metrics&hour=1400
> ```
>
> The response contains these elements:
>
> surfreport:
>
> * surfheight (units: feet)
> * wind (units: kts)
> * tide (units: feet)
> * water temperature (units: F degrees)
> * recommendation - string ("Go surfing!", "Surfing conditions okay, not great", "Not today -- try some other activity.")
>
> The recommendation is based on an algorithm that takes optimal surfing conditions, scores them in a rubric, and includes one of three responses.
>
> Sample format:
>
> ```
> {
>   "Data": {
>     "Balance": [
>       {
>         "AccountId": "AZ29VTBA00000000000160209170",
>         "Amount": {
>           "Amount": "1230.00",
>           "Currency": "AZN"
>         },
>         "CreditDebitIndicator": "Credit",
>         "Type": "InterimAvailable",
>         "DateTime": "2017-04-05T10:43:07+00:00",
>         "CreditLine": [
>           {
>             "Included": true,
>             "Amount": {
>               "Amount": "1000.00",
>               "Currency": "AZN"
>             },
>             "Type": "Pre-Agreed"
>           }
>         ]
>       }
>     ]
>   },
>   "Links": {
>     "Self": {"href": "/accounts/22289/balances"}
>   }
> }
> ```
>
> Negative numbers in the tide represent incoming tide.
>
> The report won't include any details about riptide conditions.
>
> Although users can enter beach names, there are only certain beaches included in the report. Users can look to see which beaches are available from our website at `https://example.com/surfreport/beaches_available` (not a real URL). The beach names must be url encoded when passed in the endpoint as query strings.
>
> To switch from feet to metrics, users can add a query string of `&units=metrics`. Default is `&units=imperial`.
>
> Here's an [example](https://www.surfline.com/surf-report/south-beach-ca-northern-california\_5088/) of how developers might integrate this information. This site shows the height of the surf coupled with a cam.
>
> If the query is malformed, you get error code 400 and an indication of the error.

> Gördüyünüz kimi buradakı məlumatlar struktsuzdur və dərhal anlamaq çətindir. API reference məlumatını beş standart bölmədə strukturlaşdırmaqla, məlumat daha çox forma alacaq və daha oxunaqlı olacaq.

###



\


\
