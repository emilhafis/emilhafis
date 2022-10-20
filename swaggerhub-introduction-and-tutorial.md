# SwaggerHub introduction and tutorial

> Bundan əvvəlki bölmədə open source proyekt (Pet) vasitəsilə [Swagger UI](https://idratherbewriting.com/learnapidoc/pubapis\_swagger.html)-də Open API spesifikasiyasına baxdıq. Bu kompaniya Swaggerin Editor və UI versiyalarını pulsuz olaraq istifadəyə verib. Həmçinin də bunların [SwaggerHub](https://app.swaggerhub.com/) adlanan premium məhsulları vardır.&#x20;
>
> [Buradan](https://swagger.io/tools/swaggerhub/opensource-comparison/) həmin versiyalar üzrə müqaisəni görə bilərsiniz.

### SwaggerHub qeydiyyat və Yaml import

> SwaggerHub da qeydiyyatdan keçək.

![](<.gitbook/assets/image (10).png>)

Qeydiyyatdan keçdikdən sorna gördüyünüz kimi ekran açılır. Burada `Create` new edib seçimləri görə bilərik.

![](<.gitbook/assets/image (8).png>)

Burada olan Create new API məsələsinə növbəti dərslərdə baxacağıq və manual olaraq Open API spec yaradacağıq.

İndi isə Stoplight da yaratdığımız Open API spesifikasiyasını bura add edib hansı formada parse olunduğuna baxaq. Xatırlayırsınızsa bildirmişdimki əlinizdə YOpen API spec varsa müxtəlif platformalara onu import edə bilərsiz, bir sözlə çox üstünlük verir.

1. Bunun üçün Stoplight a daxil oluruq. Yaml faylı üzərinə klik edirik.

![](.gitbook/assets/image.png)

2\. Ya export edirik yaml üzərindən yada sağda Code hissəyə klik edib kop edirib save edirik.

![](<.gitbook/assets/image (1).png>)

3\. Əldə etdiyimiz faylı Svagger Hub a import edirik.

![](<.gitbook/assets/image (15).png>)

4\. İmport etdikdən sonra aşağıdakı kimi səhifə qarşımıza çıxır&#x20;

![](<.gitbook/assets/image (3).png>)

{% hint style="info" %}
Qeyd edildiyi kimi burada problem Open API spec versiyasındadır. Belə ki Spotlight 3.1.0 versiyasın istifadə edir , amma Svagger bu yeni versiyanı dəstəkləmir. Ona görə də spesifikasiyada versiyanı 3.0.0 edirik.
{% endhint %}

5\. bu dəyişikliyi etdikdən sonra spefisifikaımız emal olunur və Svagger onu vizual interfeysdə göstərir. Həmçinin də xətaları svagger göstərir. Versiya fərqinə əsasən bir çox xətalar yaranır. Amma ən əsası istədiyimiz nəticəni aldıq.

![](<.gitbook/assets/image (12).png>)
