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
| Нотолгооны байдал | 20 annotated PNG-г гарын авлагад оруулсан; зураг бүрийн байрлал болон дутуу нотолгоог доор тэмдэглэсэн |

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
| Батлах | Review → approval comment → Approve | Эх сурвалжид reviewed/approved гэж тэмдэглэсэн; 20 зурагт UI төлөв Хянагдсан |

Алхамчилсан гарын авлага: [захиалгаас төлбөр тооцоо хүртэл](../tutorials/order-to-delivery.md).

## Known observations

- Эхний төлөвлөлтүүдэд **0/0 delivery point** гарсан; тээврийн хэрэгслийн сонголт, тохиргоог зөв болгосны дараа амжилттай болсон. Тохиргооны яг утга өгөөгүй.
- Гэрээний тээвэрлэгч **[B2C] B2C**, даалгаврынх **[B2C_TEST01] B2C_TEST** байсан үед **“Төлбөр тооцооны гэрээ таараагүй”** мэдэгдэл гарсан; зөв тээвэрлэгчийн шинэ гэрээг идэвхжүүлсний дараа амжилттай болсон.
- Calculated distance **9.547 km**, Actual mileage **0 km** хэвээр байсан. Шалтгаан тогтоогоогүй.
- UI дээр **¥** харагдсан. Currency display configuration-ийг тусад нь шалгах шаардлагатай; production орчинд ₮ хэрэглэх эсэх баталгаажаагүй.
- Төлөвлөлт ба Driver App-ийн гүйцэтгэл эхлэх дараалал ялгаатай харагдсан. Үүнийг системийн дүрэм гэж дүгнээгүй.

## Evidence ба дутуу screenshot

Зургийн README-ийн тайлбар, PNG бүрийн харагдах агуулга болон зааврын контекстийг тулгаж, 20 зургийг тус бүр нэг үндсэн байрлалд оруулсан. Доорх нь давхар зураг оруулахгүйгээр эх зураг, холбогдох зааварт хүрэх холбоос юм.

| Screenshot | Markdown file | Section |
|---|---|---|
| [01-transportation-plan-success.png](../assets/screenshots/tc-b2c-e2e-001/01-transportation-plan-success.png) | [planning/smart-plan.md](../planning/smart-plan.md) | Алхамууд: төлөвлөгөө шалгах |
| [02-delivery-task-driver-assigned.png](../assets/screenshots/tc-b2c-e2e-001/02-delivery-task-driver-assigned.png) | [dispatch/assign-driver.md](../dispatch/assign-driver.md) | Алхамууд: оноолтыг шалгах |
| [03-driver-current-task.png](../assets/screenshots/tc-b2c-e2e-001/03-driver-current-task.png) | [dispatch/publish.md](../dispatch/publish.md) | Алхамууд: Current хэсэгт шалгах |
| [04-loading-confirmation.png](../assets/screenshots/tc-b2c-e2e-001/04-loading-confirmation.png) | [execution/index.md](../execution/index.md) | 1. Ачилтын цэгт ирэх, ачилт баталгаажуулах |
| [05-loading-signature.png](../assets/screenshots/tc-b2c-e2e-001/05-loading-signature.png) | [execution/index.md](../execution/index.md) | 1. Ачилтын цэгт ирэх, ачилт баталгаажуулах |
| [06-awaiting-delivery-dp032.png](../assets/screenshots/tc-b2c-e2e-001/06-awaiting-delivery-dp032.png) | [execution/index.md](../execution/index.md) | 1. Ачилтын цэгт ирэх, ачилт баталгаажуулах |
| [07-pickup-registration-entry.png](../assets/screenshots/tc-b2c-e2e-001/07-pickup-registration-entry.png) | [execution/index.md](../execution/index.md) | 2. Эхний хүргэлтийн цэгт ирэх, сав бүртгэх |
| [08-pickup-registration-form.png](../assets/screenshots/tc-b2c-e2e-001/08-pickup-registration-form.png) | [execution/index.md](../execution/index.md) | 2. Эхний хүргэлтийн цэгт ирэх, сав бүртгэх |
| [09-pickup-registered.png](../assets/screenshots/tc-b2c-e2e-001/09-pickup-registered.png) | [execution/index.md](../execution/index.md) | 2. Эхний хүргэлтийн цэгт ирэх, сав бүртгэх |
| [10-delivery-complete-with-pickup.png](../assets/screenshots/tc-b2c-e2e-001/10-delivery-complete-with-pickup.png) | [execution/index.md](../execution/index.md) | 3. Хүргэлтийн цэгүүдийг дуусгах |
| [11-next-delivery-dp031.png](../assets/screenshots/tc-b2c-e2e-001/11-next-delivery-dp031.png) | [execution/index.md](../execution/index.md) | 3. Хүргэлтийн цэгүүдийг дуусгах |
| [12-pickup-task-to-dc.png](../assets/screenshots/tc-b2c-e2e-001/12-pickup-task-to-dc.png) | [execution/index.md](../execution/index.md) | 4. Сав буцаан татах даалгаврыг дуусгах |
| [13-pickup-order-completed-web.png](../assets/screenshots/tc-b2c-e2e-001/13-pickup-order-completed-web.png) | [execution/index.md](../execution/index.md) | 5. Web захиалга болон дууссан даалгавруудыг шалгах |
| [14-driver-completed-task-list.png](../assets/screenshots/tc-b2c-e2e-001/14-driver-completed-task-list.png) | [execution/index.md](../execution/index.md) | 5. Web захиалга болон дууссан даалгавруудыг шалгах |
| [15-store-receipt.png](../assets/screenshots/tc-b2c-e2e-001/15-store-receipt.png) | [execution/store-app.md](../execution/store-app.md) | 1. Хүлээн авалтыг шалгах |
| [16-store-evaluation.png](../assets/screenshots/tc-b2c-e2e-001/16-store-evaluation.png) | [execution/store-app.md](../execution/store-app.md) | 2. Тээврийн үнэлгээ илгээх |
| [17-web-transport-evaluation.png](../assets/screenshots/tc-b2c-e2e-001/17-web-transport-evaluation.png) | [execution/store-app.md](../execution/store-app.md) | 3. Web TMS дээр үнэлгээг шалгах |
| [18-cost-agreement-mismatch.png](../assets/screenshots/tc-b2c-e2e-001/18-cost-agreement-mismatch.png) | [reference/cost-settlement.md](../reference/cost-settlement.md) | Анхаарах зүйл |
| [19-cost-calculation-10000.png](../assets/screenshots/tc-b2c-e2e-001/19-cost-calculation-10000.png) | [reference/cost-settlement.md](../reference/cost-settlement.md) | 2. Төлбөр тооцоо хийж, зардлын баримтыг шалгах |
| [20-expense-bill-approved.png](../assets/screenshots/tc-b2c-e2e-001/20-expense-bill-approved.png) | [reference/cost-settlement.md](../reference/cost-settlement.md) | 3. Зардлын баримтыг хянан батлах |

**Зураг ба эх сурвалжийн зөрүү:**

- 01 зурагт төлөвлөгөө DP-032 → DP-031, 04 зурагт Delivery Point1 нь DP-031, 06 зурагт гүйцэтгэл DP-032-оос эхэлсэн байна. Дарааллын ялгааг аль дэлгэц, үе шаттай харьцуулсныг нэмж шалгана.
- 01 зураг дахь төлөвлөлтийн дүн 12,864.1; 19 зураг дахь settlement дүн 10,000. Эдгээр дүнгийн хамаарлыг баталгаажуулаагүй.
- 07, 09 зурагт Pickup бүртгэлийн өмнө болон дараа Arrival Confirmation харагдана. Өмнөх тестийн үйлдлийн дараалалтай тулгаж шалгана.
- 08 зурагт Tote Box талбар хоосон. Энэ нь бөглөх маягтыг харуулна; нэг сав бүртгэсний үр дүнг 12, 13, 14 зурагт шалгана.
- 13 зурагт “Үүсгэх арга: Гараар үүсгэх” харагдсан нь захиалга автоматаар үүссэн гэсэн тестийн тайлбартай зөрнө. Үүсэх механизмын талаар шинэ дүрэм дүгнээгүй.
- 16, 17 зурагт тайлбар **Good Service;**, эх тестийн тэмдэглэлд **Good Service** байна.
- 20 зурагт эцсийн төлөв **Хянагдсан** гэж харагдана. Review, тайлбар, Approve хийх явцын дэлгэцүүд энэ багцад байхгүй.
- README-ийн 03, 12, 13 зургийн highlight тайлбаруудын зарим утга өөр дугаарын хүрээнд эсвэл хүрээний гадна харагдсан. Зааврын зургийн тайлбарт бодит байрлалыг баримталсан.

**Дутуу screenshot:**

- Үндсэн өгөгдөл болон Store хэрэглэгчийн бүртгэл, нэвтрэх дэлгэцүүд.
- Тестийн хоёр Transportation Order-ийн дэлгэрэнгүй.
- 0/0 төлөвлөлт болон амжилттай ашигласан тохиргооны дэлгэц.
- Tote Box = 1 гэж бөглөсөн маягт; Pickup Order анх үүссэн мөчийн дэлгэц.
- Зөв тээвэрлэгчийн идэвхжүүлсэн гэрээ, Delivery Point based төрөл, нэг цэгийн 5,000 тариф.
- Зардлын баримтын Initial төлөв, Review, approval comment, Approve хийх дэлгэцүүд.

<!-- TODO: Screenshot required — дээр жагсаасан дутуу нотолгоонууд -->
<!-- REVIEW REQUIRED: Дараалал, төлөвлөлтийн дүн, Pickup Order-ийн үүсгэх арга болон тайлбарын бичвэрийн зөрүүг эх тесттэй тулгах. -->
<!-- TODO: Тестийн огноо, орчны хувилбар, гүйцэтгэгч, захиалгын ID болон planning configuration-ийг нөхөж баталгаажуулах. -->

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
