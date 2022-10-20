# SwaggerHub introduction and tutorial

> ![](<.gitbook/assets/image (9).png>)Bundan əvvəlki bölmədə open source proyekt (Pet) vasitəsilə [Swagger UI](https://idratherbewriting.com/learnapidoc/pubapis\_swagger.html)-də Open API spesifikasiyasına baxdıq. Bu kompaniya Swaggerin Editor və UI versiyalarını pulsuz olaraq istifadəyə verib. Həmçinin də bunların [SwaggerHub](https://app.swaggerhub.com/) adlanan premium məhsulları vardır.&#x20;
>
> [Buradan](https://swagger.io/tools/swaggerhub/opensource-comparison/) həmin versiyalar üzrə müqaisəni görə bilərsiniz.

### SwaggerHub qeydiyyat və Yaml import

> SwaggerHub da qeydiyyatdan keçək.

![](<.gitbook/assets/image (10).png>)

Qeydiyyatdan keçdikdən sorna gördüyünüz kimi ekran açılır. Burada `Create` new edib seçimləri görə bilərik.

![](<.gitbook/assets/image (8).png>)

Burada olan Create new API məsələsinə növbəti dərslərdə baxacağıq və manual olaraq Open API spec yaradacağıq.

İndi isə Stoplight da yaratdığımız Open API spesifikasiyasını bura add edib hansı formada parse olunduğuna baxaq. Xatırlayırsınızsa bildirmişdimki əlinizdə YOpen API spec varsa müxtəlif platformalara onu import edə bilərsiz, bir sözlə çox üstünlük verir.

1. Bunun üçün Stoplight a daxil oluruq. Yaml faylı üzərinə klik edirik.

![](<.gitbook/assets/image (6).png>)

2\. Ya export edirik yaml üzərindən yada sağda Code hissəyə klik edib kop edirib save edirik.

![](<.gitbook/assets/image (1) (1).png>)

3\. Əldə etdiyimiz faylı Svagger Hub a import edirik.

![](<.gitbook/assets/image (15).png>)

4\. İmport etdikdən sonra aşağıdakı kimi səhifə qarşımıza çıxır&#x20;

![](<.gitbook/assets/image (3).png>)

{% hint style="info" %}
Qeyd edildiyi kimi burada problem Open API spec versiyasındadır. Belə ki Spotlight 3.1.0 versiyasın istifadə edir , amma Svagger bu yeni versiyanı dəstəkləmir. Ona görə də spesifikasiyada versiyanı 3.0.0 edirik.
{% endhint %}

5\. bu dəyişikliyi etdikdən sonra spefisifikaımız emal olunur və Svagger onu vizual interfeysdə göstərir. Həmçinin də xətaları svagger göstərir. Versiya fərqinə əsasən bir çox xətalar yaranır. Amma ən əsası istədiyimiz nəticəni aldıq.

![](<.gitbook/assets/image (12).png>)

Burada User model və summary əvəvlki versiyada olmadığı üçün dəstəkləmir. Qalan məsələlər qaydasındadır

### Advantages of SwaggerHub

While the open-source Swagger Editor coupled with Swagger UI works, you’ll run into several problems:

* It’s challenging to collaborate with other project members on the spec.
* It’s difficult to gather feedback from reviewers about specific parts of the spec.
* You can’t automatically provide the API in the myriad code frameworks your users might want it in.

When you’re working on REST API documentation, you need tools specifically designed for REST APIs — tools that allow you to create, share, collaborate, version, test, and publish the documentation in ways that don’t require extensive customization or time.

There’s a point at which experimenting with the free Swagger UI tooling hits a wall, and you’ll need to find another way to move to the next level. This next level is where [SwaggerHub](https://swaggerhub.com/) from [Smartbear](https://smartbear.com/) comes in. SwaggerHub provides a complete solution for designing, managing, and publishing documentation for your API in ways that will simplify your life as an API technical writer.

More than 15,000 software teams across the globe use SwaggerHub. As the OpenAPI spec becomes more of an industry standard for API documentation, SwaggerHub’s swagger-specific tooling can be essential.\


### SwaggerHub Intro and Dashboard <a href="#swaggerhub-intro-and-dashboard" id="swaggerhub-intro-and-dashboard"></a>

[Smartbear](https://smartbear.com/) is the company that maintains and develops the open source Swagger tooling ([Swagger Editor](https://swagger.io/swagger-editor/), [Swagger UI](https://swagger.io/swagger-ui/), [Swagger Codegen](https://swagger.io/swagger-codegen/), and others.) They also formed the [OpenAPI Initiative](https://www.openapis.org/), which leads the evolution of the [Swagger (OpenAPI) specification](https://github.com/OAI/OpenAPI-Specification/).

Smartbear developed SwaggerHub as a way to help teams collaborate around the OpenAPI spec. Many of the client and server SDKs can be auto-generated from SwaggerHub, and there are a host of additional features you can leverage as you design, test, and publish your API.

To get started with SwaggerHub, go to [swaggerhub.com](https://swaggerhub.com/) and create an account or sign in with your GitHub credentials. After signing in, you see the SwaggerHub dashboard.

![](<.gitbook/assets/image (16).png>)

The dashboard shows a list of the APIs you’ve created. In this example, you see the [OpenWeatherMap API](https://idratherbewriting.com/learnapidoc/docapis\_scenario\_for\_using\_weather\_api.html) that I’ve been using throughout this course.

### SwaggerHub Editor <a href="#swaggerhub-editor" id="swaggerhub-editor"></a>



SwaggerHub contains the same [Swagger Editor](https://swagger.io/swagger-editor/) that you can access online. This editor provides you with real-time validation as you work on your API spec. However, unlike the standalone Swagger Editor, with SwaggerHub’s Swagger Editor, you can toggle between several modes:

* Hide Navigation
* Hide Editor and Navigation
* Hide UI Docs

![](<.gitbook/assets/image (1).png>)

Most importantly, as you’re working in the Editor, SwaggerHub allows you to _save your work_. With the free Swagger Editor, your content is kept in the browser cache, with no ability to save the file in the cloud. When you clear your cache, your content is gone. As a result, if you use the standalone Swagger Editor, you have to regularly copy the content from the Swagger Editor into a file on your own computer each time you finish.

With SwaggerHub, you can save your specification document directly on SwaggerHub’s servers, or you can reference and store it in an external source such as GitHub.

### Versions <a href="#versions" id="versions"></a>

SwaggerHub not only allows you to save your OpenAPI spec but also save different versions of your spec. As a result, you can experiment with new content by adding a new version. You can return to any version you want, and you can also publish or unpublish any version.

![](<.gitbook/assets/image (7).png>)

When you publish a version, the published version becomes Read Only. If you want to make changes to a published version (rather than creating a new version), you can unpublish the version and make edits to it.

You can link to specific versions of your documentation, or you can use a more general link path that will automatically forward to the latest version. Here’s a link to the OpenWeatherMap API published on SwaggerHub that uses version 2.5.1 of the documentation: [https://app.swaggerhub.com/apis/IdRatherBeWriting/open-weather\_map\_api/2.5.1/](https://app.swaggerhub.com/apis/IdRatherBeWriting/open-weather\_map\_api/2.5.1/). To link to a specific version, include the version number in the URL. In contrast, this more general link (which omits a version number) automatically forwards to the latest version (which is 2.5.2): [https://app.swaggerhub.com/apis/IdRatherBeWriting/open-weather\_map\_api/](https://app.swaggerhub.com/apis/IdRatherBeWriting/open-weather\_map\_api/).

Versioning is helpful when you’re collaborating on the spec with other team members. For example, suppose the original version was drafted by an engineer, and you want to make major edits. Rather than directly overwriting the content (or making a backup copy of an offline file), you can create a new version and then take more ownership to overhaul that version with your own updates, without fear that the engineer will react negatively about overwritten/lost content.

When you publish your Swagger documentation on SwaggerHub, Swagger’s base URL (`app.swaggerhub.com`) remains in the URL. Although this base URL isn’t customizable, you can add your company logo and visual branding as desired.

### Inline commenting/review

Key to the review process is the ability for team members to comment on the spec inline, similar to Google Docs and its margin annotations. When you’re working in SwaggerHub’s editor, a small plus sign ![](https://s3.us-west-1.wasabisys.com/idbwmedia.com/images/api/swaggerhub\_plus.png) appears to the left of every line. Click the plus button to add a comment inline at that point.\


![](.gitbook/assets/image.png)

When you click the plus sign, a comment pane appears on the right where you can elaborate on comments, and where others can reply. Users can edit, delete, or resolve the comments. This commenting feature helps facilitate the review process in a way that tightly integrates with your content. You can also collapse or show the comments pane as desired

Few tech comm tools support inline annotations like this, and it wouldn’t be possible without a database to store the comments, along with profiles associated with the reviewers. This feature would be tedious to implement on your own, as it would require both a database and an authentication mechanism.

This is all included in SwaggerHub.

### Auto-Generate Client SDKs

For example, suppose a user is implementing your REST API in a Java application. The user can choose to download the Java client SDK for extensive code that shows a Java implementation of your API. Other options include Ruby, Android, Go, CSharp, JavaScript, Python, Scala, PHP, Swift, and many more.

Some API documentation sites look impressive for showing implementations in various programming languages. SwaggerHub takes those programming languages and multiplies them tenfold to provide every possible output a user could want.

The output includes more than a simple code sample showing how to call a REST endpoint in that language. The output includes a whole SDK that includes the various nuts and bolts of an implementation in that language. (For more information on SDKs, see [SDKs](https://idratherbewriting.com/learnapidoc/docapis\_sdks.html).)

Providing this code speeds implementation for developers and helps you scale your language-agnostic REST API to a greater variety of platforms and users, reducing the friction in adoption.

### Export to HTML

Among SwaggerHub’s many options for generating client and SDK files is an HTML option. You can export your OpenAPI spec as a static HTML file in one of two styles: HTML or HTML2.

You can see a demo export of the OpenWeatherAPI API here: [HTML](https://idratherbewriting.com/learnapidoc/assets/files/swaggerhub\_htmloutput/index.html) or [HTML2](https://idratherbewriting.com/learnapidoc/assets/files/swaggerhub\_html2output/index.html). Both exports generate all the content into an index.html file.

The HTML export is a more basic output than HTML2. You could potentially incorporate the HTML output into your other documentation, such as what [Cherryleaf did in importing Swagger into Flare](https://www.cherryleaf.com/blog/2017/07/example-project-api-documentation-portal-using-madcap-flare/). (You might have to strip away some of the code and provide styles for the various documentation elements, and there wouldn’t be any interactivity for users to try it out, but it could be done.) In another part of the course, I expand on ways to [integrate Swagger UI’s output with the rest of your docs](https://idratherbewriting.com/learnapidoc/pubapis\_combine\_swagger\_and\_guide.html).

The HTML2 export is more intended to stand on its own, as it has a fixed left sidebar to navigate the endpoints and navtabs showing six different code samples:

You can see a demo export of the OpenWeatherAPI API here: [HTML](https://idratherbewriting.com/learnapidoc/assets/files/swaggerhub\_htmloutput/index.html) or [HTML2](https://idratherbewriting.com/learnapidoc/assets/files/swaggerhub\_html2output/index.html). Both exports generate all the content into an index.html file.

Both outputs would need a healthy dose of custom styling to be usable.\


### Mocking Servers

\


\


\


\
