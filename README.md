# Send Grid

### Task

1. Send email from Send Grid![](https://lh3.googleusercontent.com/lSgvDdKBAfhaLAprpzEFQz-nRPHW6nc4lknhawhorIwVxKcMJKagcOgOwSEGfg6MIDyV\_aOiUeXiwWy5g6Yx9J8WmDGSVhVCQYNVSgCTb9MznUbEUoZUUHHImVEc0KdUVY9iNlHM-Q4Co6-CC2YwRgazL0K8P7WgE7Sd0uQ1nVJRlCZgS6-kqpYs5o9w8w)Use[ ![](https://lh3.googleusercontent.com/lSgvDdKBAfhaLAprpzEFQz-nRPHW6nc4lknhawhorIwVxKcMJKagcOgOwSEGfg6MIDyV\_aOiUeXiwWy5g6Yx9J8WmDGSVhVCQYNVSgCTb9MznUbEUoZUUHHImVEc0KdUVY9iNlHM-Q4Co6-CC2YwRgazL0K8P7WgE7Sd0uQ1nVJRlCZgS6-kqpYs5o9w8w)Email Delivery, API, Marketing Service](https://sendgrid.com/) platform
2. Send “Hello API First from {your\_name}” email to apifirst@gmail.com
3. Provide Postman collection

### Start

1. İlk öncə [sendgrid.com daxil oluruq](https://sendgrid.com/)
2. Developer hissəyə keçirik

<figure><img src=".gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

3\. Developer hissədə seçirik

<figure><img src=".gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

4\. Burada görürük ki, sorğu göndərmək üçün 3 etapı tamamlamalıyıq

<figure><img src=".gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

5\. Start for free seçimi ilə qeydiyyata başlayırıq

<figure><img src=".gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

6\. Email və göstərilən tələbə uyğun şifrəni daxil edirik

<figure><img src=".gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

&#x20;

7\. Bizim haqda məlumat istəyir. Onu doldururuq

<figure><img src=".gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

8\. Artıq şəxsi kabinetə keçid edirik və burada sms göndərmək üçün sender yaradırıq

<figure><img src=".gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

9\. Sender üçün məlumatları daxil edirik. From email hissədə öz emailmizi yazırıq. Sms bu emaildən göndəriləcək

<figure><img src=".gitbook/assets/image (13) (1).png" alt=""><figcaption></figcaption></figure>

10\. Emailimizə keçib təsdiq edirik

<figure><img src=".gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

11\. Accountu yaratdıq indi 2-ci bənddə göstərdiyi API Key əldə etməliyik

<figure><img src=".gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

12\. Klik etdikdən sonra bu səhifə açılır və orada **Create API Key** seçirik.

<figure><img src=".gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

13\. API Key yaradılır və deyilirki bir daha göstərməyəcəyik. Ona görə bunu götürüb saxlayırıq

<figure><img src=".gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

```
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
```

14\. API Key aldıq indi isə 3-cü bəndə keçirik. Burda deyirki əmin olun ki, cURL install olunub. Bunu necə etmək lazımdır sizə təqdim etmişəm

<figure><img src=".gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

15\. cURL install olduğu üçün səhifəni aşağı scroll edib cURL kodunu götürürk və text editora atırıq

<figure><img src=".gitbook/assets/image (12) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

16\. cURL də **to email** hissənə hansı emailə göndərmək istəyirksə onu qeyd edirik, **from email** hissəyə isə qeydiyyatdan keçirdiyimiz emaili daxil edirik ki, bu emaildən göndərilsin. Nümunədə baxa bilrəsiniz

```bash
curl --request POST \
--url https://api.sendgrid.com/v3/mail/send \
--header 'Authorization: Bearer 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' \
--header 'Content-Type: application/json' \
--data '{"personalizations":[{"to":[{"email":"apifirst.aze@gmail.com","name":"API First"}],"subject":"Sample email"}],"content": [{"type": "text/plain", "value": "Hello from Inci"}],"from":{"email":"digitfins@gmail.com","name":"Emil Abbasov"},"reply_to":{"email":"digitfins.aze@egmail.com","name":"Inci"}}'
```

17\. cURL i götürüb cmd və ya terminal (MAC) run edirik. Əgər error olarsa dərhal sizə cavab qayıdır. Uğurluda isə görürük ki, komanda icrası bitdi.

<figure><img src=".gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

18\. Göndərilən email-ə keçid etdikdə (apifirst.aze@gmail.com) görürük ki, email gəlib

<figure><img src=".gitbook/assets/image (15) (1).png" alt=""><figcaption></figcaption></figure>

19\. Sonda cURL i Postmana import edib collection çıxardıb google drive-nıza yerləşdirib linkin mənə göndərirsiniz (video dərsliyin sonunda izah etmişəm)
