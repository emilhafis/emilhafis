# Resources

```
GET /employees
GET /employees/{id}
```

{% hint style="warning" %}
* Prefer <mark style="color:blue;">concrete names</mark> over abstractions&#x20;
* <mark style="color:blue;">Two primary URLs per resource type</mark>&#x20;

&#x20;      /employees is a collection&#x20;

&#x20;      /employees/1234 is a single entity&#x20;

* Use <mark style="color:blue;">plural nouns for resource names</mark>&#x20;

&#x20;      /employees/1234, NOT /employee/1234&#x20;

* Prefer <mark style="color:blue;">standard terms</mark> over internal company terminology&#x20;

&#x20;      /employees, NOT /apigeeks
{% endhint %}

####

> A core part of designing your APIs is identifying your resources.&#x20;
>
> Resources typically use concrete names instead of abstractions. In an employee API, your resources might include employees, buildings, and reporting relationships.&#x20;
>
> Each resource type typically has two primary URLs: /employees would be a collection of employees, and /employees/1234 would be the specific employee with the unique ID 1234.&#x20;
>
> We use plural nouns for resource names in the URL. Use the plural noun for the collection name, "/employees," as well as for a specific employee, "/employees/1234."&#x20;
>
> Remember also that you are designing your resources to be understood by app developers, who may not have knowledge of internal names and concepts used within your company. You should always use terminology that makes sense to your app developers and is meaningful to to them.&#x20;
>
> For example, employees of the Apigee team at Google are sometimes called "Apigeeks." This term could likely be confusing to most app developers, including app developers within Google. It would make more sense to name the resource "employees."