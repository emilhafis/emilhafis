---
description: Bu bölmədə Password grant növündən dnaışacağıq
---

# Resource Owner Password

![](../.gitbook/assets/pass\_ovner.png)

### Ümumi məlumat

> Qeyd edilən grant növünün işlədilməsi tövsiyyə olunmur. Amma buna baxmayaraq **highly-trusted** application-lar bu növdən istifadə edə bilərlər.&#x20;
>
> Bu növdən istifadə edildikdə **istifadəçinin məlumatları** (istifadəçi adı və şifrəsi) həmin platformada alınaraq backend sisteminə göndərilir
>
> **Password grant** növü qorunan istifadəçi məlumatlarına giriş icazəsi olduqda istifadə edilə bilər. bu növ icazə, yalnız **trusted** proqram təminatı üçün uyğundur ki, onu yaradan şirkətin artıq istifadəçi məlumatlarına icazəsi/girişi olsun.
>
> İstifadəçi öz məlumatlarını (istifadəçi adı, şifrə) proqram təminatına təqdim etməyə əmin deyilsə, o zaman bu növdən istifadə edilməməlidir.
>
> Bu növün əsas üstünlüyü ondan ibarətdir ki, proqrama daxil olarkən əlavə proseslər azalır, yəni başqa səhifəyə yönləndirilmə və s. olmur.
>
> Növbəti bölmədə istifadəçi məlumatlarının daxil edilməsi üçün ən çox işlədilən [**Auth code grant** ](authorization-code/)növündə görəcəyik ki, bu məlumatların daxil edilməsi, digər razılıqların verilməsi üçün başqa platformalara yönləndirilmələr baş verir. Bununla belə, **Auth code grant** növü əhəmiyyətli dərəcədə daha təhlükəsizdir və bir çox şirkətlər hətta öz tətbiqləri üçün **Auth code grant** növündən istifadə edirlər.

### Necə işləyir?

![](../.gitbook/assets/pass\_grant-2.png)

> Proses aşağıdakı formada həyata keçirilir:
>
> 1. İstifadəçi tətbiq və ya sayt daxilində **Login** bölməsinə daxil olaraq öz məlumatlarını qeyd edir.
> 2. Tətbiq və ya sayt istifadəçi məlumatlarını **API Gateway / Auth server-ə** göndərir.
> 3. **API Gateway / Auth server** məlumatları yoxlayır
> 4. Yoxlama uğurlu olduqda **API Gateway / Auth server** **Access token** generasiya edib qaytarır.
> 5. **Application** access token-dən istifadə edərək lazımı məlumatı əldə etmək üçün sorğu göndərir.
> 6. **API Gateway / Auth server** token-i yoxlayır.&#x20;
> 7. Token etibarlı olarsa **API Gateway / Auth server** sorğunu **Backend API / Backend Servis**-ə göndərir.
> 8. **Backend API / Backend Servis** lazımı məlumatları **API Gateway / Auth server**-nə qaytarır.
> 9. **API Gateway / Auth server** məlumatları **Application**-a göndərir.

