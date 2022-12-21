# Gateway

Gəlin indidə Gatewayə baxaq.&#x20;

BPMN də ən çox istifadə olunan Exclusive gateway dir. Bu həmçinində XOR kimi yəni eXclusive OR tanınır.

Gördüyünüz kimi bu romb formada və ya içərisində X kimi işarə olunur. istəniləni istifadə eəd bilərsiniz. Amma proses üzrə birindən istifadə edin.

Görəcəyimiz nümunələrdə biləcəyik ki, Gatevey gedəcəyimiz yolu təyin edir. Texniki olaraq Gatveydə qərar veririk, amma bu oturub qərar vermirik avtomatik sistem şərtlərə əsasən yolu təyin edir. bu qərar artıq gatveyə qədər verilmiş olur. Məsələn, yazacağımız proqram artıq qəbul olunmuş sorğuya əsasən hansı istiqamətə məlumat ötrüməyə qərar verə bilər.&#x20;

Məsələn Gateveydə biz yaza bilərik ki, option selected. YES or nO buna əsasən artıq prosesimiz davam edə bilər.

Gəlin indi prosesə baxaq - Kofee maşınında selectiondan sonra

Gəlin digər bir misala addım addım baxaq.

Biz artıq bilirik ki, sadə ardıcıllıq necə təşkil olunmalıdır. Beləki bizim birinci addım ikinci addım və digərləri ABCDEF kimi işarə olunur.&#x20;

burada görürük ki bizim addımlarımız A da başlayıb F də bitir.

indi isə bir az mürəkkəbə keçək. Exclusive seçimdən istifadə edək. Burada görürüsnüzki biz start ilə başladıq və A taskımız var, və Exclusive gateway seçimə çatanda şərtə əsasən 3 seçimiz olur. Burada yalnız bir seçim yolu ilə getmək mümükündür. Seçimimiz nə olsada sonra prosesimiz E  və F ilə davam edir. So we could have either something like this: ABEF or ACEF or ADEF.it is not possible that we would have ABCEF because we can either have this.

Eyni zamanda siz istəsəniz çıxışada Gatevey qoya bilərsiniz. bunların mənası tamamilə eynidir. bunlar adatən IT backgrounduna əsaəsn istifadə olunur nəyisə açmısansa bağlamlısan. Mən əsasən birincidən istifadə edirəm.&#x20;

