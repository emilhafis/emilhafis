---
description: Response example and scheme
---

# Cavab nümunəsi və sxemi



![](../.gitbook/assets/response.png)

> **Response example** - cavab nümunəsi olub sorğu əsasında qayıdan cavab üzrə nümunəni göstərir.&#x20;
>
> **Cavab nümunəsi** bütün parametr konfiqurasiyalarını və ya əməliyyatlarını əhatə etmir, lakin sorğu nümunəsində ötürülən parametrlərə uyğun qayıdan cavabı göstərməlidir. Nümunə, proqramçılara resurs üzrə məlumatları, formatı və bu məlumatın necə strukturlaşdırıldığını və s. bilməyə imkan verir.
>
> Cavabın təsviri **cavab sxemi (response scheme)** kimi tanınır. **Cavab sxemi** cavabı daha əhatəli, ümumi şəkildə sənədləşdirir, geri qaytarıla bilən hər bir xassə, hər bir xassə nələri ehtiva edir, dəyərlərin məlumat formatı, strukturu və digər təfərrüatları göstərir.

### Cavab nümunəsi və sxemi üzrə nümunələr

> Aşağıdakı nümunə [Mailchimp API](https://mailchimp.com/developer/marketing/api/campaigns/get-campaign-info/) üzrədir. Onlar cavab üzrə nümunəni sağ tərəfdə göstərərək ortada hər bir field-in izahın və məlumat növünü (**data type**) göstəriblər.&#x20;

![](../.gitbook/assets/mailchimp\_response\_sample.png)

> Aşağıdakı şəkildən göründüyü kimi burada qayıdan cavabda [**JSON**](parametrl-r.md#json-uezr-uemumi-m-lumat) field-lərin hamısı eyni səviyyəli deyil. Yəni `recepients` obyektinin daxilində bir neçə obyekt yer alır. Qeyd etdiyimiz kimi buna `nested object` deyilir. Mailchimp rahat başa düşülə bilinməsi üçün `recepients` obyektinin altındakı field-ləri əlaqəli şəkildə "expand" formasında göstərmişdir.

![](../.gitbook/assets/mailchim\_nested\_object.png)

### Cavab sxeminə və nümunəsinə ehtiyac varmı? <a href="#do-you-need-to-define-the-response" id="do-you-need-to-define-the-response"></a>

> Bəzi API dizaynlarda cavab sxemlərini vermirlər.&#x20;
>
> Amma cavabın təsvirini vermək məqsədə uyğundur. Ən əsası da cavabda abbreviaturalar olduqda. **API Tech Writer**-lər bəzən field-ləri qısaltmaqla API həcmini azaldırlar. Hər bir abbreviaturanın nə demək olduğunu aydınlaşdırmaq üçün də xeyli vaxt lazım olur.

{% hint style="warning" %}
#### Cavab nümunələrində reala uyğun məlumatlardan istifadə edin. <a href="#use-realistic-values-in-the-example-response" id="use-realistic-values-in-the-example-response"></a>

Cavab nümunəsində dəyərlər real məlumatlara uyğun olmalıdır, amma real olmamalıdır. Əgər proqramçılar sizə nümunə cavab verirsə, dəyərlərin ağlabatan olduğundan və diqqətinizi yayındıracaq qədər saxta olmadığından əmin olun (məsələn, komiks personajlarının adları və s.).&#x20;

Həmçinin də, əmin olun ki, response məlumatlarının içərisində real müştəri məlumatları yoxdur. Əgər **API** nümunələrini sizə təqdim ediblərsə və nümunələrdəki məlumatlar real məlumatlara oxşayırsa əmin olun ki, bunlar production database-dən deyildir. Adətən production verilənlər bazasının nüsxəsin (clone) çıxarıb onun üzərində development aparırlar. Belə olanda da real datalar nümunələrdə işitrak edir.&#x20;
{% endhint %}

### White space and indentation

Just a few words about whitespace and indentation to end this lecture.Whitespace refers to spaces and new lines and J sound pretty much ignores them.

You can have spaces before your lines or after your commas or any place like that.It doesn't really matter.

Also you can have line breaks wherever you want as long as they're not in the middle of quotation marks or in the middle of a number or something like that.

And although spacing doesn't matter to the computer reading the Jaison it's much easier for a human to read it if it's formatted nicely.

There are some general rules for good Jason formatting in general and 2 to 4 spaces as an indent for every new level of brackets.

Whether that's curly or square brackets after a comma is usually a good place to put a line break if you need a line break and then there are lots of exceptions to these rules.

Basically you just want to make it look good and readable. There are Jason forming tools on the web that you can use to help you with this and I'll talk about these in the next lecture which is the hands on exercise.

### JSON Formatter və Validator <a href="#format-the-json-and-use-code-syntax-highlighting" id="format-the-json-and-use-code-syntax-highlighting"></a>

> Qeyd etdiyimiz kimi, əksər API-larda cavab **JSON** formatında olur. Ona görə də, response nümunəsi hazırlayarkən [JSON Formatter and Validator](http://jsonformatter.curiousconcept.com/) istifadə edib cavabı səliqəli formada göstərin.
>
> Əgər "syntax highlighting" (yəni proqramlaşdırma dilinə uyğun rənglər ilə fərqləndirilmə, məsələn [aşağıda](cavab-nuemun-si-v-sxemi.md#hazirladigimiz-cavab-nuemun-si) mən bundan istifadə etmişəm) istifadə edə bilirsinizsə mütləq edin.&#x20;

> Gəlin, [bizim tapşırığımızda ](broken-reference)olan cavab nümunəsində format səhvi olmadığını yoxlayaq, həm də JSON-u səliqəli formaya salmağa çalışaq.
>
> Mən bunun üçün [https://jsonformatter.curiousconcept.com/](https://jsonformatter.curiousconcept.com/) saytdan istifadə edirəm. Amma xeyli sayda belə platformalar vardır.&#x20;

#### Tapşırıqdakı cavab nümunəsi

> { "Data":{ "Balance":\[ { "AccountId":"AZ29VTBA00000000000160209170", "Amount":{ "Amount":"1230.00", "Currency":"AZN" }, "CreditDebitIndicator":"Credit", "Type":"InterimAvailable", "DateTime":"2017-04-05T10:43:07+00:00", "CreditLine":\[ { "Included":true, "Amount":{ "Amount":"1000.00", "Currency":"AZN" }, "Type":"Pre-Agreed" } ] } ] }&#x20;

#### Hazırladığımız cavab nümunəsi

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

{% hint style="info" %}
Nümunədə 1 səhv tapıldı. Belə ki, sonda obyekt bağlanmamışdı. Yəni fiqurlu mötərizə qoyulmamışdı }.

Gördüyünüz kimi cavabımızda səliqəli və anlaşıqlı formada oldu.
{% endhint %}

{% hint style="info" %}
Növbəti mövzularda static site generator platformaları olan (Jekyll, GitHub, GitBook və s.) haqqında danışacağıq. Orada görəcəksiniz ki, syntax highlighting hansı fromada olur.
{% endhint %}

### Status kodları

> Response bölməsində bir çox hallarda mümkün statusu və qaytarılan xəta kodları göstərilir. Bununla belə, bu kodlar adətən API-nin bütün son nöqtələrinə aid olduğu üçün çox vaxt ayrıca bölmələrdə sənədləşdirilir. Bu səbəbdən də, bunları ayrıca mövzuda müzakirə edəcəyik.

### [Tapşırıq](../tapsiriq.md#s-n-dl-sdirm-k-uecuen-m-lumat) üzrə cavab nümunəsi və sxemi

> Son olaraq bizə verilən tapşırıq olan /accounts/<mark style="color:orange;">{AccountId}</mark>/balances endpointi üçün response nümunəsi və sxemi hazırlayaq.&#x20;

{% hint style="success" %}
#### Cavab nümunəsi

```json
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
{% endhint %}

#### Cavab sxemi

Cavab nümunəmiz gördüyünüz kimi bir birinin içərisində olan object-lərdən `nested objects` ibarətdir. Bu səbəbdən də, obyektləri <mark style="color:orange;">fərqli rənglər</mark> ilə işarələmişəm ki, daha aydın başa düşülən olsun.&#x20;

API-larda bir **object** digərlər yerlərdə də iştirak edirsə (məsələn `amount`) oradakı elementlərin təsvirini hər dəfə vermirlər. Bunun üçün **API Model** hazırlanır və oraya istinad edilir. Bunun haqqında növbəti məqalələrdə danışarıq.

| Dəyər                                                                | Məlumat növü                              | Zəruriliyi   | Təsvir                                                                                                                                 |
| -------------------------------------------------------------------- | ----------------------------------------- | ------------ | -------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:orange;">Data/Balance</mark>                      | <mark style="color:orange;">Object</mark> | Zəruridir    | Balans məlumatı                                                                                                                        |
| <mark style="color:orange;">Data/Balance/</mark>AccountId            | String                                    | Zəruri deyil | Hesab nömrəsi (IBAN)                                                                                                                   |
| <mark style="color:orange;">Data/Balance/Amount</mark>               | <mark style="color:orange;">Object</mark> | Zəruridir    | Balans məbləği                                                                                                                         |
| <mark style="color:orange;">Data/Balance/Amount/</mark>Amount        | String                                    | Zəruridir    | Məbləğ (Decimal)                                                                                                                       |
| D<mark style="color:orange;">ata/Balance/Amount/</mark>Currency      | String                                    | Zəruridir    | ISO4217 standartında 3 rəqəmli valyuta kodu                                                                                            |
| <mark style="color:orange;">Data/Balance/</mark>CreditDebitIndicator | Enum                                      | Zəruridir    | <p>Balansın credit və ya debt olmasını bildirir: </p><ul><li>Credit </li><li>Debit</li></ul>                                           |
| <mark style="color:orange;">Data/Balance/</mark>Type                 | Enum                                      | Zəruridir    | <p>Balans növü: </p><ul><li>InterimAvailable</li><li>InterimBooked</li></ul>                                                           |
| <mark style="color:orange;">Data/Balance/</mark>DateTime             | Date                                      | Zəruridir    | Balansın qaytarıldığı tarix                                                                                                            |
| <mark style="color:orange;">Data/Balance/CreditLine</mark>           | <mark style="color:orange;">Object</mark> | Zəruridir    | Kredit xətti haqqında məlumatlar                                                                                                       |
| <mark style="color:orange;">Data/Balance/CreditLine/</mark>Included  | Boolean                                   | Zəruri deyil | <p>Balansın kredit xətti olduğunu göstərir: </p><ul><li>true </li><li>false</li></ul>                                                  |
| <mark style="color:orange;">Data/Balance/CreditLine/</mark>Type      | String                                    | Zəruridir    | <p>Kreditin növünü bildirir:  </p><ul><li>Available</li><li>Credit </li><li>Emergency </li><li>Pre-Agreed </li><li>Temporary</li></ul> |

### Sonuncu addım

> indi isə gəlin bütün addımlarda hazırladığımız məlumatlara [ümumi baxış](uemumi-baxis.md) həyat keçirək.
