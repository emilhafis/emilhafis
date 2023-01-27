# Relational Database Management System

### RDBMS nədir?

> So I mentioned in the last video that MySQL was a relational database
>
> management system or RDBMS.
>
> Bildirmişdim ki, MySQL Realtional Database Managament (RDBMS) sistemidir.
>
> Və indi baxaqki RDBMS nədir
>
> Relation database bir neçə cədvəllərdə toplanmış məlumat toplusudur.&#x20;
>
> Cədvəllər stər və sütünlardan ibarət olur. Əgər biz şəkildəki nümunə üzrə baxsaq,  bizim mobil tətbiqdəki istifadəçilərin cədvəlini görərəik.
>
> Cədvəldə ID filed i, istifadəçilərin adları və soyadları qeyd edilmişdir. Deməli bizim data kateqoriyamız, yəni column (sütünlarımız) `id,`` `_`first_name, last_name`_ ibarətdir.
>
> Və hər bir row yəni sətr bir colum yəni 1 filed üzrə dəyərləri göstərir.&#x20;
>
> Beləki, `first_name` bütün userlərin adları daxildir:
>
> * Aydin
> * Azər
> * Elşən
> * Sara
>
> Eyni ilə last\_name ə bütün userlərin soyadları daxildir.&#x20;
>
> Bu nümunədə biz görürük ki, relational databse də cədvəllər hansı formada olur.

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

> Dem'li realtional database əsasını databasedə saxlanılan table-lar təşkil edir və table-lar bi biri ilə əlaqələndirilə bilnir.&#x20;

{% hint style="info" %}
Mən çalışıram terminləri ingilis dilində deyim ki qarşınıa çıxanda biləsiniz söhbət nədən gedir
{% endhint %}



> Siz şəkildə 2 cədvəl görürüsünüz.&#x20;
>
> Deməli bizdə olan **customers** table və **register\_date** cədvəli. yəni qeydiyyat tarixi.
>
> Biz **register\_**_**date** cədvəlində qeydiyyat tarixlərini görürük. Həmçinində burada **customer**_**id** filed-ini sütununu görürük. Və bu **customers** cədvəlindəki id filed-nə link olunub yəni əlaqələndiirlir.
>
> Beləliklə, əlaqəli verilənlər bazasındakı yəni relational database də cədvəllər bu şəkildə əlaqələndirilə bilər və ümumi sütünları paylaşıla bilər.  Buna görə də verilənlər bazası daxilində əlaqələr `relational database` dedikdə bunu nəzərdə tuturuq. bunun üstünlüyü odurki biz qeydiyyat cədvəlində yenidən userə məxsus eyni məlumatları kopyalamırıq. burada məlumat azdır deyə sizə sadə gələ bilər amma realda bu məlumatlar və cədvəllər həddindən çox olur.
>
> Beləki RDBMS olan MySQL bizə relation database ə giriş və onunla işləməyə imkan verən proqram təminatıdır.&#x20;

<figure><img src=".gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>
