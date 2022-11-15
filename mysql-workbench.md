# MySQL Workbench

### What is MySQL workbench&#x20;

Vaxt itirməmək üçün MySQL necə yüklənir onun məlumatlarını sizin üçün bölüşəcəm.&#x20;

İndi isə quraşdırılmış MySQL workbench ə baxaq ki, bu nədir və biz ondan necə istifadə edəcəyik.&#x20;

MySQL workbench MySQL Database-ə inteqrasiya olunmuş development mühitidir. Sadə dildə desək bu database-i dizayn etmək, onu idarə etmək, SQL sorğuları vermək üçün visual interfeysi olan bir vasitəsdir. Belə ki, biz bütün SQL kod və sorğuları buradan yaza bilirik.

Biz bu sorğuları və kodları MySQL workbench olmadan da birbaşa command line da yaza bilərik.

{% hint style="warning" %}
command line nədir?
{% endhint %}

Amma MySQL workbench bizə vizual interfeys və bir çox üstünlüklər verir. Hətta bir çox məsələləri visual interfeysdən kod yazmadan həyata keçrimək mükkün olur. Məsələn cədvəl yaratmaq içinə məlumatları doldurmaq və s.&#x20;

Artıq biz bilirik ki, MySQL workbench nədir. Gəlin MySQL workbench də sorğumuzu yazmamışdan qabaq qısa baxış keçirək.

### MySQL workbench overview

Ilk iişimiz MySQL workbench i açmaq olacaqdır. Burada **root** userə klik edirik. bura klik edəndən sonra MySQL workbench içərisinə daxil olub bu formada ekranı görürük. Və gördüyünü ekranda biz bütün sorğuları buradan yazacağıq və bütün işimiz demək olarki bu ekranla əlaqəli olacaq.&#x20;

<figure><img src="https://lh4.googleusercontent.com/d8RQ-tn1PcPmCQ1GBaRFLD7_vhkOCV5Gi4GHTMMn0TxZZ1llzHeiQm1Ri2H4LuD8TI-LNHIonoOUe1O65erqCzHixd1pdV_PVoRjnbdN1yovGmjfMpgPj6xqID_EBTRErkNo5K7GBS3b97UjBCVYZOnKhwWLMJkeCKgPV15gcJH8tyTVUicLKqc5ttwGpFDzyGs" alt=""><figcaption></figcaption></figure>

MySQL workbench -də xeyli funksionallıqlar vardır. Solda və sağda bir çox funksionallıların olduğunu görürük. Bizim kursumuzda ümumi təsviri verəcəm. Məqsədimiz hər bi rdetalı bilmək deyil. Bilməliyik ki, analitik kimi bizə sadə məlumatları necə əldə edirik.

Text editor səhifəsində biz öz sorğularımızı yazırıq. Bu səhifə Query 1, query 2 və s. xeyli sayda aça bilərik. Hazırda mən bəzi sorğuları yazacam. BAşa adüşməsənəzi narahat olmayaın keçəcəyik. Sizə gösstərmək istəyirəm ki, sql sorğular necə olur.&#x20;

```
SELECT * FROM table1;
SELECT * FROM table2;
```

Gördüyünüz kimi hər bir sorğu nöqtəli vergül ilə bitir. SQL başa burdan başa düşürki 1-ci sorğumuz bitib və 2-cin veririk. Bir sözlə SQL bu nöqtəli vergülə görə təyin edirik ki, bizim iki sorğumuz vardır.

Biz sorğumuzu yazdıq, indi isə baxaq ki onu necə işə salırıq. Bunun üçün biz üst panelə getməliyik. Biz burdakı iconların üzərinə gəldikdə hint olaraq bizə bildirir ki, bunlar nə iş görür. Məsələn buradakı folder bizə göstərərki hazır scriptləri aç. Əgər siz hazır scriptləi komputerinizdə saxlamısınızsa onları birbaşaş aça bilərsiz. həmçinin də siz yazdığınız scriptləri sonrakı istifadələr üçün saxlaya bilrəsiniz.  Amma sorğunu işə salmaq üçün bizə maraqlı olan bu 4 icondur iconlardır.&#x20;

Bunlardan 3-cü sorğuları işə salmaq, qırmızı olan isə iş prosesində olan sorğunu dayandırmaq üçün istifadə eidlir. Əgər biz ilk icon üzərinə gəlsək görərəik ki, yazılrı ki execute the `selected portion of the script or everything if there is no selection` Yəni ya seçimin üzrə run et yada nə varsa hamsını. Məsələn mən seçim edib işə salıramsa ancaq seçdiyim sorğu icra olunur. Əgər seçim etmirəmsə ilk öncə birinci sonra isə ikinci sorğu icra edilir.

**İkinci button** isə fərqli işləyir. Bu keyboardın kursorunun olduğu sorğunu icra edir. Məsələn bu ancaq birinci sorğunu icra edir çünki kursorumuz birinicnin üzərindədir. Əgər biz kursoru ikinciyə keçirsək o zaman ikicni sorğunu icra edəcək.&#x20;

**Üçüncü button** da fərqli işləyir. Bu da ikinci kimi kursor üzərində olan sorğunu icra edir. Amma fərq odurki arxada nə proseslər baş veri ronu göstərir. yəni bu sorğu necə icra edirlir. Bu çox faydalı olsada çox vaxtı bundan istifadə etmirlər. Çünki əsas lazım olan sorğunun cavabı olur.&#x20;

**4-cü qırmızı** əl işarəsi isə icra edilməkdə olan sorğunu dayandırır. Əgər siz sorğu icra edirsiniz və nəticəsində minlərlə sətir qayıdır və buda çox vaxt alırsa və siz sonuna qədər gözləmək istəmirsinizsə o zaman prosesi bu button ilə dayandırırsız.&#x20;

və üst sıradakı **digər əsas icon** isə limit ilə əlaqəlidir. Əgər siz minlərlə sətrlik cədvəldən sorğu edirsinizsə və sizə bütün məlumatlt lazım deyilsə burada limit tətbiq edə bilərsiniz. By default limit 1000 olur. Amma siz çoxaldıb və ya azlda bilərsiniz. Bunun əsas üstünlüyü odur ki, sorğunuza cavab dərhal gəlir. biri var 1 milyon sətri gözləyəsiz biridə var 1000 dətr. Yenədə bu sizin sorğu məqsədinizdən aıslı olur.

### Run command

Gəlin indi real olaraq sorğunu işə salaq.&#x20;

Gəlin burdakı ilk sorğunu işə salaq və baxaq görək nə baş verir.&#x20;

Gördüynüz kimi aşağıda action ppop up çıxdı və bu bizim aktual sorğu nəticəmizdir. Siz sorğu edərkən sizin nəticələriniz burada görünür. Əgər sorğumuz uğurlu olsa idi qayıtmış məlumatlar burada yer alacaqdır. Əgər biz uğurlu sorğu göndəririk sə nəticə burada olur, yox sorğuda səhvlik olarsa o zaman error alacağıq. Hansıkı bu keysimizdə error aldır.  Sorğu nəticəmizdədə görürük ki, nələri sorğu edirik və limit nə qədərdir.&#x20;

Siz burada errorun bizə bəlli olan qırmızı işarəsini dərhal görə bilərisz. Eror bizə səbəbi gössıtirir. **Bildirirki, Database seçilməmişdir.**&#x20;

Bir azdan biz real olaraq cədvəldən məlumatların select olunmasına baxacağıq. Və orada uğurlu nəticələrlə tanış olacağıq.

İndi biz bilirik ki, SQL sorğuları necə işə salmaq olur. İndi isə soldakı menyuya baxaq. Bu menyunu biz sürətli keçəcəyik çünki analitik kimi ondan istifadə edilmir.&#x20;

### Management menyu

Burada server stautusların görə bilərik. Üzərinə klik etdikdə serverimizin işləyib işləmədiyinin şahidi oluruq.

Növbəti connectionda bizim serverə qoşulmaları görə bilirik

Və burada həmçinində user and privilegiyalar vardır. Buradan bizim sevrerdə olan userlər və onlar üzrə imtiyazları görə bilərik.Buradan privilegiyalarıda idarə etmək mümkündür

Burada bizim üçün ən vacib məsələ **Schema** bölməsidir. Databse scheme databse diagramdır və bizə databse-mizdə olan cədvəlləri həmçinində əlaqələri və digər məlumatları göstərir. Siz buradan database siyahısın görə bilərsiz.

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Databse qarşısında bu formada silindir işarə olur hər zaman. Sxemlərdə də bu icon qoyulur.&#x20;

Hər bir databesin adın görürük. Sizdə ilk öncə mobile\_app və qrgenerator olmayacaq. Amma biz onları indi yaradacağıq. Biz databse üzrəinə klik edəndə, görürük ki burada cədvəllər,view prosedur və funskiyaları görürük. Burada table üzrəinə klik etdikdə isə qr üzrə hansı cədvəllərin olduğunu görürük. Amma bunların hamsın bilməyiniz üçün narahat olmayın. Laızm olanları keçəcəyik.

<figure><img src=".gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

Database sxemləri database də hansı cədvəllərin olduğunu hansı databse lərin olduğunu və ya digər məlumatları göstərən əhəmiyyətli bir funksionallıqdır.

Ən əsas bilməli oldğunuz məsələ odurki biz soröularımızı burada yazacağıq. Biz sorğularımızı bu icon ilə işə salacağıq.&#x20;
