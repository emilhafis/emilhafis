# Parallel Gateway (AND)

In this video I want to tell you about the next important BPMN building block.

BPMN də növbəti vacib building block "Parallel Gateway"-dir. AND" (Gateway) kimidə qarşınıza çıxa bilməz. Romb içərisində + işarəsi olur.

Bu bizə parallel taskları və ya növbəti addıma qədər eyni anda bir neçə task edilməlidirsə onarlı bildirir. bu sinxronizasiya adlanır.

Parallel gateways üzrə vacib məsələ odur ki, burada bütün tasklar eyni anda başlaya bilir. Taskın başlaması üçün hər hansı bir şərtə ehtiyac olmur.&#x20;

İkinci - bütün tasklar növbəti taska kimi bitməliir. Yəni bizim prosesimizin davam etməsi üçün bütün işlər yekunlaşmalıdır.  Paraelel activitlər yəni tasklar və subproseslər eyni anda işə düşməlidir. Əgər onlar eyni anda bitmirsə bu probelem deyil.&#x20;

Bizim şərtimiz olmadığı üçün biz nə Gatevey nədə sequency flov üçün ad göstərmirik.&#x20;





So this is rather simple. And now: how does it look like? Our case of \[Tasks named] ABCDEF would be a little bit different  if you'd like to show the "I want it all" case \[i.e. that all Tasks must take place].

So, our token is born and after we completed task A, interesting thing happens.

Please take a look: here we have one token and now voilà.  It was copied.

So we have 3 independent tokens that are ready to follow the Sequence Flow.

Let's assume that task B takes shortest (time) to complete.  So this is the fastest one.

So after it (Task B) was done our token continues but we cannot follow.

We cannot perform E and F because synchronization requires that all the tokens that were created - in this case 3 - will need to meet (together) to be merged into 1 \[token], so that the process can continue. So, after we finished C we have 2 of the 3 tokens. so we still cannot continue. \[But, after D was done] since the last element finally finished

Now those 3 tokens can be synchronized and our process can continue.

So this is very important thing about Parallel Gateways.

You will be splitting and merging parts and very importantly you will need to understand how the tokens behave.

If you take a look at a process like this, Valid logs could be for example: ABCDEF or assuming that we took it in a in a slightly different order.

It would be ABDCEF or maybe ACBDEF, but it only is a matter of order how those tasks were performed. We would not be able to say that our log was let's say ABCEF because until this \[Task D] is done our token cannot continue synchronization will not allow it.

So this is very important thing to know. It is not allowed to skip any of the elements from the parallel paths.



\
