# Step 7: The tags object (OpenAPI tutorial)

The `tags` object allows you to arrange the `paths` (endpoints) into named groups in the Swagger UI display.

### Defining tags at the root level

At the root level, the [`tags` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#tagObject) lists all the tags that are used in the [operation objects](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#operationObject) (which appear within the `paths` object, as explained in [Step 4: The paths object](https://idratherbewriting.com/learnapidoc/pubapis\_openapi\_step4\_paths\_object.html)). Here’s an example of the `tags` object for our Travelpayouts API:

```
tags:
  - name: Flight
    description: "Get the cheapest ticket"
```

> We have just one tag, but you could have as many as you want (if you have a lot of endpoints, it would make sense to create multiple tags to group them). You can list both the `name` and a `description` for each tag. The `description` appears as a subtitle for the tag name in the Swagger UI display.

{% hint style="info" %}
If you get stuck, see the [sample OpenAPI spec here](https://idratherbewriting.com/learnapidoc/docs/openapi\_spec\_and\_generated\_ref\_docs/openapi\_openweathermap.yml) for the fully working sample. This will help you spot and troubleshoot indentation or other errors.
{% endhint %}

### Tags at the path object level

> The `tags` object at the root level should list all tags (groups) that you want in your API. Then in each path object under `paths`, you list the tag you want that path grouped under.

{% hint style="info" %}
By “root level,” I mean the first level in the OpenAPI document. This level is also referred to as the global level because some object properties declared here (namely servers and security) are applied to each of the operation objects unless overridden at a lower level.
{% endhint %}

> For example, in the operations object for the `/prices_for_dates` path, we used the tag Flight:

> This tag is defined at the global level, so the `/prices_for_dates` path will be grouped here.

### &#x20;View the Appearance in Swagger UI

Add the following to the root level of your OpenAPI document in Swagger Editor:

\
\


<figure><img src="https://lh4.googleusercontent.com/VZW2Lk-B98Lnl6nR91fD-aGg3jeJAAgTWc-twbOZv9RMMmypm9QEzjIlEUSJmAOfh7Sam--9WVFlEVCZrq5Qjy2k4u-I1sO8dJfdv1ljBI_WyGmmyY6f9nmG9LeylYcEIP7uNaWed_VhdJjWHVNhWjTvOVAY7-4H9L9IIreO8ZG4bjrFcq3wScqgXt3T0eGpyRM" alt=""><figcaption></figcaption></figure>

> All paths that have the same tag are grouped together in the display. For example, paths that have the `Get the cheapest data` tag will be grouped together under the title `Flight` Each group title is a collapsible/expandable toggle.

> The order of the tags in the `tags` object at the root level determines their order in Swagger UI. Additionally, the `descriptions` appear to the right of the tag name.
>
> In our sample OpenAPI spec, tags don’t seem all that necessary since we’re just documenting one path/endpoint. (Additionally, I configured the [Swagger UI demo](https://idratherbewriting.com/learnapidoc/pubapis\_swagger\_demo.html) to expand the section by default.) But imagine if you had a robust API with 30+ paths to describe. You would certainly want to organize the paths into logical groups for users to navigate.

![](<.gitbook/assets/image (1).png>)

\
