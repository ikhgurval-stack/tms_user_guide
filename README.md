# tms_user_guide

TMS хэрэглэгчийн Монгол хэл дээрх гарын авлага.

- [Гарын авлагын нүүр](docs/index.md)
- [B2C: захиалгаас төлбөр тооцоо хүртэл](docs/tutorials/order-to-delivery.md)
- [TC-B2C-E2E-001 тестийн бүртгэл](docs/testing/tc-b2c-e2e-001.md)

## Баримтжуулалтын хүрээ

Энэ шинэчлэл нь хэрэглэгчийн өгсөн TC-B2C-E2E-001 тестийн үр дүнд тулгуурласан. Системийн тестийг энэхүү documentation шинэчлэлийн хүрээнд дахин ажиллуулаагүй. Баталгаажаагүй үйлдлийг тусад нь тэмдэглэсэн.

TC-B2C-E2E-001-ийн 20 тайлбартай PNG зургийг `docs/assets/screenshots/tc-b2c-e2e-001/`-д байрлуулж, холбогдох алхмуудад оруулсан. Эх багц repository-ийн `assest/screenshots/tc-b2c-e2e-001/` хавтаст байсан. Тэндэх `README.md`, `markdown-snippets.md` нь дотоод ажлын материал тул MkDocs-ийн `docs/` хавтас болон navigation-д оруулаагүй. Эх зургуудыг өөрчлөөгүй.

[Зургийн mapping болон дутуу нотолгоо](docs/testing/tc-b2c-e2e-001.md)-г тестийн бүртгэлээс харна. Дутуу зургийг TODO, эх сурвалжийн зөрүүг REVIEW REQUIRED гэж тэмдэглэсэн.

## Бүтэц ба засварлах зарчим

Одоо байгаа файлын замыг хадгалсан. MkDocs Material нь TMS | RPT | SYS | Mini App | Бусад гэсэн таван tab болон дэд цэстэй. Лого болон Бусад хэсгээс үндсэн нүүр рүү орно. Mermaid тохируулаагүй; урсгалыг Markdown холбоосоор үзүүлсэн.

- `docs/getting-started/`: үндсэн өгөгдөл, нэвтрэлт, чиглүүлэг.
- `docs/transportation-order/`, `docs/planning/`, `docs/dispatch/`: захиалга, төлөвлөлт, оноолт, нийтлэх.
- `docs/execution/`: Driver App болон Store App.
- `docs/reference/`: төлөв, нэр томьёо, батлагдсан дүрэм, төлбөр тооцоо.
- `docs/testing/`: тестийн үр дүн, ажиглалт, нотолгооны бүртгэл.
- `docs/_templates/how-to-template.md`: шинэ зааврын загвар.

Үндсэн тайлбарыг Монгол хэлээр бичиж, UI дахь үйлдэл болон төлөвийн нэрийг хэвээр хадгална. Шинэ screenshot ашиглахын өмнө агуулгыг нь шалгаж, холбогдох алхмын дараа бодит relative path болон тайлбартай alt text оруулна.

## Локал шалгалт

MkDocs суулгасан орчинд `python -m mkdocs build --strict` ажиллуулна. Энэ нь documentation-ийн бүтцийг шалгах бөгөөд TMS-ийн ажиллагааг тестлэхгүй.


## Navigation засварлах

- docs/tms/, docs/sys/, docs/mini-app/, docs/other/: үндсэн хэсэг болон бүлгийн тойм.
- docs/reports/index.md: RPT-ийн нүүр; хуучин URL-ийг хадгалсан.
- Бүлгийн эхний nav entry нь тухайн тойм хуудас байна. Нэг зааврыг navigation-д нэг удаа оруулж, бусад бүлгээс Markdown холбоосоор холбоно.
- navigation.tabs нь үндсэн хэсгүүдийг, navigation.indexes нь index хуудсыг дэмжинэ. Дэд бүлгүүдийг эвхэж дэлгэх боломжтой хэвээр үлдээсэн.
- Grid cards нь attr_list, md_in_html өргөтгөл ашиглана. Custom CSS, JavaScript, template override нэмээгүй.
- Баримтгүй модулиудыг бүлгийн тойм дээр TODO гэж жагсаана; ажиллагааны алхам зохиохгүй.
- _templates нь navigation-д орохгүй боловч өмнөх URL-аар бүтээнэ.

Одоогийн орчинд build шалгах:

    .\.venv\Scripts\python.exe -m mkdocs build --strict --site-dir "$env:TEMP/tms-user-guide-build"

site/ нь repository-д бүртгэгдсэн build үр дүн тул шалгалтыг тусдаа хавтас руу гаргана. Vercel нь vercel.json дахь mkdocs build командыг ашиглан site/-ийг үүсгэнэ.
