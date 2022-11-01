# Step 1: The openapi object (OpenAPI tutorial)

Ümumi olaraq bildirim ki, bizim Open API mövzumuz aşaıdakı məsələlərə görə unikaldır.

* Burada bizə əvvəldən tanış olan Travel API ları üzrə Open API konteksti ilə tanış olacaqğıq
* Yenə də bizə tanış olan platofmralarda (Stoplight və Svagger Uİ) də Open API necə hazırlanır ona baxacağıq
* Bizim mövzumuz Open API speki üzrə bütün bölmələri əhatə etmir. Yalnız lazımlı hissələri əlavə etmişəm.
* Bizim mövzumuz hazırda ən çox istifadə olunan və Svagger tərəfindən ən sonuncu versiya kimi təsdiqlənən 3.0 Open API specin əhatə edir.&#x20;

### The root-level objects in OpenAPI spec <a href="#the-root-level-objects-in-openapi-spec" id="the-root-level-objects-in-openapi-spec"></a>

> Open API spesifikasiyanın nüvəsi 8 əsas obyektdən ibratədir. Bu obyektlərində daxilində bir neçə nested obyekt vardır amma əsas parent objectlər bunlardır.

* [`openapi`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#oasObject)
* [`info`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#infoObject)
* [`servers`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#serverObject)
* [`paths`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#pathsObject)
* [`components`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#componentsObject)
* [`security`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#securityRequirementObject)
* [`tags`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#tagObject)
* [`externalDocs`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#externalDocumentationObject)

> "root level" dedikdə mən Open API spesifikasiyanın əsas səviyyələrin nəzərdə tuturam. Bu levellər həmçinin də Global level adlanır (əgər fikir vermisinizsə Stoplight da vardır), çünki bəzi object lər burada qeyd olunur (məsələn `servers` və `security)` və bütün obyketlərə şamil olunur (əgər aşağı səviyyədə başqası qeyd edilməyibsə.

> Bütün spesifikasiya (yəni bu 8 root level obyektlərdən ibarət olan) [OpenAPI documen](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#oasDocument) adlanır. Fayl extension isə yaml məsələn openapi.**yaml** adlandırılır.

{% hint style="info" %}
Yadınızda saxlayın - OpenAPI spesifikasiyaya istinad edir, “Swagger” Open API spesifikasiyanı dəstəkləyən və onun üzərində işləri görməyə imkan verən tool və ya platformadır və SmartBear kompaniyası tərəfindən idarə edilir.
{% endhint %}
