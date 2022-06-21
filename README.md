---
description: API ilə tanışlıq və kurs üzrə ümumi mənzərə
---

# Giriş

### Kurs üzrə ümumi məlumat

> API-ın hazırlanmasından onun kodlaşdırılmasına kimi prosesləri əhatə edən kursumuzda mücərrrəd uzun uzadı danışmaq əvəzinə praktiki yanaşma ilə sizlərə biliklərimi çatdırmağa çalışacağam.
>
> Saytlarda aviabilet, hotel qiymətləri üzrə ən ucuzu seçimlərin necə verilməsini praktiki göstərəcəyəm. Əlavə olaraq, sadə hava praqnozlarını əldə edib saytlarda necə yerləşdirmək lazım olduğunu əyani formada izah etməyə çalışacam.
>
> API-dən istifadə etdikcə siz endpoints, parameters, data types, authentication, curl, JSON, the command line, Chrome’s Developer Console, JavaScript və s. haqqında öyrənəcəksiniz. İdeya ondan ibarətdir ki, nağıl formasında bu anlayışları öyrənməkdənsə, siz real senarilər əsasında proseslərin necə getdiyinin şahidi olacaqsınız. Qarşılaşdığınız proseslərin hansı formada həyata keçdiyini real nümunələr ilə görmək sizə texnologiyaların iş prinsipini daha rahat qavramağa kömək edəcəkdir.
>
> Daha sonra REST API-lar üçün standartlara, alətlərə və spesifikasiyalara keçəcəyik. Siz API sənədlərində tələb olunan bölmələr haqqında öyrənəcək, müxtəlif şirkətlərin REST API sənədlərinin nümunələrini təhlil edəcək, təcrübə əldə etmək üçün proqramçılarla birlikdə real layihələrə qoşulacaqsınız.

### API nədir?

> API akronimi yəni açılışı Application Programming İnterfeysdir. Yəni iki proqram təminatının bir biri ilə danışmasına xidmət edir. Hər dəfə siz telefonunuzda YouTuba, Facebook-a daxil olanda, mesaj göndərəndə və ya hava proqnozuna baxanda API-lardan istifadə edirsiniz.

### API nümunələri

> Siz nə telefonunuzda hər hansı bir tətbiqi işlətdiyiniz vaxt, tətbiq internetə bağlanır və məlumatları serverə göndərir. Server məlumatları aldıqdan sonra lazımı prosesləri icra edir və məlumatları yenidən sizin telefonunuza daha dəqiq telefonunzdakı tətbiqinizə qaytarır. Tətbiq daha sonra həmin məlumatları emal edir və istədiyiniz məlumatları oxunaqlı şəkildə sizə təqdim edir.
>
> Bunu daha yaxşı izah etmək üçün çox məhşur olan API nümunəsi ilə tanış olaq.
>
> Təsəvvür edin ki, siz restoranda oturmusunuz və qarşısınızda bir çox seçim olan menyu vardır. Mətbəx isə sizin sifarişlərinizi hazır edən "sistemin" bir hissəsidir. buradan çatışmayan məsələ seçdiyiniz sifarişin mətbəxə çatdırılması və hazırlanmış sifarişin mətbəxdən sizə gətirilməsidir. Sırf burada isə bizim köməyimizə ofisiant və ya API gəlmiş olur. Ofisiant sorğunuzu və ya sifarişinizi qəbul edən və mətbəxə – sistemə nə etməli olduğunuzu söyləyən vasitə və ya API-dir. Yekunda ofisiant cavabı sizə çatdırır; yəni bizim keysimizdə yeməyi bizə gətirir.
>
> Burada biz - mobil telefondakı tətbiq, mətbəx - server, ofisiant - API və menyudakı seçimlər isə API parametrləridir.
>
> Bir azdan real nümunələr ilə daha da prosesi aydın formada izah edəcəyəm.
>
> API-ların əsas üstünlüklərindən və məqsədlərindən biri də ondan ibarətdir ki, sistemin daxildə necə işlədiyini gizlətmək və yalnız proqramçılara (inteqratorlara) lazım olan hissələrə kənara çıxarmaqdır. Yəni, sistemdən API vasitəsilə istifadə edən tərəflərə dəyişiklikləri bildirməməklə sistemin daxili tələbləri və funksiyalarını sonradan dəyişməyin mümkünlüyüdür. Məsələn bizim nümunəmizdə - mətbəxdəki işçilərin dəyişdirilməsi, yemək hazırlanma standartlarının dəyişdirilməsi nə biz (yəni müraciət edən tətbiq), nə də ofisiant (yəni API) tərəfdə hər hansı dəyişikliyə səbəb olmur.&#x20;

![](.gitbook/assets/blueprint-APIs-requests.jpg)

### Real təcrübədən sənədləşməyə doğru

> Bu kursda "API-lardan proqramçı kimi istifadə etmək" mövzusunu bitridikdən sonra "Technical writer" kimi API sənədləşmələrin real layihələr əsasında hazırlayıb proqramçılara təqdim edəcəksiniz. "Technical writer" kimi siz REST API sənədləşdirməsi zamanı aşağıdakı resurslara əsaslanan sənədləşdirmələr hazırlayacaqsınız:
>
> 1. **Resource descriptions**
> 2. **Endpoints and methods**
> 3. **Parameters**
> 4. **Request example**
> 5. **Response example**
>
> Bu bölmələrin hər birinin mənimsənilməyi sizlərə daha yaxşı REST API sənədləşdirilməsi necə yaradılmalısını başa düşməyə imkan verəcəkdir. Siz həmçinin API üçün konseptual bölmələri necə sənədləşdirməli lazım olduğunu öyrənəcəksiniz, məsələn ilkin təlimatlar (Getting started tutorial),  məhsulun icmalı (product overview), status və xəta kodları, sorğu icazəsi (request authorisation) və s.
>
> <mark style="color:red;">Siz həmçinin müxtəlif yollar ilə REST API sənədləşməsinin publish olunmasına, yeni tool-ların, GitHub kimi spesifikasiyaların, Jekyll kimi statik sayt generatorları və başqa docs-ad-codes yanaşmalarını öyrənəcəksiniz.</mark>
>
> <mark style="color:red;">Biz həmçinin OpenAPI spesifikasiyası və Swagger UI (OpenAPI spesifikasiyası üçün vasitələr) detallarına düşmüş olacağıq. Əlavə olaraq siz native library API-ları necə sənədləşdirməyi və Javadoc-u necə generasiya etməli olduğunuzu öyrənəcəksiniz.</mark>
>
> <mark style="color:red;">Vasitə və texnologiyalardan savayı biz proses və metodologiyaları dərindən araşdırıb, böyük və kiçik sənədləşmə layihələrini necə idarə etməyi, sənədlərlə bağlı rəyləri necə toplamağı və maraqlı tərəfləri necə məmnun etməyi öyrənəcəyik.</mark>
>
> <mark style="color:red;">Mən həmçinin</mark> hərtərəfli keyfiyyət yoxlama siyahısını əks etdirən <mark style="color:red;">metrics and measurement bölməsini kuersa daxil etmişəm.</mark> Təsvir edilən meyarlar öz developer portalınızı  ən yaxşı təcrübələrinə qarşı saysız-hesabsız üsullarla qiymətləndirməyə kömək edə bilər.
>
> Bu kurs boyu mən bu anlayışları praktiki fəaliyyətlər və demolarla real, tətbiq oluna bilən kontekstlərə göstərəcəyəm.

### Kurs kimlər üçün nəzərdə tutulmuşdur?

> Kurs ilk növbədə aşağıdakı auditoriyalara xidmət edir:
>
> 1. Proqramçılar üçün hazırlanan ənənəvi sənədləşmədən API First yönümlü sənədləşməyə keçmək istəyən peşəkar **Tech writer-lar**.
> 2. Texniki sahədə özlərini inkişaf etdirib zamanın tələblərinə cavab verən IT analitik olmaq istəyən **Tələbələr**.
> 3. Öz API-larını sənədləşdirmək və sənədləşdirmə zamanı API-lar üzrə ən yaxşı struktur, dizayn və terminalagoiyalardan istifadə etmək istəyən **Proqramçılar**.
> 4. Müəllimlər - Kimlərki IT Analitikləri yetişdirərək onlara Tech Writing öyrədirlər

### Kursun mündəricatı

> The course consists of the following sections:
>
>
>
> * [I: Introduction to REST APIs](https://idratherbewriting.com/learnapidoc/docapis\_introtoapis.html)
> * ****[**Giriş**](./#kurs-uezr-uemumi-m-lumat)****
> * [II: Using an API like a developer](https://idratherbewriting.com/learnapidoc/likeadeveloper.html)
> * [III: Documenting API endpoints](https://idratherbewriting.com/learnapidoc/docendpoints.html)
> * [IV: OpenAPI spec and generated reference docs](https://idratherbewriting.com/learnapidoc/restapispecifications.html)
> * [V: Step-by-step OpenAPI code tutorial](https://idratherbewriting.com/learnapidoc/openapi\_tutorial.html)
> * [VI: Testing API docs](https://idratherbewriting.com/learnapidoc/testingdocs.html)
> * [VII: Conceptual topics in API docs](https://idratherbewriting.com/learnapidoc/docconceptual.html)
> * [VIII: Code tutorials](https://idratherbewriting.com/learnapidoc/docapiscode.html)
> * [IX: The writing process](https://idratherbewriting.com/learnapidoc/writing\_process.html)
> * [X: Publishing API docs](https://idratherbewriting.com/learnapidoc/publishingapis.html)
> * [XI: Thriving in the API doc space](https://idratherbewriting.com/learnapidoc/jobapis.html)
> * [XII: Native library APIs](https://idratherbewriting.com/learnapidoc/nativelibraryapis.html)
> * [XIII: Processes and methodology](https://idratherbewriting.com/learnapidoc/docapis\_managing\_doc\_processes.html)
> * [XIV: Metrics and measurement](https://idratherbewriting.com/learnapidoc/docapis\_metrics\_and\_measurement.html)
> * [XV: Additional resources](https://idratherbewriting.com/learnapidoc/resources.html)

****

### Kurs sizə yeni iş imkanları açacaqmı? <a href="#will-this-course-help-you-get-a-job-in-api-documentation" id="will-this-course-help-you-get-a-job-in-api-documentation"></a>

> İnsanların bu kursu almasının ən ümumi səbəbi API sənədlərinə keçiddir. Bu kurs sizə bu keçidi həyata keçirməyə kömək edəcək, lakin siz sadəcə məzmunu passiv oxuya bilməzsiniz. Siz hər bir bölmədə qeyd olunan fəaliyyətləri, xüsusən də məzmunla işləməyi əhatə edən mövzuları yerinə yetirməlisiniz
>
> Bu kursun əsas məqsədi API-First yanaşmasının tətbiq edilməsi, API sənədləşməsinin hazırlanması və nəticədə proqramçılara aydın və dəqiq tələbləri onlara daha rahat formada çatırmaqdan ibarətdir. Həmçinin də, hazırlanmış proqram təminatının tələblərə uyğun hazırlanmasının yoxlanılmasıdır. Biz bu keyfiyyətləri mənimsəmək üçün proseslərin dərinliyinə enəcəyik.&#x20;
>
> Sadalanan keyfiyyətlərə malik olan şəxslərə isə bu gün tələblər daha yüksəkdir və artıq xaricdə Tech Writer tələbləri ilə kifayət qədər xeyli vakansiyalar mövcuddur. Əminəm ki, qısa zamanda ölkəmizdə də sırf belə mütəxəssislər axtaracaqlar.

### Proqramlaşdırma bacarıqları tələb olunmur <a href="#no-programming-skills-required" id="no-programming-skills-required"></a>

> Bu kursda iştirak etmək üçün sizə hər hansı bir proqramlaşdırma təcrübəsinin olmasına ehtiyac yoxdur. Amma HTML və JavaScript, həmçinin də texniki baza biliklərinin olması sizə prosesləri daha yaxşı anlamağa kömək edəcəkdir.
>
> JavaScript REST API sənədləşməsi zamanı ən çox istifadə edilən və ən asan başa düşülən proqramlaşdırma dillərindən biridir. JavaScript bizə kodları sadəcə brauzerdə açmaqla yoxlamağa imkan verir, yəni proqramın IDE-də işə salınmasına ehtiyac qalmır.&#x20;
>
> Kurs ərzində JavaScript-dən istifadə etdikcə ümumi prinsiplə sizi tanış edəcəm.

### Kurs üçün hansı vasitələr (tools) lazımdır?

> * **Kompüter**.
> * **Text editor -** Əgər sizin hazırda istifadə etdiyiniz text editor yoxdursa [Sublime Text](https://www.sublimetext.com/) istifadə edə bilərsiniz (həm Mac, həm də Windows üçün pulsuzdur). Əgər başqa editor-lardan (məs, [Visual Studio Code](https://code.visualstudio.com/), [Atom](https://atom.io/) və ya [Notepad++](https://notepad-plus-plus.org/)) istifadə etməyinizdə kifayətdir.&#x20;
> * **Chrome browser -** [Chrome](https://www.google.com/chrome/browser/desktop/index.html) JSON formatında göndərilmiş sorğuları rahatlıqla analiz etmək üçün Javascript Console təmin etdiyi üçün Chrome-dan istifadə edəcəyik. Həmçinin də JSON cavablarını daha rahat oxumaq üçün [JSON Formatter](https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa?hl=en) yekləməlisiniz.
> * **Postman -** [Postman](https://www.getpostman.com/) applikasiyası bizə vizual interfeys üzərindən sorğuları göndərib və alınan cavabları görmək imkanı verir. _Chrome extension əvəzinə Postman applikasiyasın yüklədiyinizdən əmin olun._
> * **curl -** [curl](https://curl.haxx.se/)  command line-dan endpoint-lərə sorğuların göndərilməsi üçün əsas vasitədir. curl MAC-da by default qurulmuş olur, amma Windows-da by default deyildir ( bəzi Windows 10-dakı Powershell-də vardır).  Windows-da Command Prompt-u açıb `curl -V` qeyd edin. Əgər qurulu deyilsə [confusedbycode.com/curl](http://confusedbycode.com/curl) səhifəsindən yükləyə bilərsiniz ( “With Administrator Privileges (free), 64-bit”). Command Prompt-u bağlayıb yenidən açın və `curl -V` yazıb nəticəsinə baxın.
> * **Gi**<mark style="color:red;">**t**</mark><mark style="color:red;">.</mark> [<mark style="color:red;">Git</mark>](https://git-scm.com/) <mark style="color:red;">is a version control tool developers often use to collaborate on code. For Windows, see</mark> [<mark style="color:red;">https://gitforwindows.org/</mark>](https://gitforwindows.org/) <mark style="color:red;">to set up Git and the Git BASH terminal emulator. For Mac, see</mark> [<mark style="color:red;">Downloading Git</mark>](https://git-scm.com/download/mac)<mark style="color:red;">.</mark>&#x20;
> * **GitHub account**. [GitHub](https://github.com) müxtəlif fəaliyyətlər üçün, bəzən Git-də iş prosesini nümayiş etdirmək üçün, bəzən isə müxtəlif developer tool-lara daxil olmaq üçün autentifikasiya vasitəsi üçün istifadə edilir.  Əgər GitHub hesabınız yoxudrsa, yaradın.
> * **OpenWeatherMap API key**. We’ll be using the OpenWeatherMap API for some exercises. It <mark style="color:red;">takes a couple of hours for the OpenWeatherMap API key to become active, so it’s best if you get the API key ahead of time — then when you get to the OpenWeatherMap API activities, you’ll be all set. To get your (free) OpenWeatherMap API key, go to</mark> [<mark style="color:red;">https://openweathermap.org/</mark>](https://openweathermap.org/)<mark style="color:red;">. Click Sign Up in the top nav bar and create an account. After you sign up, OpenWeatherMap sends you an API key to your email. you can also find it when you log in and click the API Keys tab from the dashboard. Copy the key into a place you can easily find it.</mark>

### Proqram təminatlarının yoxlanılması <a href="#testing-your-setup" id="testing-your-setup"></a>

> * **Postman yoxlanılması** - Postman app açdıqdan sonra **New** - **HTTP Request** seçib aşağıdakı **URL**-i **GET** qarşısında qeyd edin: [`https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&token=3c63416a24d3b969da6df9271faa9d6e`](https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates?origin=GYD\&token=3c63416a24d3b969da6df9271faa9d6e) `` **Send** düyməsini basın. Əgər cavab alırsınızsa hər şey qaydasındadır (bəzən komputerdə olan məhdudiyyətlərə görə sorğuya cavab alınmaya bilər)&#x20;
> * <mark style="color:red;">To check whether Git is installed, open up Terminal (on Mac) or Command Prompt (on Windows) and type</mark> <mark style="color:red;"></mark><mark style="color:red;">`git --version`</mark><mark style="color:red;">. If it’s installed, you’ll see the version.</mark>

![](<.gitbook/assets/Postman\_check (1).png>)

> * **cURL yoxlanılması** - cURL quraşdırıldığından əmin olmaq üçün Mac-da Terminalı, Windows-da isə Command Prompt-u açıb bunu qeyd edin `curl --location --request GET 'https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&token=3c63416a24d3b969da6df9271faa9d6e'` Əgər JSON cavabı alırsınızsa dmeək ki, hər şey qaydasındadır.

![](.gitbook/assets/curl\_check.png)
