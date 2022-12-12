# SLDC

Software development lifecycle həmçinin də SDLC adlanır. Yəni Proqram təminatının ərsəyə gəlməsinin prosesi. Siz developer komponaiyalarında işləyirsiznisə və ya işləyəndə bu sözü çox eşidəcəksiniz.

SDLC 7 etapdan ibarətdir. Bəzi yerlərdə ilk iki etapı birlikdə göstərirlər. Və son vaxtlar artıq API First dizayn bu prosesin əsas hissəini təşkil edir.

### Analysis and planing

İlk faza analiz və planlaşdırmadır.  İlk mərhələdə müştəri istəkləri təhlil olunur və ya şirkət prosesləri təhlil edilərək şirkət daxili nə iş görmək lazım olduğu aydınlaşdırılır. Bu etapda layihə planı və büdcəsi müəyyən edilir.

### Requirements

Bu mərhələdə layihə tələbləri müəyyənləşdirir.&#x20;

### &#x20;Design and prototyping

Burada məhsulun dizaynı və prototipi hazırlanır. Burada məhsul üzrə görünüş screen lərin hazırlanır və müştəriyə göstərilib məhsulun necə görünəcəyi ona bildirirlir. Lazım olduqda feedbacklar alınıb ona uyğun düzəlişlər edilir.

Prorotoip dizayndan qabaqkı cızma qaradır. Dizayn isə son görünüş ekran. Əsasən prortip məhsulu başa düşmək üçün istifadə olunur və ilk olaraq cızma qara edilib steykholderlə razılaşdırılır. Məhz dizaynerlərədə bu verilir. Bunlar xüsusi proqramlarla hazırlanır. Əsasən prototip analitik tərəfind.n ağır proyektlər üzrə hazırlanır. məhz bu səbəbdəndə xaricdə bir çox analitikdən vireframe hazırlamaq bacarığı tələb olunur. Çox sadə məsələdir, qarşıdakı dərslərdə sizə göstərəcəm. Özünüzünzdə produktu tam başa düşüb onun tələblərini yazmaası üçün bəzən vireframe lazım olur.

Bəzi layihələrdə Design and prototyping-ə ehtiyac olmur. Beləki biz əgər backend sistemləri arasında hər hansı bir layihə icra ediriksə bunun üçün dizyana ehtiyac qalmır. Məsələn bizim hazırladığımız Open bankingdə dizayna ehtiyac olmur. Çünki backend sistemlər bir biri ilə inteqrasiya edir. Ona görə burada dizayna ehtiyac yoxdur. Çünki müştəri bu tərəfləri görmür. Dizayn bizə müştərinin görəcəyi tərəf üçün lazımdır. Yəni Frontend development .

**Frontend və Backend nədir&**

Biz bu mövzulara kimi bunu bir neçə dəfə müzakirə etmişik. Front end məsələn şəkildə gördüyünüz kimi bizim mobil tətbiqimizin üst tərəfidir. Backend isə arxa tərəfə deyilir. Yəni server və orada olan applikasiyamız. Gördüyünüz kimi istifadəçi mobil tətbiqə girən kimi Front end backendə müraciət edib lazımı məlumatları sorğulayır.  Backend sorğunu alanda ona uyğun məlumatı qaytarır. Backend daxilində bir neçə application olur və hər endpointə biri baxa bilir. Microservisdə hər app-ın arxasında bir DB dayanır. Monilitdə isə 1. Bütün bunların hamsı isə serverdə yerləşir.

Gördüyünüz kimi ilk görünüş bu formada olur. Çünki Front hələ backenddən məlumatları almayıb. Gördüyünüz elementlər isə Frontendin öz proqramında qeyd edilib. Məsələn siz app yükləyirsiz, bütün proqramlaşdırma onun içərisində olur. Ona görə bəzi app-lara baxırıq 100 mg ytdır bəziləri 10 . Frontda nə qədər çox iş olarsa bir o qədər proqram həcmi artır. Nəticədə front bu məlumatları alıb lazımı yerlərə otuzdurub bizə göstərir. Bizim yazdıqlarımız API larda isə biz fronta deyirikki sən bu balansı almaq üçün necə request göndərməlisən. Backa da çatdırırıq ki, sən bu sorğuya nə cavab verməlisən.

### 4. API First and conditions

Dizayn lazım olan layihəlrədə Dizayn və ya prototipdən sonra, lazım olmayanda isə reqeuirementlərə əsasən API First hazırlanır və şərtlər yazılır. Bu mərhələ olmayanda developer birbaşa tələb üzrə özü bir daha analiz aparıb development etməlidir.

### 5. Softvare development

Artıq məhsulun hazırlanma mərhələsidir. Proqramçılar bizim hazırladığımız API First və şərtlər əsasında develolmetn aparırlar.

### 6. Testing

Növbəti mərhələ isə hazırlanmış məhsulun testləşdirilməsidir. Testləşdirməninin bir neçə növü vardır. Məsələn, sistemin davmlılığın yoxlamaq üçün stress testing. İstifadəçi tərəfindən qəbul testi, user acceptance test və s. Əgər testləşdirmə zamanı bug olarsa, bug hər hansı bir problem. o zaman buna düzəliş olunur. Və bütün prosesi təzəədən keçirilir.

### 7. Deployment

Yekunda isə məhsul istifdəyə verili

Analitikin iştirakı burada 1, 2,4 cü bəndlər üzrə keçirilir.
