# TC-B2C-E2E-001 — B2C Order-to-Settlement End-to-End Test

## Тестийн бүртгэл

| Үзүүлэлт | Утга |
|---|---|
| Scenario | B2C хүргэлт, сав буцаан татах, хүлээн авалт, үнэлгээ, төлбөр тооцоо |
| Preconditions | Үндсэн өгөгдөл бүрдсэн; Web TMS, Driver App, Store App-д ажиллах хэрэглэгчид бэлэн |
| Main flow | Order → Planning → Delivery → Pickup → Store Receipt → Evaluation → Cost |
| Expected | Урсгал дуусаж, холбогдох эцсийн төлөвүүд Completed/Approved болох |
| Actual | PASS — хэрэглэгчийн өгсөн гүйцэтгэсэн тестийн үр дүн |
| Эх сурвалж | Documentation шинэчлэх хүсэлтэд өгсөн TC-B2C-E2E-001-ийн батлагдсан тестийн мэдээлэл |
| Нотолгооны байдал | Repository-д бодит screenshot байхгүй; доорх TODO-уудаар бүрдүүлнэ |

Энэ нь өмнө гүйцэтгэсэн тестийн бүртгэл. Documentation шинэчлэх явцад TMS дээр дахин тест ажиллуулаагүй. Тестийн огноо, орчны хувилбар, гүйцэтгэгчийг эх сурвалжид тусад нь өгөөгүй; баримтын дугаараас таамаглан нөхөөгүй.

## Тестийн өгөгдөл

Үндсэн бүртгэлийн утгууд: [Customer, Loading Point, Delivery Point, Carrier, Vehicle, Driver](../getting-started/overview.md).

| Баримт / хэрэглэгч | Дугаар / утга |
|---|---|
| Delivery Task | B2CVS260922000001 |
| Pickup Order | B2CPG260922000001 |
| Pickup Task | B2CPT260922000001 |
| Carrier Expense Bill | B2CEP260922000001 |
| Store хэрэглэгч | qqB2C-DP-032 |
| Захиалгын тоо | 2; тус бүрийн ID өгөөгүй |

## Гүйцэтгэл ба бодит үр дүн

| Үе шат | Гүйцэтгэсэн үйлдэл | Бодит үр дүн |
|---|---|---|
| Төлөвлөлт | 2 захиалгаар Intelligent Dispatch ашигласан | 2 хүргэлтийн цэг, 9.547 km, 47 min; төлөвлөгөөнөөс Delivery Task үүссэн |
| Оноолт, нийтлэх | 1018УБА, B2C-DRV05 оноож нийтэлсэн | Driver App-ийн Current хэсэгт харагдсан |
| Ачилт | Arrival Confirmation → Confirm Loading → Loading Confirmation Signature | 2 цэг, Qty / Container = 2 / 0, Volume / Weight = 0.03 m³ / 2 kg; Awaiting Delivery |
| Савны бүртгэл | DP-032 дээр Pickup Registration, Tote Box = 1 | Pickup Order автоматаар үүссэн; барааны тоо, жин, эзлэхүүн 0; сав 1 |
| Хүргэлт | DP-032, дараа нь автоматаар гарсан DP-031 дээр Arrival Confirmation → Delivery Completed | Delivery Task Completed; савны бүртгэл хүргэлтийг үргэлжлүүлэхэд саад болоогүй |
| Буцаан татах | Хүргэлт дууссаны дараа гарсан тусдаа Pickup Task дээр Delivery Confirmation хийсэн | Pickup points = 1, Qty / Container = 0 / 1, очих газар Demo Distribution Center; Pickup Task Completed |
| Буцаан татах захиалга | Web Pickup Order-ийг шалгасан | Planned / Actual picked up / Actual delivered container = 1 / 1 / 1; Completed |
| Дууссан даалгавар | Task List → Completed шалгасан | Delivery Task, Pickup Task тусдаа Completed гэж харагдсан |
| Хүлээн авалт | qqB2C-DP-032 хэрэглэгчээр Store App-ийн Receipt List шалгасан | Delivery Task нь Completed / Received мэдээлэлтэй, Received хэсэгт байсан |
| Үнэлгээ | Punctuality 3/5 Normal, Cargo Damage 3/5 Normal, Overall 5/5 Awesome, Comment: Good Service; Submit | Web дээр Дундаж / Дундаж / Маш сайн, Good Service, үнэлэгч qqB2C-DP-032; даалгавар, цэг, 1018УБА, Мөнхөө мэдээлэлтэй харагдсан |
| Төлбөр тооцоо | Зөв тээвэрлэгчийн идэвхжүүлсэн гэрээ, Delivery Point based, 5,000 тариф | 2 × 5,000 = 10,000; Transportation Expense баримт Initial төлөвтэй үүссэн |
| Батлах | Review → approval comment → Approve | Эх сурвалжид reviewed/approved болсон гэж тэмдэглэсэн; UI төлөвийн яг бичвэрийг нэмж баталгаажуулна |

Алхамчилсан гарын авлага: [захиалгаас төлбөр тооцоо хүртэл](../tutorials/order-to-delivery.md).

## Known observations

- Эхний төлөвлөлтүүдэд **0/0 delivery point** гарсан; тээврийн хэрэгслийн сонголт, тохиргоог зөв болгосны дараа амжилттай болсон. Тохиргооны яг утга өгөөгүй.
- Гэрээний тээвэрлэгч **[B2C] B2C**, даалгаврынх **[B2C_TEST01] B2C_TEST** байсан үед **“Төлбөр тооцооны гэрээ таараагүй”** мэдэгдэл гарсан; зөв тээвэрлэгчийн шинэ гэрээг идэвхжүүлсний дараа амжилттай болсон.
- Calculated distance **9.547 km**, Actual mileage **0 km** хэвээр байсан. Шалтгаан тогтоогоогүй.
- UI дээр **¥** харагдсан. Currency display configuration-ийг тусад нь шалгах шаардлагатай; production орчинд ₮ хэрэглэх эсэх баталгаажаагүй.
- Төлөвлөлт ба Driver App-ийн гүйцэтгэл эхлэх дараалал ялгаатай харагдсан. Үүнийг системийн дүрэм гэж дүгнээгүй.

## Evidence ба дутуу screenshot

Одоогоор бодит screenshot reference байхгүй. Зураг ирэхэд агуулга, баримтын ID, төлөвийг шалгаж, холбогдох зааврын үйлдлийн дараа байрлуулна. Доорх холбоосууд нь нотлох зураг биш, зургийг байрлуулах зааврын хуудас юм.

| Шаардлагатай нотолгоо | Байрлуулах хуудас |
|---|---|
| Үндсэн өгөгдөл, Store хэрэглэгч | [Үндсэн өгөгдөл](../getting-started/overview.md) |
| Хоёр захиалга, цэгүүд | [Тээврийн захиалга](../transportation-order/create-order.md) |
| 0/0 үр дүн, зөв тохиргоо, 2 цэг / 9.547 km / 47 min төлөвлөгөө | [Intelligent Dispatch](../planning/smart-plan.md) |
| Тээврийн хэрэгсэл, жолоочийн оноолт, Current | [Тээврийн хэрэгсэл](../dispatch/assign-vehicle.md), [жолооч](../dispatch/assign-driver.md), [нийтлэх](../dispatch/publish.md) |
| Ачилт, гарын үсэг, цэгүүдийн дараалал, Pickup Registration, Pickup Order, Pickup Task, Completed жагсаалт | [Driver App](../execution/index.md) |
| Receipt List, үнэлгээ илгээх, Web дээрх үнэлгээ | [Store App](../execution/store-app.md) |
| Гэрээ, carrier mismatch, Initial, Review, Approve, эцсийн төлөв, ¥ тэмдэг | [Төлбөр тооцоо](../reference/cost-settlement.md) |
| Calculated distance 9.547 km ба Actual mileage 0 km | [GPS / бодит зай](../gps/index.md) |

<!-- TODO: Screenshot required — TC-B2C-E2E-001-ийн дээр жагсаасан нотолгоонууд -->
<!-- TODO: Тестийн огноо, орчны хувилбар, гүйцэтгэгч, захиалгын ID, planning configuration болон bill-ийн эцсийн UI төлөвийг нөхөж баталгаажуулах. -->

## Дараагийн санал болгож буй тестүүд

Доорх тестүүдийн үр дүн энэ бүртгэлд байхгүй.

- Order cancellation
- Delivery failure
- Partial delivery
- Capacity exceeded
- Multi-vehicle planning
- Pickup cancellation
- Expense bill rejection
- Expense bill void
