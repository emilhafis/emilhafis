---
description: API ilə tanışlıq və kurs üzrə ümumi mənzərə
---

# Giriş

![API First](.gitbook/assets/API-Interface.png)

### Kurs üzrə ümumi məlumat

> Kursu ümumi olaraq 3 hissəyə bölmüşəm.
>
> 1. Tech  Writing&#x20;
> 2. Business Analyst
> 3. Praktika
>
>
>
> **Birinci hissədə,** API-ın hazırlanmasından onun kodlaşdırılmasına kimi prosesləri əhatə edəcəyik. Həmçinin də, API və documentasiya üzrə sıfırdan sona kimi bütün prosesləri bitirəcəyik.
>
> Bu kursda mücərrrəd uzun uzadı danışmaq əvəzinə praktiki yanaşma ilə sizlərə biliklərimi çatdırmağa çalışacağam.
>
> Saytlarda aviabilet, hotel qiymətləri üzrə ən ucuzu seçimlərin necə edildiyini və saytlarda necə yerləşdirmək lazım olduğunu əyani formada izah etməyə çalışacam.
>
> API-dən istifadə etdikcə siz endpoints, parameters, data types, authentication, curl, JSON, the command line, Chrome’s Developer Console, JavaScript və s. haqqında öyrənəcəksiniz. İdeya ondan ibarətdir ki, nağıl formasında bu anlayışları öyrənməkdənsə, siz real senarilər əsasında proseslərin necə getdiyinin şahidi olacaqsınız. Qarşılaşdığınız proseslərin hansı formada həyata keçdiyini real nümunələr ilə görmək sizə texnologiyaların iş prinsipini daha rahat qavramağa kömək edəcəkdir.
>
> Daha sonra REST API-lar üçün standartlara, alətlərə və spesifikasiyalara keçəcəyik. Siz API sənədlərində tələb olunan bölmələr haqqında öyrənəcək, müxtəlif şirkətlərin REST API sənədlərinin nümunələrini təhlil edəcək, təcrübə əldə etmək üçün proqramçılarla birlikdə real layihələrə qoşulacaqsınız.
>
> **İkinci hissə olan** Business Analitika hissədə isə tələblərin necə toplanılması, Steykholderlə işlərin təşkili, müxtəlif formalarda analizilərin aparılması ilə tanış olacaq.
>
> **Sonuncu 3 cü** bölmədə isə öyrəndiklərimizi real olaraq proqramistlər ilə həyata keçirərəcəyik. Həmçinin də, hər dərs boyunca real layihələri işləyəcəyik. Bunlara Mobile banking app development, Open banking API-lar və s də aiddir.
>
> Bu kursda çalışcam ki, sizi yormadan məlumatları rahat şəkildə sizə çatdırım. Sırf bölgünün bu formada təşkilidə bunun üçündür, yəni ilk üçün biz bilikləri əldə edib sonradan onlar üzərindən metodologiya və standartlara baxırıq.



### API nədir?

> API akronimi yəni açılışı Application Programming İnterfeysdir. Yəni iki proqram təminatının bir biri ilə danışmasına xidmət edir. Hər dəfə siz telefonunuzda YouTuba, Facebook-a daxil olanda, mesaj göndərəndə və ya hava proqnozuna baxanda API-lardan istifadə edirsiniz.

### API nümunəli izah

> Siz telefonunuzda hər hansı bir tətbiqi işlətdiyiniz vaxt, tətbiq internetə bağlanır və məlumatları serverə göndərir. Server məlumatları aldıqdan sonra lazımı prosesləri icra edir və məlumatları yenidən sizin telefonunuza daha dəqiq telefonunzdakı tətbiqinizə qaytarır. Tətbiq daha sonra həmin məlumatları emal edir və istədiyiniz məlumatları oxunaqlı şəkildə sizə təqdim edir.
>
> Bunu daha yaxşı izah etmək üçün çox məhşur olan API nümunəsi ilə tanış olaq.
>
> Təsəvvür edin ki, siz restoranda oturmusunuz və qarşısınızda bir çox seçim olan menyu vardır. Mətbəx isə sizin sifarişlərinizi hazır edən "sistemin" bir hissəsidir. buradan çatışmayan məsələ seçdiyiniz sifarişin mətbəxə çatdırılması və hazırlanmış sifarişin mətbəxdən sizə gətirilməsidir. Sırf burada isə bizim köməyimizə ofisiant və ya API gəlmiş olur. Ofisiant sorğunuzu və ya sifarişinizi qəbul edən və mətbəxə – sistemə nə etməli olduğunuzu söyləyən vasitə və ya API-dir. Yekunda ofisiant cavabı sizə çatdırır; yəni bizim keysimizdə yeməyi bizə gətirir.
>
> Burada biz - mobil telefondakı tətbiq, mətbəx - server, ofisiant - API və menyudakı seçimlər isə API parametrləridir.

![API vs Real life](.gitbook/assets/blueprint-APIs-requests.jpg)

> Real həyatda biz artıq bir çox yerdə rastlaşırıq ki, yemək isfarişlərini online və ya restoran daxilində elektron cihazdan (planşet, mobil telefon və s) vermək mümkündür.&#x20;
>
> Burada proses bəs necə qurulmuşdur?&#x20;
>
> Məsələ çox sadədir, biz istədiyimiz sifarişi elektron cihazdan seçib təsdiq etdikdən sonra, cihaz internet üzərindən bizim sorğumuzu mətbəxdə yerləşən cihaza çatdırır. Aşpaz həmin cihaza baxaraq bizim nə sifariş etdiyimiz ilə tanış olur. Aşağıdakı şəkildə bunun texniki təsvirini daha yaxşı görə bilərsiniz. Burada biz mətbəxə bir ədə burgeri mobil cihaz üzərindən sifariş veririk.

![](.gitbook/assets/request\_response.png)

> Növbəti mövzularda real nümunələr ilə daha da prosesi aydın formada izah edəcəyəm.
>
> API-ların əsas üstünlüklərindən və məqsədlərindən biri də ondan ibarətdir ki, sistemin daxildə necə işlədiyini gizlətmək və yalnız proqramçılara (inteqratorlara) lazım olan hissələrə kənara çıxarmaqdır. Yəni, sistemdən API vasitəsilə istifadə edən tərəflərə dəyişiklikləri bildirməməklə sistemin daxili tələbləri və funksiyalarını sonradan dəyişməyin mümkünlüyüdür. Məsələn bizim nümunəmizdə - mətbəxdəki işçilərin dəyişdirilməsi, yemək hazırlanma standartlarının dəyişdirilməsi nə biz (yəni müraciət edən tətbiq), nə də ofisiant (yəni API) tərəfdə hər hansı dəyişikliyə səbəb olmur.&#x20;

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
> Siz həmçinin müxtəlif yollar ilə REST API sənədləşməsinin publish olunmasına, yeni tool-ların, GitHub kimi spesifikasiyaların, Jekyll kimi statik sayt generatorları və başqa docs-ad-codes yanaşmalarını öyrənəcəksiniz.
>
> Biz həmçinin OpenAPI spesifikasiyası və Swagger UI (OpenAPI spesifikasiyası üçün vasitələr) detallarına düşmüş olacağıq. Əlavə olaraq siz native library API-ları necə sənədləşdirməyi və Javadoc-u necə generasiya etməli olduğunuzu öyrənəcəksiniz.
>
> Vasitə və texnologiyalardan savayı biz proses və metodologiyaları dərindən araşdırıb, böyük və kiçik sənədləşmə layihələrini necə idarə etməyi, sənədlərlə bağlı rəyləri necə toplamağı və maraqlı tərəfləri necə məmnun etməyi öyrənəcəyik.
>
> Mən həmçinin hərtərəfli keyfiyyət yoxlama siyahısını əks etdirən metrics and measurement bölməsini kuersa daxil etmişəm. <mark style="color:red;"></mark> Təsvir edilən meyarlar öz developer portalınızı  ən yaxşı təcrübələrinə qarşı saysız-hesabsız üsullarla qiymətləndirməyə kömək edə bilər.
>
> Bu kurs boyu mən bu anlayışları praktiki fəaliyyətlər və demolarla real, tətbiq oluna bilən kontekstlərə göstərəcəyəm.

### Kurs kimlər üçün nəzərdə tutulmuşdur?

> Kurs ilk növbədə aşağıdakı auditoriyalara xidmət edir:
>
> 1. Proqramçılar üçün hazırlanan ənənəvi sənədləşmədən API First yönümlü sənədləşməyə keçmək istəyən peşəkar **Tech writer-lar**.
> 2. Texniki sahədə özlərini inkişaf etdirib zamanın tələblərinə cavab verən IT analitik olmaq istəyən **Tələbələr**.
> 3. Öz API-larını sənədləşdirmək və sənədləşdirmə zamanı API-lar üzrə ən yaxşı struktur, dizayn və terminalagoiyalardan istifadə etmək istəyən **Proqramçılar**.
> 4. IT Business Analitiklər&#x20;
> 5. Sistem analitiklər
> 6. IT innovasiyalar ilə məşğul olan mütəxəssislər

****

### Kurs sizə yeni iş imkanları açacaqmı? <a href="#will-this-course-help-you-get-a-job-in-api-documentation" id="will-this-course-help-you-get-a-job-in-api-documentation"></a>

> İnsanların bu kursu almasının ən ümumi səbəbi API sənədlərinə keçiddir. Bu kurs sizə bu keçidi həyata keçirməyə kömək edəcək, lakin siz sadəcə məzmunu passiv oxuya bilməzsiniz. Siz hər bir bölmədə qeyd olunan fəaliyyətləri, xüsusən də məzmunla işləməyi əhatə edən mövzuları yerinə yetirməlisiniz
>
> Bu kursun əsas məqsədi API-First yanaşmasının tətbiq edilməsi, API sənədləşməsinin hazırlanması və nəticədə proqramçılara aydın və dəqiq tələbləri onlara daha rahat formada çatırmaqdan ibarətdir. Həmçinin də, hazırlanmış proqram təminatının tələblərə uyğun hazırlanmasının yoxlanılmasıdır. Biz bu keyfiyyətləri mənimsəmək üçün proseslərin dərinliyinə enəcəyik.&#x20;
>
> Sadalanan keyfiyyətlərə malik olan şəxslərə isə bu gün tələblər daha yüksəkdir və artıq xaricdə Tech Writer tələbləri ilə kifayət qədər xeyli vakansiyalar mövcuddur. Əminəm ki, qısa zamanda ölkəmizdə də sırf belə mütəxəssislər axtaracaqlar.
>
> Aşağıda real iş imkanlarından bəzilərini görə bilərsiniz:

![](<.gitbook/assets/tech\_writer vacancy.png>)

### Proqramlaşdırma bacarıqları tələb olunmur <a href="#no-programming-skills-required" id="no-programming-skills-required"></a>

> Bu kursda iştirak etmək üçün sizə hər hansı bir proqramlaşdırma təcrübəsinin olmasına ehtiyac yoxdur. Amma HTML və JavaScript, həmçinin də texniki baza biliklərinin olması sizə prosesləri daha yaxşı anlamağa kömək edəcəkdir. Bunları isə biz kurs daxilində ümumi olaraq öyrənəcəyik.
>
> JavaScript REST API sənədləşməsi zamanı ən çox istifadə edilən və ən asan başa düşülən proqramlaşdırma dillərindən biridir. JavaScript bizə kodları sadəcə brauzerdə açmaqla yoxlamağa imkan verir, yəni proqramın IDE-də işə salınmasına ehtiyac qalmır.&#x20;
>
> Kurs ərzində JavaScript-dən istifadə etdikcə ümumi prinsiplə sizi tanış edəcəm.

### Kurs üçün hansı vasitələr (tools) lazım olacaqdır?

> * **Kompüter**.
> * **Text editor -** Əgər sizin hazırda istifadə etdiyiniz text editor yoxdursa [Sublime Text](https://www.sublimetext.com/) istifadə edə bilərsiniz (həm Mac, həm də Windows üçün pulsuzdur). Əgər başqa editor-lardan (məs, [Visual Studio Code](https://code.visualstudio.com/), [Atom](https://atom.io/) və ya [Notepad++](https://notepad-plus-plus.org/)) istifadə etməyinizdə kifayətdir.&#x20;
> * **Chrome browser -** [Chrome](https://www.google.com/chrome/browser/desktop/index.html) JSON formatında göndərilmiş sorğuları rahatlıqla analiz etmək üçün Javascript Console təmin etdiyi üçün Chrome-dan istifadə edəcəyik. Həmçinin də JSON cavablarını daha rahat oxumaq üçün [JSON Formatter](https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa?hl=en) yekləməlisiniz.
> * **Postman -** [Postman](https://www.getpostman.com/) applikasiyası bizə vizual interfeys üzərindən sorğuları göndərib və alınan cavabları görmək imkanı verir. _Chrome extension əvəzinə Postman applikasiyasın yüklədiyinizdən əmin olun._
> * **curl -** [curl](https://curl.haxx.se/)  command line-dan endpoint-lərə sorğuların göndərilməsi üçün əsas vasitədir. curl MAC-da by default qurulmuş olur, amma Windows-da by default deyildir ( bəzi Windows 10-dakı Powershell-də vardır).  Windows-da Command Prompt-u açıb `curl -V` qeyd edin. Əgər qurulu deyilsə [confusedbycode.com/curl](http://confusedbycode.com/curl) səhifəsindən yükləyə bilərsiniz ( “With Administrator Privileges (free), 64-bit”). Command Prompt-u bağlayıb yenidən açın və `curl -V` yazıb nəticəsinə baxın.
> * **Gi**<mark style="color:red;">**t**</mark><mark style="color:red;">.</mark> [<mark style="color:red;">Git</mark>](https://git-scm.com/) <mark style="color:red;">is a version control tool developers often use to collaborate on code. For Windows, see</mark> [<mark style="color:red;">https://gitforwindows.org/</mark>](https://gitforwindows.org/) <mark style="color:red;">to set up Git and the Git BASH terminal emulator. For Mac, see</mark> [<mark style="color:red;">Downloading Git</mark>](https://git-scm.com/download/mac)<mark style="color:red;">.</mark>&#x20;
> * **GitHub account**. [GitHub](https://github.com) müxtəlif fəaliyyətlər üçün, bəzən Git-də iş prosesini nümayiş etdirmək üçün, bəzən isə müxtəlif developer tool-lara daxil olmaq üçün autentifikasiya vasitəsi üçün istifadə edilir.  Əgər GitHub hesabınız yoxudrsa, yaradın.
> * Gitbook - [Gitbook](https://www.gitbook.com/) İstifadəçilər və ya proqramçılar üçün sənədləşmə yaratmağa imkan verin. Bu sənədləşmə də, API First tələblərini rahatlıqla auditoriyaya çatdırmaq mümkündür. həmçinin də, platforma avtomatik olaraq sizə URL təqdim edir və bu URL ilə istənilən yerdən sənədləşmə ilə tanış olmaq mümkün olur. Həmçinin də, platfomra GitHub ilə sinxorinizasiya olunaraq məlumat itkisinin qarşısı alınır.
> * Swagger - [Swagger](https://swagger.io/) API dizayn və sənədləşməsi üçün istifadə olunan vasitədir. Hazırda ən geniş istifadə olunan Open API vasitəsidir.
> * Stoplight
> * Apigee API Management - [Google Cloud API](https://cloud.google.com/apigee) proqramçılara cloud üzərindən çox rahatlıqla API yaratmaq, publish etmək onların monitorinqi aparmağa imkan verir.&#x20;

### Proqram təminatlarının yoxlanılması <a href="#testing-your-setup" id="testing-your-setup"></a>

> * **Postman yoxlanılması** - Postman app açdıqdan sonra **New** - **HTTP Request** seçib aşağıdakı **URL**-i **GET** qarşısında qeyd edin: [`https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&token=3c63416a24d3b969da6df9271faa9d6e`](https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates?origin=GYD\&token=3c63416a24d3b969da6df9271faa9d6e) `` **Send** düyməsini basın. Əgər cavab alırsınızsa hər şey qaydasındadır (bəzən komputerdə olan məhdudiyyətlərə görə sorğuya cavab alınmaya bilər)&#x20;
> * <mark style="color:red;">To check whether Git is installed, open up Terminal (on Mac) or Command Prompt (on Windows) and type</mark> <mark style="color:red;"></mark><mark style="color:red;">`git --version`</mark><mark style="color:red;">. If it’s installed, you’ll see the version.</mark>

![](<.gitbook/assets/Postman\_check (1).png>)

> * **cURL yoxlanılması** - cURL quraşdırıldığından əmin olmaq üçün Mac-da Terminalı, Windows-da isə Command Prompt-u açıb bunu qeyd edin `curl --location --request GET 'https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&token=3c63416a24d3b969da6df9271faa9d6e'` Əgər JSON cavabı alırsınızsa dmeək ki, hər şey qaydasındadır.

![cURL](<.gitbook/assets/curl\_check (1).png>)
