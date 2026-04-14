Trong **kỹ thuật mạng máy tính**, **ổ mạng** thường được hiểu là **ổ cắm mạng (network outlet / LAN outlet)** – điểm kết nối để cắm dây mạng từ thiết bị (máy tính, camera, wifi…) vào hệ thống mạng nội bộ.

Nó thường nằm **trên tường, sàn, hoặc trong hộp âm tường**, giống như ổ điện nhưng dùng cho **dây mạng RJ45**.

---

## 1. Ổ mạng là gì?

**Ổ mạng** là thiết bị đầu cuối của hệ thống cáp mạng, dùng để **kết nối thiết bị với mạng LAN thông qua dây Ethernet**.

Thành phần của một ổ mạng thường gồm:

* **Mặt ổ mạng (Faceplate)** – tấm nhựa gắn trên tường
* **Nhân mạng / Keystone Jack** – nơi bấm dây mạng vào
* **Cổng RJ45** – chỗ cắm dây mạng
* **Hộp âm tường hoặc hộp nổi**

Sơ đồ đơn giản:

```
Switch / Router
      │
      │ (dây mạng âm tường)
      │
   Nhân mạng (keystone)
      │
   Ổ mạng trên tường
      │
   Dây LAN
      │
   Máy tính / camera / wifi
```

---

## 2. Các loại ổ mạng phổ biến

### 1️⃣ Ổ mạng âm tường

* Lắp **bên trong tường**
* Thường dùng trong **nhà ở, văn phòng**
* Thẩm mỹ cao

### 2️⃣ Ổ mạng nổi

* Lắp **bên ngoài tường**
* Dùng khi **không đi dây âm tường được**

### 3️⃣ Ổ mạng nhiều cổng

Ví dụ:

* 1 port
* 2 port
* 4 port

Dùng khi một vị trí cần nhiều thiết bị.

---

## 3. Cấu tạo chi tiết của ổ mạng

Một ổ mạng tiêu chuẩn gồm:

| Bộ phận       | Chức năng    |
| ------------- | ------------ |
| Faceplate     | mặt ổ        |
| Keystone Jack | nhân mạng    |
| RJ45 Port     | cổng cắm dây |
| Wall box      | hộp âm       |

**Nhân mạng** là phần quan trọng nhất vì **dây mạng sẽ được bấm trực tiếp vào đây**.

---

## 4. Cách thi công ổ mạng trong thực tế

### Bước 1: Đi dây mạng

Thợ sẽ kéo dây từ **tủ mạng (switch/router)** đến vị trí cần lắp ổ.

Thường dùng:

* Cat5e Ethernet Cable
* Cat6 Ethernet Cable

Dây được đi:

* trong ống ruột gà
* trong ống PVC
* âm tường
* trên trần

---

### Bước 2: Tuốt vỏ dây

Dùng dụng cụ **tuốt dây mạng** để lộ ra 8 sợi dây nhỏ bên trong.

8 dây màu:

```
Trắng cam
Cam
Trắng xanh lá
Xanh lá
Trắng xanh dương
Xanh dương
Trắng nâu
Nâu
```

---

### Bước 3: Bấm dây vào nhân mạng

Dùng **dao bấm mạng (Punch Down Tool)** để gắn dây vào nhân mạng.

Chuẩn phổ biến:

* TIA/EIA‑568A
* TIA/EIA‑568B

Thực tế **568B được dùng nhiều hơn**.

Thứ tự dây **568B**:

```
1  Trắng cam
2  Cam
3  Trắng xanh lá
4  Xanh dương
5  Trắng xanh dương
6  Xanh lá
7  Trắng nâu
8  Nâu
```

---

### Bước 4: Gắn nhân mạng vào mặt ổ

Sau khi bấm dây:

1. Lắp **keystone jack** vào faceplate
2. Bắt vít cố định lên hộp âm tường

---

### Bước 5: Test mạng

Dùng thiết bị test:

* RJ45 Cable Tester

Để kiểm tra:

* dây đúng thứ tự
* có bị đứt dây không
* có đảo dây không

---

## 5. Sơ đồ thi công mạng trong nhà (chuẩn)

```
Internet
   │
Modem / Router
   │
Switch
   │
───────────── dây âm tường ─────────────
   │           │           │
  Ổ mạng      Ổ mạng      Ổ mạng
   │           │           │
PC / TV      Wifi AP      Camera
```

---

## 6. Lỗi thường gặp khi làm ổ mạng

1. **Sai chuẩn màu dây**
2. **Dây không bấm chặt**
3. **Gãy lõi đồng**
4. **Dây bị nhiễu do đi chung điện**
5. **Không test trước khi đóng mặt ổ**

---

✅ **Mẹo của thợ mạng:**

* Luôn dùng **dây Cat6** nếu thi công mới
* Không kéo dây mạng quá **100m**
* Không đi dây mạng song song dây điện lực lâu dài

---

💡 Nếu bạn muốn, tôi có thể giải thích thêm:

* **Cách bấm dây mạng RJ45 chuẩn thợ (rất dễ hiểu)**
* **Cách đi dây mạng cho cả một ngôi nhà chuẩn kỹ thuật**
* **Bộ dụng cụ thi công mạng mà thợ chuyên nghiệp luôn mang theo** (rất thú vị).

---

Khi thi công hệ thống mạng LAN (đi dây, lắp ổ mạng, làm tủ mạng…), thợ chuyên nghiệp thường mang theo **một bộ dụng cụ chuyên dụng**. Bộ này giúp **cắt dây, bấm đầu, kiểm tra tín hiệu và xử lý sự cố** nhanh chóng. Dưới đây là những dụng cụ quan trọng nhất.

---

# 1. Kìm bấm mạng (crimping tool)

RJ45 Crimping Tool

Đây là **dụng cụ quan trọng nhất** của thợ mạng.

### Công dụng

* Bấm đầu mạng **RJ45 connector** vào dây LAN
* Cắt dây mạng
* Tuốt vỏ dây

### Khi dùng

Ví dụ khi làm dây mạng từ:

```
Router → dây LAN → máy tính
```

Thợ sẽ:

1. Sắp xếp 8 sợi dây theo chuẩn
2. Cho vào đầu RJ45
3. Dùng kìm bấm chặt

---

# 2. Dao bấm nhân mạng (Punch Down Tool)

Punch Down Tool

Dùng khi **làm ổ mạng trên tường hoặc patch panel**.

### Công dụng

* Ép dây vào **nhân mạng (keystone jack)**
* Cắt phần dây thừa

### Ví dụ

```
Dây mạng → nhân mạng → ổ mạng trên tường
```

Thợ sẽ dùng **Punch Down Tool** để ấn dây vào rãnh kim loại.

---

# 3. Máy test dây mạng

RJ45 Cable Tester

Sau khi bấm dây, **không test là sai lầm lớn**.

### Máy test giúp kiểm tra:

* dây có bị **đứt không**
* có **đảo dây**
* có **chập dây**

Ví dụ kết quả test:

```
1-1
2-2
3-3
4-4
5-5
6-6
7-7
8-8
```

→ dây đúng chuẩn.

---

# 4. Kìm cắt và tuốt dây

Wire Stripper

Dùng để:

* tuốt vỏ dây mạng
* cắt dây
* chỉnh dây

Nếu dùng dao thường **rất dễ làm đứt lõi đồng**.

---

# 5. Bộ đầu mạng RJ45

RJ45 connector

Đây là **đầu cắm của dây mạng**.

Một thợ mạng thường mang theo:

* vài chục đến vài trăm đầu RJ45

Vì trong quá trình bấm **rất dễ lỗi phải bấm lại**.

---

# 6. Nhân mạng (keystone jack)

Keystone Jack

Dùng để làm **ổ mạng trên tường**.

Chức năng:

```
dây mạng âm tường → keystone → ổ cắm RJ45
```

Thợ thường mang theo nhiều loại:

* Cat5e
* Cat6

---

# 7. Dây mạng dự phòng

Cat6 Ethernet Cable

Thợ thường mang theo **cuộn dây mạng 100m – 305m**.

Dùng để:

* kéo dây mới
* thay dây hỏng
* test mạng

---

# 8. Bộ dò dây mạng (network toner)

Network Cable Toner and Probe

Dụng cụ này **rất quan trọng khi sửa mạng**.

### Công dụng

Giúp tìm dây trong hệ thống phức tạp.

Ví dụ:

```
1 tủ mạng
50 dây mạng
không biết dây nào đi phòng nào
```

Thợ sẽ:

1. cắm toner vào dây
2. dùng đầu dò đi tìm

→ biết dây đi đâu.

---

# 9. Laptop kiểm tra mạng

Laptop computer

Thợ thường dùng laptop để:

* kiểm tra IP
* ping mạng
* test tốc độ
* cấu hình router / switch

Ví dụ lệnh thường dùng:

```
ping 192.168.1.1
ipconfig
```

---

# 10. Bộ tua vít

Screwdriver

Dùng để:

* tháo ổ mạng
* gắn faceplate
* lắp switch

---

# 11. Máy khoan (khi đi dây mới)

Electric Drill

Dùng để:

* khoan tường
* khoan trần
* lắp hộp âm

---

# Bộ đồ nghề đầy đủ của thợ mạng

Một thợ chuyên nghiệp thường có **túi đồ như sau**:

```
Túi thi công mạng
│
├─ Kìm bấm mạng
├─ Punch Down Tool
├─ Máy test dây
├─ Dụng cụ tuốt dây
├─ Đầu RJ45
├─ Keystone Jack
├─ Dây mạng
├─ Network Toner
├─ Tua vít
└─ Laptop
```

---

💡 **Một sự thật thú vị trong nghề mạng:**

> 80% lỗi mạng thực tế không phải do thiết bị mà do **dây mạng bấm sai hoặc tiếp xúc kém**.

---

✅ Nếu bạn muốn, tôi có thể giải thích thêm rất thú vị:

* **Cách bấm dây mạng chuẩn thợ chỉ 30 giây**
* **Sơ đồ hệ thống mạng chuẩn của một tòa nhà**
* **5 lỗi bấm dây mạng mà 90% người mới đều mắc** (thợ nhìn là biết ngay).

