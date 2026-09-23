# TC-B2C-E2E-001 — Тайлбартай screenshot багц

Эдгээр зургуудыг хэрэглэгчийн гарын авлагын B2C Order-to-Settlement урсгалд ашиглахаар сонгож, чухал хэсгүүдийг дугаарласан хүрээгээр тодруулсан.

> Тайлбар: Улаан хүрээ + шар туяа нь анхаарах хэсгийг, дугаарласан тэмдэг нь доорх тайлбарын дугаарыг заана.

## 01. Тээвэрлэлтийн төлөвлөгөө амжилттай үүссэн

Файл: `01-transportation-plan-success.png`

- 1 — Захиалга/хүргэлтийн цэгийн тоо, тооцоолсон зай ба хугацаа.
- 2 — Төлөвлөгөөнд орсон DP-032 болон DP-031 хүргэлтийн цэгүүд.
- 3 — Системийн тооцоолсон маршрут.

## 02. Хүргэлтийн даалгаварт машин, жолооч оноосон

Файл: `02-delivery-task-driver-assigned.png`

- 1 — Тээвэрлэгч, Toyota Vitz, 1018УБА, B2C-DRV05 Мөнхөө гэсэн оноолт.
- 2 — Даалгаврыг нийтлэх (Publish) үйлдэл.

## 03. Driver App дээр нийтлэгдсэн хүргэлтийн даалгавар

Файл: `03-driver-current-task.png`

- 1 — Task No, улсын дугаар болон ачилтын цэг.
- 2 — Planned Delivery Points = 2 болон ачилтын нийт хэмжээ.
- 3 — Arrival Confirmation товч.

## 04. Ачилтын мэдээллийг баталгаажуулах

Файл: `04-loading-confirmation.png`

- 1 — Нийт Qty/Container болон Volume/Weight.
- 2 — Confirm Loading товч.

## 05. Ачилтын баталгаажуулалтын гарын үсэг

Файл: `05-loading-signature.png`

- 1 — Гарын үсэг зурах талбар.
- 2 — Complete товч.

## 06. Ачилт дууссаны дараах Awaiting Delivery төлөв

Файл: `06-awaiting-delivery-dp032.png`

- 1 — Task status = Awaiting Delivery.
- 2 — Эхний гүйцэтгэх хүргэлтийн цэг DP-032.
- 3 — Arrival Confirmation товч.

## 07. Хүргэлтийн цэг дээр Pickup Registration эхлүүлэх

Файл: `07-pickup-registration-entry.png`

- 1 — Pickup Registration товч.
- 2 — Arrival Confirmation товч.

## 08. Container pickup бүртгэх

Файл: `08-pickup-registration-form.png`

- 1 — Tote Box-ийн тоо болон тайлбар оруулах мөр.
- 2 — Submit товч.

## 09. Pickup бүртгэгдсэний дараах хүргэлтийн цэг

Файл: `09-pickup-registered.png`

- 1 — Pickup Cancel / Pickup Registration үйлдлүүд.
- 2 — Үндсэн хүргэлтийн Arrival Confirmation хэвээр идэвхтэй.

## 10. Pickup бүртгэлтэй үед хүргэлтийг дуусгах

Файл: `10-delivery-complete-with-pickup.png`

- 1 — Pickup Task: Registered төлөв.
- 2 — Delivery Completed товч.

## 11. Дараагийн хүргэлтийн цэг DP-031

Файл: `11-next-delivery-dp031.png`

- 1 — DP-031 автоматаар дараагийн хүргэлтийн цэг болсон.
- 2 — Arrival Confirmation товч.

## 12. Delivery дууссаны дараа автоматаар үүссэн Pickup Task

Файл: `12-pickup-task-to-dc.png`

- 1 — Pickup Task No болон Demo Distribution Center destination.
- 2 — Pickup point = DP-032, Qty/Container = 0/1.
- 3 — Delivery Confirmation товч.

## 13. Web TMS дээр Pickup Order дууссан

Файл: `13-pickup-order-completed-web.png`

- 1 — Pickup Order төлөв = Дууссан.
- 2 — Timeline-ийн дууссан цаг.
- 3 — Planned / actual picked / actual delivered container = 1.

## 14. Driver App-ийн Completed task list

Файл: `14-driver-completed-task-list.png`

- 1 — Pickup Task B2CPT... Completed.
- 2 — Delivery Task B2CVS... Completed.

## 15. Store App дээр Received болсон хүргэлт

Файл: `15-store-receipt.png`

- 1 — Received tab.
- 2 — B2CVS... task Completed/Received байдлаар харагдсан.

## 16. Store App-аас тээврийн үнэлгээ өгөх

Файл: `16-store-evaluation.png`

- 1 — Punctuality, Cargo Damage, Overall үнэлгээ.
- 2 — Comment хэсэг.
- 3 — Submit товч.

## 17. Store App-ийн үнэлгээ Web TMS дээр орж ирсэн

Файл: `17-web-transport-evaluation.png`

- 1 — Delivery task, delivery point, driver, нийт үнэлгээ, санал хүсэлт, evaluator.

## 18. Carrier agreement таараагүй validation

Файл: `18-cost-agreement-mismatch.png`

- 1 — Тохирсон 0, тооцоолох боломжгүй 1 гэсэн validation summary.
- 2 — “Төлбөр тооцооны гэрээ таараагүй” гэсэн шалтгаан.

## 19. Гэрээний дагуу тээврийн зардал тооцсон

Файл: `19-cost-calculation-10000.png`

- 1 — 2 хүргэлтийн цэг, 2 ширхэг, 2 kg, 0.03 m³, 9.547 km.
- 2 — Тооцоолсон төлбөр = 10,000.

## 20. Carrier Expense Bill хянагдаж батлагдсан

Файл: `20-expense-bill-approved.png`

- 1 — Bill No болон “Хянагдсан” төлөв.
- 2 — Carrier, Delivery Task, Transportation Expense, 10,000 дүн.
