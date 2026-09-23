# Store App: хүлээн авалт ба тээврийн үнэлгээ

## Зорилго

Хүргэлтийн хүлээн авалтын мэдээллийг Store App-аас шалгаж, тээврийн үнэлгээ илгээнэ. Илгээсэн үнэлгээг Web TMS дээр шалгана.

## Урьдчилсан нөхцөл

DP-032 цэгт **qqB2C-DP-032** Store хэрэглэгч бэлтгэгдсэн, жолоочийн талаас [хүргэлт дууссан](index.md) байна.

## Цэсний зам

- Store App → Receipt List → Received.
- Үнэлгээ хийх үйлдэл: Transport Evaluation; түүнд хүрэх цэсний бүрэн шатлал эх сурвалжид өгөөгүй.
- Web TMS → Transportation Management → Transportation Evaluation.

## Алхамууд

### 1. Хүлээн авалтыг шалгах

1. Store App-д **qqB2C-DP-032** хэрэглэгчээр нэвтэрнэ.
2. Дэлгүүр **B2C Home 032** эсэхийг шалгана.
3. **Receipt List** дотор **B2CVS260922000001** хүргэлтийг шалгана.
4. **Completed / Received** мэдээлэлтэй, **Received** хэсэгт орсныг шалгана.

<!-- TODO: Screenshot required — Store App-ийн Receipt List / Received хэсэг дэх B2CVS260922000001 -->

Тестэд жолооч хүргэлтээ дуусгасны дараа хүлээн авалтын мэдээлэл **Received** хэсэгт орсон. Store хэрэглэгч тусдаа хүлээн авалт баталгаажуулах товч дарсан гэж эх сурвалжид тэмдэглээгүй.

### 2. Тээврийн үнэлгээ илгээх

1. Store App-ийн **Transport Evaluation** үйлдлийг нээнэ.
2. Үнэлгээ болон тайлбарыг оруулна. Тестэд доорх утгуудыг ашигласан.
3. **Submit** үйлдлээр илгээнэ.

| Талбар | Монгол тайлбар | Тестийн үнэлгээ | App дээрх тайлбар |
|---|---|---|---|
| Punctuality | Цаг баримталсан байдал | 3/5 | Normal |
| Cargo Damage | Ачааны гэмтлийн үнэлгээ | 3/5 | Normal |
| Overall | Ерөнхий үнэлгээ | 5/5 | Awesome |
| Comment | Тайлбар | Good Service | — |

<!-- TODO: Screenshot required — Transport Evaluation-ийн тестийн утгууд болон Submit үйлдэл -->

### 3. Web TMS дээр үнэлгээг шалгах

1. **Transportation Management → Transportation Evaluation** хэсгийг нээнэ.
2. **B2CVS260922000001** даалгавар, **B2C-DP-032 / B2C Home 032** хүргэлтийн цэгийн үнэлгээг шалгана.
3. Доорх мэдээлэлтэй тулгана.

| Мэдээлэл | Web дээрх тестийн үр дүн |
|---|---|
| Vehicle | 1018УБА |
| Driver | Мөнхөө |
| Punctuality | Дундаж |
| Cargo damage | Дундаж |
| Overall | Маш сайн |
| Comment | Good Service |
| Evaluator | qqB2C-DP-032 |

<!-- TODO: Screenshot required — Web Transportation Evaluation дээрх даалгавар, цэг, жолооч, үнэлгээ, тайлбар, үнэлэгч -->

## Хүлээгдэж буй үр дүн

Store App-аас илгээсэн үнэлгээ Web TMS-ийн **Transportation Evaluation** хэсэгт харагдана.

## Анхаарах зүйл

Хүснэгтийн оноо нь тестийн жишээ. Бусад үнэлгээг эдгээр утгаар бөглөх шаардлагагүй. Store хэрэглэгч үүсгэх аргын тодорхойгүй хэсгийг [үндсэн өгөгдлийн зааварт](../getting-started/overview.md) тэмдэглэсэн.
