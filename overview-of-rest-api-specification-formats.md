# Overview of REST API specification formats

REST API spesifik standartı yox, yaradıcı standartı var. Yəni bir API-yı siz müxtəlif formalarda dizayn edə bilərsiniz. \
REST API-ların təsvirinin bir standartını vermək üçün ilk əvvəl bir neçə REST spesifikasiyaları yaradılmışdır. İlk 3 spek [OpenAPI (formally called Swagger)](https://github.com/OAI/OpenAPI-Specification), [RAML](https://raml.org/) və [API Blueprint](https://apiblueprint.org/) olmuşdur.\


Spesifikasiyaların ilk illərində formatlar arasında sağlam rəqabət var idi. Ancaq indi OpenAPI spesifikasiyası ən böyük community, alətlərlə və s görə ən populyardır. Buna görə mən bu kursu OpenAPI üzərində qurmuşam. İstəsəniz Raml və API Blueprint ilə özünüz təqdim etdiyim linkdən tanış ola bilərsiniz. Amma ehtiyac görümürəm çünki hazırda bütün dünya Open API spek üzərində işlərini qurur.&#x20;

Ümumiyyətlə, REST API-lər üçün spesifikasiyaların olması API üçün daha yaxşı reference sənədlərinin hazırlanmasına gətirib çıxardır. Nəzərə alın ki,REST API spesifikasiyaları əsasən API-də bundan əvvəlki APİ dizayn bölməsində danışdığımız endpointləri və onlar üzrə parametrləri təsvir edir. Bu mövzular vacib olsa da, nəzərə almaq lazımdır ki, sənədləşməmiz yalnız bunlar ilə bitmir. Məhz buna görə də bizim bununla bağlı ayrıca bir mövzumuzda olacaqdır.



Bunlara baxmayaraq, referens dokumentasiya API sənədləşməsinin əsas hissəsini təşkil edir. Beləki referens dokumentsaiysında gördüyümüz kimi bu hissə endpointlərə xitab edərək onların qaytardıqları dəyərləri əhatə edir.&#x20;

Bu tip spesifikasiyalar, API sənədlərinə əhəmiyyətli dərəcədə unikallıq qatır. OpenAPI spesifikasiya formatını mənimsəməklə, əmin olun ki, ölkədə çox fərqli analitiklər və rəhbərlər səviyyəsinə gəlmiş olacaqsınız. Bizim ölkəmiz bu sahədə çox geri qalır amma xaricə baxsaq bu gün ən çox tələb olunan sahələrdəndir. Artıq heç kimi saddə analitik (stekholderlələ danışan, standart analizlər edən və s) lazım deyildir. Hamı öz CV sinə yaza biləriki analiz qabiliyyətim var, amma analizi hansı formada aparmağı bilməsə qeyd edə bilməz.



