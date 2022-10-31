# SwaggerHub introduction and tutorial

> Bundan əvvəlki bölmədə open source proyekt (Pet) vasitəsilə Swagger UI-də Open API spesifikasiyasına baxdıq. Bu kompaniya Swaggerin Editor və UI versiyalarını pulsuz olaraq istifadəyə verib. Həmçinin də bunların [SwaggerHub](https://app.swaggerhub.com/) adlanan premium məhsulları vardır.&#x20;
>
> [Buradan](https://swagger.io/tools/swaggerhub/opensource-comparison/) həmin versiyalar üzrə müqaisəni görə bilərsiniz.

<figure><img src=".gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

### SwaggerHub qeydiyyat və Yaml import

> SwaggerHub da qeydiyyatdan keçək.

<figure><img src=".gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

Qeydiyyatdan keçdikdən sorna gördüyünüz kimi ekran açılır. Burada `Create` new edib seçimləri görə bilərik.

<figure><img src=".gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Burada olan Create new API məsələsinə növbəti dərslərdə baxacağıq və manual olaraq Open API spec yaradacağıq.

İndi isə Stoplight da yaratdığımız Open API spesifikasiyasını bura add edib hansı formada parse olunduğuna baxaq. Xatırlayırsınızsa bildirmişdimki əlinizdə YOpen API spec varsa müxtəlif platformalara onu import edə bilərsiz, bir sözlə çox üstünlük verir.

1. Bunun üçün Stoplight a daxil oluruq. Yaml faylı üzərinə klik edirik.

<figure><img src=".gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

2\. Ya export edirik yaml üzərindən yada sağda Code hissəyə klik edib kop edirib save edirik.

<figure><img src=".gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

3\. Əldə etdiyimiz faylı Svagger Hub a import edirik.

<figure><img src=".gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

4\. İmport etdikdən sonra aşağıdakı kimi səhifə qarşımıza çıxır&#x20;

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Qeyd edildiyi kimi burada problem Open API spec versiyasındadır. Belə ki Spotlight 3.1.0 versiyasın istifadə edir , amma Svagger bu yeni versiyanı dəstəkləmir. Ona görə də spesifikasiyada versiyanı 3.0.0 edirik.
{% endhint %}

5\. Bu dəyişikliyi etdikdən sonra spefisifikaımız emal olunur və Svagger onu vizual interfeysdə göstərir. Həmçinin də xətaları svagger göstərir. Versiya fərqinə əsasən bir çox xətalar yaranır. Amma ən əsası istədiyimiz nəticəni aldıq.

<figure><img src=".gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

Burada User model və summary əvəvlki versiyada olmadığı üçün dəstəkləmir. Qalan məsələlər qaydasındadır

### Share URL

![](https://lh6.googleusercontent.com/7y0118RV5c5OCCOoOUOGbF22YYQEgXw\_LoPCTropkYQQi\_P\_gDR9Q3PjmNFoxYqFmLGQKbvsfTR6hKlP7qaMRz3wViDMF2pF-vp-lHByS1ADAFhuarQcEUpZ07UAZ7w4I\_IUY4JgjJgAjfr6dKBaOy3Eg4p8yusI5nImDqo\_bpZXv2eH0K4YiOhVHGsJPxg)

Publich URL əldə edib lazımlı tərəflər ilə bölüşə bilərsiz.

### Advantages of SwaggerHub

While the open-source Swagger Editor coupled with Swagger UI works, you’ll run into several problems:

* It’s challenging to collaborate with other project members on the spec.
* It’s difficult to gather feedback from reviewers about specific parts of the spec.
* You can’t automatically provide the API in the myriad code frameworks your users might want it in.

When you’re working on REST API documentation, you need tools specifically designed for REST APIs — tools that allow you to create, share, collaborate, version, test, and publish the documentation in ways that don’t require extensive customization or time.

There’s a point at which experimenting with the free Swagger UI tooling hits a wall, and you’ll need to find another way to move to the next level. This next level is where [SwaggerHub](https://swaggerhub.com/) from [Smartbear](https://smartbear.com/) comes in. SwaggerHub provides a complete solution for designing, managing, and publishing documentation for your API in ways that will simplify your life as an API technical writer.

More than 15,000 software teams across the globe use SwaggerHub. As the OpenAPI spec becomes more of an industry standard for API documentation, SwaggerHub’s swagger-specific tooling can be essential.\


### SwaggerHub Intro and Dashboard <a href="#swaggerhub-intro-and-dashboard" id="swaggerhub-intro-and-dashboard"></a>

[Smartbear](https://smartbear.com/) is the company that maintains and develops the open source Swagger tooling ([Swagger Editor](https://swagger.io/swagger-editor/), [Swagger UI](https://swagger.io/swagger-ui/), [Swagger Codegen](https://swagger.io/swagger-codegen/), and others.) They also formed the [OpenAPI Initiative](https://www.openapis.org/), which leads the evolution of the [Swagger (OpenAPI) specification](https://github.com/OAI/OpenAPI-Specification/).

Smartbear developed SwaggerHub as a way to help teams collaborate around the OpenAPI spec. Many of the client and server SDKs can be auto-generated from SwaggerHub, and there are a host of additional features you can leverage as you design, test, and publish your API.

To get started with SwaggerHub, go to [swaggerhub.com](https://swaggerhub.com/) and create an account or sign in with your GitHub credentials. After signing in, you see the SwaggerHub dashboard.

<figure><img src=".gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

The dashboard shows a list of the APIs you’ve created. In this example, you see the [OpenWeatherMap API](https://idratherbewriting.com/learnapidoc/docapis\_scenario\_for\_using\_weather\_api.html) that I’ve been using throughout this course.

### SwaggerHub Editor <a href="#swaggerhub-editor" id="swaggerhub-editor"></a>



SwaggerHub gördüyünüz kimi sizə online API validation xidmətidə verir. Beləki siz istənilən Yamlı copy past edərək onun valid olmasın yoxlaya bilərsiz. Swagger Editordan f'rqli olaraq burda bir ne,' funksionallıqdan yaralana bilərsiz.

* Hide Navigation
* Hide Editor and Navigation
* Hide UI Docs

<figure><img src="https://lh5.googleusercontent.com/MjqgEePUbgLXCYmT7gNIps7mK9Qzm0h4gcsd80iJR4fUYkXngjn0CIUpxTAc_i_7UDVcXgBxqs_Pxicapo_Fa92XZCfXsJfvgetbk7llBTB0q5mp0t_x71mFWXfkduWJ526vTUlpNASimbePcL5z2YvgrdfJq_WZgadJeM8t0YLQw30n--97IsAeATpjmyw" alt=""><figcaption></figcaption></figure>

Ən əsası, siz Editorla işləyərkən SwaggerHub sizə işinizi saxlamağa imkan verir. Pulsuz Swagger Editor ilə (Svagger Uİ) ilə gördüyünüz iş brauzerin ön yaddaşında saxlanılır, faylı cloud-da saxlamaq imkanı yoxdur. Keşi təmizlədiyiniz zaman işiniz yox olur. Nəticədə, Swagger Uİ dən istifadə edirsinizsə, hər dəfə işi bitirdiyiniz zaman Swagger Redaktorundan işinizi mütəmadi olaraq öz kompüterinizdəsaxlamlısız

Svagger HUB ilə siz spesifikasiyanızı birbaşa Svagger Hub serverində və ya HitHub da saxlaya bilərsiz.

### Versions <a href="#versions" id="versions"></a>

SwaggerHub yalnız OpenAPI spesifikasiyanızı saxlamağa imkan vermir, həm də spesifikasiyanızın müxtəlif versiyalarını saxlamağa imkan verir. Nəticədə, yeni versiya əlavə etməklə yeni məzmunla sınaqdan keçirə bilərsiniz. İstədiyiniz versiyaya qayıda bilərsiniz, həmçinin istənilən versiyanı dərc edə və ya dərcdən çıxara bilərsiniz.

SwaggerHub&#x20;

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

Versiyanı dərc etdiyiniz zaman dərc edilmiş versiya Yalnız Read only olur. Əgər dərc edilmiş versiyaya dəyişiklik etmək istəyirsinizsə (yeni versiya yaratmaq əvəzinə) versiyanı dərcdən çıxarıb ona düzəlişlər edə bilərsiniz.

Siz spesifikasiyalarınızın xüsusi versiyalarına keçid edə bilərsiniz və ya avtomatik olaraq ən son versiyaya yönləndirəcək daha ümumi URL dən istifadə edə bilərsiniz.&#x20;

Məsələn, Sənədlərin 3 versiyasından istifadə edən SwaggerHub-da dərc edilmiş TravelPayouts API-yə keçid buradadır:&#x20;

[https://app.swaggerhub.com/apis/emilabbas/travelpayouts-api/](https://app.swaggerhub.com/apis/emilabbas/travelpayouts-api/3.1)

Müəyyən bir versiyaya keçid üçün URL-də versiya nömrəsini daxil edin. Bunun əksinə olaraq, bu daha ümumi keçid (versiya nömrəsini buraxan) avtomatik olaraq ən son versiyaya (3.1) yönləndirir:&#x20;

[https://app.swaggerhub.com/apis/emilabbas/travelpayouts-api/3.1](https://app.swaggerhub.com/apis/emilabbas/travelpayouts-api/3.1)



Versioning is helpful when you’re collaborating on the spec with other team members. For example, suppose the original version was drafted by an engineer, and you want to make major edits. Rather than directly overwriting the content (or making a backup copy of an offline file), you can create a new version and then take more ownership to overhaul that version with your own updates, without fear that the engineer will react negatively about overwritten/lost content.

When you publish your Swagger documentation on SwaggerHub, Swagger’s base URL (`app.swaggerhub.com`) remains in the URL. Although this base URL isn’t customizable, you can add your company logo and visual branding as desired.

Digər komanda üzvləri ilə spesifikasiyalar üzərində əməkdaşlıq etdiyiniz zaman versiya yaratmaq faydalıdır. Məsələn, fərz edək ki, orijinal versiya injiner tərəfindən tərtib edilib və siz əsaslı redaktə etmək istəyirsiniz. Məzmunun üzərinə birbaşa yazmaq (və ya faylın offline backuipin etmək) əvəzinə siz özünüzün yeni versiyaısn hazırlayıb onun üzərində istənilən dəyişiklikləri edə bilərsiz və yaradılan spesifikasiyada nəyinsə korlanmamasından narahat olmursuz.&#x20;

Swagger sənədlərinizi SwaggerHub-da dərc etdiyiniz zaman Swagger-in əsas URL-i (app.swaggerhub.com) URL-də qalır. Bu əsas URL fərdiləşdirilə bilməsə də, istədiyiniz kimi şirkət loqotipinizi və vizual brendinizi əlavə edə bilərsiniz.

### Inline commenting/review

Key to the review process is the ability for team members to comment on the spec inline, similar to Google Docs and its margin annotations. When you’re working in SwaggerHub’s editor, a small plus sign ![](https://s3.us-west-1.wasabisys.com/idbwmedia.com/images/api/swaggerhub\_plus.png) appears to the left of every line. Click the plus button to add a comment inline at that point.\


<figure><img src=".gitbook/assets/image (1) (5).png" alt=""><figcaption></figcaption></figure>

When you click the plus sign, a comment pane appears on the right where you can elaborate on comments, and where others can reply. Users can edit, delete, or resolve the comments. This commenting feature helps facilitate the review process in a way that tightly integrates with your content. You can also collapse or show the comments pane as desired

Few tech comm tools support inline annotations like this, and it wouldn’t be possible without a database to store the comments, along with profiles associated with the reviewers. This feature would be tedious to implement on your own, as it would require both a database and an authentication mechanism.

This is all included in SwaggerHub.



###

### Organizations and projects

The collaborative aspect of SwaggerHub is the most common reason people move from the open source tools to SwaggerHub. You might have a lot of different engineers working on a variety of APIs in SwaggerHub. To organize the work, you can group APIs into [organizations](https://app.swaggerhub.com/help/organizations/index), and then assign members to the appropriate organization. When that member logs in to SwaggerHub, he or she will see only the organizations to which he or she has access.

Additionally, within an organization, you can further group APIs into different projects. This way teams working in the same organization but on different projects can have visibility into other APIs.\


\


<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

This aspect of organizations and projects may not seem essential if you have just one or two APIs, but consider how you’ll scale and grow as you have dozens of APIs and multiple teams. In these more robust scenarios, the organization and project features become essential.

### Expanding the tech writer’s role with APIs

Tech writers are positioned to be power players in the spec-first philosophy with OpenAPI design. By becoming adept at coding the OpenAPI spec and familiar with robust collaborative tools like SwaggerHub, tech writers can lead engineering teams not only through the creation and refinement of the API documentation but also pave the way for beta testing, spec review, client/server SDK generation, and more.

Designing a fully-featured, highly functioning OpenAPI spec is at the heart of this endeavor. Few engineers are familiar with creating these specs, and technical writers who are skilled at both creating the spec and setting up Swagger tooling can fill critical roles on API teams.

Great tools aren’t free. SwaggerHub does [cost money](https://swaggerhub.com/pricing/), but this is a good thing since free tools are frequently abandoned, poorly maintained, and lack documentation and support. By using a paid tool from a robust API company (the same company that maintains the Swagger tools and sponsors the OpenAPI specification), you can plug into the infrastructure you need to scale your API documentation efforts.\


\
