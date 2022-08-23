---
description: Endpoint and HTTP methods
---

# Endpoint və metodlar



![](../.gitbook/assets/endpoint.png)

### Endpoint və metod nədir?

> **Endpoint** resursa necə giriş əldə edə biləcəyimizi, **metod** isə resurs üzərində hansı əməliyyatları (`GET`, `POST`, `DELETE` və s) icra edə biləcəyimizi göstərir.
>
> **Resurslar** müxtəlif **Endpoint**-lərə malik olur. **Endpoint**-lərin müxtəlif **Path (yəni URL-ləri)** və **metodları** olsa da onların hamısı **Resurs** üzrə müxtəlif məlumatları qaytarırlar.&#x20;
>
> **Endpoint**-lərin təsviri adətən ümumi **resursun** təsvirinə oxşar, lakin daha qısa təsvirlərə malik olur.&#x20;

{% hint style="info" %}
Məsələn, aşağıda [Mailchimp API](step-2-endpoints-and-methods-api-reference-tutorial.md#mailchimp-api) **** üzrə nümunədə görə bilərsiniz ki, ümumi resurs **Campaings** adlanır və onun təsviri belə göstərilir:

<mark style="color:orange;">`Campaigns are how you send emails to your Mailchimp list. Use the Campaigns API calls to manage campaigns in your Mailchimp account.`</mark>

**Campaings** resursunun Endpoint-lərindən biri olan ** `GET /campaigns`** təsviri isə resursa nəzərən qısa olaraq belə göstərilir:

<mark style="color:orange;">`Get all campaigns in an account.`</mark>
{% endhint %}

> Həmçinin, **Endpoint** bütün **Endpoint**-lər üçün ümumi olan əsas **Path**-i (yol) deyil, yalnız resurs **URL**-in **Path**-in (yolunu) göstərir.&#x20;
>
> Cümlə çətindir bilirəm, narahat olmayın [aşağıdakı bölmədə](step-2-endpoints-and-methods-api-reference-tutorial.md#endpoint-yalniz-end-path-i-goest-rir) izahı vermişəm.

### Endpointlər üzrə nümunə

#### [Mailchimp API](https://mailchimp.com/developer/marketing/api/campaigns/)

> Aşağıda [Mailchimp APı-ın "Campaings"](https://mailchimp.com/developer/marketing/api/campaigns/) resursu üzrə **endpoint**-lər göstərilmişdir.

![](../.gitbook/assets/mailchimp\_endpoint.PNG)

> **Endpoint**-lər adətən gözə daha tez çarpması üçün xüsusi dizaynla interfeysdə göstərilir. API sənədləşmələrinin əksəriyyətinin əsas məğzini **Endpoint**-lər təşkil edir. Bu səbəbdən də sənədləşmənizdə **Endpoint**-ləri xüsusi formada göstərməyiniz tövsiyyə olunur. &#x20;
>
> Çünki proqramçılar test sorğuları etmək üçün dərhal **Endpoint**-ləri axtaracaqlar.&#x20;

### Path parametrlərini fərqləndirin

> Əgər sizin **endpoint**-də [**path parameter**](../api-dizayn/parametrl-r.md#path-parameters) **** varsa onları _<mark style="color:orange;">fiqurlu mötərizə</mark>_ <mark style="color:orange;"></mark><mark style="color:orange;">(</mark>_<mark style="color:orange;">curly braces</mark>_<mark style="color:orange;">)</mark> ilə göstərin. Məsələn aşağıda **Mailchimp API** üzrə nümunə göstərilmişdir.

{% hint style="warning" %}
**/campaigns/**<mark style="color:orange;">**{campaign\_id}**</mark>
{% endhint %}

> <mark style="color:orange;">{Fiqurlu mötərizədən}</mark> istifadə edərək **path parametrini** göstərmək mütləq bir qayda deyildir. Sadəcə bu formada edildikdə gözə daha tez çarpır.&#x20;
>
> Məsələn, yuxarıdakı nümunədə yalnız <mark style="color:orange;">`{campaign_id}`</mark> <mark style="color:orange;"></mark><mark style="color:orange;"></mark> üzrə bu formadan istifadə edildiyi üçün dərhal başa düşülür ki, bu dəyərin ümumi **endpoint** üzrə fərqliliyi vardır.

> Aşağıdakı digər bir nümunədə görürük ki, [OpenWeather API](https://openweathermap.org/api/one-call-3) platforması da **path parametrini** dediyimiz qaydada fərqli formada göstərmişdir.

#### [OpenWeather API](https://openweathermap.org/api/one-call-3)

![](../.gitbook/assets/Open.PNG)

{% hint style="info" %}
#### [OpenWeather API](https://openweathermap.org/api/one-call-3)-dan istifadə edərək siz hava haqqında məlumatları pulsuz formada alıb öz platformanız ilə inteqrasiya edə bilərsiniz.
{% endhint %}

> Qeyd etdiyimiz kimi, **path parameterlərinin** standart təyin edilən bir rəngi yoxdur. Məsələn aşağıda [Amazon API-](step-2-endpoints-and-methods-api-reference-tutorial.md#amazon-api)larında şahidi oluruq ki, path parametri olan <mark style="color:orange;">`{eventGroupId}`</mark>  **URL**-dəki digər dəyərlərdən seçilmir. &#x20;

{% hint style="warning" %}
Amma siz sənədləşmə edərkən, bu parametrlərin dərhal gözə çarpası üçün fərqli formada və fərqli rəngdən istifadə edin.&#x20;

Mən standart olaraq [OpenWeather API](https://openweathermap.org/api/one-call-3)-da olduğu kimi <mark style="color:orange;">narıncı rəngdən</mark> istifadə edirəm.
{% endhint %}

#### [Amazon API](https://developer-docs.amazon.com/sp-api/docs/finances-api-reference#get-financesv0financialeventgroupseventgroupidfinancialevents)

<figure><img src="../.gitbook/assets/Amazon_v1.PNG" alt=""><figcaption></figcaption></figure>

### Metodların təyini

> Bəs **endpoint**-lərin qarşısında olan **GET, POST, PUT** və s. bunlar nədir?
>
> Bunlar **HTTP metodlardır** və **endpoint**-lərin qarşısında verilməsi qəbul olunmuş praktikadır. Metodlar resurslar ilə nə iş görə biləcəyimizi təyin edir. Qısa olaraq, metodları aşağıda qeyd edib nə iş gördüyünü qeyd edirəm:
>
> * <mark style="color:orange;">**GET**</mark>: **Resursu** qaytarır. Yəni **Resurs** haqqında hansısa məlumatı əldə etmək istədikdə <mark style="color:orange;">**GET**</mark>-dən istifadə edilir.
> * <mark style="color:orange;">**POST**</mark>: **Resursu** yaradır.&#x20;
> * <mark style="color:orange;">**PUT**</mark>: Mövcud **resursu** və ya **resurs** daxilindəki hansısa hissələri yeniləyir.&#x20;
> * <mark style="color:orange;">**PATCH**</mark>: Mövcud **resursu** qismən dəyişdirir.
> * <mark style="color:orange;">**DELETE**</mark>: **Resursu** silir.
>
> Ətraflı məlumat üçün Vikipediyanın HTTP məqaləsində [Request methods](https://en.wikipedia.org/wiki/Hypertext\_Transfer\_Protocol#Request\_methods)-a baxın. Bəzi əlavə **metodlar** da var, lakin onlar nadir hallarda istifadə olunur.

{% hint style="danger" %}
**Metodların** **endpoint**-lər ilə sıx əlaqəsi olduğu üçün onları bir yerdə göstərdim.&#x20;

Əlavə olaraq aşağıda [Stripe API](step-2-endpoints-and-methods-api-reference-tutorial.md#stripe-api)-da metodları endpoint-lərin əvvəlində hansı formada qruplaşdırdıqlarını da görə bilərsiniz.
{% endhint %}

### [Tapşırıq](../tapsiriq.md#s-n-dl-sdirm-k-uecuen-m-lumat) üzrə metodu təyin edək

> Məlumatlarda qeyd edildiyi kimi, 3-cü tərəf təşkilatlar banklardan hesab üzrə balansları əldə edəcəklər. Məlumatın əldə edilməsi üçündə <mark style="color:orange;">**GET**</mark> metodundan istifadə edilir.

{% hint style="success" %}
Deməli **endpointimiz** üçün metod - <mark style="color:orange;">**GET**</mark>
{% endhint %}

### Endpoint yalnız "<mark style="color:orange;">end path</mark>"i göstərir

> **Endpoint**-i göstərdiyiniz zaman yalnız "**end path**"-i göstərin. "**Full path**" - "Base Path və Endpoint-dən ibarət olur və bunlar ümumilikdə **resurs URL** adlanır.&#x20;
>
> Yuxarıdakı Stripe nümunəmizdə də endpoint  `/v1/customers/:id/sources` kimi göstərilir. Burada Stripe hər dəfə resurs URL-ni tam formada, yəni bu formada `https://api.stripe.com/v1/customers/:id/sources` göstərmir. yuxarıdakı qeydimizi bu nümunə üzrə izah etsək burada `https://api.stripe.com` **Base path** `/v1/customers/:id/sources isə` **Endpoint-dir.**  Bunların ikisi bir yerdə isə `https://api.stripe.com/v1/customers/:id/sources` **Full path yəni Resurs URL-dir.**

{% hint style="warning" %}
Tam **resurs URL**-nin sənədləşməyə daxil edilməsi, istifadəçilərin lazımı **Endpoint**-lərə diqqətini yönəltməkdən yayındırır.&#x20;

Adətən **resurs URL** user guide-ın giriş hissəsində (məsələn, getting starting tutorial) avtorizasiya metodları ilə birgə göstərilir.

Bu səbəbdən də, hər dəfə **Endpoint** yazarkən **full resurs URL** göstərməyiniz lazım deyil.
{% endhint %}

### Endpoint-lərin qruplaşdırılması <a href="#how-to-group-multiple-endpoints-for-the-same-resource" id="how-to-group-multiple-endpoints-for-the-same-resource"></a>

> **Endpoint**-lərin və **metodların** sənədləşdirilməsində diqqət yetirilməli olan digər məqam onları necə qruplaşdırmaq və başa düşülən formada göstərməkdir, xüsusən də eyni resurs üzrə çoxlu sayda **endpoint**-ləriniz olarsa.&#x20;
>
> [Resursun təsviri](step-1-resource-description-api-reference-tutorial.md) bölməsində biz müxtəlif API nümunələrinə baxdıq. Bir çox platformalar **resurs** üzrə hər bir **endpoint**-i qruplaşdırmaq və ya sənədləşdirmək üçün müxtəlif dizayndan istifadə edirlər, buna görə də eyni nümunələrə yenidən baxmayacağıq.
>
> Amma ümumi konsepsiyaya nəzər salaq. Məsələn, deyək ki, sizin üç <mark style="color:orange;">**GET**</mark> və bir <mark style="color:orange;">**POST**</mark> **endpoint**-niz var və bunların hamısı eyni **resursa** aiddir.&#x20;
>
> Belə olan halda, bəzi platformalar eyni **resurs** üzrə bütün **endpoint**-ləri bir qrupda, digərləri isə müxtəlif qruplarda - məsələn, <mark style="color:orange;">**GET**</mark> üçün bir qrup, <mark style="color:orange;">**POST**</mark> üçün başqa bir qrupda və ya başqa səhifələrdə verə bilərlər.&#x20;
>
> Əgər endpoint-lər mahiyyətcə eynidirlərsə, onları bir qrupda və ya bir səhifədə vermək daha məntiqli olar. Lakin onlar əhəmiyyətli dərəcədə unikaldırsa (müxtəlif cavablar, parametrlər və error mesajları ilə), onları müxtəlif qruplara və ya səhifələrə ayırmaq daha uyğun olar.&#x20;

{% hint style="info" %}
Hazırkı dövrdə, siz daha yaxşı veb sayt dizaynı ilə eyni səhifədə bütün məlumatları da verə bilərsiniz. Çünki biz adətən lazım olan məlumatı səhifədə `control+F` ilə axtarırıq.
{% endhint %}

{% hint style="warning" %}
Mən eyni **resursa** aid olan müxtəlif **endpoint**-ləri bir qrupda toplayıb verirəm. Aşağıdakı Stripe nümunəsində olduğu kimi.
{% endhint %}

#### [Stripe API](https://stripe.com/docs/api/customer\_bank\_accounts)

<figure><img src="../.gitbook/assets/Stripe_1.png" alt=""><figcaption></figcaption></figure>

### [Tapşırıq](../tapsiriq.md#s-n-dl-sdirm-k-uecuen-m-lumat) üçün Endpoint <a href="#endpoint-for-surfreport-api" id="endpoint-for-surfreport-api"></a>

> Bizə verilmiş məlumat əsasında **Endpoint**-imizi hazırlayaq. **Endpoint** üçün çox fikirləşməyə dəyməz çünki bizə təqdim ediblər.&#x20;
>
> Qeyd etdiyimiz kimi **endpointi** təsvir edən 1 cümlə də əlavə edək.

{% hint style="success" %}
<mark style="color:green;">**Endpoint**</mark>

<mark style="color:orange;">**GET**</mark>**   **<mark style="color:blue;">****</mark>**   /accounts/**<mark style="color:orange;">**{AccountId}/**</mark>**balances**

**Hesab üzrə balansı əldə et (Request to get account balance)**
{% endhint %}

### Növbəti addım

> Hazırda biz resursumuzun təsvirini verdik, endpoint və metodu təyin etdik. İndi isə gəlin API üzrə **ən əsas bölmə** olan [Parametrlərə](../api-dizayn/parametrl-r.md) keçək.
