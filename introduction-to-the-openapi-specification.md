# Introduction to the OpenAPI specification

Open API JSON obyektlərinin adlandırılmasını, sırasını və məzmununu müəyyən edən xüsusi sxemə malikdir. Bu JSON faylı (çox vaxt JSON əvəzinə YAML-də deyilir) API-nizin hər bir hissəsini təsvir edir. API-nizi standart formatda təsvir etməklə, API publishing tool-ları vasitələri API haqqında məlumatı proqramlı şəkildə təhlil edə və hər bir komponenti stilizə edilmiş, interaktiv displeydə göstərə bilərsiniz. Yəni bu o anlama gəlirki siz API -ları Open Api spesifikasiyasına əsasən hazırlasanız sonradan onları rahatlıqla istənilən auto doc platformalarına import edə bilərsiniz. Hətta hazırda proqramistlər avtomatik olaraq həmin API ları avtomatik şəkildə kodları əldə edirlər. Daha sonra görəcəyikki platformalar bizə hazır formada client SDK lər verirlər.

### Glancing at the OpenAPI specification

OpenAPI spesifikasiyasını daha yaxşı başa düşmək üçün bəzi spesifikasiyalara nəzər salaq. Növbəti mövzuda spesifikasiya üzrə hə rbir elementi dərindən analiz edəcəyimizə görə burada ümumi məlumat veririəm və başa düşməsəniz narahat olmayın.

Rəsmi OpenAPI spesifikasiyanı buradan [Github repository](https://github.com/OAI/OpenAPI-Specification) əldə edə bilərsiniz. OpenAPI elementlərindən bəziləri `paths`, `parameters`, `responses`, və `security.`Bu elementlərin hər biri JSON obyektidir və özündə bəzi xassələri (properities) və massivləri (arrays) saxlayır.

OpenAPI spesifikasiyasında sizin **endpointləriniz** `paths` olaraq göstərilir. Əgər sizin “pets” adlandırdığınız endpointiniz varsa sizin bu endpoint üzrə OpenAPI spesifikasiyasınız aşağıdakı kimi görünərdi.

```json
paths:
  /pets:
    get:
      summary: List all pets
      operationId: listPets
      tags:
        - pets
      parameters:
        - name: limit
          in: query
          description: How many items to return at one time (max 100)
          required: false
          schema:
            type: integer
            format: int32
      responses:
        '200':
          description: An paged array of pets
          headers:
            x-next:
              description: A link to the next page of responses
              schema:
                type: string
          content:
            application/json:    
              schema:
                $ref: "#/components/schemas/Pets"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
```

This [YAML code](https://github.com/OAI/OpenAPI-Specification/blob/master/examples/v3.0/petstore.yaml) comes from the [Swagger Petstore demo](http://petstore.swagger.io/).

Qeyd edilən obyektlərin mənaları:

* `/pet` - endpoint path-dir.
* `get` - HTTP method.
* `parameters` - endpoint üçün parametrlər listi.
* `responses` - request üzrə response listi-i.
* `200` - HTTP status code.
* `$ref` - burada başqa hissəyə istinad edilib orada olan dəyərlərdən istifadə edilmək üçün istifadə olunur. Yəni reference. OpenAPI-də kodunuzu təmiz saxlamaq və təkrar istifadəni asanlaşdırmaq üçün bu kimi çoxlu `$ref` markerləri istifida etmək daha yaxşı edir. Yəni eyni dəyərləri və ya responsları təkrar təkrar yazmağa ehtiyac qalmır. Məsələn ola bilər ki, siz öz API-nizdə amount hissəni bir neçə yerdə göstərməli olacaqsınız. Bunun üçün bütün endpointlərə ayrı ayrı amountu yazmağa ehtiyac qalmır. bir dəfə yaradırsız və bütün endpointlərdə ona istinad edirsiniz. Həmçinində error kod.

OpenAPI spesifikasiyanı öyrəndiyiniz zaman YAML və ya JSON u manual olaraq hazırlamağınız eyni zamanda dəyərlərin nə olmasını müəyyənləşdirməyiniz ilk dəfə çox çətin gələ bilər. Buna görə də visual editorlardan (məsələn Stoplight) istifadə etməklə spesifikasiyanı hazırlayacağıq. Daha sonra isə birbaşa kod əsaslı yanaşmaya keçəcəyik.

Bu səbəbdən mən bu kursda ilk öncə vizual redaktor mövzusuna keçəcəyik, vizual redaktordan (**Stoplight Studio**) istifadə edərək OpenAPI sənədi yaradacağıq və daha sonra **Swagger Editor** və **Swagger UI** dən istifadə edərək **OpenAPI tutorial overviewı** keçəcəyik. UI. Bir məsələni bildirim kiƏ vizual redaktordan istifadə edərək bütün məsələləri həll edə bilərsiz, amma OpenAPI spekinə əsasən manual kod strukturunu hazırlaya bilmək sizin üçün çox böyük üstünlük olacaqdır. Əlinizdəki spesifikasiyanı istənilən platformaya import etməklə bir çox əməliyyatları həyata keçirə biləcəksiniz.

### Auto-generation options for creating the OpenAPI spec <a href="#autogeneration" id="autogeneration"></a>

Before we dive into ways to manually create the OpenAPI specification document, it’s worth noting some other approaches to the task, beyond choosing whether to use a visual editor or manually write the code. You can also choose to auto-generate the OpenAPI spec from annotations in your programming code. This developer-centric approach may make sense if you have a large number of APIs or if it’s not practical for technical writers to create this documentation. In my [2020 Developer Documentation Trends survey](https://idratherbewriting.com/learnapidoc/docapis\_trends.html), approaches for auto-generating the spec versus manually generating it were split:

If you want to go the code-generation route, Swagger offers a variety of libraries that you can add to your programming code to generate the specification document. These Swagger libraries then parse the annotations that developers add and generate the OpenAPI specification document. These libraries are considered part of the [“Swagger Codegen”](https://swagger.io/swagger-codegen/) project.

### Spec-first development of the OpenAPI spec <a href="#specfirst" id="specfirst"></a>

Now let’s talk about the spec-first approach. Many feel that auto-generation, described in the previous section, is _not_ the best approach. In [_Undisturbed REST: A Guide to Designing the Perfect API_](https://www.mulesoft.com/lp/ebook/api/restbook), [Michael Stowe](https://twitter.com/mikegstowe) recommends that teams implement the OpenAPI specification by hand and then treat the specification document as a contract that developers use when doing the actual coding. This approach is often referred to as “spec-first development.”

In other words, developers consult the OpenAPI specification document to see what the parameter names should be called, what the responses should be, and so on. After this “contract” or “blueprint” has been established, Stowe says you can then put the annotations in your code (if you want) to generate the specification document in a more automated way. But don’t code without first having a spec.

Too often, development teams quickly jump to coding the API endpoints, parameters, and responses without doing much user testing or research into whether the API aligns with what users want. Since versioning APIs is extremely difficult (you have to support each new version going forward with full backward-compatibility to previous versions), you want to avoid the “fail fast” approach that agile enthusiasts so commonly celebrate. There’s nothing worse than releasing a new version of your API that invalidates endpoints or parameters used in previous releases. Constant versioning in APIs can become a documentation nightmare.

Even before the API has been coded, your spec can generate a [mock response](https://idratherbewriting.com/learnapidoc/pubapis\_swaggerhub\_smartbear.html#mocking\_servers) by adding response definitions in your spec. The mock server generates a response that looks like it’s coming from a real server, but in reality it’s just a pre-defined response in your code and appears to be dynamic to the user.

If the OpenAPI spec isn’t used as the blueprint for the API, what is? Most likely, the descriptions about the endpoints and what they return will be stored on a wiki page or Word document, often incomplete in terms of all the details (e.g., casing of the responses, the structure and what’s included), so developers will make these decisions on the fly while coding.\
\




