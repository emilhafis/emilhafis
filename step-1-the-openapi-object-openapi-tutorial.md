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

> OpenAPI sənədi üzrə dərsliyi bir çox varaintda hazırlamaq olar. Mən qedy etdiyim root level obyektləri əsasında bu dərsliyi hazırlamışam.&#x20;
>
> Siz burada iki yanaşma əsasında izah görəcəksiz
>
> 1. Kod səviyyəsində işləyən Swagger-dən,&#x20;
> 2. digəri isə istifadəçi interfeysində işləyən Stoplight Studio-dan istifadə .

### Swagger <a href="#swagger" id="swagger"></a>

> Kodlaşdırmaya keçməmişdən əvvəl, baxaki kodlaşdırmanı harada edəcəksiniz və nə kimi seçiləriniz vardır
>
>

#### Where to write your spec code

> Kodlaşırmanın ən sadə yolu online [Swagger Editor](https://swagger.io/swagger-editor/) istifadə etməkdir. Swagger Editor split viyu təqdim edir, yəni sol tərəfdə kodlaşdırma edirsinz və sağ tərəfdə yazdığınız kodun necə görünməsini real rejimdə izləyirsiniz. Hətta Displaydə dəyişiklik etdikdə kodda da bunun dərhal nəzərə alındığını görə bilərsiniz.

> &#x20;[Swagger Editor](https://swagger.io/swagger-editor/) yazdığınız kodu real vaxt rejimində yoxlayacaq və siz spesifikasiya sənədini kodlamağı bitirənə qədər xətalar varsa onları göstərəcəkdir. Üzərində işlədiyiniz kodda X işarələrini görməyincə xətalardan narahat olmayın. Çünki bir çox tövsiyyə xətalarıda qarşımıza çıxacaqdır.

> Mən adətən text editordan (Sublime Text kimi mətn redaktorundan istifadə etməklə) istifadə etməklə öz spesifikasiyamı komputerimdə saxlayıram. Amma onun üzərində işi online olaraq  [Swagger Editor](https://swagger.io/swagger-editor/) vasitəsilə edir. İşimi bitirdikdən sonra yenədə eyni qaydada kopyalayıb Sublime textdə saxlayıra.&#x20;
>
> Amma bir məsələnidə deyimki  [Swagger Editor](https://swagger.io/swagger-editor/) bizim spesifikasıyımızı brauzerin cach-də saxlayır. Siz cahsi təmizləmədikcə spesifikasıyımız orada qalacaqdır. &#x20;
>
> Əvvəl xatırlayırdınızsa demişdik ki Swagger HUB cloudda saxlay;r
