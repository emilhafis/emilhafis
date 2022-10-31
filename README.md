# YAML

> OpenAPI tutorial mövzusuna keçməmişdən öncə Yaml nədir ona baxaq. Çünki YAML OpenAPI  spesifikasiyasının sintaksisidir (siz JSOn formatından da istifadə edə bilərsiz, amma qəbul olunmuş praktika YAML dır).
>
> YAML açılışı "YAML Ain't Markup Language" deməkdir. Bunun mənası odur ki, YAMl sintaksisində markup tag-ları yəni < tag > olmur. Bunların əvəzində obyektin xassələrini göstərmək üçün iki nöqtədən, massivi (array) göstərmək üçün isə tirelərdən istifadə edir.

### Working in YAML

YAML is easier to work with because it removes the brackets, curly braces, and commas that get in the way of reading content

> YAML ilə işləmək daha asandır, çünki məzmunu oxumağa mane olan mötərizələri, fiqurlu mötərizələr və vergüllər burada olmur.
>
> YAML daha çox insan tərəfindən oxuna bilən məlumat mübadiləsi formatı yaratmaq addımıdır. O, JSON-a bənzəyir, lakin strukturu göstərmək üçün boşluqlar, iki nöqtə və defislərdən istifadə edir.
>
> Bir çox proqram təminatları məlumatları YAML və ya JSON formatında qəbul edir. Bu, demək olar əksər server konfiqurasiya fayllarında və avto doc platformalarında istifadə edirlir. Ona görə YAMl ı bilmək sizin üçün çox faydalı olacaqdlr.

### Yaml JSON nun bir üst versiyadır deyək

For the most part, YAML and JSON are different ways of structuring the same data. Dot notation accesses the values the same way. For example, the Swagger UI can read the `openapi.json` or `openapi.yaml` files equivalently. Pretty much any parser that reads JSON will also read YAML. However, some JSON parsers might not read YAML because there are a few features YAML has that JSON lacks (more on that [below](https://idratherbewriting.com/learnapidoc/pubapis\_yaml.html#yaml\_specific\_features)).

> Əksər hallarda YAML və JSON eyni verilənləri strukturlaşdırmağın müxtəlif yollarıdır. Məsələn, Swagger UI  olaraq `openapi.json` və ya `openapi.yaml` fayllarını oxuya bilər və nəticə eyni olur. JSON-u oxuyan demək olar ki, hər hansı bir parser YAML-i də oxuyacaq. Bununla belə, bəzi JSON parser-lər YAML-i oxumaya bilər, çünki YAML-də JSON-da çatışmayan bir neçə xüsusiyyət var .

### YAML syntax <a href="#yaml-syntax" id="yaml-syntax"></a>

> YAML sintaksisində boşluq (probel) əhəmiyyət kəsb edir. Beləki sətrin əvvəlinə iki boşluq qoysaq bu obyektin səviyyəsini təyin edir.&#x20;

```yaml
level1:
  level2:
    level3:
```

> Burada hər bir level bir obyektdir. Bu nümunədə `level1` obyektinin tərkibində `level 2`, `level 2` nin tərkibində isə `level 3` göstərilmişdir.

{% hint style="info" %}
YAML da əsasən tab istifadə edilmir. Beləkə tab üzrə məsafə standart təyin edilmir. bunun əvəzinə iki dəfə space yəni boşluq istifadə edilir.
{% endhint %}

> Hər bir level ya key-value cütlüyündən (YAML linqosunda dictionary kimi də adlandırılır) və ya ardıcıllıqdan 9sequency) (tirelərin siyahısı) ibarət ola bilər:

```yaml
level3:
  -
    itema: "one"
    itemameta: "two"
  -
    itemb: "three"
    itembmeta: "four"
```

> Hər bir key üçün dəyərlər istəyə bağlı olaraq (yəni optional) dırnaq içərisində verilə bilər.  Əgər sizin dəyərinizdə iki nöqtə və ya dırnaq işarəsi varsa onu dırnaq içərisində verin.

### Comparing JSON to YAML <a href="#comparing-json-to-yaml" id="comparing-json-to-yaml"></a>

> Bundan əvvəlki dərslərdə müxtəlif obyekt və array lər olan JSOn strukturlarına baxmışdıq. Gəlin indi də onların Yaml qarşılığı üzrə ekvivalentlərinə baxaq.

{% hint style="info" %}
You can use [Unserialize.me](http://www.unserialize.me/) dən istifadə edərək  JSON to YAML or YAML to JSON. faylları konvert edə bilərsiz.
{% endhint %}

JSON üzrə key value cütlüyü

{% code overflow="wrap" %}
```json
{
"key1":"value1",
"key2":"value2"
}
```
{% endcode %}

Eyni dəyərlərin YAML da alternativi

```yaml
key1: value1
key2: value2
```

JSON da array

```json
["first", "second", "third"]
```

YAML da array defis ilə göstərilir

```yaml
- first
- second
- third
```

Aşağıda isə JSON da iki obyekt üzrə array göstərilib

```json
{
"children": ["Avery","Callie","lucy","Molly"],
"hobbies": ["swimming","biking","drawing","horseplaying"]
}
```

YAML üzrə qarşılığı

```yaml
{
"children": ["Avery","Callie","lucy","Molly"],
"hobbies": ["swimming","biking","drawing","horseplaying"]
}
```

JSON da array daxilində iki obyekt göstərilib

```json
[  
   {  
      "name":"Tom",
      "age":43
   },
   {  
      "name":"Shannon",
      "age":41
   }
]
```

Aşağıda isə eyni dəyərlərin YAML-a konvert olumuş forması

```yaml
-
  name: Tom
  age: 42
-
  name: Shannon
  age: 41
```

Bununla belə, YAML daha çətin ola bilər, çünki bu, probeldən çox asılıdır. Bəzən bu məsafəni görmək çətindir (xüsusilə də mürəkkəb quruluşda) və JSON-da (bəlkə də daha çətin olsa da) problemi həll etmək daha asandır.

### Some features of YAML not present in JSON

YAML-də JSON-da çatışmayan bəzi xüsusiyyətlər var. `#` işarəsindən istifadə edərək YAML fayllarına şərhlər əlavə edə bilərsiniz. YAML həmçinin “anchors” adlanan elementdən də istifadə etməyə imkan verir. Məsələn, tutaq ki, sizdə oxşar olan iki definiton var.&#x20;

Definitonu bir dəfə yaza və hər ikisinə istinad etmək üçün göstəricidən istifadə edə bilərsiniz:\


```yaml
api: &apidef Application programming interface
application_programming_interface: *apidef
```

> Əgər bu dəryərləri götürsəniz hər ikisi üçün eyni izah (definition) istifadə olunacaqdır.&#x20;
>
> `*apidef` `&apidef-`də qurulmuş definiton üçün anchor və ya göstərici kimi çıxış edir.
>
> Siz OpenAPI tutorial-da bu unikal YAML xüsusiyyətlərindən istifadə etməyəcəksiniz, lakin JSON və YAML tam ekvivalent olmadığı üçün onları qeyd etmək lazımdır. For details on other differences between JSON and YAML, see [Learn YAML in Minutes](http://learnxinyminutes.com/docs/yaml/). To learn more about YAML, see this [YAML tutorial](http://rhnh.net/2011/01/31/yaml-tutorial).
>
> YAML is also used with [Jekyll](https://idratherbewriting.com/learnapidoc/pubapis\_jekyll.html). See my [YAML tutorial in the context of Jekyll](https://idratherbewriting.com/documentation-theme-jekyll/mydoc\_yaml\_tutorial) for more details.

### JSON versus YAML for the spec format <a href="#json-versus-yaml-for-the-spec-format" id="json-versus-yaml-for-the-spec-format"></a>

> JSON və YAML ətrafında bəzi məsələləri aydınlaşdıraq.&#x20;
>
> Mənim göstərəcəyim OpenAPI təlimatımdakı spesifikasiya sənədi YAML-dən istifadə edirəm, lakin JSON-da da ifadə oluna bilər. JSON YAML-in alt dəstidir, ona görə də ikisi praktik olaraq bir-birini əvəz edə bilən formatlardır (istifadə etdiyimiz məlumat strukturları üçün). Nəhayət, OpenAPI spesifikasiyası JSON obyektidir. Spesifikasiya qeyd edir:

{% hint style="info" %}
OpenAPI Spesifikasiyasına uyğun gələn OpenAPI sənədinin özü JSON və ya YAML formatında təqdim oluna bilən JSON obyektidir. (See [Format](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#format))
{% endhint %}

> Başqa sözlə, yaratdığınız OpenAPI sənədi JSON obyektidir, lakin siz bu obyekti həm JSOn ilə həmdə YAML ilə göstərə bilərsiniz.
>
> YAML daha oxunaqlıdır və daha çox yayılmış formatdır (see API Handyman’s take on [JSON vs YAML](https://apihandyman.io/writing-openapi-swagger-specification-tutorial-part-1-introduction/#json-vs-yaml) for more discussion), buna görə də mən YAML-dən buradakı kod nümunələrində istifadə etmişəm.&#x20;
>
> Siz görəcəksiniz ki, GitHub-da OpenAPI spesifikasiya sənədləri spesifikasiya formatlarını göstərərkən həmişə JSON və YAML sintaksisinin hər ikisini verirlər. (For a more detailed comparison of YAML versus JSON, see “Relation to JSON” in the [YAML spec](http://www.yaml.org/spec/1.2/spec.html).)

> YAML üç əsas termini olan məlumat strukturlarına istinad edir:&#x20;
>
> “mappings (hashes/dictionaries),&#x20;
>
> sequences (arrays/lists) və&#x20;
>
> scalars (strings/numbers)” &#x20;
>
> Bununla belə, OpenAPI spesifikasiyası JSON obyekti olduğu üçün o, JSON terminologiyasından istifadə edir - məsələn, “objects,” “arrays,” “properties,” “fields,”və s. Beləliklə, mən YAML formatlı məzmunu göstərəcəyəm, lakin onu JSON terminologiyasından istifadə edərək təsvir edəcəyəm.

### Review and summary

> Növbəti dərsləri daha yaxşı başa düşmək üçün gəlin bir daha məsələyə nəzər salaq.
>
> YAML-də hər level (iki boşluqlu abzas ilə müəyyən edilir) obyektdir. Aşağıdakı kodda `california` bir obyektdir. `animal`, `flower` və `bird` isə `california` obyektinin propertisi yəni xüsusiyyətləridir.\
>

```yaml
california:
  animal: Grizzly Bear
  flower: Poppy
  bird: Quail
```

JSON üzrə isə bu formada görünür

```json
{
  "california": {
    "animal": "Grizzly Bear",
    "flower": "Poppy",
    "bird": "Quail"
  }
}
```

The specification often uses the term “field” in the titles and table column names when listing the properties for a specific object. (Further, it identifies two types of fields — “fixed” fields are declared, unique names while “patterned” fields are regex expressions.) _Fields_ and _properties_ are used synonymously in the OpenAPI spec.

In the following code, `countries` contains an object called `united_states`, which contains an object called `california`, which contains several properties with string values:

> Aşağıdakı kodda `countries` obyektinə `united_states` obyekti daxildir buna isə `california` obyekti. `california` obyektinin isə bir neçə string dəyəri vardır.

```yaml
countries:
  united_states:
    california:
      animal: Grizzly Bear
      flower: Poppy
      bird: Quail
```

> Bu nümunədə isə `demographics`  obeyktinə array-lər daxildir.

```yaml
demographics:
 - population
 - land
 - rivers
```

JSON üzrə isə bu formada görünür

```json
{
  "demographics": [
    "population",
    "land",
    "rivers"
  ]
}
```

Ümid edirəmki bu qısa nümunələr bizə mövzunu başa düşməyə daha çox kömək olacaqdır.

#### İndi isə addım addım YAML sintaksisində OpenAPI code tutorial ilə tanış olaq
