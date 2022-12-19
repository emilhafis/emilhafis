# Introduction

Sizlərin bəzilərinin BPMN ilə işləmək təcrübəsi var, bəziləriniz yəqinki ilk dəfə işləyəcəksiniz. İnterviyularda dəqiq bilinki sizdən ən azından soruşulacaq ki, BPMN nədir.

indi sizdə sual yaranıb ki yəqin BPMn nədir və niyə onu öyrənirik. Biz Open Banking API yazanda proseis dərhal başa düşə bilmirdik, bilmirdik ki nədən sonra nə gəlməlidir nə necə olmalıdır. inteqrasiyada backend sistemləri arası idi deyə dizayn və s edə bilmirdikir. BPMN bu prosesləri göstərmək üçün əla vasitədir. Biz BPMN ilə proseslərin necə getdiyini həta hansı təşkilatın və ya strukturların hansı işləri görəcəyini vizual olaraq təsvir edib görə bilirik.

Çox gmün ki, siz görənmüsüz və ya eşitmisinizki BPMN çox qəlizdir. Bəli bu belədir. Orada çoxlu sayda proseslər və addımlar var. Spesifikasiya isə 500 səhifədir. Və bu spesifikasiyanın demək olar ki, yarısıda bizə lazım belə deyil. Bu səbəbdəndə mən sizə faydalı olan prosesləri göstərcəm və dəqiq olaraq hansılardan istifadə etmək bizim işimizə yarayırsa onlara baxacağıq. qəliz sxmelər qurmaq müxtəlif işarələrlə onları göstərmək bizə lazım belə deyil əsas odurki ona baxan insanlar dərhal prosesi başa düşsünlər.

### Basics of modelling process with BPMN

Yəqin indi sizdə sual yaranır ki, nə üçün bizə prosesləri modelləşdirməl lazımdır.&#x20;

Məlumdurki bütün işləri görmək üçün böyük və ya kiçik team-lərə ehtiyacımız var. Əgər bizim planımız və nə edəcəyimiz məlum olmazsa işimizdə effektli olmaz. Əgər bizim edəcəyimiz proses bizə məlum olmasa onu etməkdə qeyri mümkün olar. Hətta start up edəndə də, 3- nəfər ilə işi görəndə də edəcəklərimizi və viziyonumuzu dəqiq müəyyənləşdirməliyik. Bunun üçün bir xeyli yanaşma vardır.



Ən birincisi prosudr və instruksiyadır. Adətən bunlar uzun və mürəkkəb sənədlər olur. Buna görədə onlar user friendly olmur.  Sonra diaqramlar var. Diaqramlar daha yaxşıdır, çünki onlar qrafikdir, ona görə də başa düşmək daha asandır mənası nədir. Lakin problem ondadır ki, diaqramlar bir çox formada ola bilər və onların hamısı formal deyil və bəziləri sadəcə gözəl şəkillərdir.



Amma biz öz məqsədlərimizə çatmaq üçün və oxuyucalara aydın mesaj ötürmək üçün prosess diaqramdan istifadə edəəcyik. Bizim proses diaqramımız aşağıdakı suallara cavab verəcəkdir

1. Prosesi nə başladır
2. Prosesimiz haradan başlayır

Bundan sonra biz dəqiq biləcəyik ki, nələr icra edilməlidir. Hansı işlər görülməlidir və razılaşdırılmış mərhələlər üçün nələr lazımdır. Sonra, adətən, bir neçə addımı yerinə yetirməyimiz həmin addımlar vaxtı nələr baş verdiyini və əksər vaxtı addımın dərhal bitmədiyini və bir neçə sub proses olduğunu görcəyik.

Ən əsası bizim oxuyucalar ilə eyni dilmizi olur yəni komanda üzvlərimiz prosesə baxmaqla nəyin necə getdiyini başa düşür.

