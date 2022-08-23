---
description: Request example
---

# Sorğu nümunəsi

![](../.gitbook/assets/request.png)

> **Sorğu nümunəsi** **Endpoint**-də daxil olmaqla istifadə edilmiş `parametrlər konfiqurasiyanı` göstərir. Sorğu nümunəsi adətən bütün mümkün parametr konfiqurasiyalarını göstərmir amma mümkün qədər parametrləri göstərmək lazımdır.
>
> Sorğu nümunələrində çox vaxt müxtəlif dillərdə hazırlanmış kod nümunələrini də `code snipets` göstərirlər. Bunu göstərmək mütləq deyil, amma göstərilməsi daha yaxşıdır.

### Sorğu nümunələri

> Aşağıdakı nümunə [Stripe-ın göstərdiyi sorğu](https://stripe.com/docs/api/customer\_bank\_accounts/create) nümunəsidir.

![](../.gitbook/assets/Stripe\_request\_example.PNG)

> Gördüyünüz kimi burada API dizayn 3 hissəli təsvir edilmişdir. Sol tərəfdə Resurs və resurs üzrə əməliyyatlar, ortada Parametrlər, sağda isə request və response nümunəsi.&#x20;

{% hint style="info" %}
Bu formada dizaynı ilk dəfə **Stripe** gətirmişdir. Mənim bu dizayn çox xoşuma gəlir. API documenting üçün istifadə olunan ReDoc və Stoplight platformasının da dizaynı buna çox oxşardır. Nümunə üçün sonda verəcəyim **avtomatlaşdırılmış API Dizaynı da** bu formada olacaqdır.
{% endhint %}

> Sorğu nümunəsi default olaraq **cURL**-də göstərilmişdir. **cURL**-i daha dərindən növbəti mövzularda müzakirə edəcəyik.&#x20;
>
> Həmçinin də seçim əsnasında digər proqramlaşdırma dillərində nümunələrə baxmaq mümkündür.

#### [Travelpayouts](https://support.travelpayouts.com/hc/en-us/articles/203956163-Travel-insights-with-Aviasales-Data-API)

> Digər nümunə isə travelpayouts-dır. Gördüyünüz kimi buraya nümunə üçün tam olaraq sorğunu yerləşdiriblər. Yəni siz hazır sorğunu götürüb ona uyğun qayıdan cavaba baxa bilərsiniz.

{% hint style="info" %}
Travelpayouts-dan müxtəlif aviabilet qiymətləri ilə tanış olub öz platformanıza inteqrasiya edə bilərsiniz.
{% endhint %}

<figure><img src="../.gitbook/assets/travel-request_example_v1.png" alt=""><figcaption></figcaption></figure>

> Sorğunu göndərmək üçün sadəcə bizdən `API Key` tələb olunur. `API Key` saytda qeydiyyatdan keçdikdən sonra əldə olunur. Məsələn, mən `API Key` əldə etmişəm və aşağıdakı [**URL**-](https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates?origin=GYD\&token=3c63416a24d3b969da6df9271faa9d6e)ə əlavə etmişəm. Bu səbəbdən də URL-i sadəcə brazuerdə açaraq qayıdan cavab ilə tanış ola bilərsiniz.

{% hint style="info" %}
API Key nədir? Bundan əvvəlki bölmədə tanış ola bilərsiniz - [API Security](https://multibank.gitbook.io/api-security/avtorizasiya-noevl-ri/api-key)
{% endhint %}

```javascript
https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&token=3c63416a24d3b969da6df9271faa9d6e
```

> Bəzən bu formada bir neçə sorğu nümunələri göstərirlər. Əgər sorğu nümunəsi üçün eyni vaxtda bir neçə parametrin birgə işlədilməsi mümkün olmazsa bu zaman bir neçə sorğu nümunəsinin göstərilməsi məqsədəuyğundur.

### Müxtəlif proqramlaşdırma dillərində sorğular <a href="#requests-in-various-languages" id="requests-in-various-languages"></a>

> Bildiyimiz kimi **REST API** "`language agnostic`"-dir, yəni proqramlaşdırma dili deyil. Müxtəlif proqramlaşdırma dilləri üzrə istifadə olunan protokoldur. Proqramçılar öz tətbiqlərini istənilən dildə (**Java, Ruby, Python** və s) yaza bilərlər. Proqramçılar istifadə etdikləri proqramlaşdırma dili vasitəsilə **API-**ları sorğulayıb onlar üzrə cavabları ala bilərlər. Cavablar [**JSON**](parametrl-r.md#json-uezr-uemumi-m-lumat) və ya **XML** formatında olur.&#x20;
>
> Yazdıqlarımızın məntiqi nəticəsi olaraq biz proqramçıların hansı dildən istifadə edəcəyini tam olaraq bilməyəcəyimiz üçün, proqramlaşdırma dillərində kod nümunələri təqdim etməyimiz bir növ nəticəsizdir. Bir çox API-larda sorğu və cavab nümunələri təqdim olunur və proqramçıların özləri bilir ki, yazdıqları dildə hansı formada **HTTP** requests göndərə bilərlər.
>
> Buna baxmayaraq əksər **API**-lar bir neçə fərqli proqramlaşdırma dillərində nümunələr təqdim edirlər:
>
> Məsələn aşağıda [Stripe üzrə](https://stripe.com/docs/api/customer\_bank\_accounts/object?lang=python) görə bilərsiniz ki, bir neçə seçim imkanı verilir.

![](../.gitbook/assets/stripe\_code\_snip.png)

{% hint style="info" %}
Çox vaxt **Tech writer**-lər API-ların hansı proqramlaşdırma dilində yazılacağını bilirlər. Belə olduqda həmin proqramlaşdırma dilinə fokuslanmaq məqsədəuyğundur.&#x20;

Əgər siz **API doc platformalarından** (Swagger UI, ReDoc, Stoplight və s) istifadə edirsinizsə bu platformalar yazdığınız API-lara uyğun sizin üçün avtomatik kod nümunələri generasiya edirlər.
{% endhint %}

### Kod nümunələrinin avtomatik generasiyası

> Əgər siz **API doc platformalarından** istifadə etmirsinizsə və qeyd etdiyimiz kimi fərqli dillərdə kod nümunələri vermək istəyirsinizsə narahat olmayın bunun sadə yolu var. Belə ki, **API testing** üçün geniş istifadə olunan Postman-dan istifadə edərək cURL və müxtəlif proqramlaşdırma dilləri üzrə kod nümunələri generasiya edə bilərsiniz.

> **Postman**-da göndərəcəyiniz sorğuları qeyd edirsiniz və şəkildə göstərilən bölməyə daxil olub siyahını açırsınız.&#x20;
>
> Məsələn bizə verilən tapşırığa uyğun URL hazırlayıb **Postman**-da **GET** metodunun qarşısına birbaşa əlavə edin.

```
http://obank-test.anipay.az:53080/api/obis/v1.0/accounts/AZ83MOSZ00000000000019988155/balances
```

![](<../.gitbook/assets/Screenshot from 2022-08-16 16-20-29 (1).png>)

> Siyahıdan **Python** seçilən zaman, bizə Pythona uyğun kod nümunəsi təqdim olunur.

![](<../.gitbook/assets/postman\_python (1).png>)

> Hazırda bizə sənədləşmədə göstərmək üçün **cURl** lazımdır, ona görə də **cURL** üzrə nümunəni götürək.

![](<../.gitbook/assets/postman\_cUrl (1).png>)

> Aşağıdakı formada kod nümunəsi əldə edirik. Artıq bu kod nümunəsini öz sənədləşməmizdə istifadə edə bilərik.

```javascript
curl --location --request GET 'http://obank-test.example.az:50000/api/obis/v1.0/accounts/AZ83MOSZ00000000000019988155/balances' \
--header 'Sender-Participant-Code: AIBAAZ20' \
--header 'Receiver-Participant-Code: IBAZAZ20' \
--header 'PSU-Device-ID-Type: IMEI' \
--header 'PSU-Device-ID: 43437437347347' \
--header 'PSU-IP-Address: 333' \
--header 'Consent-ID: qwer3456tzui7890' \
--header 'Authorization: Basic QVpFUkFaMjBBWFhYOjE='
```

{% hint style="danger" %}
Bu kod nümunələrini hər zaman öz proqramçılarınız ilə dəqiqləşdirin.
{% endhint %}

{% hint style="info" %}
Postman, cURL, API doc platformaları (SwaggerHub, ReDoc və s) üzrə ayrıca mövzularımız olacaqdır.
{% endhint %}

### [Tapşırıq](../tapsiriq.md#s-n-dl-sdirm-k-uecuen-m-lumat) üçün sorğu nümunəsi <a href="#request-example-for-the-surfreport-endpoint" id="request-example-for-the-surfreport-endpoint"></a>

> İndi isə bizə verilən taska qayıdaq və `/accounts/`<mark style="color:orange;">`{AccountId}/`</mark>`balances` endpointi üçün sorğu nümunəsi hazırlayaq.&#x20;
>
> Yuxarıda Postman-dan aldığımız nümunə bizim tapşırığa aid olduğu üçün ondan istifadə edə bilərik. Əlavə olaraq da, adətən sorğu nümunələrində nümunə avtorizasiya məlumatları verildiyindən hər zaman qeyd apararaq bunu bildirin.&#x20;

{% hint style="success" %}
### <mark style="color:blue;">**Sorğu nümunəsi**</mark>

```javascript
curl --location --request GET 'http://obank-test.example.az:50000/api/obis/v1.0/accounts/AZ83MOSZ00000000000019988155/balances' \
--header 'Sender-Participant-Code: AZERAZ20' \
--header 'Receiver-Participant-Code: MOSZAZ20' \
--header 'PSU-Device-ID-Type: IMEI' \
--header 'PSU-Device-ID: 43437437347347' \
--header 'PSU-IP-Address: 333' \
--header 'Consent-ID: qwer3456tzui7890' \
--header 'Authorization: Basic QVpFUkFaMjBBWFhYOjE='
```

(Təşkilatınıza aid olan avtorizasiya məlumatlarından istifadə edin)
{% endhint %}

### Növbəti addım

> Növbəti bölmədə resurs üzrə [Cavab nümunəsi və sxemi](cavab-nuemun-si-v-sxemi.md)[ ](../avtorizasiya-noevl-ri/step-2-endpoints-and-methods-api-reference-tutorial.md)ilə tanış olacağıq.&#x20;
