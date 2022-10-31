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

Each level can contain either a single key-value pair (also referred to as a _dictionary_ in YAML lingo) or a _sequence_ (a list of hyphens):

> Hər bir key üçün dəyərlər istəyə bağlı olaraq (yəni optional) dırnaq içərisində verilə bilər.  Əgər sizin dəyərinizdə iki nöqtə və ya dırnaq işarəsi varsa onu dırnaq içərisində verin.
