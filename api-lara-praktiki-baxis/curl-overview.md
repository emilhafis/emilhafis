# cURL Overview

> Postman daha rahat olsada sənədlərdə sorğuları onunla necə göndərə biləcəyinizi rahatlıqla göstərə bilməzsiniz.&#x20;
>
> Bu səbəbdəndə sənədlərdə sorğu formalarını command line-dan cURL istifadə etməklə göstərirlər.

### cURL nədir

> cURL **(client URL)**, HTTP sorğularını müxtəlif parametrlər və üsullarla yerinə yetirməyə imkan verən bir command line proqramıdır. Brauzerin axtarış bölməsindən və ya Postmandan sorğu vermək əvəzinə sadəcə cURL vasitəsilə sorğularınızı göndərib cavablarınızı alırsınız.

> Sizə hansı formada bunu quraşdırmağın yollarını göndərəcəm. İndi fərz edək ki, sizin komputerinizdə bu quraşıdırlmışdır. Ona görə gəlin sorğu göndərməyə çalışaq. Əlimizdə hazır nümunə olmadığından Postman dakı hazır sorğumuzdan cUrl yaradaq.
>
> postman-da kod bölməsinə daxil olub cUrl seçirik və yaranmış kod nümunəsin götürürk.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

```url
curl --location --request GET 'https://api.travelpayouts.com/aviasales/v3/prices_for_dates?origin=GYD&destination=IST&departure_at=2023-03-26&unique=false&sorting=price&direct=false&currency=rub&limit=30&page=1&one_way=true&token=3c63416a24d3b969da6df9271faa9d6e' \
--header 'X-Access-Token: 3c63416a24d3b969da6df9271faa9d6e'
```

Komputerimizdə terminalı açırıq (Windows-da CMD) və kodu olduğu kimi ora əlavə edib enter vururuq. Və sorğumuza cavabın gəldiyini görürük. &#x20;

{% hint style="info" %}
Lazım olarsa sorğudakı API Key dəyərini öz dəyiriniz ilə əvəz edərsiz
{% endhint %}

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Windows-da Ctrl+ V ilə kopyaladığınızı əlavə edə bilməyəcəksiz. Bunun üçün **Paste** istifadə edin.
{% endhint %}

> **Windows ilə işləyənlər üçün qeydlər**
>
> Windows ilə işləyirsinizsə aşağıdakı formatlara fikir verin:
>
> * Sətrləri ayırmaq üçün (`\`) istifadə etməyin. (Ümumiyyətlə bu simvol kodun oxuna bilməsi üçün istifadə olunur və adətən MAC user-ləri istifadə edir. Olmamaıs MAC üçündə problem deyil.)

{% hint style="info" %}
cURL-i növbəti mövzularda geniş müzakirə edəcəyik
{% endhint %}
