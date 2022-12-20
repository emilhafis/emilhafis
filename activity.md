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

>
>
>
>
> Now, I'll tell you few words about tool usage \[of ADONIS:CE]. As you could see I was using option called Hover modeling
>
> or modeling assistant. So every time I clicked, tool suggested me next elements. This is just element of "tool smarts" \[usability]
>
> so it will differ from a tool to a tool.
>
> But what will be the same is that every argument will be circle with the fin barter average and then
>
> the circle with a thick marker and every task will be rounded.
>
> Now I'll show you how I could use other methods of joining elements of sequence flows.
>
> So let's assume that I would like for zealots first of all it would be simpler to click on the arrow
>
> click here on the stomach and drag it to the carpet.
>
> And now this is ready or I could also click to have a modeling assistant select the arrow and simply
>
> select an element so we can create.
>
> Here you can see only mark element of payments if you would like to show what is happening inside us.
>
> We would need to link this element this sub process with a lower level diagram to save your time.
>
> I created one for you so we have it here telling them they can double click to open a notebook.
>
> And simply the and grew up to link those highlights now if needed.
>
> I can either read that diagram or if I prefer I can click and come inside here process will be a little
>
> bit more interesting.
>
> When payment is needed we do verify payment options.
>
> If hopefully the vending machine is smarter we can pay with our car then event will simply pay and then
>
> bring this down.
>
> But if it is old one probably need to prepare coins with coins and on the other works we can complete
>
> with our higher level process so we can take a copy and continue.
>
> So here you could see those moves and basic elements you could see in practice starting those and events
>
> tasks such processes gateways and sequence flows and those are the most important elements you'll be
>
> using every repeal and dagger.
