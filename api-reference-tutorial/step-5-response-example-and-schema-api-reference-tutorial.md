# Step 5: Response example and schema (API reference tutorial)

|   |   |   |
| - | - | - |
|   |   |   |
|   |   |   |
|   |   |   |

> Response example - cavab nümunəsi olub sorğu əsasında qayıdan cavab üzrə nümunəni göstərir. Cavab sxemi qayıdan bütün mümkün elementləri göstərməlidir.&#x20;
>
> Cavab nümunəsi bütün parametr konfiqurasiyalarını və ya əməliyyatlarını əhatə etmir, lakin sorğu nümunəsində ötürülən parametrlərə uyğun qayıdan cavabı göstərməlidir. Nümunə proqramçılara resurs üzrə məlumatları, formatı və bu məlumatın necə strukturlaşdırıldığını və s. bilməyə imkan verir.
>
> Cavabın təsviri cavab sxemi (response scheme) kimi tanınır. Cavab sxemi cavabı daha əhatəli, ümumi şəkildə sənədləşdirir, geri qaytarıla bilən hər bir xassə, hər bir xassə nələri ehtiva edir, dəyərlərin məlumat formatı, strukturu və digər təfərrüatları göstərir.

### Examples of response examples and schemas

> Aşağıdakı nümunə [Mailchimp API](https://mailchimp.com/developer/marketing/api/campaigns/get-campaign-info/) üzrədir. Onlar cavab üzrə nümunəni sağ tərəfdə göstərərək ortada hər bir field-in izahın və məlumat növünü (data type) göstəriblər.&#x20;

![](../.gitbook/assets/mailchimp\_response\_sample.png)

> Aşağıdakı şəkildən göründüyü kimi burada qayıdan cavabda JSON fieldlərin hamsı eyni səviyyəli deyil. Yəni `recepients` obyektinin daxilində bir neçə obyekt yer alır. Qeyd etdiyimiz kimi buna `nested object` deyilir. mailchimp rahat başa düşülə bilinməsi üçün `recepients`  obeyktinin altındakı field-ləri əlaqəli şəkildə "expand" formasında göstərmişdir.

![](../.gitbook/assets/mailchim\_nested\_object.png)

> The definition of the response is called the _schema_ or _model_ (the terms are used synonymously) and aligns with the [JSON schema language and descriptions](https://json-schema.org/). What works particularly well with the SendGrid example is the use of expand/collapse tags to mirror the same structure as the example, with objects at different levels.
>
>

### Do you need to define the response? <a href="#do-you-need-to-define-the-response" id="do-you-need-to-define-the-response"></a>

> Some API documentation omits the response schema because the responses might seem self-evident or intuitive. In Twitter’s API, the responses aren’t explained (you can see an [example here](https://developer.twitter.com/en/docs/accounts-and-users/manage-account-settings/api-reference/get-account-settings))
>
> However, most documentation would be better off with the response described, especially if the properties are abbreviated or cryptic. Developers sometimes abbreviate the responses to increase performance by reducing the amount of text sent. In one endpoint I documented, the response included about 20 different two-letter abbreviations. I spent days tracking down what each abbreviation meant, and found that many developers who worked on the API didn’t even know what many of the responses meant.

{% hint style="warning" %}
#### Cavab nümunələrində reala uyğun məlumatlardan istifadə edin. <a href="#use-realistic-values-in-the-example-response" id="use-realistic-values-in-the-example-response"></a>

Cavab nümunəsində dəyərlər real məlumatlara uyğun olmalıdır, amma real olmamlıdır. Əgər proqramçılar sizə nümunə cavab verirsə, dəyərlərin ağlabatan olduğundan və diqqətinizi yayındıracaq qədər saxta olmadığından əmin olun (məsələn, komiks personajlarının adları və s.).&#x20;

Həmçinin də, əmin olun ki, response məlumatlarının içərisində real müştəri məlumatları yoxdur. Əgər API nümunələri sizə təqdim ediblərsə və nümunələrdəki məlumatlar real məlumatlara oxşayırsa əmin olun ki, bunlar production databse dən deyildir. Adətən production verilənlər bazasının nüsxəsin (clone) çıxarıb onun üzərində development aparırlar. Belə olanda da real datalar nümunələrdə işitrak edir.&#x20;
{% endhint %}



### Format the JSON and use code syntax highlighting <a href="#format-the-json-and-use-code-syntax-highlighting" id="format-the-json-and-use-code-syntax-highlighting"></a>

>
>
> Qeyd etdiyimiz kimi, Response JSON formatında olur. Ona görə də, response nümunəsi hazırlayarkən [JSON Formatter and Validator](http://jsonformatter.curiousconcept.com/) istifadə edib cavabı səqliəli formada göstərin.
>
> Əgər "syntax highlighting" istifadə edə bilirsəniz mütləq edin. Səliqəli və  "syntax highlighting"  istifadə edilmiş cavab nümunəsini aşağıda göstərirəm.

```javascript
{
"id": 10,
"name": "doggie",
"category": {
"id": 1,
"name": "Dogs"
},
"photoUrls": [
"string"
],
"tags": [
{}
],
"status": "available"
}
```

> If you don’t have any syntax highlighters to integrate directly into your authoring tool, you can use an online syntax highlighter such as [tohtml.com/jScript/](https://tohtml.com/jScript/). However, manually pasting code into these editors will be tedious and probably unsustainable.

{% hint style="info" %}
Növbəti mövzularda static site genrator platformaları olan (Jekyll, GitHub, GitBook vəs.) haqqında danışacağıq. Orada görəcəksiniz ki, syntax highlighting hansı fromada olur.
{% endhint %}



\
