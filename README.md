# SLDC

Software development lifecycle həmçinin də SDLC adlanır. Yəni Proqram təminatının ərsəyə gəlməsinin prosesi. Siz developer komponaiyalarında işləyirsiznisə və ya işləyəndə bu sözü çox eşidəcəksiniz.

SDLC 7 etapdan ibarətdir. Bəzi yerlərdə ilk iki etapı birlikdə göstərirlər. Və son vaxtlar artıq API First dizayn bu prosesin əsas hissəini təşkil edir.

### Analysis and planing

İlk faza analiz və planlaşdırmadır.  İlk mərhələdə müştəri istəkləri təhlil olunur və ya şirkət prosesləri təhlil edilərək şirkət daxili nə iş görmək lazım olduğu aydınlaşdırılır. Bu etapda layihə planı və büdcəsi müəyyən edilir.

### Requirements

Bu mərhələdə layihə tələbləri müəyyənləşdirir.&#x20;

### &#x20;Design and prototyping

Burada məhsulun dizaynı və prototipi hazırlanır. Burada məhsul üzrə görünüş screen lərin hazırlanır və müştəriyə göstərilib məhsulun necə görünəcəyi ona bildirirlir. Lazım olduqda feedbacklar alınıb ona uyğun düzəlişlər edilir.

Bəzi layihələrdə Design and prototyping-ə ehtiyac olmur. Beləki biz əgər backend sistemləri arasında hər hansı bir layihə icra ediriksə bunun üçün dizyana ehtiyac qalmır. Məsələn bizim hazırladığımız Open bankingdə dizayna ehtiyac olmur. Çünki backend sistemlər bir biri ilə inteqrasiya edir. Ona görə burada dizayna ehtiyac yoxdur. Çünki müştəri bu tərəfləri görmür. Dizayn bizə müştərinin görəcəyi tərəf üçün lazımdır. Yəni Frontend development .

**Frontend və Backend nədir&**

Biz bu mövzulara kimi bunu bir neçə dəfə müzakirə etmişik. Front end məsələn şəkildə gördüyünüz kimi bizim mobil tətbiqimizin üst tərəfidir. Backend isə arxa tərəfə deyilir. Yəni server və orada olan applikasiyamız. Gördüyünüz kimi istifadəçi mobil tətbiqə girən kimi Front end backendə müraciət edib lazımı məlumatları sorğulayır.  Backend sorğunu alanda ona uyğun məlumatı qaytarır. Backend daxilində bir neçə application olur və hər endpointə biri baxa bilir. Microservisdə hər app-ın arxasında bir DB dayanır. Monilitdə isə 1. Bütün bunların hamsı isə serverdə yerləşir.

Gördüyünüz kimi ilk görünüş bu formada olur. Çünki Front hələ backenddən məlumatları almayıb. Gördüyünüz elementlər isə Frontendin öz proqramında qeyd edilib. Məsələn siz app yükləyirsiz, bütün proqramlaşdırma onun içərisində olur. Ona görə bəzi app-lara baxırıq 100 mg ytdır bəziləri 10 . Frontda nə qədər çox iş olarsa bir o qədər proqram həcmi artır. Nəticədə front bu məlumatları alıb lazımı yerlərə otuzdurub bizə göstərir. Bizim yazdıqlarımız API larda isə biz fronta deyirikki sən bu balansı almaq üçün necə request göndərməlisən. Backa da çatdırırıq ki, sən bu sorğuya nə cavab verməlisən.

>
>
>
>
>
>
> The second Cleartrip requirement phase where customer will hand over these requirements or our project
>
> plan to the project team who will going to work on that project.
>
> The third phase is design and prototyping.
>
> In this phase, the project team will go through the requirement and come up with the smart designs
>
> and prototypes.
>
> We showed customers how their final product will look like.
>
> The port phases, software development, both customer approval on design and buying phase project team
>
> will start coding those requirements.
>
> The fifth place is testing in this phase, the audit functionalities will be tested not only by the
>
> testing team against the defined requirements.
>
> The six phase is deployment.
>
> Once testing is completed, application will be deployed to what means it is released for customers
>
> who use the seven phases maintenance and updates, both releasing project to customer art public.
>
> They will keep on discovering nationalities or bugs in the existing functionalities.
>
> These new use cases are requirements, and bugs will be provided to project team for fixing.
>
> Bugs will be fixed and the updates will be released in the application.
>
> However, for the new requirement, entire SDLC cycle will be repeated again.
>
> This is just a high level view of SDLC, but in the upcoming session, we'll see what exactly happens
>
> at the top level at each step.
>
> Autoscroll
>
>
>
> \
>
