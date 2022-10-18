# Stoplight: visual modeling tools for creating your OpenAPI spec

> Stoplight ilə OpenAPI spesifikasiyasını yaratmazdan öncə demək istərdim ki, OpenAPI spesifikasiyanı sadə formada yazılaraq OpenAPI spesifikasiyasına çox rahatlıqla keçirilməsinə icazə verən bir tool-dur.&#x20;
>
> Mən özüm Stoplightdan istifadə edirəm və interfeysin və funksionallıqların çox bəyənirəm.&#x20;
>
> Stoplight API OpenAPI spesifika yaratmaq üçün vizual modelləşdirmə alətləri təqdim edir. Yəni siz OpenAPI spesifikasiyasının təfərrüatlarını bilmənizi və ya spesifikasiyanı sətir-sətir kodlaşdırmanızı tələb etmədən, sizin üçün avtomatik Open APı spesifikasiyası (Yaml) generasiya edir. burada biz öz API-lərimizi yaza onu testləşdirə, developer portalı yarada bilərik. bir sözlə API üzrə bütün lifecycle-ı əhatə edə bilərik.

### Limits to line-by-line spec coding <a href="#limits-to-line-by-line-spec-coding" id="limits-to-line-by-line-spec-coding"></a>

> Detallara keçməmişdən əvvəl bir məsələni də bildirim ki, bu platformaların ən özəl tərəfi ondan ibarətdir ki, manual olaraq Yaml hazırlamırsan. nə qədər spesifikasiyanı gözəl bilsən də, yenədə onun hazırlığı zamanı hansısa nüansları unuda bilərsən və belə olduqda, səhvin tapılması üçün sənə xeyli vaxt lazım olur.
>
> As part of the visual modeling tools, Stoplight’s interface for describing JSON schemas (used in request bodies or responses) is especially welcome.
>
> Vizual modelləşdirmə üsullarından biri olan JSON interfeysdə JSOn sxemlərini (request və response body) xüsusi göstərilməsi çox yaxşı fikirləşilmişdir.
>
> Stoplight-da xüsusilə yaxşı olan bir məqam ondan ibarətdir ki, siz əlinizdə olan JSON-u birbaşa YAML a yəni OpenAPI spesifikasiyanı convert edə bilirsiniz. Ən çox istifadə etdiyim özəlliklərindən biri budur. praktiki olaraq bunu necə edirik tanış olacağıq.

> Sonda qayıtmaq
