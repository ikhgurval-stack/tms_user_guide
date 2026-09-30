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


## SYS заавар ба нүүр хуудас

Business Organization → User Management → Role Management зааврыг docs/sys/ хавтаст холбоно. SYS-ийн 10 screenshot-аар жагсаалт, хэрэглэгч болон role үүсгэх маягт, хэрэглэгч сонгох цонх, дэлгэрэнгүй болон General Data тоймыг баримтжуулсан. Дутуу цонх, хадгалалтын үр дүн, бизнесийн дүрмийг тусад нь тэмдэглэсэн.

Үндсэн index.md нь module navigation-д харьяалагдахгүй, not_in_nav-д орсон. Зөвхөн нүүрийн metadata дахь hide: [navigation, toc] тохиргоогоор sidebar, TOC-ийг нууна. Нүүр дээр аль нэг tab идэвхжихгүй; модуль дотор тухайн tab идэвхтэй байна. Лого болон Бусад тойм дахь холбоос нүүр рүү очно.


## SYS screenshot эх сурвалж

SYS-ийн 10 зураг docs/assets/screenshots/sys/ дотор хадгалагдана. assest/screenshots/sys/ дахь давхардсан зургуудыг SHA-256-аар ижил болохыг шалгасны дараа устгасан. Зургийн агуулгыг өөрчлөөгүй. Цаашид docs/assets/screenshots/sys/ дахь зургийг ашиглаж шинэчилнэ.


TC-B2C-E2E-001-ийн 20 давхардсан зургийг мөн ижил байдлыг шалгасны дараа assest/screenshots/ хавтсаас устгасан. docs/assets/screenshots/ нь SYS болон TC-B2C-E2E-001-ийн өмнөх 30 зургийг хадгална. Хуучин тайлбар файлуудыг хадгалж, markdown-snippets.md-ийн холбоосуудыг шинэчилсэн.


## TMS үндсэн мэдээллийн заавар ба screenshot стандарт

[Тээврийн хэрэгслийн төрөл](docs/tms/vehicle-type-management.md) болон [Тээвэрлэгчийн мэдээлэл](docs/tms/carrier-information.md)-ийн зааврыг 23 шинэ зурагт тулгуурлан боловсруулсан. Carrier Information нь есөн дэд заавартай. Систем дээр хадгалалт болон бизнесийн урсгалыг дахин туршаагүй; зураггүй алхам, баталгаажаагүй дүрмийг заавар дотор тэмдэглэсэн.

Шинэ screenshot-ийн үндсэн байрлал нь **docs/assets/images/screenshots/**. Vehicle Type болон Carrier Information-ийн 23 зураг **docs/assets/images/screenshots/tms/** дотор модуль, үйлдлээрээ ангилагдана. Эх зургуудыг **assest/screenshots/tms/**-ээс агуулгыг өөрчлөхгүй хуулж, SHA-256-аар ижил болохыг болон зааврууд үндсэн байрлалыг ашиглаж байгааг шалгасны дараа гаднах 23 давхардсан зургийг устгасан. Шинэ Markdown холбоос бүр үндсэн байрлалыг ашиглана.

Өмнөх SYS болон B2C тестийн холбоосыг хэвээр ажиллуулахын тулд **docs/assets/screenshots/** дахь зургуудыг хуучин замд нь хадгалсан. SYS агуулгыг өөрчлөхгүй байх шаардлагын дагуу тэдгээрийг энэ ажлаар шилжүүлээгүй. Цаашдын шинэ зургийг **docs/assets/images/screenshots/** дотор нэмнэ.

Зургийн дугаарын тайлбарыг бодит хүрээний байрлалтай тааруулсан. Required буюу заавал бөглөх тэмдэглэгээг зөвхөн зураг дээр харагдах улаан одоор баталгаажуулсан.

**assest/screenshots/tc-b2c-e2e-001/** дахь тайлбар файлуудыг хадгалсан.


## Customer Information заавар

[Харилцагчийн мэдээллийн тойм](docs/tms/customer-information.md) болон Client Management, Client Loading Point, Client Delivery Point, Fixed Route, Region Division гэсэн таван дэд зааврыг 22 зурагт тулгуурлан боловсруулсан. Шинэ хэрэглэгчийн бэлтгэх дараалал, талбарууд, Store хэрэглэгчийн холбоо, маршрутын төлөвлөгөө ба маршрутын ялгаа, бүсэд цэг нэмэх алхмыг тайлбарласан.

Зургийн үндсэн байрлал: **docs/assets/images/screenshots/tms/customer-information/**. Бүх 22 зургийг нэг удаа ашигласан. Эх зургуудыг **assest/screenshots/tms/customer-information/**-ээс агуулгыг өөрчлөхгүй хуулж, ижил байдал болон холбоосыг шалгасны дараа гаднах 22 давхардсан хувилбарыг устгасан.

Repository-д тусдаа customer-information-image-map.md, manifest.csv эсвэл developer guide олдоогүй тул зураг бүрийг нээж, дугаарын тайлбарыг бодит байрлалтай нь тулгасан. Road Network Update нь хүргэлтийн цэгийн зааврын нэмэлт ажиллагааны хэсэгт байна. Initialize Region, маршрут шинээр нэмэх маягт, Store хэрэглэгч үүсгэсний дараах үр дүн зэрэг дутуу нотолгоог зааварт тодорхой тэмдэглэсэн. Системийн ажиллагааг энэ шинэчлэлээр дахин туршаагүй.

## Transportation Management заавар

[Transportation Management](docs/tms/transportation-management.md)-ийг ерөнхий ойлголт болон Pickup Order, Transport Order, Quick Scheduling, Route Scheduling, Smart Scheduling, Transport Plan, Delivery Task, Pickup Task, Transportation Evaluation гэсэн дарааллаар шинэчилсэн. Одоо байсан transportation-order/, planning/, dispatch/ хуудсуудын URL-ийг хадгалж, дутуу таван заавар нэмсэн. Гараар төлөвлөх өмнөх тестийн хүрээ planning/manual-plan.md замаар холбоосоос нээгдэнэ.

21 шинэ зургийг нэг бүрчлэн нээж шалган, тус бүр нэг зааварт ашигласан. Зургууд ажлын эхэнд docs/tms/transportation-management/ дотор байсан; үндсэн стандарт болох **docs/assets/images/screenshots/tms/transportation-management/** руу агуулгыг өөрчлөхгүй шилжүүлсэн. Шилжүүлэхийн өмнөх/дараах SHA-256-ыг тулгасан. Repository-д тусдаа transportation-management-image-map.md, manifest.csv, developer guide олдоогүй.

Зургийн эх сурвалж ба хуудасны mapping:

| Зургийн дэд хавтас | Тоо | Заавар |
|---|---|---|
| pickup-order | 3 | [Pickup Order](docs/tms/transportation-management/pickup-order.md) |
| transport-order | 3 | [Жагсаалт, дэлгэрэнгүй](docs/transportation-order/overview.md), [шинэ маягт](docs/transportation-order/create-order.md) |
| quick-scheduling | 2 | [Quick Scheduling](docs/planning/quick-scheduling.md) |
| route-scheduling | 2 | [Route Scheduling](docs/planning/route-scheduling.md) |
| smart-scheduling | 2 | [Smart Scheduling](docs/planning/smart-plan.md) |
| transport-plan | 2 | [Transport Plan](docs/planning/overview.md) |
| delivery-task | 4 | [Delivery Task](docs/dispatch/publish.md) |
| pickup-task | 2 | [Pickup Task](docs/tms/transportation-management/pickup-task.md) |
| transportation-evaluation | 1 | [Transportation Evaluation](docs/tms/transportation-management/transportation-evaluation.md) |

Quick Scheduling-ийн Save, Pickup Task-ийн No Data-гийн дараах Save/Publish, advanced actions болон алгоритмын мэдээлэл баталгаажаагүй хэвээр. Smart Scheduling төрлийн төлөвлөгөө, Route Scheduling төрлийн task detail, өмнөх TC-B2C-E2E-001-ийн Mini App гүйцэтгэлийг тусдаа жишээгээр тайлбарласан. Шинэ Web зургуудын ижил task дугааруудаар Initial → Publish task → Shipped (Scheduled) шилжилт батлагдсан.

SYS, Carrier Information болон Vehicle Type Management-ийн агуулгыг өөрчлөөгүй. Customer Information-ийн тойм дахь захиалгын маягт байхгүй гэсэн хуучирсан ганц өгүүлбэрийг шинэ зааврын холбоосоор зассан. TMS / RPT / SYS / Mini App / Бусад үндсэн tab хэвээр. Энэ нь баримтжуулалтын шинэчлэл; TMS дээр ажиллагааг дахин туршаагүй.
