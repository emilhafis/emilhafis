# Where clause

Burada isə biz select statemntsdə `where`  şərtinə baxacağıq. Burada biz customer tabledə bütün məlumatları select edirik. Bunun üçün ulduzdan istifadə edirik. Və nəticədə cusotmer də nə məlumat varsa hamsı qaydıır.&#x20;

Bəs mən ancaq istədiyim bir rov nu yəni stəri gətirmək istəsəm nə emtəliyəm. Gəlin dəqiqləşdirək, mən anca Babayev soyadlı şəxsləri axtarmaq istəyirəmş. Bunun üçün biz sorğumuza vhere şərtini əlavə edirik.

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

Burada gördüyünüz kimi bütün məlumatları gətirdik. İndi isə şərt yazıb dediyimiz məlumatı gətirək. Bunun üçün sorğudan sonra ühere clause yazırıq

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

Gördüyümüz kimi burada yalnız bizə lazım olan Babayev soyadlı şəxs qayıdıb. char və varchar üçün tək dırnaq isitfadə edirik.Və bu dırnaq içərisində istədiyimiz soyadı qeyd edirik.  API dan öyrəndiyimiz kimi String üçün dırnaq əlavə edirik. Rəqəm üçün ehtiyac olmur. Nəticəədə gördünüz ki istədiyimiz sətr qyaıtdı. əgər burda 1-dən çox Babayev olsa idi hamsı qayıdacaqdır.

Əgər type char və ya varchar deyilsə, int və ya decimal dırsa onda dırnaqsızda yazmaq olar.

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

Gördüyümz kimi biz burada Babayev ilə sorğu edəndə 2 Babayev gəlir.&#x20;

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

Bəs biz konkret olaraq Babayev ləri və istədiyimiz nömrələri axtaranda necə olur. bunun üçün AND şərtindən istifdə edirik. Nəticədə bizim tətbiq etdiyimiz nömrəyə uyğun yalnız bir Bababyev qayıtdı.

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

```
SELECT * FROM customers;

SELECT * FROM customers
WHERE last_name = 'Babayev';

SELECT * FROM customers
WHERE last_name = 'Babayev'
and phone_number = '+994708976545';

```



### Or

AND istifadə etdiyimiz kimi OR da istifadə edə bilərik. Əgər biz hər iki dəyərdən birinin olmasını istəyiriksə onda OR yalnız ikisinədə iuyğun olmasın istəyirksə AND işlədirik.

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Gördüymüz kimi OR nəticəsində bizə həm Əhmədov, çünki Əhmədov istəmişik, həmdə mobil nömrə çünki bunuda istəmişik qayıtdı. Amma bunu AND ə dəyişsək nəticə olmayaca. Çünki hər iki dəyərin eyni olduğu sətr və ya şəxs yoxdur.

Burada biz AND və OR üzrə istədiyimiz qədər bir birinin ardınca şərt yaza bilərik.

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>
