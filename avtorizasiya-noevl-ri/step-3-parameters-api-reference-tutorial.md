# Step 3: Parameters (API reference tutorial)

> Parameter-lər Endpoint ilə göndərə biləcəyiniz dəyərlərdir. Bu dəyərlər qayıdan cavabda (bundan sonra Response) hansı dəyərlərin olmasını və ya Response-un formatını təyin edir.&#x20;
>
> Br neçə parameter növü vardır:
>
> * Header parameter
> * Path parameter
> * Query string parameter.
>
> Request body (sorğunun mətni) parametr funskiyasını daşıyır amma texniki olaraq parametr deyildir.&#x20;
>
> Yuxarıda göstərdiymiz Parameterin müxtəlif növləri adətən sənədləşmələrdə növlərinə aid qruplaşmalarda göstərilir. Məsələn Header parameter-ləri.
>
> Endpoint-lərdə göstərilən 3 növ Parametrin olması məcburi deyil.

### Examples of parameters <a href="#examples-of-parameters" id="examples-of-parameters"></a>

> The following screenshot shows a sample parameters section with the Box API:
>
> Aşağıdakı şəkildə [Mailchimp üzrə](https://mailchimp.com/developer/marketing/api/campaigns/get-campaign-info/) dizayn olunmuş Parameter nümunələrin yerləşdirmişəm.

![](../.gitbook/assets/param.PNG)

> Bu nümunədə Parameter-lər növlər üzrə qruplaşdırılmışdır. Path parameter və Query Parameter-ləri. Həmçinin də Path parametri olan `campaign_id` Endpoint-də tanınması üçün fərqli verilmişdir (fiqurlu mötərizədə).

#### [YouTube Parameters](https://developers.google.com/youtube/v3/docs/comments/list)

> Aşağıdakı nümunə YouTube-dandır. Gördüyünüz kimi burada Parameter-lər fərqli formada verilmişi və Required, optional olmasına görə qruplaşdırılmışdır. Parameter növü isə yaşıl ilə işarələdiyim kimi şərh daxilində göstərilmişdir.

![](../.gitbook/assets/youtube\_param.PNG)

> You can format the values in a variety of ways (aside from a table). If you’re using a definition list or other non-table format, be sure to develop styles that make the values easily readable.
>
> Siz fərqli formalarda bunu göstərə bilərsiniz. Bu mövzumuzun məqsədi Parametr-ləri öyrənmək və onların fərqlərini bilməkdir. Bu səbəbdən də, növbəti mövzularda "Best Practice" sənədləşmələri göstərəcəm.
>
>

{% hint style="info" %}
Parameter-ləri hansı formada verməyinizdən asılı olarmayaraq tövsiyyə edirəm ki, onları qruplaşdırıb gözə çarpan formada Developerlərə çatdırasınız.&#x20;
{% endhint %}

### Parameter növləri

> REST API-nin qeyd etdiyimiz kimi bir neçə parameter növü vardır:
>
> * **Header parameter:** Request header-ə əlavə olunan dəyərlərdir və adətən avtorizasiya ilə əlaqəli olur. Bundan əvvəlki API təhlükəsizlik mövzusunda buna istinad etmişdik.
> * **Path parameter:** Endpoint daxilində query string **(?)** işarəsindən əvvəl gələn dəyərlərdir. Adətən fiqurlu mötərizə **({})** ilə göstərirlər.
> * **Query string parameter:** Endpoint-in query string dəyərləridir. !uery string **(?)** işarəsindən sonra gəlir.
>
> Another property closely related to parameters, and which used to be [referred to as a parameter in OpenAPI v2.0](https://swagger.io/docs/specification/2-0/describing-request-body/), is the request body, or [`requestBody`](https://swagger.io/docs/specification/describing-request-body/) in OpenAPI code form. The request body is usually only used with CREATE or PUT methods and often includes a JSON object included in the body of the request. More details are provided in [Request bodies](https://idratherbewriting.com/learnapidoc/docapis\_doc\_parameters.html#request\_bodies).

### What to note in parameter documentation <a href="#what-to-note-in-parameter-documentation" id="what-to-note-in-parameter-documentation"></a>

> Parametr-ləri göstərərkən onların aşağıdakı xassələrinidə mütləq qedy edin.
>
> * [Data type](https://idratherbewriting.com/learnapidoc/docapis\_doc\_parameters.html#data\_types\_parameters) (Məlumüt növü)
> * [Max və min dəyər](https://idratherbewriting.com/learnapidoc/docapis\_doc\_parameters.html#max\_min\_values)
>
> #### Parametrlər üçün Data type-lar
>
> Əgər API parametrinin Data type-ı və ya formatı düzgün olmazsa, bu zaman API-lar proqramlaşdırıldıqdan sonra dəyərlər emal olunmayacaqdır. Bütün dəyərlərin Data type-larını qeyd etmək lazımdır.&#x20;

{% hint style="warning" %}
Əgər sizin Parameter-lərinizdən birinin formatı **string** olmalıdırsa və siz sənədləşmədə onu **integer** göstərirsinizsə, API hazırlandıqdan sonra ora daxil edilmiş dəyər emal olunmayacaq və nəticədə Proqram təminatı işləməyəcəkdir.&#x20;

Məsələn, nümunədə bizə Credit kartımızın balansı lazımdır və biz parameter kimi CreditCard yazıb göndəririk. Amma yazılmış proqram bu Parameter üçün bizdən yalnız rəqəm gözləyir və CreditCard sözünə error qaytarır.
{% endhint %}

> REST API-lər üzrə ən çox istifadə edilən data type-lar:
>
> * **string**: An alphanumeric sequence of letters and/or numbers
> * **integer**: A whole number — can be positive or negative
> * **boolean**: True or false value
> * **object**: Key-value pairs in JSON format
> * **array**: A list of values

{% hint style="warning" %}
Proqramlaşdırmada daha çox Məlumat növləri vardır. Əgər sizdə xüsusi ilə qeyd etmək istədiyiniz məlumat növü varsa bunu mütləq sənədləşmədə qeyd edin.&#x20;

Məsələn, Java dili üzrə proqramlaşdırma edərkən icazə verilən məlumat növünü qeyd etmək vacibdir, çünki Java verilənlərin ölçüsünə əsasən yaddaş sahəsi ayırır. Beləliklə, Java ölçülərin daha dəqiq olmasını xoşlayır. Məsələn, byte, short, int, double, long, float, char, boolean, və s. var.&#x20;

Bununla belə, siz REST API sənədləşməsində bu səviyyədə detala düşməli deyilsiniz. bunları proqramçı arxitektlər təyin edirlər. Amma proqramlaşdırma bilyiniz varsa və əminsinizsə, qeyd etməyiniz çox yaxşı olar.

Məsələn mən hər zaman sənədləşmələrdə enum məlumat növünü göstərirəm. Enum məlumat növü o halda istifadə olunurki, sizin daxil etmək üçün bəlli sayda dəyəriniz olur. Məsələn, nümunədəki kimi, hansı kartın abalansın əldə etmək üçün, sizdə 4 seçim var CreditCard, DebitCard and others. Bu səbəbdəndə CardType filed-nin məlumat növü enumdır.&#x20;
{% endhint %}

#### Max and min values for parameters <a href="#max_min_values" id="max_min_values"></a>

>
>
> Data type-ları müəyyən etməkdən savayı, həmçinin də parametrlər üzrə minimum, maximum və olduğu təqdirdə icazə verilən dəyərləri göstərməliyik. For example, if the weather API allows only longitude and latitude coordinates of specific countries, these limits should be described in the parameters documentation. Omitting information about max/min values or other prohibited values (when applicable) is a common pitfall in docs.,&#x20;
>
> Not every parameter needs max and min values, however. Note these exceptions:
>
> Bununla belə, hər parametrin maksimum və min dəyərlərini göstərməyə bəzən ehtiyac olmur: Məsələn,
>
> * **Booleans**: Bu dəyər üzrə yeganə seçimlər true və ya false-dur. Bu səbəbdən də burada max/min göstərməyə ehtiyac yoxdur.
> * **Strings that use enums**: If a string restricts possible values to enums (an enumerated list), the max/min values wouldn’t be appropriate. For example, a geo-related enum might allow only these values: north, south, east, west. There is no max/min value in this case.
>
> Ümumiyyətlə proqram ilkin testləşdirmə üçün hazır olduqdan sonra, Boolean və enum-dan fərqli data type-lara icazə verilən parameter-ləri (məs, string, integer) yoxlayın. məsələn, API-da ID sahəsi olarsa həmin sayə 300 simvol uzunluğunda, əgər fayl əlavə edə bilərsinizsə 100 MB həcmində əlavə etməyə çalışın. Əmin olun ki, API normal qaydada sorğularınızı emal edəcəkdir.

> Bizim vəzifəmiz proqramçıların işini tam rahatlaşdırmaq və dəqiq tələblər verməklə sonradan yaranacaq qarışıq situasiyaların qarşısını almaqdır. Bu səbəbdəndə, sahələr üzrə tətbiq olunan məhdudiyyətləri mütləq göstərin. Çünki onları sizdən yaxşı bilən olmayacaq.
>
> Çox vaxt nə proqramçılar nə məhsul komandanız nə də QA komandanız bu məhdudiyyətləri bilmir və nəticədə əsas mühitdə istifadəçilər kobud səhvlər ilə qarşılaşırlar.\
>

{% hint style="warning" %}
API-ları prqramçılardan təhvil alıb testləşdirən zaman mütləq fərqli formalarda parameterlər ilə yoxlayın. Məsələn, tələb olunan parametrdən az və ya çox, səhv parametter və s. Baxın görən hansı formada error cavabları qaydacaqdır.&#x20;

Tesləşdirmə, qayıdan error kodları və s.haqqında növbəti məqalələrimizdə danışacağıq.
{% endhint %}



### Header parameters

> header parametr-ləri sorğu başlığına (request header) əlavə edilir. Adətən bu dəyərlər bütün endpoint-lərə aid olmaqla avtorizasiya parametrləri olur və bütün endpointlərə aid olur; yəni header parametrin sənədləşmədə bir dəfə göstərilir və o bütün endpoint-lərdə təkara göstərilmir. Buna baxmayaq, Header parametrləri üzrə avtorizasiya detalları sənədləşmədə ayrıca bölmə kimi adətən **avtorizasiya tələbləri** bölməsində göstərilir.

{% hint style="info" %}
Avtorizasiya və Authentifikasiya üzrə detallı məlumat ilə bundan əvvəlki mövzumda tanış ola bilərsiniz. [API Təhlükəsizliyi](https://multibank.gitbook.io/api-security/)
{% endhint %}

\


