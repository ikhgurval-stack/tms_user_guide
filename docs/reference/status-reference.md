# Төлөвийн лавлах

Энэ хүснэгтэд зөвхөн TC-B2C-E2E-001 тестийн эх сурвалжид дурдсан төлөвийг оруулсан. Системийн бүх төлөв, бүх шилжилтийн жагсаалт биш.

| Объект | Төлөв / харагдах хэсэг | Тестэд ажиглагдсан үе |
|---|---|---|
| Delivery Task | Current | Нийтэлсний дараа Driver App-ийн энэ хэсэгт харагдсан; төлөвийн нэр гэж баталгаажуулаагүй |
| Delivery Task | Awaiting Delivery | Ачилт, гарын үсгийн баталгаажуулалт дууссаны дараа |
| Delivery Task | Completed | Хоёр хүргэлтийн цэг дууссаны дараа |
| Pickup Task | Completed | Очих газарт Delivery Confirmation хийсний дараа |
| Pickup Order | Completed | Нэг сав татан авч, нэг сав хүргэсэн үр дүнтэй |
| Store Receipt | Completed / Received | Жолооч хүргэлт дуусгасны дараа Received хэсэгт харагдсан |
| Carrier Expense Bill | Initial | Баримт анх үүсэхэд |
| Carrier Expense Bill | reviewed/approved | Review, тайлбар, Approve-ийн дараах эх сурвалжийн тэмдэглэл; UI дахь яг бичвэрийг баталгаажуулах шаардлагатай |

Үйлдлийн заавар: [Driver App](../execution/index.md), [Store App](../execution/store-app.md), [зардлын баримт](cost-settlement.md).
