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

> Aşağıdakı şəkildən göründüyü kimi burada qayıdan cavabda JSON fieldlərin hamsı eyni səviyyəli deyil. Yəni `recepients` obyektinin daxilində bir neçə obyekt yer alır. Qeyd etdiyimiz kimi buna `nested object` deyilir. mailchimp rahat başa düşülə bilinməsi üçün `recepients`  obeyktinin altındakı field-ləri əlaqəli şəkildə göstərmişdir.

![](../.gitbook/assets/mailchim\_nested\_object.png)

\
