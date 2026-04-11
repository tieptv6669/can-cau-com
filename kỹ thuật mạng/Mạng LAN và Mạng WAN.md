# Mạng LAN và Mạng WAN

**Mạng LAN** và **Mạng WAN** đều là các loại mạng máy tính, nhưng chúng khác nhau chủ yếu ở **phạm vi, tốc độ, chi phí và cách quản lý**. Dưới đây là bảng so sánh dễ hiểu:

| Tiêu chí               | **LAN (Local Area Network)**                       | **WAN (Wide Area Network)**                      |
| ---------------------- | -------------------------------------------------- | ------------------------------------------------ |
| **Phạm vi**            | Nhỏ, trong một phòng, tòa nhà, trường học, công ty | Rất lớn, có thể giữa các thành phố hoặc quốc gia |
| **Ví dụ**              | Mạng trong quán net, văn phòng                     | Internet là mạng WAN lớn nhất                    |
| **Tốc độ**             | Nhanh (thường 100 Mbps → vài Gbps)                 | Chậm hơn LAN do khoảng cách xa                   |
| **Chi phí**            | Thấp, dễ lắp đặt                                   | Cao hơn vì cần hạ tầng lớn                       |
| **Quản lý**            | Thường do một tổ chức quản lý                      | Có thể do nhiều nhà cung cấp mạng quản lý        |
| **Độ trễ (latency)**   | Thấp                                               | Cao hơn                                          |
| **Công nghệ phổ biến** | Ethernet, Wi-Fi                                    | MPLS, cáp quang đường dài, vệ tinh               |

### Ví dụ dễ hiểu

* **LAN**: Các máy tính trong **một văn phòng** kết nối với nhau qua router hoặc switch.
* **WAN**: Khi văn phòng ở **Hà Nội kết nối với chi nhánh ở TP.HCM** qua Internet.

### Tóm tắt ngắn gọn

* **LAN** → mạng **nhỏ, nhanh, nội bộ**.
* **WAN** → mạng **rộng, kết nối nhiều LAN lại với nhau**.

✅ Có thể hiểu đơn giản:
**WAN = nhiều LAN kết nối lại với nhau.**

---

Nếu bạn muốn, tôi có thể giải thích thêm:

* **Sơ đồ minh họa LAN vs WAN (rất dễ hiểu)**
* **So sánh LAN – MAN – WAN**
* **Thiết bị dùng trong LAN và WAN**.

---

Để hiểu **sự khác nhau giữa LAN và WAN**, cách tốt nhất là nhìn vào **sơ đồ kết nối của chúng**. Ta tưởng tượng theo 2 bước đơn giản sau.

---

## 1. Sơ đồ của mạng LAN (mạng nội bộ)

```
 Máy tính 1
      │
 Máy tính 2 ─── Switch/Router ─── Máy tính 3
      │
 Máy in
```

**Giải thích:**

* Tất cả thiết bị (máy tính, máy in…) nằm **trong cùng một khu vực nhỏ**.
* Chúng kết nối với nhau thông qua **switch hoặc router**.
* Dữ liệu truyền **trực tiếp trong mạng nội bộ**, nên **tốc độ rất nhanh**.

📌 Ví dụ thực tế:

* Mạng máy tính trong **một phòng học**
* Mạng trong **văn phòng công ty**
* Mạng trong **quán game**

---

## 2. Sơ đồ của mạng WAN (mạng diện rộng)

```
 LAN (Văn phòng Hà Nội)
        │
        │ Internet / mạng viễn thông
        │
 LAN (Chi nhánh Đà Nẵng)
        │
        │
 LAN (Chi nhánh TP.HCM)
```

**Giải thích:**

* Mỗi văn phòng có **một mạng LAN riêng**.
* Các LAN này được **kết nối với nhau qua Internet hoặc hạ tầng viễn thông**.
* Mạng kết nối trên **khoảng cách rất xa** (thành phố, quốc gia, toàn cầu).

📌 Ví dụ thực tế:

* Công ty có **nhiều chi nhánh ở các tỉnh**
* Hệ thống ngân hàng kết nối **tất cả các chi nhánh**
* **Internet** chính là **WAN lớn nhất thế giới**

---

## 3. Sơ đồ tổng thể LAN nằm trong WAN

```
      [LAN nhà bạn]
            │
            │
        Internet (WAN)
      ┌──────┼──────┐
 [LAN trường học] [LAN công ty] [LAN quán café]
```

👉 Điều quan trọng cần nhớ:

* **LAN = mạng nhỏ trong một địa điểm**
* **WAN = mạng lớn kết nối nhiều LAN lại**

Hay nói ngắn gọn:

**LAN → mạng cục bộ**
**WAN → mạng của nhiều LAN**

---

✅ Nếu bạn muốn, tôi có thể giải thích thêm một số phần rất hay và dễ hiểu:

* **Sơ đồ thiết bị trong LAN (Switch – Router – Access Point)**
* **Tại sao Internet được gọi là WAN**
* **So sánh LAN – MAN – WAN bằng hình minh họa rất dễ nhớ**.

---

Ba loại mạng **LAN – MAN – WAN** khác nhau chủ yếu ở **phạm vi địa lý** và **mục đích sử dụng**. Có thể tưởng tượng chúng giống như **các vòng tròn mở rộng dần**.

---

## 1. LAN (Local Area Network – Mạng cục bộ)

**Phạm vi:** rất nhỏ

* Trong **một phòng**
* **Một tòa nhà**
* **Một trường học hoặc công ty**

**Đặc điểm:**

* Tốc độ **rất nhanh**
* Chi phí **thấp**
* Do **một tổ chức quản lý**

**Ví dụ:**

* Mạng máy tính trong **phòng máy của trường**
* Mạng trong **văn phòng công ty**
* Wi-Fi trong **nhà bạn**

**Sơ đồ đơn giản**

```
Máy tính ──┐
Máy in  ───┼── Switch/Router ─── Internet
Laptop ────┘
```

---

## 2. MAN (Metropolitan Area Network – Mạng đô thị)

**Phạm vi:** **một thành phố hoặc khu đô thị**

MAN được tạo ra khi **nhiều mạng LAN trong thành phố được kết nối lại**.

**Đặc điểm:**

* Phạm vi **lớn hơn LAN**
* Thường do **nhà cung cấp dịch vụ mạng** quản lý
* Dùng **cáp quang tốc độ cao**

**Ví dụ:**

* Hệ thống mạng của **các trường đại học trong cùng một thành phố**
* Mạng kết nối **các cơ quan chính phủ trong một tỉnh**

**Sơ đồ**

```
LAN (Trường A)
      │
      │
LAN (Trường B) ─── Mạng MAN của thành phố ─── LAN (Bệnh viện)
      │
LAN (Cơ quan nhà nước)
```

---

## 3. WAN (Wide Area Network – Mạng diện rộng)

**Phạm vi:**

* **Quốc gia**
* **Châu lục**
* **Toàn thế giới**

WAN kết nối **nhiều MAN và LAN lại với nhau**.

**Đặc điểm:**

* Khoảng cách **rất xa**
* Chi phí **cao**
* Sử dụng nhiều công nghệ: **cáp quang biển, vệ tinh, mạng viễn thông**

**Ví dụ lớn nhất:**
🌍 **Internet**

**Sơ đồ**

```
MAN (Hà Nội)
      │
      │
      ├──── Internet / WAN ──── MAN (Tokyo)
      │
      │
   MAN (Paris)
```

---

## 4. Bảng so sánh nhanh

| Tiêu chí | LAN               | MAN               | WAN                 |
| -------- | ----------------- | ----------------- | ------------------- |
| Phạm vi  | Nhỏ (tòa nhà)     | Thành phố         | Quốc gia / toàn cầu |
| Tốc độ   | Rất cao           | Cao               | Thấp hơn LAN        |
| Quản lý  | Cá nhân / tổ chức | Nhà cung cấp mạng | Nhiều tổ chức       |
| Ví dụ    | Mạng văn phòng    | Mạng đô thị       | Internet            |

---

## 5. Cách nhớ cực dễ

Hãy tưởng tượng **3 vòng tròn lớn dần**:

```
LAN  →  MAN  →  WAN
Nhà   → Thành phố → Thế giới
```

* **LAN** = trong **nhà / tòa nhà**
* **MAN** = trong **thành phố**
* **WAN** = **toàn thế giới**

---

✅ Nếu bạn muốn, tôi có thể giải thích thêm một phần rất quan trọng mà sinh viên IT thường học:

* **Thiết bị dùng trong LAN – MAN – WAN (Router, Switch, Gateway)**
* **Tại sao Internet vừa là WAN nhưng vẫn chứa hàng triệu LAN bên trong**
* **Sơ đồ thực tế của mạng công ty có nhiều chi nhánh** (rất dễ hiểu).

---

Trong mạng **LAN** và **WAN**, các thiết bị mạng có nhiệm vụ **kết nối, điều hướng và truyền dữ liệu** giữa các máy tính. Tuy nhiên, vì phạm vi của hai loại mạng khác nhau nên **thiết bị sử dụng cũng có sự khác biệt**.

---

# 1. Thiết bị thường dùng trong mạng LAN

LAN là mạng **trong phạm vi nhỏ**, nên thiết bị thường đơn giản và chi phí thấp.

### 1. Switch (Bộ chuyển mạch)

**Chức năng:**

* Kết nối nhiều thiết bị trong mạng nội bộ
* Chuyển dữ liệu **đúng đến thiết bị cần nhận**

**Ví dụ:**
Trong văn phòng có 20 máy tính → tất cả cắm dây mạng vào **switch**.

**Sơ đồ**

```
PC1 ─┐
PC2 ─┼── Switch ─── Router ─── Internet
PC3 ─┤
PC4 ─┘
```

---

### 2. Router (Bộ định tuyến)

**Chức năng:**

* Kết nối **mạng LAN với mạng khác** (thường là Internet)
* Xác định **đường đi của dữ liệu**

**Ví dụ:**
Router WiFi trong nhà bạn.

---

### 3. Access Point (Điểm truy cập WiFi)

**Chức năng:**

* Cho phép thiết bị **không dây** kết nối vào mạng LAN.

**Ví dụ:**
Laptop, điện thoại kết nối WiFi của công ty.

---

### 4. Network Interface Card – NIC (Card mạng)

**Chức năng:**

* Cho phép máy tính **kết nối vào mạng**.

Có 2 loại:

* **Ethernet card** (dây mạng)
* **WiFi card**

---

# 2. Thiết bị thường dùng trong mạng WAN

WAN có phạm vi rất lớn nên cần thiết bị **mạnh và phức tạp hơn**.

---

### 1. Router WAN

Router trong WAN thường **công suất lớn hơn** và dùng để:

* Kết nối **nhiều mạng LAN ở các địa điểm khác nhau**
* Điều hướng dữ liệu qua Internet hoặc mạng viễn thông

**Ví dụ:**
Router của nhà mạng hoặc router của doanh nghiệp lớn.

---

### 2. Modem

**Chức năng:**

* Chuyển đổi tín hiệu từ **nhà cung cấp Internet (ISP)** thành tín hiệu mạng cho router.

Ví dụ trong nhà:

```
Internet
   │
 Modem
   │
 Router
   │
 Switch
   │
 Máy tính
```

---

### 3. Gateway

**Chức năng:**

* Kết nối **các mạng dùng giao thức khác nhau**.

Ví dụ:

* Mạng nội bộ công ty ↔ Internet.

---

### 4. Multiplexer / CSU-DSU

Các thiết bị này thường dùng trong **hạ tầng viễn thông** để:

* Kết hợp nhiều tín hiệu truyền dữ liệu
* Quản lý đường truyền WAN tốc độ cao

---

# 3. So sánh thiết bị LAN và WAN

| Tiêu chí          | LAN                          | WAN                        |
| ----------------- | ---------------------------- | -------------------------- |
| Thiết bị phổ biến | Switch, Router, Access Point | Router WAN, Modem, Gateway |
| Phạm vi hoạt động | Nội bộ                       | Liên tỉnh / quốc tế        |
| Độ phức tạp       | Thấp                         | Cao                        |
| Tốc độ xử lý      | Rất nhanh                    | Phụ thuộc đường truyền     |

---

# 4. Ví dụ mạng thực tế của một công ty

```
Chi nhánh Hà Nội (LAN)
 PC ─ Switch ─ Router
                │
                │ Internet (WAN)
                │
 PC ─ Switch ─ Router
Chi nhánh TP.HCM (LAN)
```

👉 Hai **LAN của hai chi nhánh** được kết nối qua **WAN (Internet)**.

---

✅ Nếu bạn muốn, tôi có thể giải thích thêm một phần **rất dễ hiểu nhưng cực kỳ quan trọng trong mạng máy tính**:

* **Hub vs Switch vs Router (3 thiết bị dễ bị nhầm nhất)**
* **Đường đi của một gói dữ liệu từ máy tính của bạn ra Internet**
* **Sơ đồ mạng của một quán net hoặc công ty thực tế** (rất trực quan).

---

Dưới đây là cách hiểu **rõ và dễ hình dung nhất** về **Modem** và **Gateway**, vì hai thiết bị này thường bị nhầm với nhau.

---

# 1. Modem là gì?

**Modem** là thiết bị **chuyển đổi tín hiệu mạng của nhà cung cấp Internet thành tín hiệu mà máy tính hoặc router có thể sử dụng**.

Tên **Modem** viết tắt của:

**MOdulator + DEModulator**

* **Modulator** → chuyển **tín hiệu số thành tín hiệu truyền đi**
* **Demodulator** → chuyển **tín hiệu nhận được thành dữ liệu số**

### Hiểu đơn giản

Modem giống như **phiên dịch viên giữa Internet và mạng nhà bạn**.

---

## Ví dụ thực tế

Trong nhà bạn:

```
Internet (từ nhà mạng)
        │
      Modem
        │
      Router
        │
  Laptop / Điện thoại
```

* **Modem** nhận tín hiệu từ nhà mạng
* **Router** chia Internet cho nhiều thiết bị

---

## Một số loại modem phổ biến

1. **DSL Modem**
   → dùng đường dây điện thoại

2. **Cable Modem**
   → dùng cáp truyền hình

3. **Fiber Modem (ONT)**
   → dùng **cáp quang** (phổ biến hiện nay)

---

# 2. Gateway là gì?

**Gateway** là thiết bị **kết nối hai mạng khác nhau và cho phép chúng giao tiếp với nhau**.

### Hiểu đơn giản

Gateway giống như **cửa ra vào của một mạng**.

Khi dữ liệu muốn **ra ngoài mạng nội bộ**, nó phải đi qua **gateway**.

---

## Ví dụ

Trong mạng gia đình:

```
Laptop
   │
Router (Gateway)
   │
Internet
```

Ở đây:

👉 **Router chính là Gateway của mạng LAN**

---

## Vai trò của Gateway

Gateway có thể:

* kết nối **LAN với Internet**
* chuyển đổi **giao thức mạng**
* kiểm soát **dữ liệu ra vào mạng**

---

# 3. So sánh Modem và Gateway

| Tiêu chí          | Modem                        | Gateway                               |
| ----------------- | ---------------------------- | ------------------------------------- |
| Chức năng chính   | Chuyển đổi tín hiệu Internet | Kết nối hai mạng                      |
| Vị trí trong mạng | Giữa ISP và router           | Cửa ra vào của mạng                   |
| Nhiệm vụ          | Nhận Internet từ nhà mạng    | Cho phép mạng giao tiếp với mạng khác |
| Ví dụ             | Modem cáp quang của nhà mạng | Router trong nhà                      |

---

# 4. Trường hợp đặc biệt (rất phổ biến)

Ngày nay nhiều thiết bị **gộp modem + router + gateway vào một thiết bị**.

Ví dụ:
Thiết bị WiFi của nhà mạng.

```
Internet
   │
 Modem + Router + Gateway
   │
Laptop / Điện thoại
```

👉 Vì vậy nhiều người **không thấy modem riêng**.

---

# 5. Ví dụ thực tế dễ hiểu

Giả sử **nhà bạn là một khu nhà**:

* **Modem** = cổng kết nối **đường Internet từ bên ngoài vào khu nhà**
* **Gateway** = **cổng ra vào của khu nhà**

Tất cả dữ liệu muốn **ra ngoài hoặc vào mạng** đều đi qua **gateway**.

---

✅ Nếu bạn muốn, tôi có thể giải thích thêm một phần **rất thú vị trong mạng máy tính**:

* **Sự khác nhau giữa Hub – Switch – Router – Gateway** (90% người mới học mạng bị nhầm)
* **Quá trình một trang web được tải từ Internet về máy tính của bạn** (rất dễ hiểu).

---

Ba thiết bị **Hub – Switch – Router** đều dùng để **kết nối các thiết bị mạng**, nhưng cách chúng **xử lý và truyền dữ liệu** khác nhau. Hiểu đúng 3 thiết bị này rất quan trọng khi học mạng máy tính.

---

# 1. Hub (Bộ chia mạng)

**Hub** là thiết bị **đơn giản nhất** trong ba loại.

### Cách hoạt động

Khi một máy tính gửi dữ liệu vào Hub, Hub sẽ **phát dữ liệu đó đến tất cả các cổng**.

```text
PC1 gửi dữ liệu → Hub → gửi cho PC2, PC3, PC4 (tất cả)
```

**Sơ đồ**

```
PC1 ─┐
PC2 ─┼── Hub
PC3 ─┤
PC4 ─┘
```

### Đặc điểm

* Không biết **ai là người nhận**
* Gửi dữ liệu **cho mọi thiết bị**
* Dễ gây **xung đột dữ liệu**
* Hiện nay **ít dùng**

📌 Ví dụ: giống như **loa phát thanh** – ai cũng nghe.

---

# 2. Switch (Bộ chuyển mạch)

**Switch** là phiên bản **thông minh hơn Hub**.

### Cách hoạt động

Switch **ghi nhớ địa chỉ MAC của từng thiết bị** và chỉ gửi dữ liệu đến **đúng thiết bị cần nhận**.

```text
PC1 gửi dữ liệu cho PC3 → Switch → chỉ gửi cho PC3
```

**Sơ đồ**

```
PC1 ─┐
PC2 ─┼── Switch ── PC3 (nhận dữ liệu)
PC4 ─┘
```

### Đặc điểm

* Truyền dữ liệu **đúng thiết bị**
* **Nhanh hơn Hub**
* Ít xung đột dữ liệu
* Thiết bị **rất phổ biến trong LAN**

📌 Ví dụ: giống như **bưu điện giao thư đúng địa chỉ**.

---

# 3. Router (Bộ định tuyến)

**Router** dùng để **kết nối các mạng khác nhau**.

Ví dụ:

* Mạng **LAN của bạn** kết nối với **Internet**.

### Cách hoạt động

Router **xác định đường đi tốt nhất cho dữ liệu** giữa các mạng.

**Sơ đồ**

```
Máy tính ─ Switch ─ Router ─ Internet
```

### Đặc điểm

* Kết nối **nhiều mạng khác nhau**
* Có thể **cấp địa chỉ IP**
* Thường có **WiFi**
* Là thiết bị **cửa ra Internet**

📌 Ví dụ: giống như **bản đồ giao thông chọn đường đi nhanh nhất**.

---

# 4. So sánh nhanh Hub – Switch – Router

| Tiêu chí          | Hub            | Switch            | Router                        |
| ----------------- | -------------- | ----------------- | ----------------------------- |
| Mức độ thông minh | Thấp           | Trung bình        | Cao                           |
| Cách gửi dữ liệu  | Gửi cho tất cả | Gửi đúng thiết bị | Chọn đường giữa các mạng      |
| Phạm vi           | LAN            | LAN               | LAN ↔ WAN                     |
| Tốc độ            | Chậm           | Nhanh             | Phụ thuộc mạng                |
| Sử dụng hiện nay  | Ít             | Rất phổ biến      | Bắt buộc khi kết nối Internet |

---

# 5. Sơ đồ mạng thực tế

```
PC1
PC2 ── Switch ── Router ── Internet
PC3
```

* **Switch**: kết nối các máy trong mạng nội bộ
* **Router**: kết nối mạng nội bộ với Internet

---

# 6. Cách nhớ cực nhanh

* **Hub** → chia dữ liệu **cho tất cả**
* **Switch** → gửi dữ liệu **đúng máy**
* **Router** → tìm **đường đi giữa các mạng**

Hoặc nhớ câu:

**Hub chia – Switch chọn – Router định tuyến**

---

✅ Nếu bạn muốn, tôi có thể giải thích thêm một phần **rất quan trọng khi học mạng**:

* **Địa chỉ IP vs địa chỉ MAC (Switch và Router dùng cái nào?)**
* **Quá trình một gói dữ liệu đi từ máy tính của bạn tới một website** (cực dễ hiểu).
