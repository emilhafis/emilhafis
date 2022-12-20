# Activity

indi isə praktika tərəfindən baxaq.

Belə təsəvvür edək ki, aşağıdakı kimi prosesi qurmalıyıq.

Kofesiz işə başlaya bilmirik və cofee aparatına gedib kofemizi almalıyıq.&#x20;

Biz bu prosesi BPMn də quracağıq və siz real olaraq görəcəksiniz ki, proses hansı formada baş verir.&#x20;

Bunun üçün mən Lucidchart dan istifadə edəcəm. Amma siz digərlərindən, Visio BPMn və d istifadə edə bilərsiniz. Fikir verinki export və import olsun. Dediyimiz kimi bu bir standartdır və digər toollar bunu emal edib göstərə bilir. Biz [https://demo.bpmn.io/](https://demo.bpmn.io/) istifadə edəcəyik.

1. ilk olaraq biz özümüzə sual verməliyik ki, nə baş verməlidir ki, bizim prosesimiz start olsun? Bu keysdə bildirdiyim kimi, qeyd edə bilərik ki, **Cofee needed.** Start event edib yazırıq.
2. Bundan sonra biz prosesləri əlavə etməliyki və biz təyin etməliyik ki, nə baş verməlidir. Təsəvvür edinki kofee maşını qarşısındasız nə etməlisiniz ilk öncə? Mümkün vkofee variantların seçməlisiniz. BElə ki, biz Task əlavə edib yazırıq - **Check available options**
3. Deməli biz seçimləri gördük və onların arasından seçməliyik. Məsələn latte, Americano və s. Deyəkki sçim etməliyik. Yenədə sadə Task artırıb qeyd edirik - **Select coffee**
4. Biz seçdikdən sonra adətən pulun ödəyirik. Bu isə bir az mürəkkəb prosesdir. Burada bir çox proses var və biz istəmirikki onları ümumi floda göstərək və qarışıqlıq olsun. Ona görə Sub-Process artırırıq. Və adını Payment qoyuruq. Fikir verirsinizsə burda sub process olduğu üçün icraya uyğun Fel qoymadıq.&#x20;

{% hint style="info" %}
Lazımsız mürəkkəbliyi gizlətmək üçün ümumiyyətlə çox böyük diaqramlar yaratmaq yaxşı təcrübə deyil. Auditoriya üçün lazım olmayan elementləri Sub-Process də gizlətməlisiniz.

Bu həm də daha yaxşı görüntü yaratmaqla yanaşı, aşağı səviyyəli diaqramlardan yenidən istifadə etməyə imkan verən təcrübədir. API modeli xatırlayın. buna sonra baxacağıq.
{% endhint %}

5\. Cofee üçün pulu ödədikdən sonra biz kofemizi götürməliyik. Bu da bizim sadə taskımızdır. Take cofee

6\. Və nəhayət happy ednimizə çatdır.q  Beləki biz End event əlavə edib Coffee ready to drink əlavə edirik. Prosesdə ən xoşladığımız fiur bu olacaq çünki yekunlaşdırırq.



İndi isə sizə bir az tool haqqında deyim.&#x20;

1. İmport və Export göstərmək
2. IBM də import etmək

İndi isə sizə elemtlərin bir biri ilə necə birləşdiyini göstərim. Yəni Sequenc floları.

İndi isə keçək sub process-ə və baxaqki orada nə baş verir

1. Burada ilk işimiz event start-dır.
2. İkinci nə ola bilər? Select Payment option

Sub-Prosesdə baş verənləri görmək üçün klik edib daxil ola bilərsiniz. əlaqələndirməliyik. Mən sizin üçün bir dəftər yaratdım, ona görə də qeyd edək ki, qeyd dəftərini açmaq üçün iki dəfə klikləyə bilsinlər. Və sadəcə olaraq və lazım gələrsə, bu məqamları indi əlaqələndirmək üçün böyüdü. O diaqramı ya oxuya bilərəm, ya da istəsəm klikləyib içəri girə bilərəm bura proses bir az olacaq biraz daha maraqlıdır. Ödəniş tələb olunduqda biz ödəniş variantlarını yoxlayırıq. Ümid edirik ki, satış avtomatı daha ağıllıdırsa, biz avtomobilimizlə ödəyə bilərik, onda hadisə sadəcə ödəyəcək və sonra bunu azaldacaq. Ancaq köhnədirsə, yəqin ki, sikkələrlə sikkələr hazırlamaq lazımdır və digər işlərdə daha yüksək səviyyəli prosesimizi tamamlaya bilərik ki, surətini götürüb davam edə bilək. Beləliklə, burada siz o hərəkətləri və əsas elementləri görə bilərsiniz ki, bu və hadisələrin tapşırıqlarını, məsələn, proseslərin şlüzləri və axınları ardıcıllığı və bunlar hər bir ləğv və xəncərdən istifadə edəcəyiniz ən vacib elementlərdir.
