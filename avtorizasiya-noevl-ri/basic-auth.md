# Basic Auth

### Basic Auth nədir

> Avtorizasiyanın başqa növü də Basic Auth adlanır. Bu metod da sorğunu göndərən `username:password` dəyərlərini `request header` - də göndərir. İstifadəçi adı və şifrəsi [Base64 ilə encode ](basic-auth.md#undefined)olunur, yəni `username:password` təhlükəsiz tranmissiya üçün 64 xarakterli dəyər halına çevrilir. Aşağıda request header-də **Basic Auth** üzrə nümunə göstərilmişdir:

```
Authorization: Basic bG9sOnNlY3VyZQ==
```

#### Base 64 encode və decode

{% hint style="warning" %}
**Encode** - məlumatları məxfi formaya, həmçinin də mürəkkəb məlumatları sadə və qısa formaya çevirərək göndərilməsi üçün istifadə olunur.&#x20;

Bu şifrələmə deyil və rahatlıqla əvvəlki formasına çevirmək, yəni **decode** etmək mümkündür.

Məsələn - **API Security** dəyərin [bu sayt vasitəsilə](https://www.base64encode.org/) **encode Base64** formasına çevirib bu nəticəni - **QVBJIFNlY3VyaXR5** - alırıq.

Həmçinin də, bu dəyəri geriyə yəni əvvəlki vəziyyətinə də (**API Security)** qaytara bilirik, yəni **decode** edirik. [Bu sayt vasitəsilə](https://www.base64decode.org/) yoxlaya bilərsiniz.
{% endhint %}

### HTTPS

> API-lar **Basic Auth** la yanaşı [**HTTPS**](broken-reference)-də istifadə edirlər.&#x20;
>
> HTTPS istifadə edildikdə mesajın konteksti HTTP transport protokol daxilində **encrypt** edilir. Yəni API sorğusundakı məlumatlar açıq formada göndərilmir, şifrələnir (HTTPS olmadan, yəni bildiyimiz **SSL** olmadan çox rahatlıqla göndərilən trafikdən API sorğusundakı username və password-u götürmək olar).&#x20;
>
> Göndərilən sorğunu API server qəbul etdikdən sonra, mesajı **decrypt** edir (yəni şifrələnmiş məlumatları açır) və header-dəki məlumatları (username və password) götürür. Bunları əldə etdikdən sonra yoxlayaraq qərar verir ki, sorğunu qəbul etsin yoxsa imtina.

### Postman nümunə

> Postmanda siz sorğu göndərərkən **Basic Auth** dəyərlərindən istifadə etmək üçün **Authorization bölməsində drop-down** listdən **Basic Auth** seçib `username:password` **** qeyd edib yoxlaya bilərsiniz. Aşağıda nümunə göstərilmişdir.

![](<../.gitbook/assets/Postman\_apikey (1).png>)
