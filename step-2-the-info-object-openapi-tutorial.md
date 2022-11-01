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
  description: '**Aviabilet** haqqında məlumatların əldə olunması üçün  istifadə olunur '
  license: 
    name: "License (MIT, Apache 2.0, etc): Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) License"
    url: https://creativecommons.org/licenses/by-sa/4.0/'
  termsOfService: https://support.travelpayouts.com/hc/en-us/articles/360004162111-Terms-of-the-Travelpayouts-Travel-Affiliate-Network
  contact:
    name: Travelpayouts support
    url: https://support.travelpayouts.com/hc/en-us
    email: someone@gmail.com
  
paths: {}
```

{% hint style="info" %}
If you get stuck, see the [sample OpenAPI spec here](https://idratherbewriting.com/learnapidoc/docs/openapi\_spec\_and\_generated\_ref\_docs/openapi\_openweathermap.yml) for the fully working sample. This will help you spot and troubleshoot indentation or other errors.
{% endhint %}

### Description properties and Markdown

Note that in any `description` property, you can use [CommonMark Markdown](http://spec.commonmark.org/0.27/), which is much more precise, unambiguous, and robust than the original Markdown.

For example, CommonMark markdown offers some [backslash escapes](http://spec.commonmark.org/0.27/#backslash-escapes), and it specifies exactly how many spaces you need in lists and other punctuation. You can also break to new lines with  and escape problematic characters like quotation marks or colons with a backslash.\
