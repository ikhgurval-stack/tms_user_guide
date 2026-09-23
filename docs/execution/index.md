# Driver App: ачилт, хүргэлт, сав буцаан татах

## Зорилго

Нийтэлсэн хүргэлтийн даалгаврын ачилт, хүргэлтийг гүйцэтгэж, сав буцаан татах (Pickup) ажиллагааг дуусгана. Доорх дараалал нь TC-B2C-E2E-001 тестийн үр дүнд тулгуурласан.

## Урьдчилсан нөхцөл

**B2CVS260922000001** даалгаврыг **1018УБА** тээврийн хэрэгсэл, **[B2C-DRV05] Мөнхөө** жолоочид оноож, [нийтэлсэн](../dispatch/publish.md) байна.

## Цэсний зам

Driver App → Current; дууссан даалгаврыг шалгахдаа Task List → Completed хэсгийг нээнэ.

## Алхамууд

### 1. Ачилтын цэгт ирэх, ачилт баталгаажуулах

1. **Current** хэсгээс хүргэлтийн даалгаврыг нээнэ.
2. Ачилтын цэг **[DEMO-DC01] Demo Distribution Center** болон доорх мэдээллийг шалгана.

    | Талбар | Тайлбар | Тестийн утга |
    |---|---|---|
    | Planned Delivery Points | Төлөвлөсөн хүргэлтийн цэгийн тоо | 2 |
    | Qty / Container | Барааны тоо / савны тоо | 2 / 0 |
    | Volume / Weight | Эзлэхүүн / жин | 0.03 m³ / 2 kg |

3. Ачилтын цэгт ирээд **Arrival Confirmation** үйлдлээр ирснээ баталгаажуулна.
4. **Confirm Loading** үйлдлээр ачилтыг баталгаажуулна.

    ![Нийт барааны тоо, эзлэхүүн, жин болон Confirm Loading товч](../assets/screenshots/tc-b2c-e2e-001/04-loading-confirmation.png)

5. **Loading Confirmation Signature** хэсэгт гарын үсэг зурж, **Complete** дарна.

    ![Ачилтын гарын үсэг зурах талбар болон Complete товч](../assets/screenshots/tc-b2c-e2e-001/05-loading-signature.png)

6. Ачилт дууссаны дараа даалгавар **Awaiting Delivery** төлөвт шилжсэнийг шалгана.

    ![Awaiting Delivery төлөвтэй даалгаврын эхний хүргэлтийн цэг DP-032](../assets/screenshots/tc-b2c-e2e-001/06-awaiting-delivery-dp032.png)

### 2. Эхний хүргэлтийн цэгт ирэх, сав бүртгэх

1. Апп дээр гарсан хүргэлтийн цэгийг шалгана. Тестэд эхлээд **[B2C-DP-032] B2C Home 032** гарсан.
2. Тухайн цэгт ирээд **Arrival Confirmation** үйлдэл хийнэ.
3. Сав буцаан татах бүртгэл хийхдээ **Pickup Registration** үйлдлийг ашиглана.

    ![Хүргэлтийн цэгийн Pickup Registration болон Arrival Confirmation товчнууд](../assets/screenshots/tc-b2c-e2e-001/07-pickup-registration-entry.png)

4. **Tote Box** мөрийн тооны талбарт **1** оруулж, **Submit** дарна.

    ![DP-032 цэгийн сав бүртгэх маягт дахь Tote Box мөр болон Submit товч](../assets/screenshots/tc-b2c-e2e-001/08-pickup-registration-form.png)

    Зурагт бөглөхийн өмнөх маягт харагдана. **1** гэсэн утга энэ зурагт ороогүй; тестэд бүртгэсэн нэг савыг Web-ийн дууссан захиалгаар шалгана.

Бүртгэлийн дараах дэлгэцэд **Pickup Cancel**, **Pickup Registration**, **Arrival Confirmation** харагдаж байгааг шалгана.

![Сав бүртгэсний дараа Pickup Cancel болон Arrival Confirmation харагдаж буй байдал](../assets/screenshots/tc-b2c-e2e-001/09-pickup-registered.png)

> Туршилтын үед ажиглагдсан:
> Өмнөх тестийн тайлбарт Arrival Confirmation-ийн дараа сав бүртгэсэн гэж тэмдэглэсэн боловч 07 болон 09 зурагт энэ товч харагдсан хэвээр байна. Дэлгэцүүдийн дарааллаас шинэ нөхцөл, дүрэм дүгнэхгүй. Pickup Cancel харагдсан нь цуцлах ажиллагааг тестэлсэн гэсэн үг биш.

<!-- REVIEW REQUIRED: Arrival Confirmation болон Pickup Registration-ийн бодит гүйцэтгэлийн дарааллыг баталгаажуулах. -->

Бүртгэлийн дараа Web TMS дээр **B2CPG260922000001** буцаан татах захиалга (Pickup Order) автоматаар үүссэн гэж тестийн эх сурвалжид тэмдэглэсэн.

| Мэдээлэл | Тестийн утга |
|---|---|
| Pickup point | [B2C-DP-032] B2C Home 032 |
| Delivery destination | [DEMO-DC01] Demo Distribution Center |
| Product quantity | 0 |
| Weight | 0 |
| Volume | 0 |
| Container | 1 |

### 3. Хүргэлтийн цэгүүдийг дуусгах

1. DP-032 дээр **Delivery Completed** үйлдэл хийнэ. Тестэд Pickup Registration нь үндсэн хүргэлтийн даалгаврыг үргэлжлүүлэхэд саад болоогүй.

    ![Pickup Task Registered мэдээлэлтэй үед Delivery Completed товч харагдсан байдал](../assets/screenshots/tc-b2c-e2e-001/10-delivery-complete-with-pickup.png)

    1-р хүрээнд **Pickup Task: Registered**, 2-р хүрээнд **Delivery Completed** товч байна. Энэ нь хүргэлтийг дуусгахаас өмнөх дэлгэц.

2. Дараагийн хүргэлтийн цэг **[B2C-DP-031] B2C Home 031** автоматаар гарсныг шалгана.

    ![DP-032-ийн дараа гарсан DP-031 хүргэлтийн цэг болон Arrival Confirmation товч](../assets/screenshots/tc-b2c-e2e-001/11-next-delivery-dp031.png)

3. DP-031 дээр **Arrival Confirmation**, дараа нь **Delivery Completed** үйлдэл хийнэ.
4. Хоёр цэгийн хүргэлт дууссаны дараа **B2CVS260922000001** даалгавар **Completed** төлөвтэй болсныг шалгана.

### 4. Сав буцаан татах даалгаврыг дуусгах

1. Бүх хүргэлтийн цэг дууссаны дараа автоматаар гарсан тусдаа **B2CPT260922000001** буцаан татах даалгаврыг (Pickup Task) нээнэ.
2. **Pickup points = 1**, **Qty / Container = 0 / 1**, очих газар **Demo Distribution Center** эсэхийг шалгана.
3. Савыг очих газарт хүргээд **Delivery Confirmation** үйлдэл хийнэ.

    ![Demo Distribution Center рүү сав хүргэх Pickup Task болон Delivery Confirmation товч](../assets/screenshots/tc-b2c-e2e-001/12-pickup-task-to-dc.png)

    **Зураг дээрх тэмдэглэгээ:** 1 — даалгаврын дугаар, очих газар, нийт Qty / Container = 0 / 1; 2 — DP-032 татан авах цэг; 3 — **Delivery Confirmation**. Дууссан үр дүнг дараах Completed жагсаалтаас шалгана.

4. Буцаан татах даалгавар **Completed** төлөвт шилжсэнийг шалгана.

### 5. Web захиалга болон дууссан даалгавруудыг шалгах

1. Web TMS дээр **B2CPG260922000001** Pickup Order-ийг шалгана.

    ![Web Pickup Order-ийн Дууссан төлөв, дууссан цаг болон нэг савны гүйцэтгэл](../assets/screenshots/tc-b2c-e2e-001/13-pickup-order-completed-web.png)

    **Зураг дээрх тэмдэглэгээ:** 1 — **Дууссан** төлөв; 2 — дууссан цаг; 3 — тоо, жин, эзлэхүүний хэсэг. Төлөвлөсөн, татан авсан, хүргэсэн савны **1 / 1 / 1** утгууд 3-р хүрээний доорх мөрөнд харагдана.

    > Туршилтын үед ажиглагдсан:
    > Тестийн тайлбарт захиалга автоматаар үүссэн гэж тэмдэглэсэн боловч энэ зурагт “Үүсгэх арга: Гараар үүсгэх” гэж харагдана. Үүсэх механизмыг зөвхөн энэ талбараас дүгнэхгүй.

    <!-- REVIEW REQUIRED: Pickup Registration-аас үүссэн захиалгын үүсгэх аргын талбарын утгыг шалгах. -->

    | Талбар | Тестийн үр дүн |
    |---|---|
    | Planned container | 1 |
    | Actual picked up container | 1 |
    | Actual delivered container | 1 |
    | Status | Completed |

2. Driver App → **Task List → Completed** хэсэгт дараах хоёр даалгавар тусдаа харагдаж байгааг шалгана.

    ![Completed жагсаалтад Pickup Task болон Delivery Task тусдаа дууссан байдал](../assets/screenshots/tc-b2c-e2e-001/14-driver-completed-task-list.png)

    | Даалгаврын дугаар | Төрөл | Төлөв |
    |---|---|---|
    | B2CPT260922000001 | Pickup Task | Completed |
    | B2CVS260922000001 | Delivery Task | Completed |

## Хүлээгдэж буй үр дүн

Хүргэлтийн даалгавар, буцаан татах даалгавар болон буцаан татах захиалга **Completed** төлөвтэй байна. Нэг сав төлөвлөж, нэг сав татан авч, нэг сав хүргэсэн байна.

Дараагийн шалгалт: [Store App-ийн хүлээн авалт ба үнэлгээ](store-app.md).

## Анхаарах зүйл

Энэ тестийн Pickup нь **сав буцаан татах** ажиллагаа. Бараа буцаах ажиллагааг тестлээгүй.

Тестэд DP-032 → DP-031 дарааллаар хүргэлт гүйцэтгэсэн. Төлөвлөлтийн дараалалтай ялгаатай харагдсан ажиглалтыг бүх даалгаварт үйлчлэх дүрэм гэж тайлбарлахгүй.

Туршилтын үр дүнд бодит явсан зай **0 km** хэвээр бүртгэгдсэн. Шалтгааныг энэ тестээр тогтоогоогүй.
