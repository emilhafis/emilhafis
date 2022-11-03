# Step 6: The security object (OpenAPI tutorial)

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

> Swagger UI  istifadəçilərin real sorğu göndərməsi üçün “Try it out” funksionallığı təqdim edir. API serveri tərəfindən göndərilən sonruğunnn avtorizasiyadan keçməsi üçün spesifikasiyada avtorizaiysa məlumatları olmadıır.he [`security` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#securityRequirementObject) sorğu göndərən zaman avtorizaiy və ya təhlükəsizlik protokolunu müəyyənləşdirir.

### Which security scheme? 

> Bildiyimi zkimi REST API müxtəlif security yanaşmalarından istifadə edir.&#x20;
>
> Swagger UI supports four authorization schemes:
>
> * API key
> * HTTP
> * OAuth 2.0
> * Open ID Connect
>
> Bu bölmədə biz API Key yanaşmasından istifadə edəəyik. Çünki göstərdiyimiz nümunədə APİ Key dən istifadə edir. Əgər gələcəkdə başqa protokollar olarsa [Security Scheme information](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#security-scheme-object) oxuyarsız. Amma bütün metodlar eyni formada qeyd edilir.

### API key authorization

The sample OpenWeatherMap API we’re using in this course uses an API key passed in the URL’s query string (rather than in the header). If you submit a request without the API key in the query string (or without a valid API key), the server denies the request. For details on the OpenWeatherMap’s authorization model, see [How to start](https://openweathermap.org/appid#use).

>
