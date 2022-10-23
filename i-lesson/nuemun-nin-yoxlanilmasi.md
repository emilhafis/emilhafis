# Nümunənin yoxlanılması

Demək olar ki, bütün API-larda təhlükəsizliklə əlaqədar autentifikasiya parametrləri tələb olunur. Yəni, API-dan cavab almaq üçün platforma tərəfindən sizə verilmiş təhlükəsizlik parametrlərindən istifadə etməlisiniz. Bu parametrlərə üzrə ən çox qarşılaşacağımız anlayış API Key olacaqdır. Həmçinin də, biz sonradan autentifikasiya və avtorizasiyanı detallı analiz edəcəyik. İndi isə bizə travelpayouts API-lara sorğu göndərə bilmək üçün API Key lazımdır.&#x20;

### Nə üçün avtorizasiya lazımdır?

> Avtorizasiyanın olması API-ı hazırlayan tərəflərə aşağıdakı üstünlükləri verir:
>
> * API-lara giriş üzrə icazə (lisenziya) verilməsi
> * Göndərilən sorğular üzrə limitlər tətbiq etmək
> * API daxilində müxtəlif parametrlərin sorğu göndərən üzrə idarə edilməsi
>
> Aviabilet üzrə sorğunu göndərmək üçün bizə travelpayouts veb səhifəsindən API Key almaq lazımdır. API Key servisə giriş üçün parol rolunu oynayır və açıq şəkildə paylaşılmır.

### Activity. Travelpayouts API Key əldə olunması

> Gördüyümüz kimi sorğu göndərə bilmək üçün Key əldə etməliyik

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>



> Travelpayouts-dan API Key əldə etmək üçün:
>
> 1. [https://www.travelpayouts.com/en/](https://www.travelpayouts.com/en/) səhifəsinə daxil oluruq
> 2. Qeydiyyatdan keçirib dashboarda daxil oluruq
> 3. Qeydiyyatdan keçdikdən sonra **Create Project** klik edib yeni layihə yaradırıq
> 4. Layihə məqsədi Others seçib layihəmizin adın daxil edirik, məsələn My flight app
> 5. **Aviasales** proqramına qoşuluruq
> 6. Program bölməsin --> API bölməsinə keçirik və oradakı API Key-i əldə edib rahat bir yerdə saxlayırıq

{% hint style="info" %}
Əgər API Key əldə etməkdə çətinlik çəkirsinizsə aşağıdakı Key-lərdən istifadə edə bilərsiniz. Amma çalışın prosesi özünüz tamamlayın.

60dc1c126941417021d843ca3edca258

3c63416a24d3b969da6df9271faa9d6e
{% endhint %}

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Daha sonrakı dərslərdə autorisation metodlarının detallarına enəcəyik. Hazırda ümumi olaraq başa düşün ki, avtorizasiya prosesi necə həyata keçirilir və API sənədləşməsində hansı formalarda qeyd edilir.
{% endhint %}

### Nümunənin yoxlanılması

APIKey əldə etdiyimizə görə sorğunu necə göndərə bilərik ona baxaq.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Adətən hazır sorğu formatları yerləşdilir. Bunu göndərmək üçün isə bizə tool lazımdır

### Text editor-un olmasından əmin olun

> Növbəti praktikalarda siz kodları text faylda analiz edəcəksiniz. Kodlarla işləyəndə siz əsasən text editor-lardan (plain text) istifadə edəcəksiniz. Aşağıda text editorlar üzrə nümunələr göstərirəm.
>
> * [Sublime Text](https://www.sublimetext.com/) (Mac or PC)
> * [Notepad++](https://notepad-plus-plus.org/) (PC)
> * [Atom](https://atom.io/) (Mac or Windows)
>
> Bu editorlar text-ləri idarə etmək üçün yaxşı imkanlar yaradır. İstədiyinizi seçə bilərsiniz. Əgər indi başqasından istifadə edirsinizsə və sizi qane edirsə onu saxlaya bilərsiniz. Mənim üstünlük verdiyim ilk ikisidir.

###
