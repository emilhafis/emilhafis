# Step 2: The info object (OpenAPI tutorial)

The [info object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#infoObject) contains basic information about your API, including the title, a description, version, link to the license, link to the terms of service, and contact information. Many of the properties are optional.

[info object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#infoObject)  sizin API nız haqqında ümümu məlumatları göstərir. Buraya adlandırma, təsvir, versiya, lisenziyaya link, istifadəçi şərtlərinə lin və müqavilə məlumatları qeyd edilir. Bu dəyərlərdən çoxu optionaldır

<figure><img src="https://lh4.googleusercontent.com/mc-6GZKRasETBi9DLlvdiFuqlSrXEO97gBqzxpFDXyzAy2Sp6jwygeX4CfnXZMHdM3LrRWhJR6H6QNSEtg54nRLuLur2rN5KVz6kXkLL6fQww39caCaA7uLdVBJU_SxvU0Zwhu4dhpdnFnDttJNhgCpz3p-IqL3hWwcHzGiAJIWcjXoRLcMvfehr1Fp-fW4" alt=""><figcaption></figcaption></figure>

### Sample info object

> Here’s an example of the `info` object and its properties. (The `openapi` object and the empty `paths` object are commented out to maintain the focus on the `info` object.)

```yaml
openapi: 3.0.3
info:
  title: Travelpayouts API
  version: v3
  description: "Aviasales Data API — the way to get travel insights for your site or blog. Get flight price trends and find popular destinations for your customers.
Data is transferred from the cache, which is formed on the basis of searches of users of sites Aviasales for the last 48 hours. So it is recommended that you use them to generate static pages.
For developers, documentation is available with examples of requests and answers in various programming languages, as well as a link to Postman.
Please note, API methods use limits, which are described in the article API rate limits.
This documentation is for the public Aviasales API of the same name.
To access the API, you must pass your token in the X-Access-Token header or in the token parameter. To obtain a token for the Data Access API, go to https://www.travelpayouts.com/programs/100/tools/api"
  license: 
    name: "License (MIT, Apache 2.0, etc): Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) License"
    url: https://creativecommons.org/licenses/by-sa/4.0/'
  termsOfService: "https://support.travelpayouts.com/hc/en-us/articles/360004162111-Terms-of-the-Travelpayouts-Travel-Affiliate-Network"
  contact:
    name: "Travelpayouts support"
    url: https://support.travelpayouts.com/hc/en-us
    email: someone@gmail.com
  
paths: {}
```

{% hint style="info" %}
If you get stuck, see the [sample OpenAPI spec here](https://idratherbewriting.com/learnapidoc/docs/openapi\_spec\_and\_generated\_ref\_docs/openapi\_openweathermap.yml) for the fully working sample. This will help you spot and troubleshoot indentation or other errors.
{% endhint %}

### Description properties and Markdown

### 1.1What is Markdown? <a href="#what-is-markdown" id="what-is-markdown"></a>

Markdown is a plain text format for writing structured documents, based on conventions used for indicating formatting in email and usenet posts. It was developed in 2004 by John Gruber, who wrote the first Markdown-to-HTML converter in Perl, and it soon became ubiquitous. In the next decade, dozens of implementations were developed in many languages. Some extended the original Markdown syntax with conventions for footnotes, tables, and other document elements. Some allowed Markdown documents to be rendered in formats other than HTML. Websites like Reddit, StackOverflow, and GitHub had millions of people using Markdown. And Markdown started to be used beyond the web, to author books, articles, slide shows, letters, and lecture notes.

What distinguishes Markdown from many other lightweight markup syntaxes, which are often easier to write, is its readability. As Gruber writes:

> Qeyd edim ki, bütün `description` propertilər üzrə siz [https://www.markdownguide.org/basic-syntax/](https://www.markdownguide.org/basic-syntax/) daha detallı [CommonMark Markdown](http://spec.commonmark.org/0.27/) istifadə edə bilrəsiniz.&#x20;

> As you write content in `description` properties, note that colons are problematic in YAML because they signify new levels. Either enclose the `description` value in quotation marks or escape colons with a backslash. (If you enclose the values in quotation marks, syntax highlighters in text editors can display better color coding between the properties and values.)

### Update your file in Swagger Editor

> To update the spec file in Swagger Editor:
>
> 1. Paste the code from the preceding section (“Sample info object”) containing the `info` object into the Swagger Editor.
> 2. Uncomment the `openapi` and `paths` objects (remove the “`#`”). The display looks as follows:

Open API uyğun olaraq info object üçün kodlaşdırmanı edək.

{% hint style="warning" %}
Swagger UI interfeysində`info` obyekt məlumatı `title` məluamtının altında verilir&#x20;
{% endhint %}

{% hint style="info" %}
`description` property sizin API nız üzrə ümumi məlumatı əks etdirir. Siz ola bilsinki burada intruksiya ilə bağlı ümumi məlumatda verə bilərsiniz.&#x20;
{% endhint %}

### Markdown dan istifadə edək

Ilk öncə paraqraf əlavə edək. Sonra bəzi dəyişikliklər edək. Məsələn bold, italic. Code blok.\


```yaml
openapi: 3.0.3
info:
  title: Travelpayouts API
  version: v3
  description: "Aviasales Data API — the way to get travel insights for your site or blog. Get flight price trends and find popular destinations for your customers. <p> 
  
    Data is transferred from the cache, which is formed on the basis of searches of users of sites Aviasales for the last 48 hours. So it is recommended that you use them to generate static pages. <p>
  
    For developers, documentation is available with examples of requests and answers in various programming languages, as well as a link to Postman.<p>

    >**Please note**: *API methods use limits, which are described in the article API rate limits.*<p>

  This documentation is for the public Aviasales API of the same name.
    To access the API, you must pass your `token` in the `X-Access-Token header` or in the token parameter. To obtain a token for the Data Access API, go to the [Dashboard](https://www.travelpayouts.com/programs/100/tools/api)"
  license: 
    name: "License (MIT, Apache 2.0, etc): Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) License"
    url: https://creativecommons.org/licenses/by-sa/4.0/'
  termsOfService: "https://support.travelpayouts.com/hc/en-us/articles/360004162111-Terms-of-the-Travelpayouts-Travel-Affiliate-Network"
  contact:
    name: "Travelpayouts support"
    url: https://support.travelpayouts.com/hc/en-us
    email: someone@gmail.com
  
paths: {}
```
