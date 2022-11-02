# Step 4: The paths object (OpenAPI tutorial)

The [`paths` object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#pathsObject) contains the meat of your API information. The `paths` object has several sub-objects: a [path items object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#pathItemObject), an [operations object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#operationObject), and more.

{% hint style="info" %}
Əvvəlki 3 mövzunu asta keçdik və bütün obyektlər ilə tanış olduq. Burada isə sürətli keçəcəyik. İlk dəfədən başa düşməsəniz problem yoxdur, hazır mən təqdim etdiyim kod üzərində işləyərsiniz və sonra lazım olduqda geriq ayıdıb baxarsınız.

Hər zaman hər şeyi yadda saxlamaq yox nəyi haradan tapacağınızı bilmək önəmlidir.
{% endhint %}

### Paths objects

> Bu bizim bildiyimiz endpointdir. open API spesifikasiyasında endpoint path adlandırılır deyə burada da Path deyəcəyik.

> `path` obyektindəki hər bir maddə operation [operation object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.1.0.md#operation-object) ibarət olur. (GET, POST, Delete və PUt haqqında bundan əvvəlki mövzuda danışmışıq) &#x20;
>
> Gəlin indi, path 9endpoint) qeyd edib onlar üzrə metodu təyin edək. Flight endpoint i üçün bir path-a (/[prices\_for\_dates](https://api.travelpayouts.com/aviasales/v3/prices\_for\_dates?origin=string\&destination=BCN\&departure\_at=string\&return\_at=string\&unique=false\&sorting=price\&direct=false\&currency=rub\&limit=30\&page=1\&one\_way=true\&token=PutYourTokenHere)) baxmışdıq. Və bunun metodu `GET` idi.

### &#x20;
