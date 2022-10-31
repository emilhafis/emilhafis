# Spec-first development of the OpenAPI spec

### Mocking Servers

SwaggerHub-ın digər gözəl xüsusiyyəti Mock API serverləri yaratmaq qabiliyyətidir. Tutaq ki, istifadəçilərin real sorğular yaratmasını istəmədiyiniz bir API var. (Bəlkə bu, istifadəçilərin API vasitəsilə məhsul sifariş edə biləcəyi bir sifariş sistemidir və ya sizin test hesablarınız/sistemləriniz yoxdur). Bununla belə, siz hələ də istifadəçilərə API-nizin necə işlədiyini anlamağa imkan verən cavabları simulyasiya edə bilərsiniz.

API spesifikasiyanızda nümunə cavablarınız olduğunu fərz etsək, API-nizi “auto-mock” olaraq təyin edə bilərsiniz. İstifadəçi sorğunu test etdikdə, SwaggerHub spesifikasiyanızda olan nümunə cavabı qaytaracaq. Cavab istifadəçinin UI-yə daxil etdiyi xüsusi parametrlər olmayacaq, əksinə, spesifikasiyanızda olan cavab nümunəsi qaytaracaq hansıkı real server cavabı ilə eynilik təşkil edəcək.

Əlavə olaraq auto mock un üstünlüyü ondan ibarətdir ki, istifadəçinin real məlumatları və ya serverdən götürülən real API key lər lazım olmur. Bir çox keyslərdə siz istəməyəcəksinizki real məlumatlar ortalıqda gəzsin. Həmçinin də siz API cavablarını rahatlıqla simulyasiya edə biləcəksiz.&#x20;

API-ların simulyasiya edilməsi xüsusilə beta user-lər ilə API-larınızın test edilməsi üçün çox əhəmiyyətli olacaqdır.  Kodlaşdırılma edilməmişdən öcə API spesifikasiyanın hazırlanmasının ən əsas səbəbi istifadəçilər tərəfindən istənilməyən və ya lazım olmayan endpoint və cavabların kodlaşdırılmamaısıdr (buna spec-first philosophy və ya API-first approach deyilir)

SwaggerHub mock server yanaşmasından istifadə etməklə təkcə sənədləri təqdim etmir, həm də  saatlarla faktiki kodlaşdırmaya sərf etməzdən dərhal əvvəl API-nizin dizaynını əldə etmək üçün beta-sınaq vasitəsi kimi çıxış edir. Siz API-nizin müxtəlif versiyaları üçün avtomatik mock-u aktivləşdirə, variantlar yarada və variantların hər birini sınaqdan keçirə bilərsiniz.

SwaggerHub-da mock server qurmaq üçün plug ikonasına klikləyin və yeni inteqrasiya əlavə edin. API Auto Mocking xidmətini seçin və konfiqurasiya təfərrüatlarını tamamlayın. Spesifikasiyanızda endpointlərin hər biri üçün `nümunələr` olduğundan əmin olun. Ətraflı məlumat üçün [API Auto Mocking](https://app.swaggerhub.com/help/integrations/api-auto-mocking) -ə baxın.

### Spec-first development of the OpenAPI spec <a href="#specfirst" id="specfirst"></a>

Now let’s talk about the spec-first approach. Many feel that auto-generation, described in the previous section, is _not_ the best approach. In [_Undisturbed REST: A Guide to Designing the Perfect API_](https://www.mulesoft.com/lp/ebook/api/restbook), [Michael Stowe](https://twitter.com/mikegstowe) recommends that teams implement the OpenAPI specification by hand and then treat the specification document as a contract that developers use when doing the actual coding. This approach is often referred to as “spec-first development.”

In other words, developers consult the OpenAPI specification document to see what the parameter names should be called, what the responses should be, and so on. After this “contract” or “blueprint” has been established, Stowe says you can then put the annotations in your code (if you want) to generate the specification document in a more automated way. But don’t code without first having a spec.

Too often, development teams quickly jump to coding the API endpoints, parameters, and responses without doing much user testing or research into whether the API aligns with what users want. Since versioning APIs is extremely difficult (you have to support each new version going forward with full backward-compatibility to previous versions), you want to avoid the “fail fast” approach that agile enthusiasts so commonly celebrate. There’s nothing worse than releasing a new version of your API that invalidates endpoints or parameters used in previous releases. Constant versioning in APIs can become a documentation nightmare.

Even before the API has been coded, your spec can generate a [mock response](https://idratherbewriting.com/learnapidoc/pubapis\_swaggerhub\_smartbear.html#mocking\_servers) by adding response definitions in your spec. The mock server generates a response that looks like it’s coming from a real server, but in reality it’s just a pre-defined response in your code and appears to be dynamic to the user.

If the OpenAPI spec isn’t used as the blueprint for the API, what is? Most likely, the descriptions about the endpoints and what they return will be stored on a wiki page or Word document, often incomplete in terms of all the details (e.g., casing of the responses, the structure and what’s included), so developers will make these decisions on the fly while coding.\
