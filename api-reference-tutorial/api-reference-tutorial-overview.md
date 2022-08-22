# Overview

> Burada biz REST API Dizaynı üçün əsas olan 5 bölməyə baxacağıq: resursun təsviri, enpoint və metodlar, parametrlər, sorğu nümunəsi və cavab nümunəsi/sxemi. API dizayn etmək üçün hər bölmədə lazımlı məlumatlar ilə tanış olub "best parctice" nümunələrə bacağıq.

### REST API dizaynında 5 əsas bölmə

> Demək olar ki, bütün API-larda bu 5 bölmə iştirak edir.

#### [Resursun təsviri](../avtorizasiya-noevl-ri/step-1-resource-description-api-reference-tutorial.md)

Resurslar API tərəfindən qaytarılan məlumatlara deyilir.

#### [Endpoint və metodlar](broken-reference)

**Endpoint** resursa necə giriş əldə edə biləcəyinizi, **metod** isə resurs üzərində hansı əməliyyatları (`GET`, `POST`, `DELETE` və s) icra edə biləcəyinizi göstərir.

#### [Parametrlər](../api-dizayn/parametrl-r.md)

**Parameter**-lər **Endpoint** ilə göndərə biləcəyiniz dəyərlərdir. Bu dəyərlər qayıdan cavabda (bundan sonra **Response**) hansı dəyərlərin olmasını və ya **Response**-un formatını təyin edir.&#x20;

#### [Sorğu nümunəsi](../api-dizayn/sorgu-nuemun-si.md)

**Sorğu nümunəsi** **Endpoint**-də daxil olmaqla istifadə edilmiş `parametrlər konfiqurasiyanı` göstərir.&#x20;

#### [Cavab nümunəsi](step-5-response-example-and-schema-api-reference-tutorial.md)

Cavab nümunəsi sorğu nümunəsinə əsaslanan nümunə cavabı göstərir; cavab sxemi isə cavabın bütün mümkün elementlərini müəyyən edərək onların təsvirini verir.
