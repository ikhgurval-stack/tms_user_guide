# Transportation Management — Тээврийн удирдлага

[TMS-ийн тойм](index.md)

## Энэ хэсэг юу хийдэг вэ?

Харилцагчийн барааг хаанаас авч, хаана хүргэхийг захиалгаар бүртгэнэ. Захиалгуудыг төлөвлөж, маршрут, машин, жолоочтой холбоно. Дараа нь хүргэлтийн даалгаврыг нийтэлж, жолоочийн гүйцэтгэл болон хүлээн авагчийн үнэлгээг шалгана.

**Цэсний зам:** TMS → Transportation Management → тохирох дэд цэс.

## Transportation Management ашиглахын өмнө

Дараах үндсэн мэдээллийг **ерөнхийдөө урьдчилан бэлтгэсэн байх шаардлагатай**. Энэ нь бүх талбарыг систем ижил нөхцөлөөр заавал шаардана гэсэн дүрэм биш.

| Мэдээлэл | Юунд ашиглах вэ? | Бэлтгэх заавар |
|---|---|---|
| Client | Захиалга аль харилцагчийнх болохыг сонгоно. | [Client Management](customer-information/client-management.md) |
| Loading Point | Барааг ачих газрыг сонгоно. | [Client Loading Point](customer-information/client-loading-point.md) |
| Delivery Point | Бараа хүргэх газрыг сонгоно. | [Client Delivery Point](customer-information/client-delivery-point.md) |
| Carrier | Тээвэр гүйцэтгэх байгууллага. | [Carrier](carrier-information/carrier.md) |
| Vehicle Type | Машины төрөл, даац, багтаамж. | [Vehicle Type Management](vehicle-type-management.md) |
| Vehicle | Улсын дугаартай бодит машин. | [Vehicle Management](carrier-information/vehicle-management.md) |
| Driver / Employee | Тээвэр гүйцэтгэх жолооч, түүний аппын хэрэглэгч. | [Employee Management](carrier-information/employee-management.md) |

Маршрутаар төлөвлөх бол [Fixed Route](customer-information/fixed-route.md), бүсээр шүүх бол [Region Division](customer-information/region-division.md)-ийн бүртгэлээ шалгана. Дэлгүүрийн хүлээн авалт, үнэлгээнд [Store хэрэглэгчийн холбоо](customer-information/client-delivery-point.md#store-user) хэрэгтэй.

## Захиалга, төлөвлөгөө, даалгаврын ялгаа

| Ойлголт | Энгийн тайлбар |
|---|---|
| [Transport Order](../transportation-order/overview.md) | Харилцагчийн барааг ачилтын цэгээс хүргэлтийн цэг рүү тээвэрлэх захиалга. |
| Scheduling | Захиалгуудыг тээвэрлэхээр төлөвлөх ажиллагаа. |
| [Transport Plan](../planning/overview.md) | Төлөвлөлтийн үр дүн; дотроо маршрут, хүргэлтийн цэгүүдтэй. |
| [Delivery Task](../dispatch/publish.md) | Төлөвлөгөөний маршрутыг бодитоор гүйцэтгэх хүргэлтийн даалгавар. |
| [Pickup Order](transportation-management/pickup-order.md) | Тодорхой Pickup Point-оос бараа, сав татан авах захиалга. |
| [Pickup Task](transportation-management/pickup-task.md) | Pickup Order-уудыг татан авах бодит ажиллагаатай холбосон даалгавар. |

**Transport Order ба Pickup Order нь тусдаа захиалга.** B2C тестэд Transport Order-оор бараа хүргэсэн; Pickup Order-оор нэг савыг хүргэлтийн цэгээс агуулах руу буцаан татсан. Сав буцаахыг бүх бараа буцаалтын дүрэм гэж ойлгохгүй.

## Үндсэн холбоо

[Customer Information](customer-information.md)
→ [Transport Order](../transportation-order/overview.md)
→ Scheduling
→ [Transport Plan](../planning/overview.md)
→ [Delivery Task](../dispatch/publish.md)
→ [Driver Mini App](../execution/index.md)
→ Delivery Completed
→ [Store / Receiver](../execution/store-app.md)
→ [Transportation Evaluation](transportation-management/transportation-evaluation.md).

Татан авах ажиллагаа байгаа үед тусдаа холбоо үүснэ:

[Pickup Order](transportation-management/pickup-order.md) → [Pickup Task](transportation-management/pickup-task.md).

## Scheduling-ийн аргуудыг ялгах {#scheduling}

| Арга | Зориулалт | Одоогийн нотолгоо |
|---|---|---|
| [Quick Scheduling](../planning/quick-scheduling.md) | Захиалгыг хурдан, гараар маршрут болгон бэлтгэх урсгал. | Захиалга сонгох ба төлөвлөх дэлгэц нээгдсэн. Planned Route = 0, Save идэвхгүй. |
| [Route Scheduling](../planning/route-scheduling.md) | Маршрут, тогтмол маршрутад тулгуурлан нөөцөө төлөвлөх урсгал. | Маршрутын мэдээлэл, машин/жолооч, Start planning баталгаажуулалт харагдсан. |
| [Smart Scheduling](../planning/smart-plan.md) | Систем захиалга, багтаамжийн мэдээллээр төлөвлөгөө боловсруулах урсгал. | Order selection, Capacity selection дэлгэц болон Smart Scheduling төрлийн бүртгэлтэй төлөвлөгөө байна. Эдгээрийг нэг оролдлого гэж батлаагүй. |

Арга тус бүрийн зааврыг өөрийнх нь зурагтай уншина. Маршрут, машин, жолооч сонгох автомат тооцооллын дүрэм одоогийн тестээр баталгаажаагүй.

## B2C хүргэлтийн баталгаажсан үндсэн урсгал

Доорх нь шинэ Web зургууд болон өмнөх [TC-B2C-E2E-001](../testing/tc-b2c-e2e-001.md)-ийн нотолгоог үе шатаар холбосон зураглал. Бүх зургийг нэг захиалгын нэг удаагийн гүйцэтгэл гэж үзэхгүй.

```text
Transport Order → Scheduling → Transport Plan → Delivery Task
                                                     │
                                              Initial → Publish
                                                     ↓
                                            Shipped (Scheduled)
                                                     ↓
                                              Driver Mini App
                                                     ↓
                                           Ачилт (Loading) → Delivery
                                                     ↓
                                                 Completed
                                                     ↓
                                           Store: Received шалгах
                                                     ↓
                                          Transportation Evaluation
```

1. [Transport Order үүсгэх](../transportation-order/create-order.md) маягтыг бөглөж, жагсаалт ба дэлгэрэнгүй мэдээллийг шалгана.
2. Тохирох Scheduling цэсээр захиалга, тээврийн нөөцөө бэлтгэнэ.
3. [Transport Plan](../planning/overview.md)-ийн маршрут, машин, жолоочийг шалгана. Төлөвлөгөө нийтлэх ба даалгавар нийтлэх нь өөр дэлгэцийн үйлдлүүд.
4. [Delivery Task](../dispatch/publish.md)-ийг дугаар, төлөвлөгөө, маршрутаар нь тулгаж, **Publish task** хийнэ. Шинэ Web тестэд төлөв **Initial → Shipped (Scheduled)** болсон.
5. [Driver Mini App](../execution/index.md)-д ачилт, хүргэлтээ гүйцэтгэнэ. Өмнөх B2C тестэд даалгавар **Completed** болсон.
6. [Store App](../execution/store-app.md)-д **Received** мэдээллийг шалгаж, үнэлгээг **Submit** хийнэ.
7. [Transportation Evaluation](transportation-management/transportation-evaluation.md)-д даалгавар болон хүргэлтийн цэгээр үнэлгээг шалгана.

Өмнөх B2C тестэд хүргэлтийн үеэр савны Pickup Registration хийсэн. Үндсэн хүргэлт дууссаны дараа тусдаа Pickup Task-ийг гүйцэтгэсэн. Энэ нь Web дээр **New Pickup Task → Save → Publish** урсгалыг туршсан гэсэн үг биш.

## Төлөвүүдийг ойлгох

| Status | Аль бүртгэлд? | Энгийн тайлбар |
|---|---|---|
| Initial | Delivery Task | Даалгавар үүссэн, нийтлэгдээгүй. |
| Initial | Pickup Order | Жагсаалтад харагдсан эхний төлөв; цаашдын шилжилтийн зураг байхгүй. |
| Pending release | Transport Plan | Үүссэн боловч нийтлэгдээгүй төлөвлөгөө. |
| Published | Transport Plan | Нийтлэгдсэн төлөвлөгөө. |
| Shipped (Scheduled) | Delivery Task | Тестэд Publish task хийсний дараа харагдсан төлөв. Машин бодитоор хөдөлснийг дангаар батлахгүй. |
| In Transit | Transport Order | Тээвэрлэлт явагдаж буй захиалгын төлөв. |
| Completed | Delivery Task / Pickup Task / Pickup Order | Тухайн ажил дууссан. |
| Cancelled | Delivery Task | Цуцлагдсан даалгавар. Цуцалсан нөхцөлийг зураг дангаар батлахгүй. |

Дэлгэрэнгүйг [төлөвийн лавлахаас](../reference/status-reference.md) харна. Нэг төрлийн бүртгэлийн төлөвийг нөгөөгийнхтэй адилтгахгүй.

## Одоогоор бүрэн баталгаажаагүй хэсгүүд

- Quick Scheduling-ээр маршрут амжилттай үүсгэж, Save хийсний дараах үр дүн.
- Pickup Task-д Pickup Order сонгосны дараах Save болон Publish-ийн үр дүн.
- Захиалгын шинэ маягтыг хадгалсны дараах баталгаажуулалт, импортын загвар, batch үйлдлүүд.
- Зарим cancel, adjust, direct complete, re-plan болон auto-match үйлдлийн нөхцөл, үр дүн.
- Төлөвлөлтийн алгоритм, автомат эрэмбэ, маршрут, машин, жолооч сонгох тооцоолол.
- Газрын зургийг бодит GPS гүйцэтгэлтэй холбох дүрэм.

Эдгээр нь **одоогийн тестээр баталгаажаагүй** зүйлс. Дэлгэцийн зураг, тестийн хязгаарыг тухайн зааварт тэмдэглэсэн.
