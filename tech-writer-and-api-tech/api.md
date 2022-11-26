# API



### API nədir?

> API akronimi yəni açılışı Application Programming İnterfeysdir. Yəni iki proqram təminatının bir biri ilə danışmasına xidmət edir. Hər dəfə siz telefonunuzda YouTuba, Facebook-a daxil olanda, mesaj göndərəndə və ya hava proqnozuna baxanda API-lardan istifadə edirsiniz.

### API nümunəli izah

> Gəlin real nümunə üzrə başa düşməyə çalışaq.
>
> Məsələn, Siz telefonunuzda hər hansı bir tətbiqi işlətdiyiniz vaxt nə baş verir?
>
> Bu sxemdə bizim mobil telefonumuz və serverimiz vardır. Server məlumatların emal olunduğu yer kimi başa düşək, növbəti dərslərdə daha yaxşı başa düşəcəksiniz.
>
> Deməli bizim telefon və serverimiz vardır. Telefondakı tətbiqimizi açdıqdıa, təsəvvür edək ki, bu mobil bankşılıqdır, tətbiqimiz internetə bağlanır və məlumatları serverə göndərir.&#x20;
>
> Server məlumatları aldıqdan sonra lazımı prosesləri icra edir və məlumatları yenidən sizin telefonunuza daha dəqiq telefonunzdakı tətbiqinizə qaytarır.&#x20;
>
> Tətbiq daha sonra həmin məlumatları emal edir və istədiyiniz məlumatları oxunaqlı şəkildə sizə təqdim edir.
>
>
>
> Bunu daha yaxşı izah etmək üçün digər çox məhşur olan real həyatla müqayisədəki API nümunəsi ilə tanış olaq.
>
> Təsəvvür edin ki, siz restoranda oturmusunuz və qarşısınızda bir çox seçim olan menyu vardır. Mətbəx isə sizin sifarişlərinizi hazır edən "sistemin" bir hissəsidir. buradan çatışmayan məsələ seçdiyiniz sifarişin mətbəxə çatdırılması və hazırlanmış sifarişin mətbəxdən sizə gətirilməsidir. Sırf burada isə bizim köməyimizə ofisiant və ya API gəlmiş olur. Ofisiant sorğunuzu və ya sifarişinizi qəbul edən və mətbəxə – sistemə nə etməli olduğunuzu söyləyən vasitə və ya API-dir. Yekunda ofisiant cavabı sizə çatdırır; yəni bizim keysimizdə yeməyi bizə gətirir.
>
> Burada biz - mobil telefondakı tətbiq, mətbəx - server, ofisiant - API və menyudakı seçimlər isə API parametrləridir.

![API vs Real life](../.gitbook/assets/blueprint-APIs-requests.jpg)

> Real həyatda biz artıq bir çox yerdə rastlaşırıq ki, yemək isfarişlərini online və ya restoran daxilində elektron cihazdan (planşet, mobil telefon və s) vermək mümkündür və bu sifarişlər mətbəxdə yerləşən cihaza necə çatdırılır.
>
> Burada proses bəs necə qurulmuşdur?&#x20;
>
> Məsələ çox sadədir, biz istədiyimiz sifarişi elektron cihazdan seçib təsdiq etdikdən sonra, cihaz internet üzərindən bizim sorğumuzu mətbəxdə yerləşən cihaza çatdırır. Aşpaz həmin cihaza baxaraq bizim nə sifariş etdiyimiz ilə tanış olur. Aşağıdakı şəkildə bunun texniki təsvirini daha yaxşı görə bilərsiniz. Burada biz mətbəxə bir ədə burgeri mobil cihaz üzərindən sifariş veririk.
>
> Bizim sifarişimiz mətbəxə çatdıqdan sonra dərhal mobil tətbiqimizə qayıdır ki, burgeriniz hazırlanır. Müəyyən müddətdən sonra sifarişimi zhazır olan kimi mətbəx bizim mobil tətbiqimizə hazırdır qaytarır.

![](../.gitbook/assets/request\_response.png)

> Növbəti mövzularda real nümunələr ilə daha da prosesi aydın formada izah edəcəyəm.

### API əsas üstünlükləri

> API-ların əsas üstünlüklərindən və məqsədlərindən biri də ondan ibarətdir ki, sistemin daxildə necə işlədiyini gizlətmək və yalnız proqramçılara (inteqratorlara) lazım olan hissələrə kənara çıxarmaqdır. Yəni, sistemdən API vasitəsilə istifadə edən tərəflərə dəyişiklikləri bildirməməklə sistemin daxili tələbləri və funksiyalarını sonradan dəyişməyin mümkünlüyüdür. Məsələn bizim nümunəmizdə - mətbəxdəki işçilərin dəyişdirilməsi, yemək hazırlanma standartlarının dəyişdirilməsi nə biz (yəni müraciət edən tətbiq), nə də ofisiant (yəni API) tərəfdə hər hansı dəyişikliyə səbəb olmur.&#x20;

###
