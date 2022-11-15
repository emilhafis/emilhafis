# Databases. SQL and MySQL

### Database (Verilənlər bazası) nədir?

> Database-i məlumat və məlumatların toplandığı yer kimi başa düşün.
>
> Database-i kitabdakı index kimi başa düşün. Şəkildə gördüyünüz kimi, burada bir kitab üzrə mündəricat və index əks olunmuşdu. Mündəricat hansı səhifədə hansı mövzuların olduğunu göstərir. Beləliklə, bizdə kitabın əhatə etdiyi mövzular var və bizdə həmin mövzuların yer aldığı index var. İndeks əslində kitab üçün yol xəritəsidir, adları, yerləri və əşyaları əlifba sırası ilə sadalayır və hər bir mövzu ilə əlaqəli səhifə nömrələrini verir. Məsələn bizə Fibonacci lazım olsa biz F hərfini axtarırıq və orada görürük ki, 21.22... və s səhifələrdə bunun haqqında qeyd edilib. Yəni kitab bizim database-mizdir və oradakı mövzular bizim databse də olan məlumatlardır. Index isə məlumatların database-də harada yerləşməsini göstərir.&#x20;
>
> **Kitabdakı məlumata getmək üçün səhifəni açıb baxırıq. Bəs Database-dəki bizə lazım olan məlumatları necə əldə edə bilərik? Burada bizim köməyimizə SQL və Database Management system gəlir.**

<figure><img src="https://lh5.googleusercontent.com/_u0sNpfOkWaqUsk0Dv2fs5Dfb5Q9uXBPk1KewpjpnLR6kNKq1XxYsNhoybAodt-sGnLLFZwt2GYplXbS35fXkdYk7LeqaflKyNx3Wfba7XzT4Qxkpm1_SULaJnVyUKuZbMKLmNRxd2c4qLaQK89t6pSpjzmOUv4jxDcr4UmP9lTtCpqtMtQS7gFVWwq4ZcEAT5k" alt=""><figcaption></figcaption></figure>

### SQL və DMS nədir?

> Bütün bu danışdığımız məsələləri etməkdə bizə kömək olan DMS və SQL kömək edir. Database management System (yəni  DMS- Verilənlər bazasının idarəedilməsi sistemi) və Structured Query Language (yəni SQL - Strukturlaşdırılmış Sorğu Dili) bizə kömək edəcəkdir.&#x20;
>
> Belə ki, istifadəçilər Databse-dəki məlumatları SQL ilə sorğulayır. Biz SQL də sorğu yazarkən bu sorğu ilk öncə DMS-ə gedir və DMS özü birbaşa Database ilə əlaqədə olur.

<figure><img src="https://lh3.googleusercontent.com/jyVM5Mict2blXRo1WEHcYjKGJzr9etZQuEMKROGnzpcM8B_RFGMjSydjwujvh8_RbyppHJ6cKv3odXvwvuoYBMgKVCxk9mhoMnrGUicFkq6jng27vGoNG80CEkO8iC3IwPUNRfIHfXJhsehQRgw6-E8B3Giw57fUQCBqGj2PUdqS7S1Lc-LqXQ3BnzU5NuBHaak" alt=""><figcaption></figcaption></figure>

> Dediyimiz kimi SQL Strukturlaşdırılmış Sorğu dilidir. Və database ilə kommunikasiya üçün standart sorğu dilidir. Belə ki, bir çox fərqli Database-lər vardır və onların əksəriyyəti kommunikasiya üçün SQL dən istifadə edirlər.
>
> SQL Databse-də məlumatların yaradılması, silinməsi yenilənməs və s. həyata keçirir.&#x20;
>
> Şəkildə nümunə SQL sorğusu yer alır. Bu sorğu database-də customers yəni müştərilər cədvəlindəki bütün məlumatları qaytarır. Burada ulduz bütün nə varsa qaytar deməkdir.&#x20;
>
> Bir azdan biz SQL sorğularına baxıb örənəcəyik

<figure><img src=".gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

### MySQL nədir?

> MySQL Database Management System  (DMS - Verilənlər Bazasının Diarəetmə Sistemi) dir. MySQL bizə məlumatları giriş və onları idarə etmək üçün vizual interfeys verir. Beləki biz SQL sorğularını MySQL də yazırıq. MySQL relational DMS dir. Yəni buradakı cədvəllər bir bir ilə əlaqəli olur. Digər məhşur Relational Database Management Systemləri - Postgre, Oracle və s.&#x20;
>
> RDBMS-lərin daha çox nümunələri var, lakin onların hamısı verilənlər bazalarını sorğulamaq üçün standart dil kimi SQL-dən istifadə edirlər.

<figure><img src=".gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

