# Getting started tutorial: Using Stoplight Studio to create an OpenAPI specification document

> OpenAPI spesifikasiyası bir neçə yol ilə hazırlana bilər:
>
> 1. Source code-lardan avto generate edilməklə
> 2. Editor-lardan istifadə etməklə (məsələn Swagger Editor) manual kodlaşdırmaqla
> 3. GUI editordan (məsələn Stoplight) istifadə etməklə.
>
> Hazırda biz 3 variantda bildirdiyimiz GUİ editor olan Stoplight vasitəsilə API dizayn edəcəyik. Yəni, əvvəlki mövzularda travelpayouts üzrə göstərdiyimiz real API-ları daxili istifadə üçün APı First yanaşması tətbiq edəcəyik.

> For a higher-level introduction to the Open API, see [Introduction to the OpenAPI specification](https://idratherbewriting.com/learnapidoc/pubapis\_openapi\_intro.html). For a more conceptual introduction to Stoplight Studio is available here: [Stoplight — visual modeling tools for creating your OpenAPI spec](https://idratherbewriting.com/learnapidoc/pubapis\_stoplight.html).

### Using a visual editor <a href="#using-a-visual-editor" id="using-a-visual-editor"></a>

> Before we get started, let’s address an initial question about the approach we’re taking. When creating your OpenAPI specification document, why should you use a visual/GUI editor, which hides the code (unless you toggle the view open) instead of coding every detail of the spec by hand?
>
> All approaches have their merits. But if you don’t work with the OpenAPI specification enough to remember all the fields and syntax for each property, or if you’re learning it for the first time, trying to get the syntax valid in the raw code can be challenging. Coding by hand leads to many errors and forces you to spend a lot of time troubleshooting invalid syntax.
>
> Using an editor helps you avoid these errors and focus instead on the content. The less time you spend fiddling with syntax and more time working on content, the better the outcome of the documentation. For more on the philosophy of not getting lost in the syntactical details of the spec, but instead focusing on content, read this post by Phil Sturgeon, who says Stoplight Studio is “an absolute game changer for API Design, and something I’ve been waiting for since I found out about it somewhere in 2018” ([Reinventing API Design with Stoplight Studio](https://phil.tech/2019/08/22/reinventing-api-design-stoplight-studio/)).
>
> As a technical writer who likes working in Markdown and other raw formats, I can see the appeal of working directly in the code. But the OpenAPI syntax is quite complex, and YAML is fussy. I’d rather be worrying more about the content than addressing syntax questions. But even so, Stoplight lets you switch into the code view to work in that mode when you want, and switch back into the visual view when you want. Changes you make in one mode sync to the other. This gives you the best of both world
