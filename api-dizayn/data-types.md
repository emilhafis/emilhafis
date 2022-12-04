# Data Types

API Writer olaraq sizin əsas işiniz Məlumat növlərini təyin etmək olacaq.

Bu mövzuda mən xüsusilə Veb API üzrə data typelar necə təyin olunur onları bildirəcəm sənə.

Softvare development edən zaman hər bir məlumatın müvafiq data type ı olur.&#x20;

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Ən çox istifadə olunan növlər bunlardır.&#x20;

* Integer - mənfi və müsbət tam ədədlər
* Decimal - kəsr olan ədədlər. Ən çox amount da bundan istifadə olunur. Məsələn 1.10 qəpik
* Text
* True or false
* Date - Tarix və d
* Həmçinində siz öz API nəza məxsus type yarada bilərsiz. Məsələn Hesab nömrəsi üzrə yazsanız IBAN bu o deməkdirdiki burada IBAN strukturu olmalıdır.

### JSON Data types

API üzrə məlumat mübadiləsində JSON istifadə olunur deyə, JSOn data typelarına baxaq.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

JSON çox sadadir və orada 3 tipdən istifadə olunur

* Number
* String
* Boolean

#### String

String texniki termindir və mansı tekst deməkdir. Mahiyyətcə birləşmiş mətn simvolları qrupudur. -&#x20;

* Adətən string tək və ya cüt dırnaq işarəsinin içərisində olur
* String tərkibinə rəqəmlər, hərflər xüsusi işarələr və daxil ol abilir
* Həmçinində boşluq işarəsidə götürülür

Gəlin nümunəyə baxaq

#### Boolean

Boolean adı qəliz görünsədə özü çox sadədir. Bunu xeyli vaxt əvvəl riyaziyyatçı George Boole yaratmışdır. Bilməli olduğunuz yalnız odurki bu növdə iki dəyər vardır true və ya false.

Gəlin nümunədə baxaq

<figure><img src="https://lh6.googleusercontent.com/FeqA90MLkBPjz5NxgEDoA3VASp8gflyzMsl7mWNWrJwslrFipZkM0C-o_xLITZADxmYOBDS226adToTJWetUETgRE4Lhmd-zvzwvMhXQZ8aWAMxVEQ_YkrzXZeJ_ABlN-HTuSpR2W3RLdBeETw1Boq-C6PH__n_1WlnoZ03CDbHloasbdJ-bZ2--tOtnzO71r2kl5nMA3Q=s2048" alt=""><figcaption></figcaption></figure>

Bu Facebookdan üscreen shot dur.&#x20;

This is a screen shot from a Facebook profile.

Once I make changes and submit it, it'll send data back to Facebook.

Of course the data will have data types.

Let's see if we can find all three of the data types that I've talked about.

Well, string is easy. The current city and hometown are both strings.

Numbers are easy, too. The day and year of the birthday are clearly numbers.

What about Booleans?

It has a value of true if it's checked and false if it's not.

### Array

* Array məlumatlar listidir. Listdəki məlumatların ölçüsü olur
* Listdəki məlumatlaırn sırlaması vacibdir. yəni hansı məlumat hansından sonra gəlir. Çünki Proqram yazılarkən həmin məlumata gedib çıxmaq üçün sırlamadan istifadə olunur. Buna Dot notation deyilir. Buna növbəti mövzularda göz gəzdirəcəyik
* Məsələn sizin rəqəmlərdən ibraət və ya stringlərdən ibarət listiniz ola bilər. Həçinində siin list içərisində listiniz ola bilər.

### Object or Dictionary

Burada data key listi və onun dəyərləri olur. İdea ondan ibarətdirki siz key dən istifadə edib onun dəyərini tapa bilərsiniz. Fikirləşinki biz lüğəti necə istifadə edirik. Hər bir sözün mənası olur. Əgər bizim dictionrimiz elektorndursa onda biz söz veririk və mənası qayıdır.&#x20;

Gəlin nümunə üzərindən baxaq.&#x20;

Güman edəkki bizdə məlumatlar var və biz bilirik ki USAnin 7 regionu var. İndi biz istəyirikk i, biz region adı verək və bizə ordakı rayonları qaytarmalıdır.&#x20;

**Your dictionary might look like this. In front of the colon is the key -- a string in quotes -- and after the**

### Structured data. Nested JSON

Nested JSON array və objectlördən ibarət olur. Array başqa arraydən object isə başqa objectlərdən ibarət ola bilər. Nə qədər istəsəz şaxələndirə bilərsiz amma ehtiyatlı olun.

> Structured data combines data types and collections. Collections can consist of other
>
> collections.
>
> In other words, you can have a dictionary of lists, or a list of dictionaries, a dictionary of dictionaries,
>
> and so on.
>
> You can have as many levels as you need. What you end up with is a tree structure where each collection
>
> is a branch and at the end of each branch is a data value.
>
> You may be wondering what this has to do with APIs.
>
> The answer is very simple.
>
> As I mentioned in the introductory lecture API, I have requests and responses. The responses almost always
>
> return information from the server in the form of structured data and sometimes the request uses structured
>
> data to pass information to the server
>
> That's all for structured data.
>
> Next take the quiz to see how much you've learned.
>
> Autoscroll
>
>

### Parametrlər üzrə qeyd edilməli məqamlar

> **Parametr**-ləri göstərərkən onların aşağıdakı xassələrini də mütləq qeyd edin.
>
> * [Data type ](data-types.md#data-type-m-lumat-noevl-ri)(Məlumat növü)
> * [Max və min dəyərlər](data-types.md#max\_min\_values)

#### Data type (Məlumat növləri)

> #### Parametrlər üçün Data type-lar
>
> Əgər **API** parametrinin **Data type**-ı və ya formatı düzgün olmazsa, bu zaman **API**-lar proqramlaşdırıldıqdan sonra dəyərlər emal olunmayacaqdır.&#x20;
>
> Bu səbəbdən də, bütün dəyərlərin [**Data type**](data-types.md#value-uezr-data-type-lar)-larını qeyd etmək lazımdır.&#x20;

{% hint style="warning" %}
Əgər sizin Parameter-lərinizdən birinin formatı **string** olmalıdırsa və siz sənədləşmədə onu **integer** göstərirsinizsə, API hazırlandıqdan sonra ora daxil edilmiş dəyər emal olunmayacaq və nəticədə Proqram təminatı işləməyəcəkdir.&#x20;

Məsələn, nümunədə bizə Credit kartımızın balansı lazımdır və biz parameter kimi CreditCard yazıb göndəririk. Amma yazılmış proqram bu **Parametr** üçün bizdən yalnız rəqəm gözləyir və CreditCard sözünə **error** qaytarır.
{% endhint %}

Data Type ları haqqında məlumat verməmişdən öncə istərdim ki, JSON üzrə sizə məlumat verim və ondan sonra fieldlər üzrə istifadə olunan data type ları analiz edək

### JSON üzrə ümumi məlumat

**JSON**, _**JavaScript Object Notation**_ deməkdir. **JSON** məlumatları **Strukturlaşdırılmış Məlumat** kimi təqdim etmək üçün insan və maşın tərəfindən oxuna bilən formatdır. JSON **əsasən** məlumatları bir kompüterdən digərinə və ya hətta eyni kompüterdəki müxtəlif proqramlar arasında ötürmək üçün istifadə olunur.

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
