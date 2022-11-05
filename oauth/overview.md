---
description: API-lar üçün avtorizasiya framework-u
---

# Overview

### OAuth nədir?

> İlk ağlımıza gələn sual o olur ki, OAuth ümumiyyətlə nədir?

{% hint style="info" %}
**OAuth** istifadəçilər və ya müştərilər üzrə məlumatları (credentials) paylaşmadan onlara başqa bir sistemin server resurslarına giriş icazəsi verməyə imkan verən avtorizasiya çərçivəsidir (bundan sonra - framework).&#x20;
{% endhint %}

> Bu cümlə bir az qəliz oldu, gəlin onu sadələşdirək.
>
> OAuth API-lara giriş zamanı icazələrin kontrol edilməsi üçün istifadə edilən avtorizasiya framework-dur. Məsələn, biz tez-tez görürük ki, hansısa platformaya daxil olmaq istədikdə bizdən əlavə variantlar kimi Google və ya Facebook vasitəsilə daxil olmaq seçimləri də verilir. Məsələn, [Rapid API](https://rapidapi.com/) saytında qeydiyyat zamanı `Sign up with Google` seçimi də verilir.&#x20;
>
> Bu seçimə klik etdikdə, gmail hesabınızın məlumatlarını istəyir. Əgər məlumatları düzgün daxil edirsinizsə bu zaman **Google** sizin şəxsi məlumatlarınızı **Rapid** saytı ilə paylaşmadan onlara bildirir ki, bu şəxsin mənim platformama daxil olması üçün istifadəçi adı və parolu doğrudur və səndə icazə verə bilərsən.&#x20;
>
> Beləliklə, siz **Rapid** saytında əlavə olaraq məlumatlarını yazıb qeydiyyatdan keçmirsiniz.
>
> **Bax bu OAuth 2.0 autentifikasiya metodu əsasında baş verir.**&#x20;

{% hint style="info" %}
[Rapid API](https://rapidapi.com/) - Dünyanın ən böyük API Marketplace-dir. Bu platformada minlərlə API-ları tapıb onlar ilə tanış ola, onları testləşdirə və onlardan istifadə edə bilərsiniz.&#x20;

Bir sözlə müxtəlif API-ları bir yerə toplayan böyük bir platformadır. Siz fərqli API saytlarına girməkdənsə yalnız Rapid-dən istifadə edə bilərsiniz.
{% endhint %}

#### Rapid API platforması

![Rapid API](../.gitbook/assets/vk\_swiftshader\_icd.json.png)

### OAuth versiyaları

> Hazırda OAuth-un iki versiyası vardır - 1.0a və 2.0.
>
> Versiya 1.0a köhnəlmişdir və demək olar ki, artıq ondan istifadə edən yoxdur. Bizim danışacaqlarımız **OAuth 2.0** haqqında olacaqdır və hazırda **Google**-da ondan çox geniş istifadə edir.

> OAuth-un bir neçə adlandırma növü də vardır - **one-legged OAuth** və **three-legged OAuth.**&#x20;
>
> **One-legged OAuth** o zaman istifadə olunur ki, sizin qoruduğunuz həssas (sensitive) məlumatlar olmur. Məsələn, siz yalnız ümumi məlumatları və yaxud da oxuna bilən (read-only) məlumatları əldə edirsiniz.
>
> Bunun əksinə olaraq **three-legged OAuth** həssas məlumatları qorumaq lazım olanda istifadə edilir. Bu senaridə 3 qrup qarşılıqlı fəaliyyət göstərir:
>
> * Autentifikasiya serveri
> * Resurs serveri (API server)
> * İstifadəçi və ya tətbiq/sayt (Application)
>
> Aşağıda OAuth 2.0 üzrə ümumi təsvir göstərilmişdir.

![](<../.gitbook/assets/OAuth authentication (1).png>)

> Növbəti bölmələrdə prosesi daha dərindən analiz edəcəyik.

{% hint style="info" %}
**OAuth-un ən əsas xüsusiyyəti** - əgər siz API server rolunda çıxış edirsənizsə, yəni sorğular sizə göndərilirsə bu zaman, siz öz bazanızda saxladığınız istifadəçilərin məlumatını paylaşmadan digər resurslara öz resursunuz vasitəsilə icazə verə bilərsiniz. Yəni istifadəçi artıq 1 dəfə sizin resursa daxil olubsa, artıq digər resurslara sizin vasitənizlə daxil ola bilər.&#x20;

Siz bu giriş icazəsini [**Access token**](access-refresh-token.md)-dən istifadə etməklə verə bilirsiz.

Növbəti bölmələrdə daha detallı danışacağıq.
{% endhint %}

