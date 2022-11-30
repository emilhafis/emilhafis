# AccuWeather APIs

1. **Get current weather in BakuUse**[ **AccuWeather APIs | home**](https://developer.accuweather.com/) **platform**
2. **Get current weather in Baku**
3. **Provide Postman collection**

[https://developer.accuweather.com/getting-started](https://developer.accuweather.com/getting-started)

1. Sayta daxil oluruq

<figure><img src=".gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

2\. Register ilə qeydiyyatdan keçirik

<figure><img src=".gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

3\. Qeydiyyatdan keçdikdən sonra bizə bildirilirki e-mailə təsdiq linki getdi

<figure><img src=".gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>

4\. Həmçinində e-maildə instruksiya linkin görürük və klik etdikdə addım addım nə etməli olduğumuz yazılır

<figure><img src=".gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

5\. Bizə laızm olan paketi seçirik. Yəni pulsuz olanı

<figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

6\. AKtivləşdirmək üçün klik edirik

<figure><img src=".gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

7\. Paketimiz aktivləşir və yeni APP yaratmalıyıq

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

8\. Məlumatları daxil edib APP ı yaradırıq

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

9\. APP-ın yarandığını görürük və klik edib içərisinə giririk

<figure><img src=".gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

10\. API Key hissədə Key i götürürük

<figure><img src=".gitbook/assets/image (21) (1).png" alt=""><figcaption></figcaption></figure>

```
bJHZ7tw1F9DeMnXUYjqt0nXbzM8e8dM3
```

11\. API Key bizdə olduğu üçün indi API reference bölməsinə gedirik və bizə lazım olan API tapmağa çalışırıq. Bizə lazım olan API Current  Weather dir və onun içərisinə daxil oluruq

<figure><img src=".gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

12\. Burada görürük ki, bizə apiKey ilə yanaşı locationKey də lazım olur. Və descriptiona baxdıqda bildiri ki, Location API hissədən götürə bilərsiz.

<figure><img src=".gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

13\. Qayıdırq API Refrenece ə və Location API daxil oluruq

<figure><img src=".gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

14\. Aşağı scroll edəndə bizə lazım olan City search API görürük

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

15\. Burada apiKey -mizi və axtardığımız şəhəri yəni Baku qeyd edirik

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

16\. Qayıdan cavabda artıq Bakının Location Key-in Key yazılan hissədən götürürük

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

17\. Qayıdıb Current Conditions API da&#x20;

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

1rw6adQzFkEzjDvxvXGYo8CQYoElIh4J

<figure><img src=".gitbook/assets/image (12) (2).png" alt=""><figcaption></figcaption></figure>

```
curl -X GET "http://dataservice.accuweather.com/currentconditions/v1/27103?apikey=1rw6adQzFkEzjDvxvXGYo8CQYoElIh4J"
```
