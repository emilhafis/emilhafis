# Step 3: The servers object (OpenAPI tutorial)

Server obyektində siz basPath göstəririsniz. basePath əvəvlki mövzudan bildiyimiz kimi URL in bir hissəsi olub endpoint qarşısında göstərilir.&#x20;

### Sample servers object <a href="#sample_servers_object" id="sample_servers_object"></a>

The following is a sample `servers` object:

```yaml
servers:
- url: https://api.travelpayouts.com/aviasales/v3/prices_for_dates
```

> İstifadəçi “Try it out” edəndə sizin hər bir endpointiniz (spec də "paths" adlandırılır) Server URL nə əlavə edilir. Məsələn, bizim paths-lardan biri /flight adlanırsa, bu zaman Swagger UI dən göndərilən sorğularda, bu path parametri kimi mənimsədiləcək `{server URL}{path}, tam olaraq isə sorğu bu formada göndərilcəəkdir https://api.openweathermap.org/data/2.5/weather`.

### Options with the server URL <a href="#options-with-the-server-url" id="options-with-the-server-url"></a>

> Server URL-niz üçün bəzi konfiqurasiya seçimləriniz var. Siz müxtəlif mühitlərə (test, beta, production) aid ola biləcək çoxsaylı server URL-lərini təyin edə bilərsiniz. Çoxsaylı server URL-ləriniz varsa, istifadəçilər serverlər arasından istədikləri mühiti seçə bilərlər. Məsələn, bu kimi birdən çox server URL-lərini təyin edə bilərsiniz:

```yaml
servers:
- url: https://api.travelpayouts.com/aviasales/v3/
  description: Production server
- url: https://test.travelpayouts.com/aviasales/v3/
  description: Test server
```

{% hint style="info" %}
Production

Test

Pre-Production
{% endhint %}

{% hint style="info" %}
If you get stuck, see the [sample OpenAPI spec here](https://idratherbewriting.com/learnapidoc/docs/openapi\_spec\_and\_generated\_ref\_docs/openapi\_openweathermap.yml) for the fully working sample. This will help you spot and troubleshoot indentation or other errors.
{% endhint %}

> In Swagger UI də server seçimləri drop down listdən seçmək hüququ verilir&#x20;

> If you have just one URL, you still see a drop-down box but with just one option
>
> Əgər sizin 1 URL niz olsa yenədə drop dovn görəcəskiz amma orada bir seçim olacaqdır.
>
> Əgər sizin ednpointləriniz fərqli URL lərə müraciət edirsə bunuda tənzimləyə bilərsiz. Local olaraq mənimsədilmiş hər zaman Global server URL nə nəzərən priroitetli olur.
>
> See [“Overriding Servers”](https://swagger.io/docs/specification/api-host-and-base-path/) in “API Server and Base URL” (Swagger’s docs) for more details.

### Swagger <a href="#swagger" id="swagger"></a>

> Paste the `servers` object (the [first code sample above](https://idratherbewriting.com/learnapidoc/pubapis\_openapi\_step3\_servers\_object.html#sample\_servers\_object) showing just one `url`) into your Swagger Editor, adding to the code you already have there. Swagger UI will look as follows.
>
> Təyin etdiyimiz `servers` URL ni Swaggerə daxil edək. Bunu bizim kodlarımızın arxasına əlavə edəj. Görünüş bu formada olacaqdır.

<figure><img src="https://lh4.googleusercontent.com/TJstZ-fZyj82byGYdpTigD9ccRV98sEhF70Axaf8bNkWEvSMiPkrjC38af3svT7Av9huramPGDRYiokzQvG5i5oaU5NPLLSMrw0Tuhw3FRXsUYM2ZGAsN5lZ3UWJTMlziPvpwNKnkaFpsywKdUuLmGqO7_h-LaCuhq-RLiMPJXNkTNeppTRpmmFuge-4CH4" alt=""><figcaption></figcaption></figure>

> Notice the drop-down menu that appears in the lower-right. (Even if you have just one URL, it still appears in a drop-down menu.)
