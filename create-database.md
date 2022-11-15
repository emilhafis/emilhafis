# Create Database

Biz MySQL and MySQL workbench install etdik indi isə gəlin ilk SQL sorğumuzu yazaq.

Burada ilk işimiz root user adından MySQL workbench ə daxil olmaqdır. Sol menyudan users and privileges menyuya daxil oluruq, orada işlərimizi görmək üçün user açırıq. Adını analyst qoyaq və parol təyin edək.

Və bu useri seçib administrativ bölməyə keçək. Burada görürüsünzki heç bir bölmə seçkili deyil. Və biz burada bu istifadəçiyə root ilə eyni hüquqlara malik olan DBA rolun verək. Və userimiz artıq root ilə eyni hüquqa malikdir. Və artıq biz Databsevə Table yarada və onları idarə edə bilərik. Yəni tam bizim istədiyimiz hər şeyi edə bilərik. Və sonda apply edək. Və son olaraq root userdən çıxıb yeni yaratdığımız user ilə daxil olaq.&#x20;

<figure><img src=".gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

### Creating Database and Tables

Hazırda biz ilk SQL sorğumuzu yazacağıq. İlk sorğumuz bizə mövcud olan Database-ləri göstərmək olacaq.&#x20;

```sql
SHOW DATABASES;
```

<figure><img src=".gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

Bu sorğu bizə mövcud olan bütün Databaseləri göstərir. Burada 4 database görəcəksiniz. Hansıkı default olaraq install vaxtı yaranır. Və bunların heç biri bizim üçün yararlı olmayacaq. Bunun üçün də biz öz Databasemizi yaratmalıyıq və onu adlandırmalıyıq. Biz databasemizi analyst adlandıraq.

```
CREATE DATABSE ANALYST;
```

Və gəlin komandanı icra edək. Və görürsünüzki uğurlu oldu. VƏ yenidən SHOW DATABASES; edək və yaratdığımız database i aşağıda görəəcyik.

<figure><img src=".gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

Buradan gördük ki, biz database necə yaratdıq. İndi isə biz yaratdığımız database ə daxil olaq. Bunun üçün biz aşağıdakı komandanı buraxmalıyıq.&#x20;

```
USE ANALYST;
```

Indi biz yaratd;];m;z database daxilindəyik. İndi isə biz bunun içərisində hansı cədvəllər olduğuna baxaq. Komandamızın nəticəsindən görürükki heç bir table yoxdur ,wnki he, bir table yaratmamışıq. Onu bir azdan yaradacağıq

```
SHOW TABLES;
```

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

### Delete Database

Son sorğumuz isə Databse in silinməsi olacaqdır. Bunun üçün biz aşağıdakı komandanı icra edirik. Gəlin komandanı run edək və databasein necə uğurlu silinməsinə baxaq. Silindikdən sonra mövud Database lərə baxdıqda əvvəlki formada olan Databaeləri görürük.

```
DROP DATABASE ANALYST;

SHOW DATABASES;
```

<figure><img src=".gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

İndi isə biz yenidən Databse yaradıb onun daxilində cədvəl yaradacğaıq.
