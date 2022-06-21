---
description: Proqramçı kimi API-lardan necə istifadə etmək lazımdır?
---

# API-lara praktiki baxış

### Ümumi məlumat

> Özünüzü proqramçıların yerinə qoymaqla onların ehtiyacların daha yaxşı başa düşəcəksiniz və onlara API sənədləşdirilməsində nələr lazım olduğunu daha yaxşı anlayacaqsınız. Proqramçılar adətən Postman və cURL tool-larından istifadə edərək sorğu nəticəsində əldə etdikləri cavab strukturu ilə tanış olurlar və dinamik olaraq sadə formada lazımı məlumatları veb səhifələr və ya digər tətbiqlər ilə inteqrasiya edib yoxlayırlar.

### Bölmənin mövzuları

> * [Aviabilet məlumatının əldə olunması üçün senari](api-lara-praktiki-baxis.md#aviabilet-uezr-m-lumatin-ld-olunmasi-uecuen-senari)
> * [Get authorization keys](https://idratherbewriting.com/learnapidoc/docapis\_get\_auth\_keys.html)
> * [Submit requests through Postman](https://idratherbewriting.com/learnapidoc/docapis\_postman.html)
> * [curl intro and installation](https://idratherbewriting.com/learnapidoc/docapis\_install\_curl.html)
> * [Make a curl call](https://idratherbewriting.com/learnapidoc/docapis\_make\_curl\_call.html)
> * [Understand curl more](https://idratherbewriting.com/learnapidoc/docapis\_understand\_curl.html)
> * [Activity: Use methods with curl](https://idratherbewriting.com/learnapidoc/docapis\_curl\_with\_petstore.html)
> * [Analyze the JSON response](https://idratherbewriting.com/learnapidoc/docapis\_analyze\_json.html)
> * [Inspect the JSON from the response payload](https://idratherbewriting.com/learnapidoc/docapis\_json\_console.html)
> * [Access and print a specific JSON value](https://idratherbewriting.com/learnapidoc/docapis\_access\_json\_values.html)
> * [Dive into dot notation](https://idratherbewriting.com/learnapidoc/docapis\_diving\_into\_dot\_notation.html)

### Aviabilet məlumatının əldə olunması üçün senari

> Məsələn [www.bilet.az](https://bilet.az/)[ ](https://tickets.az/)saytına daxil olub kriteriyaları göstərərək axtarış edək.

### Kurs kimlər üçün nəzərdə tutulmuşdur?

> Kurs ilk növbədə aşağıdakı auditoriyalara xidmət edir:
>
> 1. Peşəkar Tech writer-lər kimlərki proqramçılar üçün hazırlanan ənənəvi sənədləşmədən API First yönümlü sənədləşməyə keçmək istəyirlər
> 2. Tələblər - kimlərki texniki sahədə özlərini inkişaf etdirib zamanın tələblərinə cavab verən IT analitik olmaq istəyirlər
> 3. Proqramçılar - kimlərki öz API-larını sənədləşdirmək istəyir və sənədləşdirmə zamanı API-lar üzrə ən yaxşı struktur, dizayn və terminalagoiyalardan istifadə etmək istəyir
> 4. Müəllimlər - Kimlərki IT Analitikləri yetişdirərək onlara Tech Writing öyrədirlər

### Kursun mündəricatı

> The course consists of the following sections:
>
> * [I: Introduction to REST APIs](https://idratherbewriting.com/learnapidoc/docapis\_introtoapis.html)
> * [II: Using an API like a developer](https://idratherbewriting.com/learnapidoc/likeadeveloper.html)
> * [III: Documenting API endpoints](https://idratherbewriting.com/learnapidoc/docendpoints.html)
> * [IV: OpenAPI spec and generated reference docs](https://idratherbewriting.com/learnapidoc/restapispecifications.html)
> * [V: Step-by-step OpenAPI code tutorial](https://idratherbewriting.com/learnapidoc/openapi\_tutorial.html)
> * [VI: Testing API docs](https://idratherbewriting.com/learnapidoc/testingdocs.html)
> * [VII: Conceptual topics in API docs](https://idratherbewriting.com/learnapidoc/docconceptual.html)
> * [VIII: Code tutorials](https://idratherbewriting.com/learnapidoc/docapiscode.html)
> * [IX: The writing process](https://idratherbewriting.com/learnapidoc/writing\_process.html)
> * [X: Publishing API docs](https://idratherbewriting.com/learnapidoc/publishingapis.html)
> * [XI: Thriving in the API doc space](https://idratherbewriting.com/learnapidoc/jobapis.html)
> * [XII: Native library APIs](https://idratherbewriting.com/learnapidoc/nativelibraryapis.html)
> * [XIII: Processes and methodology](https://idratherbewriting.com/learnapidoc/docapis\_managing\_doc\_processes.html)
> * [XIV: Metrics and measurement](https://idratherbewriting.com/learnapidoc/docapis\_metrics\_and\_measurement.html)
> * [XV: Additional resources](https://idratherbewriting.com/learnapidoc/resources.html)

### How long will it take to finish the course? <a href="#how-long-will-it-take-to-finish-the-course" id="how-long-will-it-take-to-finish-the-course"></a>

****

### Will this course help you get a job in API documentation? <a href="#will-this-course-help-you-get-a-job-in-api-documentation" id="will-this-course-help-you-get-a-job-in-api-documentation"></a>

> The most common reason people take this course is to transition into API documentation. This course will help you make that transition, but you can’t just passively read through the content. You need to do the activities outlined in each section, especially those topics that involve working with content from an [open-source project](https://idratherbewriting.com/learnapidoc/docapis\_find\_open\_source\_project.html) (or something similar). These activities are crucial to building experience and credibility with a portfolio. I provide more details in [Getting an API documentation job and thriving](https://idratherbewriting.com/learnapidoc/jobapis.html). Without a strong portfolio to demonstrate your writing expertise, almost no manager will hire you, even if you have an extensive tech background.

### Proqramlaşdırma bacarıqları tələb olunmur <a href="#no-programming-skills-required" id="no-programming-skills-required"></a>

> As for the needed technical background for the course, you don’t need any programming background or other prerequisites, but it will help to know some basic HTML, CSS, and JavaScript.
>
> If you do have some familiarity with programming concepts, you might speed through some of the sections and jump ahead to the topics you want to learn more about. This course assumes you’re a beginner, though.
>
> Some of the code samples in this course use JavaScript. JavaScript may or may not be a language that you actually use when you document REST APIs, but most likely there will be some programming language or platform that becomes important to know.
>
> JavaScript is one of the most useful and easy languages to become familiar with, so it works well in code samples for this introduction to REST API documentation. JavaScript allows you to test code by merely opening it in your browser (rather than compiling it in an IDE). (I have a [quick crash-course in JavaScript here](https://idratherbewriting.com/javascript/) if you need it.)

### Sənin üçün nələr lazımdır

>
>
> Here are a few tools you’ll need to do the activities in this course:
>
> * **Computer.** You need a computer (if attending the live workshop, a laptop and charging cord), as there are many activities to work through.
> * **Text editor**. If you don’t already have a favorite text editor, download [Sublime Text](https://www.sublimetext.com/), as it works well on both Mac and Windows and is free. If you have another text editor you prefer (e.g., [Visual Studio Code](https://code.visualstudio.com/), [Atom](https://atom.io/), or even [Notepad++](https://notepad-plus-plus.org/)), that will work too. Just make sure you can write code in plain text.
> * **Chrome browser**. [Chrome](https://www.google.com/chrome/browser/desktop/index.html) provides a Javascript Console that works well for inspecting JSON, so we’ll be using Chrome. Also, in order to read JSON responses more easily in the browser, install the [JSON Formatter](https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa?hl=en) Chrome extension.
> * **Postman**. [Postman](https://www.getpostman.com/) is an app that allows you to make requests and see responses through a visual client. _Make sure you download the app and not the Chrome extension._
> * **curl**. [curl](https://curl.haxx.se/) is essential for making requests to endpoints from the command line. Mac already has curl built-in, but it might not be available by default on Windows. (Some Windows 10 builds already have it in Powershell.) On Windows, open a Command Prompt and type `curl -V`. If it’s not installed, go to [confusedbycode.com/curl](http://confusedbycode.com/curl) and install a version (usually “With Administrator Privileges (free), 64-bit”). Close and re-open your Command Prompt and try typing `curl -V` again.
> * **Git**. [Git](https://git-scm.com/) is a version control tool developers often use to collaborate on code. For Windows, see [https://gitforwindows.org/](https://gitforwindows.org/) to set up Git and the Git BASH terminal emulator. For Mac, see [Downloading Git](https://git-scm.com/download/mac).
> * **GitHub account**. [GitHub](https://github.com) will be used for various activities, sometimes to demonstrate the Git workflow and other times as an authentication service for developer tools. If you don’t already have a GitHub account, sign up for one.
> * **Stoplight Studio Editor**. When working with the OpenAPI specification, we’ll use the Stoplight Studio Editor. Stoplight Studio provides visual modeling tools for working with the OpenAPI specification. Stoplight offers both a web browser and standalone app versions of the editor. We’ll be using the web browser version because it provides more complete functionality (such as trying out requests). Go to [https://stoplight.io/studio](https://stoplight.io/studio) and log in with GitHub.
> * **OpenWeatherMap API key**. We’ll be using the OpenWeatherMap API for some exercises. It takes a couple of hours for the OpenWeatherMap API key to become active, so it’s best if you get the API key ahead of time — then when you get to the OpenWeatherMap API activities, you’ll be all set. To get your (free) OpenWeatherMap API key, go to [https://openweathermap.org/](https://openweathermap.org/). Click Sign Up in the top nav bar and create an account. After you sign up, OpenWeatherMap sends you an API key to your email. you can also find it when you log in and click the API Keys tab from the dashboard. Copy the key into a place you can easily find it.

### Testing Your Setup <a href="#testing-your-setup" id="testing-your-setup"></a>

>
>
> In the past, people have asked for some tests to check whether their laptops are correctly set up.
>
> * If you want to test whether Postman works, open up the Postman app and paste this into the GET box: `https://api.openweathermap.org/data/2.5/weather?zip=95050&units=imperial&appid=126cac1a482f51de0f1287b45ae2bf9a`. Then click **Send**. If you get a response, it’s working correctly. (In rare cases, sometimes people have security restrictions on their computers that block all network access.)
> * If you want to test whether curl is installed, open Terminal (on Mac) or Command Prompt (on Windows) and paste in `curl --get "https://api.openweathermap.org/data/2.5/weather?zip=95050&units=imperial&appid=126cac1a482f51de0f1287b45ae2bf9a"`. If you get a JSON response, you’re good.
> * To check whether Git is installed, open up Terminal (on Mac) or Command Prompt (on Windows) and type `git --version`. If it’s installed, you’ll see the version.
