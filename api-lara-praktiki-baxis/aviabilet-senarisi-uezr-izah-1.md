---
description: Proqramçı kimi API-lardan necə istifadə etmək lazımdır?
---

# Taskın həlli

### Haradan başlamaq lazımdır?

### Activity: Travelpayouts API-larının araşdırılması

> Ilk öncə araşdıraq görək, hansı platformaların API-larına müraciət edib bilet haqqında məlumatı ala bilərik. Bunun üçün müxtəlif yolar var, məsələn google.&#x20;
>
> Ümumiyyətlə sizə Rapid API platformasın məsləhət görürəmki orada müxtəlif API lar ilə tnaış ola bilərsiz.&#x20;
>
> Siz sadəcə google-dan axtarış edərək və ya [RapidAPI](https://rapidapi.com/hub) platformasından API xidmətləri üzrə resursları tapa bilərsiniz.&#x20;

![](../.gitbook/assets/Rapid\_data.png)

{% hint style="info" %}
RapidAPI dünyada ən böyük API Hub-dır. Milyonlarla proqramçılar tərəfindən minlərlə API-ləri tapmaq, sınaqdan keçirmək və onları öz sistemlərinə qoşmaq üçün istifadə olunur. Burada demək olar ki, bütün API dizaynları eyni formada verilmişdir və qruplaşdıraraq daha sadə formada istifadə etmək üçün şərait yaradır. Bir çox API-lara yalnız RapidAPI-dən əldə olunan bir ApiKey ilə daxil olmaq mümkündür.&#x20;
{% endhint %}

> Məsələn məndə dediyimiz API yı bu platformadan tapdım. Bu platforma üzrəindən də, sorğu göndərib məlumatları almaq olar. Bunun üçün Rapid API-da qeydiyyatdan keçib onun verdiyi key-i götürmək və travelpayouts-un key-i lazımdır.&#x20;

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

> Amma məsələni tam başa düşmək üçün Rapid platforması üzrəindən yox, birbaşa sayta keçid edərək oradan məlumatları göstürməyə qərar verdim.
>
> Proqramçılar üçün xeyli yaxşı [aviabilet API variantları](https://rapidapi.com/collection/flight-data-apis) olsa da, bu kursda [Travelpayouts API-dən ](https://rapidapi.com/Travelpayouts/api/flight-data/)istifadə etmək qərarına gəldim, çünki xidmətdən istifadə etmək pulsuz və sadədir.

### Travelpayouts araşdırılması

> [Travelpayouts API-da](https://support.travelpayouts.com/hc/en-us) əsas bölmələri araşdıraq.
>
>

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Help centre-ə keçirik

<figure><img src="../.gitbook/assets/image (1) (1) (2).png" alt=""><figcaption></figcaption></figure>

> 1. Bizə lazım olan [API and data](https://support.travelpayouts.com/hc/en-us/articles/203956163-Travel-insights-with-Aviasales-Data-API) bölməyə daxil oluruq.
> 2. Sol tərəfdə müxtəlif API-ları görürük.
> 3. [Aviasales flight data API](https://support.travelpayouts.com/hc/en-us/sections/201008338-Aviasales-flight-data-API) bölməsinə daxil oluruq. Bu bölmə qeyd edildiyi kimi `The section contains a description of API methods that return various flights data by Aviasales` API metodlarının təsvirini və qayıdan uçuş məlumatlarını əhatə edir.
> 4. Hər hansı bir [endpoint](https://support.travelpayouts.com/hc/en-us/articles/203956163-Travel-insights-with-Aviasales-Data-API) (yəni müraciət edəcəyimiz URL-API) üzərinə klik edib onun parametrləri ilə tanış ola bilərik.
>
> Bu API-lar proqramçıların istədikləri məlumatları əldə etməyə xidmət edir. Proqramçılar onlara lazım olan API-lara müvafiq kriteriyalar ilə müraciət edərək lazımı məlumatları əldə edə bilirlər.
>
>

![Travel insight](<../.gitbook/assets/Travel\_insight (1).png>)

### Aşağıdakı suallara cavab verməyə çalışın

> 1. Travel insights with [Aviasales Data API-dan](https://support.travelpayouts.com/hc/en-us/articles/203956163-Travel-insights-with-Aviasales-Data-API) bizə lazım olan məlumatı qaytarır? Gediş, gəliş aeroport, tarix, qiymət və s.
> 2. Nümunə sorğu hansı formada olmalıdır?
> 3. Hansı avtorizasiya credential-ları tələb olunur?
> 4. Bu API-lərdən istifadə edərək daha hansı məlumatları əldə etmək olar?

****
