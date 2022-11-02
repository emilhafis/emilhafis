# Step 5: The components object (OpenAPI tutorial)

> `components` obyekti Open API spesifikasiyasında digər obeyektlərdən xüsusidir. Çünki siz burada bir neçə yerdə istifadə edilə bilən məlumatlar yaradıb öz spesifikasiyanızın müxtəlif yerində ondan istifadə edə bilər. Hər dəfə eyni məlumatları yazmağa ehtiyac qalmadan.
>
> Bizim APı snearimizdə `parameters` və `responses` obyekti üzrə detalları `components` də daxlayacağıq.

> Parametrlərinizin təfərrüatlarını təsvir etmək və mürəkkəb response scheme sxemini təsvir etmək OpenAPI spesifikasiyasının ən çətin aspektləri ola bilər.&#x20;
>
> `parameters` və `responses` birbaşa `parameters` və `responses` obyektlərində müəyyən edə bilsəniz də, adətən iki səbəbə görə onları siyahıya salmırsınız:
>
> * Bu definitions hissələrini digər requests və ya responses yenidən istifadə etmək istəyə bilərsiniz. API-də bir neçə yerdə eyni parametr və ya response istifadə etmək adi haldır. `components` obyekti vasitəsilə OpenAPI sizə eyni definitions bir neçə yerdə təkrar istifadə etməyə imkan verir.
> * You might not want to clutter up your `paths` object with too many parameter and response details, since the `paths` object is already somewhat complex with several levels of objects.
> * Siz `paths` obyektinizi həddən artıq çox parameter və response təfərrüatları ilə qarışdırmaq istəməyə bilərsiniz, çünki `paths` obyekti artıq bir neçə səviyyəli obyektlərlə bir qədər mürəkkəbdir.
>
> Daha mürəkkəb sxemlər üçün (və ya bir neçə əməliyyatda və ya `paths` da yenidən istifadə olunan sxemlər üçün) requests və responses üçün sxemi `paths` obyektində siyahıya almaq əvəzinə, adətən siz [reference object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#referenceObject) dən (referenced with `$ref`) xüsusi [`components` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#componentsObject) definitina müraciət etmək üçün istifadə edirsiniz (For more details on `$ref`, see [Using $ref](https://swagger.io/docs/specification/using-ref/).)
>
>

> Think of the `components` object like a document appendix where the re-usable details are provided. If multiple parts of your spec have the same schema, you point each of these references to the same object in your `components` object, and in so doing you single source the content. The `components` object can even be [stored in a separate file](http://apihandyman.io/writing-openapi-swagger-specification-tutorial-part-8-splitting-specification-file/) if you have a large API and want to organize the information that way. (However, with multiple files, you wouldn’t be able to use the online Swagger Editor to validate the content.)

### Objects in components

You can store a lot of different re-usable objects in the `components` object. The [`components` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#componentsObject) can contain these objects:

* [`schemas`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#schemaObject)
* [`responses`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#responses-object)
* [`parameters`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#parameterObject)
* [`examples`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#examples-object)
* [`requestBody`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#requestBodyObject)
* [`headers`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#headerObject)
* [`securitySchemes`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#securitySchemeObject)
* [`links`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#linkObject)
* [`callbacks`](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#callbackObject)

> `components` daxilindəki hər bir obyektin properties OpenAPI spesifikasiyasının digər hissələrində eyni formada istifadə edilir. Bunun reference işarəsindən (`$ref`) istifadə olunaraq `components` obyektinə istinad edilir. `$ref` stands for [`reference` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#referenceObject) and is part of JSON.
>
>

### Re-using parameters across multiple paths

> Bundan əvəvlki stepdə biz bütün parametrləri birbaşa olaraq `parameters` obyektinin daxilində yaratmışdır. Eyni parametrlərin digər paths da təkrar istifadəsi üçün `parameters`  `components` saxlayaq.

\
