# Тээврийн захиалгын төлөв

## Харагдсан төлөв

Шинэ Transport Order-ийн жагсаалт болон дэлгэрэнгүйд **In Transit** харагдана. Энэ нь тээвэрлэлт явагдаж буй захиалгын төлөв.

Дэлгэрэнгүйн хугацааны мөрөнд **Order time**, **Operation start time**, **Completion time** байна. Жишээний дууссан цаг бөглөгдөөгүй.

## Захиалга ба даалгаврын төлөвийг ялгах

[Order Detail](overview.md#transport-order-detail)-ийн Delivery task хүснэгтэд **Cancelled**, **Shipped (Scheduled)** харагдана. Эдгээр нь холбоотой даалгавруудын төлөв бөгөөд Transport Order-ийн төлөвүүд биш.

**Initial → Publish task → Shipped (Scheduled)** нь [Delivery Task дээр батлагдсан урсгал](../dispatch/publish.md). Үүнийг Transport Order-ийн төлөвийн шилжилт гэж ашиглахгүй.

## Баталгаажуулалтын хүрээ

Шинэ захиалга хадгалсны дараах эхний төлөв, засварлах ба цуцлах үеийн шилжилт одоогийн тестээр баталгаажаагүй.

[Transport Order-ийн тойм](overview.md) · [Төлөвийн лавлах](../reference/status-reference.md).
