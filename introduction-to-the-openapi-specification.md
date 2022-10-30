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

Bu YAML kodu [Swagger Petstore demo](http://petstore.swagger.io/) nümunəsidir. Svaggerdə bu formada görünür.&#x20;

<figure><img src="https://lh3.googleusercontent.com/8GIqG-rCLuyQtniMuszB1SyJ-nBiVW6G2nD8wPAtBC4flC54splwQCbK58uHW2ld-C6ZRal57qcB3P7JLiX3qG5ee1HAcFOdbe-eBk9dakmmsEuA__B2WDNSh0SlsizEcdU0Y4YEA2SN0LOu46O_D8Dkqk6Q6k_B44Tbt48QXL0JxfLJ2v6U0FCoGaVFhFU" alt=""><figcaption></figcaption></figure>

**Əlimizdə hazır Open API spek olduğu üçün Svagger onu başa düşüb emal edir**

Bunu necə edirlər ona baxacağıq

{% hint style="info" %}
Open API spesifikasiyaya istinad edir, Swagger isə spesifikasiyadakı məlumatlı oxuyub onları nümayiş etdirə bilən API tool-dur. OpenAPI spesifikasiyası bir çox şirkətdən ibarət rəhbər komitə tərəfindən idarə olunan vendordan sılı olmayan formatdır. Gələcək mövzularda həm OpenAPI, həm də Swagger-i daha dərindən analiz edəcəyik.
{% endhint %}

Qeyd edilən obyektlərin mənaları:

* `/pet` - endpoint path-dir.
* `get` - HTTP method.
* `parameters` - endpoint üçün parametrlər listi.
* `responses` - request üzrə response listi-i.
* `200` - HTTP status code.
* `$ref` - burada başqa hissəyə istinad edilib orada olan dəyərlərdən istifadə edilmək üçün istifadə olunur. Yəni reference. OpenAPI-də kodunuzu təmiz saxlamaq və təkrar istifadəni asanlaşdırmaq üçün bu kimi çoxlu `$ref` markerləri istifida etmək daha yaxşı edir. Yəni eyni dəyərləri və ya responsları təkrar təkrar yazmağa ehtiyac qalmır. Məsələn ola bilər ki, siz öz API-nizdə amount hissəni bir neçə yerdə göstərməli olacaqsınız. Bunun üçün bütün endpointlərə ayrı ayrı amountu yazmağa ehtiyac qalmır. bir dəfə yaradırsız və bütün endpointlərdə ona istinad edirsiniz. Həmçinində error kod.

OpenAPI spesifikasiyanı öyrəndiyiniz zaman YAML və ya JSON u manual olaraq hazırlamağınız eyni zamanda dəyərlərin nə olmasını müəyyənləşdirməyiniz ilk dəfə çox çətin gələ bilər. Buna görə də visual editorlardan (məsələn Stoplight) istifadə etməklə spesifikasiyanı hazırlayacağıq. Daha sonra isə birbaşa kod əsaslı yanaşmaya keçəcəyik.

**Gəlin vizual platformaya ilk öncə baxaq**

