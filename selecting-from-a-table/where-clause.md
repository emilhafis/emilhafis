# Where clause

Burada isə biz select statemntsdə `where`  şərtinə baxacağıq. Burada biz customer tabledə bütün məlumatları select edirik. Bunun üçün ulduzdan istifadə edirik. Və nəticədə cusotmer də nə məlumat varsa hamsı qaydıır.&#x20;

Bəs mən ancaq istədiyim bir rov nu yəni stəri gətirmək istəsəm nə emtəliyəm. Gəlin dəqiqləşdirək, mən anca Babayev soyadlı şəxsləri axtarmaq istəyirəmş. Bunun üçün biz sorğumuza vhere şərtini əlavə edirik.

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

Burada gördüyünüz kimi bütün məlumatları gətirdik. İndi isə şərt yazıb dediyimiz məlumatı gətirək. Bunun üçün sorğudan sonra ühere clause yazırıq

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

Gördüyümüz kimi burada yalnız bizə lazım olan Babayev soyadlı şəxs qayıdıb. char və varchar üçün tək dırnaq isitfadə edirik.Və bu dırnaq içərisində istədiyimiz soyadı qeyd edirik.  API dan öyrəndiyimiz kimi String üçün dırnaq əlavə edirik. Rəqəm üçün ehtiyac olmur. Nəticəədə gördünüz ki istədiyimiz sətr qyaıtdı. əgər burda 1-dən çox Babayev olsa idi hamsı qayıdacaqdır.

Əgər type char və ya varchar deyilsə, int və ya decimal dırsa onda dırnaqsızda yazmaq olar.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

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

![](<../.gitbook/assets/image (20).png>)

As well as using the and

statement, we can also use or.

So we can say select star from products

where price is equal to 3.00

or coffee origin is equal to Colombia.

And if we run that, let's see what we get.

So you can see here it's returned all the rows

which meet either one or both of the criterias.

So here we've got both our coffee origins which are equal to Colombia.

But you can see it's also included the espresso,

which has a price of 2.5, so that didn't meet

the price is equal to 3.0 but it did meet the coffee origin is equal to Colombia.

And then similarly here, we have the filter coffee

which does have a price of 3.00,

but it doesn't have a coffee origin of Sri Lanka.

So that all means it only has to meet one of the where clauses

but the and it has to meet both of the where clauses.

So that's it for adding a simple where clause to our select statement.

We just have to type where column name is equal to a certain value,

and we can add as many where clauses as we want

using the and or the or statement.

So let's move on to the next video.
