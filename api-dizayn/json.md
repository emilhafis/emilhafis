# JSON

### Parametrlər üzrə qeyd edilməli məqamlar

> **Parametr**-ləri göstərərkən onların aşağıdakı xassələrini də mütləq qeyd edin.
>
> * [Data type ](json.md#data-type-m-lumat-noevl-ri)(Məlumat növü)
> * [Max və min dəyərlər](json.md#max\_min\_values)

#### Data type (Məlumat növləri)

> #### Parametrlər üçün Data type-lar
>
> Əgər **API** parametrinin **Data type**-ı və ya formatı düzgün olmazsa, bu zaman **API**-lar proqramlaşdırıldıqdan sonra dəyərlər emal olunmayacaqdır.&#x20;
>
> Bu səbəbdən də, bütün dəyərlərin [**Data type**](json.md#value-uezr-data-type-lar)-larını qeyd etmək lazımdır.&#x20;

{% hint style="warning" %}
Əgər sizin Parameter-lərinizdən birinin formatı **string** olmalıdırsa və siz sənədləşmədə onu **integer** göstərirsinizsə, API hazırlandıqdan sonra ora daxil edilmiş dəyər emal olunmayacaq və nəticədə Proqram təminatı işləməyəcəkdir.&#x20;

Məsələn, nümunədə bizə Credit kartımızın balansı lazımdır və biz parameter kimi CreditCard yazıb göndəririk. Amma yazılmış proqram bu **Parametr** üçün bizdən yalnız rəqəm gözləyir və CreditCard sözünə **error** qaytarır.
{% endhint %}

Data Type ları haqqında məlumat verməmişdən öncə istərdim ki, JSON üzrə sizə məlumat verim və ondan sonra fieldlər üzrə istifadə olunan data type ları analiz edək

### JSON üzrə ümumi məlumat

**JSON**, _**JavaScript Object Notation**_ deməkdir. **JSON** məlumatları **Strukturlaşdırılmış Məlumat** kimi təqdim etmək üçün insan və maşın tərəfindən oxuna bilən formatdır. JSON **əsasən** məlumatları bir kompüterdən digərinə və ya hətta eyni kompüterdəki müxtəlif proqramlar arasında ötürmək üçün istifadə olunur.

JavaScript prorqramlaşdırma dilidir və JSOn məlumatlrın strukturlaşdırılmış formada bu proqram təminatında istifadəsi üçün yaradılmışdır. Cammaat bunun rahatlığın görəndən sonra artıq demək olarki çox yerdə istifadə etməyə başlayıb. Və indi Veb API larında əsasən JSOn formatında məluamt mübadiləsi həyata keçirilir. Bunu siz bu günəkimi olan dərslərdə şahidi olmusuz.

### JSON Data Types

JSOn da sadə data typelardan istifadə olunur. Hansıkı bir az əvvəl danışdıq

* String - Rəqəmlər, hərflər xüsusi işarələr və s. istifadə oluna bilər
* Number - İnteger kimi mənfi və müsbət ədədlər
* Boolean - Stringdən fərqli olaraq burada dırnaq işarəsinə ehityac olmur
* Null - Dərnaq işarəsin işlədə bilərsiz. mƏnası heç nə deməkdir

### Array

Bunlardan əlavə olaraq, JSON da array və object data type-ıda vardır. Buradakı dəyərlər mötərziələr içərisində olur və bir birindən vürgül ilə ayrılır.

Arraydəki məlumat növləri fərqli ola bilər. Nümunəyə baxaq.

### Objects

JSOn da objecct dicitionries adlanır. **Strukturun göstərmək.** burada bütün data typelar ola bilər amma əsasən string istifadə edilir.

Here's an example of an object that holds values for red green and blue. You can see that the first key is this string red which has a value of 2 0 5. These are separated by a colon. Then there is a comma and then the next key is green with a value of 123 and the same for blue.Everything is enclosed in curly brackets.

### Nested

Nesting mənası odurki obyektləri bir birinin içərisindədir. Yəni qarışıqdır. Siz müxtəlif təbəqələi məlumatlar üçün array ləri obyektlərin və obyektləridə obyektlərin içərisində verə bilərsiniz.&#x20;

Example

Let's look at an example&#x20;

Jason File that captures information about a song.&#x20;

It starts with a curly bracket. So that means that the whole thing is an object. The object has only one key value pair the key of that key value pair is the string song.

The value starts with a curly bracket.So that means that the value is another object.This is a really common way for Jason files to begin because it informs immediately what the object is supposed to represent.In this case a song inside the song object you can see that there are three keys.Title artist and musicians.The value for the title and artist keys are also strings.The value for the musicians key starts with the bracket.So that means it's an array.The array has four strings in it.Each separated by commas I'll go over this whole file one more time just so that you can see it from a slightly different point of view. This data on file consists of two objects.Note that there are two pairs of curly brackets and one array.Note that there is one pair of square brackets from a nesting point of view the top object contains the second object which contains the array. The top object has only one key which is song. The value of song is the second object which contains the song data. The first key of the data is title which has a value of Hey Jude.The second key is artist which has the value of the Beatles and the Laskey musicians which has a value that is an array of strings which is the Beatles names.

> <mark style="color:orange;">**object**</mark><mark style="color:orange;">:</mark> JSON formatı üzrə object (obyekt) **key-value** cütlüyünü bildirir. **Key-value** cütlərinin bu kolleksiyası <mark style="color:orange;">{fiqurlu mötərizlərin açılması və bağlanması ilə}</mark> <mark style="color:orange;">{ }</mark> qruplaşdırılır.
>
> Obyektin yazılması qaydaları
>
> * _**Key-value** cütlüyü **vergül**  **,** ilə ayrılmalıdır_
> * _Hər bir **obyekt** Fiqurlu mötərizənin açılması <mark style="color:orange;">{</mark> ilə **başlamalıdır**_
> * _Hər bir **obyekt** Fiqurlu mötərizənin bağlanması <mark style="color:orange;">{</mark> ilə **bitməlidir**_
>
> Aşağıdakı nümunə **Person** obyektidir. **Person** obyektində qeyd olunan qaydalara əməl edilmişdir.

Məsələn, bizim yoxladığımız bütün API larda məlumat mübadiləsi JSON üzərindən edilir. Amma bu o demək deyilki mütləq JSOn olmalıdır. XML də ola bilər. Amma JSOn çox sadə olduğu üçün demək olarki hamı JSON istifadə edir

```javascript
{
 "FirstName" : "Anar",
 "Age"  : 32,
 "isMan"       : true,
 "Profession": "Developer"
}
```

> Burada <mark style="color:blue;">iki nöqtədən :</mark> solda olanlara **`key`** , sağda olanlara isə **`value`** deyilir. Yəni - <mark style="color:blue;">`"FirstName"`</mark> **Key**, `"Anar"` isə **value**-dir.

> * <mark style="color:orange;">**array**</mark>: Dəyərlərin listi.
>
> Proqramlaşdırma dillərində istifadə olunan Array anlayışı ilə eynilik təşkil edir. **JSON**-da **Array** _Vergül_ ilə ayrılmış dəyərlər toplusundan ibarətdir.&#x20;
>
> **Array**-in hazırlanması üçün qaydalar:
>
> * _**Array** düz mötərizənin açılması **\[** ilə başlayır_
> * _**Array** düz mötərizənin bağlanması **]** ilə bitir_
> * _**Array**-dəki məlumatlar Vergül **,** ilə ayrılır_
>
> **Array**-i tam başa düşmək üçün gəlin aşağıdakı nümunəyə baxaq.
>
> Deyək ki, Anarın **hobbisi**-də vardır və biz onu **Person Object**-nə əlavə etməliyik. Onun hobbisi _Video oyunlarıdır_. Gəlin **object**-ə `key-value` əlavə edək

```javascript
{
 "FirstName" : "Anar",
 "Age"  : 32,
 "isMan"       : true,
 "Profession": "Developer",
 "Hobbies"   : "Videos games"
}
```

> Göründüyü kimi burada bir problem yoxdur. Bəs Anarın 1-dən artıq hobbisi olsa nə edəcəyik? Məsələn - _Video oyunları, Komputer, Musiqi_. Bunun üçün **Person Object**-in 3 dəfə təkrarlayacağıq?

```javascript
{
 "FirstName" : "Anar",
 "Age"  : 32,
 "isMan"       : true,
 "Profession": "Developer",
 "Hobbies"   : "Videos games"
}
{
 "FirstName" : "Anar",
 "Age"  : 32,
 "isMan"       : true,
 "Profession": "Developer",
 "Hobbies"   : "Computers"
}
{
 "FirstName" : "Anar",
 "Age"  : 32,
 "isMan"       : true,
 "Profession": "Developer",
 "Hobbies"   : "Music"
}
```

> <mark style="color:red;">**XEYR.**</mark> Bunun üçün **Array**-dən istifadə edilməlidir.

```javascript
{
 "FirstName" : "Anar",
 "Age"  : 32,
 "isMan"       : true,
 "Profession": "Developer",
 "Hobbies"   : ["Videos games", "Computers", "Music"]
}
```

> Bu nümunə JSON üzrə Array-dən düzgün istifadə olunan nümunədir.

### JSON dəyərləri üzrə Data type-lar

> * <mark style="color:orange;">**string**</mark><mark style="color:orange;">:</mark> Hərflərdən və ya rəqəmlərdən ibarət dəyərlər.
>
> Məsələn - nümunədəki `"Anar"` <mark style="color:orange;">string</mark>-dir.

> * <mark style="color:orange;">**integer**</mark><mark style="color:orange;">:</mark> Mənfi və müsbət tam ədədlər
>
> Məsələn - nümunədəki `32` <mark style="color:orange;">integer</mark>-dir.

> * <mark style="color:orange;">**boolean**</mark><mark style="color:orange;">:</mark> true və ya false dəyəri (yalnız iki dəyər olur, təsdiq və inkar)
>
> Məsələn - nümunədəki `true` <mark style="color:orange;">boolean</mark>-dır.

{% hint style="warning" %}
Proqramlaşdırmada daha çox data type (məlumat növləri) vardır. Əgər sizin xüsusi ilə qeyd etmək istədiyiniz məlumat növü varsa bunu mütləq sənədləşmədə qeyd edin.&#x20;

Məsələn, Java dili üzrə proqramlaşdırma edərkən icazə verilən məlumat növünü qeyd etmək vacibdir, çünki Java verilənlərin ölçüsünə əsasən yaddaş sahəsi ayırır. Beləliklə, Java ölçülərin daha dəqiq olmasını xoşlayır. Məsələn, byte, short, int, double, long, float, char, boolean, və s. var.&#x20;

Bununla belə, siz **REST API** sənədləşməsində bu səviyyədə detala düşməli deyilsiniz. bunları proqramçı arxitektlər təyin edirlər. Amma proqramlaşdırma biliyiniz varsa və əminsinizsə, qeyd etməyiniz çox yaxşı olar.

Məsələn, mən hər zaman sənədləşmələrdə **enum** məlumat növünü göstərirəm. **Enum** məlumat növü o halda istifadə olunurki, sizin daxil etmək üçün bəlli sayda dəyəriniz olur. Məsələn, yuxarıda göstərdiyimiz nümunədə biz Credit kartı üzrə balansı əldə etdik. Bizə kartın növləri (**CardType**) üzrə 2 fərqli seçim verilə bilər - **CreditCard, DebitCard**.&#x20;

Əgər bizim **CardType** üzrə bəlli sayda seçimimiz olursa bu məlumat növü **enum** adlanır.&#x20;
{% endhint %}

double da göstərməyiniz yaxşıdır. Çünki amount ilə çox işləyəcəksiz

### Max and min dəyərlər <a href="#max_min_values" id="max_min_values"></a>

> **Data type**-ları müəyyən etməkdən savayı, həmçinin də **parametrlər** üzrə **minimum**, **maximum** və olduğu təqdirdə **icazə verilən** dəyərləri göstərməliyik.&#x20;
>
> Bununla belə, hər parametrin _maksimum_ və _min_ dəyərlərini göstərməyə bəzən ehtiyac olmur: Məsələn,
>
> * <mark style="color:orange;">**Booleans**</mark>: Bu dəyər üzrə yeganə seçimlər **true** və ya **false**-dur. Bu səbəbdən də burada _max/min_ göstərməyə ehtiyac yoxdur.
> * <mark style="color:orange;">**Enums**</mark>: Bundan əvvəldə qeyd etdiyimiz kimi, əgər string mümkün dəyərləri (an enumerated list) tələb edərsə bu zaman _max/min_ göstərməyə ehtiyac yoxdur. Məsələn, API-da **yarımkürə** field-imiz varsa burada mümkün 4 dəyər ola bilər - _şimal, cənub, şərq və qərb_. Bu səbəbdən də burada max/min dəyərlərinə ehtiyac olmur.
>
> Ümumiyyətlə proqram ilkin testləşdirmə üçün hazır olduqdan sonra, <mark style="color:orange;">boolean</mark> və <mark style="color:orange;">enum</mark>-la yanaşı digər **data type**-lara icazə verilən parameter-ləri (məs, <mark style="color:orange;">string</mark>, <mark style="color:orange;">integer</mark>) yoxlayın. Məsələn, API-da ID sahəsi olarsa həmin sahəyə 300 simvol uzunluğunda, əgər fayl əlavə edə bilərsinizsə 100 MB həcmində əlavə etməyə çalışın. Əmin olun ki, API normal qaydada sorğularınızı emal edəcəkdir.

{% hint style="danger" %}
Bizim vəzifəmiz proqramçıların işini tam rahatlaşdırmaq və dəqiq tələblər verməklə sonradan yaranacaq qarışıq situasiyaların qarşısını almaqdır. Bu səbəbdən də, sahələr üzrə tətbiq olunan məhdudiyyətləri mütləq göstərin. Çünki onları sizdən yaxşı bilən olmayacaqdır.

Çox vaxt nə proqramçılar, nə məhsul komandanız, nə də QA komandanız bu məhdudiyyətləri düzgün təyin etmir və ya testləşdirmir və nəticədə əsas mühitdə istifadəçilər kobud səhvlər ilə qarşılaşırlar.
{% endhint %}

{% hint style="warning" %}
API-ları proqramçılardan təhvil alıb testləşdirən zaman mütləq fərqli formalarda parametrlər ilə yoxlayın. Məsələn, tələb olunan parametrdən az və ya çox, səhv parametr və s. Düzgün formada error cavablarının qayıtdığından əmin olun.&#x20;

_Tesləşdirmə, qayıdan error kodları və s. haqqında növbəti məqalələrimizdə danışacağıq_.
{% endhint %}
