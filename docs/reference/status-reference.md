# Төлөвийн лавлах

Эхний хүснэгтэд TC-B2C-E2E-001 тестийн эх сурвалжид дурдсан төлөвийг оруулсан. Системийн бүх төлөв, бүх шилжилтийн жагсаалт биш.

| Объект | Төлөв / харагдах хэсэг | Тестэд ажиглагдсан үе |
|---|---|---|
| Delivery Task | Current | Нийтэлсний дараа Driver App-ийн энэ хэсэгт харагдсан; төлөвийн нэр гэж баталгаажуулаагүй |
| Delivery Task | Awaiting Delivery | Ачилт, гарын үсгийн баталгаажуулалт дууссаны дараа |
| Delivery Task | Completed | Хоёр хүргэлтийн цэг дууссаны дараа |
| Pickup Task | Completed | Очих газарт Delivery Confirmation хийсний дараа |
| Pickup Order | Completed | Нэг сав татан авч, нэг сав хүргэсэн үр дүнтэй |
| Store Receipt | Completed / Received | Жолооч хүргэлт дуусгасны дараа Received хэсэгт харагдсан |
| Carrier Expense Bill | Initial | Баримт анх үүсэхэд |
| Carrier Expense Bill | Хянагдсан | Тестийн эх сурвалжид reviewed/approved гэж тэмдэглэсэн; 20 зураг дахь эцсийн UI төлөв |

Үйлдлийн заавар: [Driver App](../execution/index.md), [Store App](../execution/store-app.md), [зардлын баримт](cost-settlement.md).

## Transportation Management-ийн шинэ Web зургууд

| Объект | Төлөв | Энгийн тайлбар |
|---|---|---|
| Transport Order | In Transit | Захиалгын тээвэрлэлт явагдаж байна. |
| Transport Plan | Pending release | Төлөвлөгөө үүссэн, нийтлэгдээгүй. |
| Transport Plan | Published | Төлөвлөгөө нийтлэгдсэн. |
| Delivery Task | Initial | Даалгавар үүссэн, нийтлэгдээгүй. |
| Delivery Task | Shipped (Scheduled) | Шинэ тестэд Publish task-ийн дараа харагдсан. |
| Delivery Task | Cancelled | Цуцлагдсан даалгавар; аль төлөвөөс цуцалсан нь баталгаажаагүй. |
| Pickup Order | Initial / Completed | Эхний болон дууссан төлөвтэй тусдаа захиалгууд байна. |
| Pickup Task | Completed | Өмнө үүссэн дууссан даалгавар байна. |

Шинэ Web тестийн батлагдсан шилжилт: **Delivery Task: Initial → Publish task → Shipped (Scheduled)**. [Нийтлэх заавар](../dispatch/publish.md)-аас ижил дугаартай өмнөх/дараах зургуудыг харна.

Plan-ийн Published ба task-ийн Shipped (Scheduled) нь өөр бүртгэлд хамаарна. Бүх төлөвийн бүх шилжилтийг энэ хүснэгтээр батлаагүй. [Нийт урсгал ба нотолгооны хүрээ](../tms/transportation-management.md).
