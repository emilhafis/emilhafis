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
