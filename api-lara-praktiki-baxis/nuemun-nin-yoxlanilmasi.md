# Nümunənin yoxlanılması

Demək olar ki, bütün API-larda təhlükəsizliklə əlaqədar autentifikasiya parametrləri tələb olunur. Yəni, API-dan cavab almaq üçün platforma tərəfindən sizə verilmiş təhlükəsizlik parametrlərindən istifadə etməlisiniz. Bu parametrlərə üzrə ən çox qarşılaşacağımız anlayış API Key olacaqdır. Həmçinin də, biz sonradan autentifikasiya və avtorizasiyanı detallı analiz edəcəyik. İndi isə bizə travelpayouts API-lara sorğu göndərə bilmək üçün API Key lazımdır.&#x20;

### Nə üçün avtorizasiya lazımdır?

> Requiring authorization allows API publishers to do the following:
>
> Avtorizasiyanın olması API-ı hazırlayan tərəflərə aşağıdakı üstünlükləri verir:
>
> * API-lara giriş üzrə icazə (lisenziya) verilməsi
> * Göndərilən sorğular üzrə limitlər tətbiq etmək
> * API daxilində müxtəlif parametrlərin sorğu göndərən üzrə idarə edilməsi
>
> Aviabilet üzrə sorğunu göndərmək üçün bizə travelpayouts veb səhifəsindən API Key almaq lazımdır. API Key servisə giriş üçün parol rolunu oynayır və açıq şəkildə paylaşılmır.

### Activity. Travelpayouts API Key əldə olunması

> Travelpayouts-dan API Key əldə etmək üçün:
>
> 1. [https://www.travelpayouts.com/en/](https://www.travelpayouts.com/en/) səhifəsinə daxil oluruq
> 2. Qeydiyyatdan keçirib dashboarda daxil oluruq
> 3. Qeydiyyatdan keçdikdən sonra **Create Project** klik edib yeni layihə yaradırıq
> 4. Layihə məqsədi Others seçib layihəmizin adın daxil edirik, məsələn My flight app
> 5. **Aviasales** proqramına qoşuluruq
> 6. Program bölməsin seçdikdən sonra API bölməsinə keçirik və oradakı API Key-i əldə edirib rahat bir yerdə saxlayırıq

{% hint style="info" %}
Əgər API Key əldə etməkdə çətinlik çəkirsinizsə aşağıdakı Key-lərdən istifadə edə bilərsiniz. Amma çalışın prosesi özünüz tamamlayın.

60dc1c126941417021d843ca3edca258

3c63416a24d3b969da6df9271faa9d6e
{% endhint %}

![Create Project](<../.gitbook/assets/travel\_create\_project (1).png>) ![Join Aviasales](<../.gitbook/assets/aviasales (1).png>)

![API Key](<../.gitbook/assets/api\_key (1).png>)

{% hint style="info" %}
Keep in mind how users authorize calls with an API — this is something you usually cover in API documentation. Later in the course, we will dive into [authorization methods](https://idratherbewriting.com/learnapidoc/docapis\_more\_about\_authorization.html) in more detail.
{% endhint %}

### Text editor-un olmasından əmin olun

> In the upcoming activities, you’ll work with code in a text file. When you’re working with code, you use a text editor (to work in plain text) instead of a rich text editor (which would provide a WYSIWYG interface). Here are a few choices for text editors:
>
> * [Sublime Text](https://www.sublimetext.com/) (Mac or PC)
> * [Notepad++](https://notepad-plus-plus.org/) (PC)
> * [Atom](https://atom.io/) (Mac or Windows)
>
> These editors provide features that let you better manage the text. Choose the one you want. (My preference is to use Sublime Text when I’m working with independent code samples, and Atom when I’m working with Jekyll projects.) Avoid using TextEdit since it adds some formatting behind the scenes that can corrupt your content.

###
