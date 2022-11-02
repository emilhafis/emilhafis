# Step 4: The paths object (OpenAPI tutorial)

The [`paths` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#pathsObject) contains the meat of your API information. The `paths` object has several sub-objects: a [path items object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#pathItemObject), an [operations object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#operationObject), and more.

{% hint style="info" %}
Əvvəlki 3 mövzunu asta keçdik və bütün obyektlər ilə tanış olduq. Burada isə sürətli keçəcəyik. İlk dəfədən başa düşməsəniz problem yoxdur, hazır mən təqdim etdiyim kod üzərində işləyərsiniz və sonra lazım olduqda geriq ayıdıb baxarsınız.

Hər zaman hər şeyi yadda saxlamaq yox nəyi haradan tapacağınızı bilmək önəmlidir.
{% endhint %}

### Paths objects

> Bu bizim bildiyimiz endpointdir. open API spesifikasiyasında endpoint path adlandırılır deyə burada da Path deyəcəyik.

> `path`  obeykti daxilindəki Path item obyektləri  daxilinə HTTP metodları da daxildir.  (GET, POST, Delete və PUt haqqında bundan əvvəlki mövzuda danışmışıq)  &#x20;
>
> Gəlin indi, path endpoint) qeyd edib onlar üzrə metodu təyin edək. Flight endpoint i üçün bir path-a (/[prices\_for\_dates](https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates?origin=string\&destination=BCN\&departure\_at=string\&return\_at=string\&unique=false\&sorting=price\&direct=false\&currency=rub\&limit=30\&page=1\&one\_way=true\&token=PutYourTokenHere)) baxmışdıq. Və bunun metodu `GET` idi.

```
paths:
  /prices_for_dates:
    get:
```

> The operation object (`get` in the code above) contains various properties and objects:
>
> Yuxarıda göstərilən **get** üzrə operation obyektlər bir neçə xassədən və obyektlərdən ibarətdir.&#x20;
>
> * `tags`:  Endpointləri qruplaşdırmaq üçün istifadə edilir. Yadınızdadırsa Stoplight da demişdim. Svagge Uİ təyin etdiyiniz tag altında endpointləri quruplaşdırır
> * `summary`: path üzrə qısa təsvir. Svagger UI təsviri path in yanında göstərir. Təsvir üçün limit 5-10 sözdən ibarət olmaldıır. Çalışın qısa və lokanik edin. Təsvir endpointlər collapse olduqda belə görünür
> * `description`: path üzrə tam təsvir. Burada artıq detallı məlumat yaza bilərsiniz. Svagger Uİ də description üçün kifayət qədər yer olur. Burada həmçinində Markdown dili dəstəklənir.
> * [`externalDocs`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#externalDocumentationObject) (object): path üzrə əlavə məlumat əldə etmək üçün, kənar sənədləşməyə link
> * `operationId`: path üzrə unikal id. Spesifikasiya daxilində
>
>
>
> * [`parameters`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#parameterObject) (object):  Əvvəlki mövzuda bildirdiyimiz kimi son versiyalarda Reqeust body parametr kimi nəzərə alınmadığından ayrıca obyekt kimi göstərilir. parametr obyketinə həmçinində [reference object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#requestBodyObject) daxildir və bu `components` object nə istnad edir (bu step 5 də izah ediləcək)
>
>
>
> * [`requestBody`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#requestBodyObject) (object): path üçün request body detalları. `requestBody` obyektinə də həmçinin compnenet obyektinə istinad edən r[eference object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#referenceObject) daxildir. (You can find an example of a `requestBody` parameter in the [Swagger Petstore demo](https://petstore.swagger.io/#/pet/addPet). The `/pet` endpoint submits a request body when adding a pet. Check out the `requestBody` YAML syntax in [petstore-expanded.yml](https://github.com/OAI/OpenAPI-Specification/blob/master/examples/v3.0/petstore-expanded.yaml) — look at `post` under `/pets`. Also see [Describing Request Body](https://swagger.io/docs/specification/describing-request-body/).)
>
>
>
> * [`responses`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#responsesObject) (object): Request nəticəsində qayıdan Responsu göstərir. Response obyektinə də reference obyekti daxildir. Response standart status codelarından istifadə edir. [status codes](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#http-status-codes).&#x20;
>
>
>
> * [`callbacks`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#callbackObject) (object): Callback details to be initiated by the server if desired. Callbacks are operations performed after a function finishes executing. The `callbacks` object can also include a [reference object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#referenceObject) that contains a pointer to the description in the `components` object.
>
>
>
> * `deprecated`: Whether the path is deprecated. Omit unless you want to indicate a deprecated field. Boolean.
>
>
>
> * [`security`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#securityRequirementObject) (object): Security authorization method used with the operation. Include this object at the path level only if you want to overwrite the `security` object at the root level. The name is defined by the `securitySchemes` object in the `components` object. More details about this are provided in the [security object](https://idratherbewriting.com/learnapidoc/pubapis\_openapi\_step6\_security\_object.html).
> *
> * [`servers`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#serverObject) (object): Server obyketi global server obyektindən fərqli olduqda qeyd edilir. Yadınızdadırsa 3 cü addımda bildirdimki hə rendpoint üzrə server fərqli ola bilər.
>
>
>
> Göstərilən hyperlinkli olanlar obyektlər dir. yəni onlar daxilində fieldlər olur. Onların dəyərləri sadə string deyir, hər xassəsəinə uyğun məlumatlar təşkil edir.



### &#x20;
