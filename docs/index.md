---
hide:
  - navigation
  - toc
---

# E-Mart TMS Knowledge Base

Transportation Management System (TMS)-ийн эцсийн хэрэглэгчийн гарын авлага.

## Үндсэн хэсгүүд

<div class="grid cards" markdown>

-   **[TMS](tms/index.md)**

    Мастер мэдээлэл, тээврийн төлөвлөлт, гүйцэтгэл, хяналт, зардал.

-   **[RPT](reports/index.md)**

    Report Application болон тайлангийн баримтжуулалтын төлөв.

-   **[SYS](sys/index.md)**

    Платформын системийн удирдлага ба ерөнхий өгөгдөл.

-   **[Mini App](mini-app/index.md)**

    Driver App болон Store App-ийн заавар.

-   **[Бусад](other/index.md)**

    Танилцуулга, нэр томьёо, End-to-End процесс, FAQ болон тест.

</div>

## Шинэ хэрэглэгч бол хаанаас эхлэх вэ?

### Эхлэх дараалал

Дараах нь санал болгож буй бэлтгэлийн дараалал. Бүх алхмын дэлгэрэнгүй заавар хараахан бэлэн болоогүй; холбоос бүрээс баримтжуулалтын төлөвийг шалгана.

1. [SYS → Business Organization](sys/business-organization.md).
2. [User Management](sys/user-management.md) → [Role Management](sys/role-management.md).
3. [TMS Master Data — үндсэн өгөгдөл бэлтгэх](getting-started/overview.md).
4. [Carrier](tms/carrier-information.md).
5. [Vehicle Type](tms/vehicle-type-management.md).
6. [Vehicle → Employee/Driver](tms/carrier-information.md).
7. [Customer → Loading Point → Delivery Point](tms/customer-information.md).
8. [Transport Order](transportation-order/overview.md).

Өгөгдөл бэлэн бол [B2C урсгалыг бүтнээр нь дагах](tutorials/order-to-delivery.md) зааврыг ашиглана.

## Documentation Status

Энэхүү гарын авлага нь UAT болон тестийн явцад боловсруулагдаж байна. B2C урсгалын тайлбарыг хэрэглэгчийн өгсөн **TC-B2C-E2E-001** тестийн үр дүнгээр шинэчилсэн. Батлагдсан алхмуудад 20 тайлбартай screenshot оруулсан. Дутуу нотолгоо болон эх сурвалжийн зөрүүг [тестийн бүртгэлд](testing/tc-b2c-e2e-001.md) тэмдэглэсэн.

## Эндээс юу олох боломжтой вэ?

### Getting Started

[Үндсэн өгөгдөл бэлтгэх](getting-started/overview.md), [нэвтрэх](getting-started/login.md), [гарын авлагын чиглүүлэг](getting-started/navigation.md).

### Transportation Order

[Тээврийн захиалгын тойм](transportation-order/overview.md) болон тестэд ашигласан захиалгын мэдээлэл.

### Transportation Planning

[Төлөвлөлтийн тойм](planning/overview.md), [ухаалаг төлөвлөлт (Intelligent Dispatch)](planning/smart-plan.md), [гараар төлөвлөх үйлдлийн баталгаажуулалтын хүрээ](planning/manual-plan.md).

### Dispatch

[Тээврийн хэрэгсэл оноох](dispatch/assign-vehicle.md), [жолооч оноох](dispatch/assign-driver.md), [хүргэлтийн даалгавар нийтлэх](dispatch/publish.md).

### Execution

[Driver App: ачилт, хүргэлт, сав буцаан татах](execution/index.md), [Store App: хүлээн авалт ба тээврийн үнэлгээ](execution/store-app.md).

### GPS

[GPS болон бодит явсан зайн баталгаажуулалтын хүрээ](gps/index.md).

### Reports

[Тайлангийн баталгаажуулалтын хүрээ](reports/index.md).

### Troubleshooting

[Туршилтаар ажиглагдсан асуудлууд](troubleshooting/index.md).

## B2C урсгалыг бүтнээр нь дагах

[B2C: захиалгаас төлбөр тооцоо хүртэл](tutorials/order-to-delivery.md) хуудсаас эхэлнэ. [Төлбөр тооцооны заавар](reference/cost-settlement.md), [төлөвийн лавлах](reference/status-reference.md), [тестийн үр дүн](testing/tc-b2c-e2e-001.md)-г холбогдох алхамд ашиглана.

## Documentation Legend

| Status | Тайлбар |
|---|---|
| 🟡 Draft | Баримтжуулж байгаа |
| 🔵 Testing | UAT/тест хийж байгаа |
| 🟢 Verified | Тестийн эх сурвалжаар баталгаажсан хүрээ |
| 🔴 Needs Update | Шинэчлэх шаардлагатай |

Verified нь тухайн тестэд хамаарах бөгөөд системийн бүх хувилбар, тохиргоог хамарсан баталгаа биш.
