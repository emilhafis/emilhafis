# cURL tips

> **Postman** daha rahat olsada sənədlərdə sorğuları onunla necə göndərə biləcəyinizi rahatlıqla göstərə bilməzsiniz.&#x20;
>
> Bu səbəbdəndə sənədlərdə sorğu formalarını **command line-dan cURL** istifadə etməklə göstərirlər.

### cURL nədir

> cURL **(client URL)**, HTTP sorğularını müxtəlif parametrlər və üsullarla yerinə yetirməyə imkan verən bir command line proqramıdır. Brauzerin axtarış bölməsindən və ya Postmandan sorğu vermək əvəzinə sadəcə **cURL** vasitəsilə sorğularınızı göndərib cavablarınızı alırsınız.

> Sizə hansı formada bunu quraşdırmağın yollarını [Tools](../) hissədə göstərmişəm.&#x20;
>
> İndi fərz edək ki, sizin komputerinizdə **cURL** quraşıdırlmışdır.&#x20;
>
> Ona görə gəlin sorğu göndərməyə çalışaq. Əlimizdə hazır nümunə olmadığından Postman funskionallığından istifadə edib sorğumuzu cURL formatında yaradaq.
>
> Bunun üçün, **Postman**-da kod bölməsinə daxil olub cURL seçirik və yaranmış kod nümunəsin götürürük.

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

```url
curl --location --request GET 'https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-26&unique=false&sorting=price&direct=false&currency=rub&limit=30&page=1&one_way=true&token=3c63416a24d3b969da6df9271faa9d6e' \
--header 'X-Access-Token: 3c63416a24d3b969da6df9271faa9d6e'
```

> Komputerimizdə terminalı açırıq. Mac-da terminal yazıb axtarışa veririk, Windows-da isə CMD qeyd edib açırıq. Açılan interfeysə kodu olduğu kimi əlavə edib enter vururuq. Və sorğumuza cavabın gəldiyini görürük. &#x20;

{% hint style="info" %}
Lazım olarsa sorğudakı **API Key** dəyərini öz dəyiriniz ilə əvəz edərsiz
{% endhint %}

<figure><img src="../.gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Windows-da **Ctrl+ V** ilə kopyaladığınızı əlavə edə bilməyəcəksiz. Bunun üçün **Paste** istifadə edin.
{% endhint %}

> **Windows ilə işləyənlər üçün qeydlər**
>
> Windows ilə işləyirsinizsə aşağıdakı formatlara fikir verin:
>
> * Sətrləri ayırmaq üçün (`\`) istifadə etməyin. (Ümumiyyətlə bu simvol kodun oxuna bilməsi üçün istifadə olunur və adətən MAC user-ləri istifadə edir. Olmamaıs MAC üçündə problem deyil.)

{% hint style="info" %}
cURL-i növbəti mövzularda geniş müzakirə edəcəyik
{% endhint %}

### Quick start with cURL

> Ev tapşırıqları zamanı qarşısınıza **Quick Star**t tipli başlqılar çıxa bilər. Belə olanda adətən cURL də hazır sorğu nümunəsi yerləşdirirlər. Bu zaman işiniz çox rahat olacaqdır.&#x20;
>
> Məsələn deyək ki, convertor API ilə işləyirik və [saytın API documentation](https://apilayer.com/marketplace/exchangerates\_data-api#documentation-tab) bölməsinə daxil olmuşuq

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

> Gördüyünüz kimi, burada sorğu nümunəsi cURL ilə göstərilmişdir. Sənədləşmədə bu formada göstərmək çox rahat və başa düşüləndir. Bu komandanı göstərdiyimiz kimi işə salsanız nəticəni görəcəksiniz.

{% hint style="warning" %}
Əmin olun ki, **cURL** tərkibinə öz **API Key və digər parametrlər** sorğuda iştirak edir. Texti edit edərkən text editordan istifadə edin.
{% endhint %}

```
curl --request GET \
--url 'https://api.apilayer.com/exchangerates_data/convert?to=AZN&from=EUR&amount=100' \
--header 'apikey: UL6BuS0OZKmI1xMrsOwfvtFKIFwRxW9A'
```

> Nəticə bu formada olacaqdır

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption><p>t</p></figcaption></figure>

### Postman import

> Postman-ın əsas özəlliklərindən biridə onun import funksiyasıdır. Bu funksiya ilə siz cURL-i Postmana import edib sorğu göndərə bilərsiniz. Bunun üçün Postman da import seçimin edib Raw text seçməlisiniz

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

> Nəticədə endpoint-in Postmana import edildiyini görə bilərsiniz. Bundan sonra istədiyiniz əməliyyatı Postman vasitəsilə edib collection hazırlaya bilərsiz.

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>





