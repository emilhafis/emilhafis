# I Lesson. APIs. A programmer's View of APIs

### Kurs üçün hansı vasitələr (tools) lazım olacaqdır?

> * **Kompüter**.
> * **Text editor -** Əgər sizin hazırda istifadə etdiyiniz text editor yoxdursa [Sublime Text](https://www.sublimetext.com/) istifadə edə bilərsiniz (həm Mac, həm də Windows üçün pulsuzdur). Əgər başqa editor-lardan (məs, [Visual Studio Code](https://code.visualstudio.com/), [Atom](https://atom.io/) və ya [Notepad++](https://notepad-plus-plus.org/)) istifadə etməyinizdə kifayətdir.&#x20;
> * **Chrome browser -** [Chrome](https://www.google.com/chrome/browser/desktop/index.html) JSON formatında göndərilmiş sorğuları rahatlıqla analiz etmək üçün Javascript Console təmin etdiyi üçün Chrome-dan istifadə edəcəyik. Həmçinin də JSON cavablarını daha rahat oxumaq üçün [JSON Formatter](https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa?hl=en) yekləməlisiniz.
> * **Postman -** [Postman](https://www.getpostman.com/) applikasiyası bizə vizual interfeys üzərindən sorğuları göndərib və alınan cavabları görmək imkanı verir. _**Chrome extension əvəzinə Postman applikasiyasın yüklədiyinizdən əmin olun.**_
> * **curl -** [curl](https://curl.haxx.se/)  command line-dan endpoint-lərə sorğuların göndərilməsi üçün əsas vasitədir. curl MAC-da by default qurulmuş olur, amma Windows-da by default deyildir ( bəzi Windows 10-dakı Powershell-də vardır).  Windows-da Command Prompt-u açıb `curl -V` qeyd edin. Əgər qurulu deyilsə [confusedbycode.com/curl](http://confusedbycode.com/curl) səhifəsindən yükləyə bilərsiniz ( “With Administrator Privileges (free), 64-bit”). Command Prompt-u bağlayıb yenidən açın və `curl -V` yazıb nəticəsinə baxın.

### Proqram təminatlarının yoxlanılması <a href="#testing-your-setup" id="testing-your-setup"></a>

> * **Postman yoxlanılması** - Postman app açdıqdan sonra **New** - **HTTP Request** seçib aşağıdakı **URL**-i **GET** qarşısında qeyd edin: [`https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&token=3c63416a24d3b969da6df9271faa9d6e`](https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates?origin=GYD\&token=3c63416a24d3b969da6df9271faa9d6e) `` **Send** düyməsini basın. Əgər cavab alırsınızsa hər şey qaydasındadır (bəzən komputerdə olan məhdudiyyətlərə görə sorğuya cavab alınmaya bilər)&#x20;
> * <mark style="color:red;">To check whether Git is installed, open up Terminal (on Mac) or Command Prompt (on Windows) and type</mark> <mark style="color:red;"></mark><mark style="color:red;">`git --version`</mark><mark style="color:red;">. If it’s installed, you’ll see the version.</mark>

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

> * **cURL yoxlanılması** - cURL quraşdırıldığından əmin olmaq üçün Mac-da Terminalı, Windows-da isə Command Prompt-u açıb aşağıdakı kod bloku qeyd edin. Əgər JSON cavabı alırsınızsa demək ki, hər şey qaydasındadır.

```
curl --location --request GET 'https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-23&return_at=2023-03-26&currency=azn&limit=2&token=3c63416a24d3b969da6df9271faa9d6e'
```

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

****
