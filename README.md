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

### Modelling with BPMN

Bu m\[vzuda m'n siz' prosess modelling wzr' BPMN dən necə istifadə edirlər onu göstərəcəm.

BPMN açıqlaması "Business Process Model and Notation" BPMN in version 2.0 is the de-facto standard for modeling processes held by the Object Management Group.

Bu standart yüzlərlə tool-lar və servis provayderlər tərəfindən dəstəklənir.  Bununla belə, spesifikasiyanı oxuyaraq BPMN-ni öyrənməyə çalışsanız, bu, bir az qorxulu ola bilər, çünki spesifikasiya kifayət qədər uzun və çox maraqlı deyil.

Buna görə də mən əsas məsələləri sizə bildirəcəm.&#x20;

Bu mövzunun sonunda siz çox rahatlıqla diaqramlar yarada biləcəksiniz.Yratdığını diaqramlar çox asan olmaqla hamı tərəfindən başa düşüləcəkdir. Çünki ümumi standart əsasında hazırlayacağıq.&#x20;

#### BPMN blocks

Biz indi BPMN üzrə əsas elementlərə başxacağıq.

Start Events - "Prosesi nə başladır sualnıa cavab verəcəkdir. Bundan sonra bizi maraqlandıran nə işlər görülməlidir sualına cavab sadə proseslər addımı və Sub prosesləri göstərən mürəkkəb proseslər olan işarələr olacaqdır.

Sonra biz proses zamanı hansı variantların olduğunu göstərmək üçün Gateways dən istifadə edəcəyik.

Həmçinində istiqamətimizi göstəmək üçün oxlardan sitifadə edəcəyik. Və nəhayət End events prosesimizin necə bitdiyini və hədən sonra bitəcəyini göstərir.

#### BPMN building blocks

Gəlin tez bir daha üzzərindən keçək.

Start events hadisələri tək nazik haşiyəli dairələrdir. Onlar bizə nə baş verməli olduğunu göstərir ki, bizim proses başlaya bilsin və onlar bizim etdiyimiz deyil, baş verməli olan şeydir ki, proses başlasın.

End eventsdə tək haşiyəli dairələrdir. Lakin bu haşiyə qalındır. Və onlar bizə prosesin nəticələrinin nə olduğunu göstərir ki, biz prosesin daxilində və xaricində nə olduğunu bilək.

Start event kimi bu da bizə nə etməli olduğumuzu deyil prosesin nəticəsini bildirirk. Elementlərin adlandırılması bizə prosesləri daha yaxşı başa düşməyə imkan verir. Beləki proses içərisində və ya kənarında nələr baş verir.&#x20;

Siz bu formada adlandıra bilərsiniz. Adlandırmanı çalışın fel və məchul növdə edin. Məsələn, Order received yəni Sifariş qəbul olundu. və End eventsimiz belə olacaq - Məhsullar göndərildi - Goods shipped.

#### Activities

Bunlardan başqa bizim acitivtələrimiz vardır. Bunlar - Dairəvi düzbaclıqlıardır hansıkı bizə sadə prosesləri göstərir. bunlardan başqa bizim eyni formada amma içərisində + işarəsi olan Sub proseslərdə vardır. Bunlar bizə daha mürəkkəb prosesi göstərmirir və həmçinində bizə mürəkkəb prosesləri gozlətməyə kömək edir. Yəni... Və adından bilinməlidirki bu prosesdə nələr edilməlidir.&#x20;

Məsələn sadə proses üçün Check order, Prepare report işlədə bilərik. Amma sub process üçün Məsələn Payment shipping və s. çünki onun daxilində proseslər yer alır.

#### Gatevey

Bunlardna başqa bizim Gateveyimi də vardır. gatevey hər zaman romb formasında göstərilir. Bir neçə gatevey növü vardır. Onlara gedişatda baxacağıq.  gatevey bizə prosesləri ayırmaqda və ya birləşdirməkdə kömək edir. Yəni gedəcəyimiz yolları şərtlərə görə ayırır.

#### Squence flow

n'hay't Sequence flov/ Ox vasit'sil' t'svir edirlir. Bu oxlar Start evnetdən son evenetə kimi aparılır.&#x20;





