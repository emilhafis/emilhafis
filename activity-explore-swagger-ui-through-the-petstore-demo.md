# Activity: Explore Swagger UI through the Petstore Demo

Petstore demosundan istifadə edərək Swagger UI ilə praktiki təcrübəyə keçək. **Petstore** demosu OpenAPI spesifikasiyasının vizual olaraq necə göstərilə biləcəyinə yaxşı bir nümunədir.

1. [Swagger Pet Store Demo](https://petstore.swagger.io/) ya keçid edək

Əksər Swagger-əsaslı platformalarda olduğu kimi, **Swagger UI** də “**Try it out**” funksionallığını təmin edir. Bunun işləməsi üçün ilk növbədə, **Avtorizasiya** düyməsini klikləyərək və Avtorizasiya box-da API açarınızı daxil etməklə Swagger-ə icazə verməlisiniz. Burada, Petstore demo məqsədi üçün olduğundan burada real avtorizasiya kodundan istifadə edilmir. Buna görəd də Avtotorizasiyanı bağlaya və ya tamamilə skip edə bilərsiniz.

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

2\. **POST `/pet`** endpoint-ni expand edək

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

3\. Klik **Try it out**.

**Try it out** klik etdikdən sonra Request Body-dəki nümunə dəyərləri redaktə oluna bilən olur.

4\. Nümunə dəyərlərdəki birinci `id` dəyərinə unikal və təkrarolunmaz bir dəyər verək (məsələn 335678). Çünki bizim kimi minlərlə şəxs bu API yı test edir. `doggie` adını isə yadımızda qalan bir it adı ilə əvəz edək (məsələn Rex)

5\. **Execute** klik edək

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Swagger UI sorğunu göndərdikdən sonra istifadə edilmiş **curl** sorğusunu göstərir. Burada göndərilmiş **curl** sorğusunu görə bilərsiniz

<figure><img src=".gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

```json
curl -X 'POST' \
  'https://petstore.swagger.io/v2/pet' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "id": 335678,
  "category": {
    "id": 0,
    "name": "string"
  },
  "name": "Rex",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}'r
```

> Notice that, with the `-d` (data) parameter, the request body is escaped and added directly into the curl command rather than being loaded from a file (as explained in [Common curl commands related to REST](https://idratherbewriting.com/learnapidoc/docapis\_understand\_curl.html#common)).

Response hissədə serverdən qayıdan cavab göstərilir. By default qayıdan cavab JSON formatında olur.

<figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

```json
{
  "id": 335678,
  "category": {
    "id": 0,
    "name": "string"
  },
  "name": "Rex",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}
```

6\. İstifadə etdiyimiz **Petstore** işlək bir API yəni servisdir. Yəni, əslində biz servisdə real olaraq bir heyvan yaratdıq. Maraq üçün **GET/pet/{petId}** endpointini expand edib **Try it out** klik edək. Əvvəlki əməliyyatda istifadə etdiyimiz pet id-ni daxil edək və sonra sorğunu göndərək. Qeyed etdiyimiz itimizin adı olan Rex qayıtdığını görərik.

Sorğu. Buradad eyni formada göndərilən sorğunun **curl** formasını görürük.

<figure><img src=".gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Response - qayıdan cavabda isə bildirdiyimiz kimi əlavə etdiyimiz Rex-i görürük.

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

\
\
