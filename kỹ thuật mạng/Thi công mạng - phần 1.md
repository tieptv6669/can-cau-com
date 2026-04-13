Để **cắm mạng LAN cho nhiều máy tính**, bạn cần tạo một **mạng nội bộ (LAN)** bằng **router hoặc switch**. Dưới đây là các cách phổ biến và dễ làm nhất. 🔌💻

---

## 1️⃣ Cách phổ biến nhất: Dùng Router + dây LAN

**Thiết bị cần:**

* 1 **Wi‑Fi Router**
* Nhiều dây **Ethernet Cable** (dây LAN)
* Máy tính

**Sơ đồ kết nối:**

```
Internet
   │
Modem
   │
Router
 ├── PC 1
 ├── PC 2
 ├── PC 3
 └── PC 4
```

**Cách làm:**

1. Cắm dây mạng từ **modem → cổng WAN của router**.
2. Cắm dây LAN từ **cổng LAN của router → từng máy tính**.
3. Máy tính sẽ **tự nhận IP** và dùng mạng ngay.

✅ Ưu điểm:

* Dễ cài đặt
* Có internet cho tất cả máy
* Có WiFi luôn

---

## 2️⃣ Dùng Switch để chia mạng nhiều máy

Nếu router **không đủ cổng LAN**, bạn dùng thêm **Network Switch**.

**Sơ đồ:**

```
Router
   │
Switch
 ├── PC 1
 ├── PC 2
 ├── PC 3
 ├── PC 4
 └── PC 5
```

**Cách làm:**

1. Cắm dây từ **router → switch**.
2. Cắm dây từ **switch → các máy tính**.

✅ Có thể chia mạng cho **10 – 20 – 50 máy** tùy loại switch.

---

## 3️⃣ Kết nối LAN trực tiếp giữa 2 máy

Nếu chỉ có **2 máy**, có thể cắm trực tiếp bằng **Ethernet Cable**.

**Sơ đồ:**

```
PC 1 ───── PC 2
```

Sau đó:

* đặt IP thủ công (ví dụ)

| Máy | IP          |
| --- | ----------- |
| PC1 | 192.168.1.1 |
| PC2 | 192.168.1.2 |

---

💡 **Ví dụ thực tế:**

* Phòng game 🎮
* Văn phòng 🏢
* Phòng máy trường học 🏫

→ thường dùng **Router + Switch + dây LAN**.

---

✅ **Nếu bạn muốn mình hướng dẫn chi tiết hơn:**

* Cách **bấm dây mạng LAN**
* Cách **chia mạng cho 10–50 máy**
* Cách **chia sẻ file giữa các máy trong LAN**

Mình có thể vẽ **sơ đồ cực dễ hiểu** cho bạn.

---

Để **sử dụng tất cả các chuẩn dây mạng LAN**, bạn cần hiểu 3 phần chính:
1️⃣ Chuẩn **dây mạng (Cat)**
2️⃣ Chuẩn **bấm dây (T568A / T568B)**
3️⃣ Chuẩn **kết nối (thẳng / chéo)**

Mình sẽ dạy theo cách **từ cơ bản → chuyên nghiệp**, giống như học nghề mạng. 🔧💻

---

# 1️⃣ Các chuẩn dây mạng (CAT)

Dây mạng thường dùng **Ethernet Cable** và đầu **RJ45 connector**.

| Chuẩn | Tốc độ     | Khoảng cách | Dùng khi          |
| ----- | ---------- | ----------- | ----------------- |
| CAT5  | 100 Mbps   | 100 m       | mạng cũ           |
| CAT5e | 1 Gbps     | 100 m       | phổ biến          |
| CAT6  | 1–10 Gbps  | 55–100 m    | văn phòng         |
| CAT6a | 10 Gbps    | 100 m       | server            |
| CAT7  | 10 Gbps    | 100 m       | trung tâm dữ liệu |
| CAT8  | 25–40 Gbps | 30 m        | datacenter        |

📌 Thực tế thường dùng:

* **CAT5e**
* **CAT6**

---

# 2️⃣ Chuẩn bấm dây mạng

Có 2 chuẩn quốc tế:

* **T568A**
* **T568B**

### Chuẩn T568A

Thứ tự dây:

```
1 trắng xanh lá
2 xanh lá
3 trắng cam
4 xanh dương
5 trắng xanh dương
6 cam
7 trắng nâu
8 nâu
```

---

### Chuẩn T568B (phổ biến nhất)

```
1 trắng cam
2 cam
3 trắng xanh lá
4 xanh dương
5 trắng xanh dương
6 xanh lá
7 trắng nâu
8 nâu
```

📌 **95% mạng LAN dùng T568B**

---

# 3️⃣ Các loại dây mạng theo cách bấm

## 1. Dây thẳng (Straight Cable)

Hai đầu **bấm giống nhau**.

Ví dụ:

```
T568B —— T568B
```

Dùng để nối:

* PC → Router
* PC → Switch
* Router → Switch

Thiết bị mạng như:

* **Network Switch**
* **Wi‑Fi Router**

---

## 2. Dây chéo (Crossover Cable)

Hai đầu **khác chuẩn**:

```
T568A —— T568B
```

Dùng để nối:

* PC ↔ PC
* Switch ↔ Switch
* Router ↔ Router

📌 Nhưng **thiết bị mới tự đảo dây** nên ít dùng.

---

# 4️⃣ Dụng cụ bấm dây mạng

Bạn cần:

* **RJ45 Crimping Tool** (kìm bấm mạng)
* **RJ45 connector**
* **Ethernet Cable**

---

# 5️⃣ Quy trình bấm dây mạng chuẩn

### Bước 1

Cắt vỏ dây khoảng **2 cm**

### Bước 2

Duỗi thẳng 8 sợi dây

### Bước 3

Sắp xếp theo chuẩn **T568B**

```
trắng cam
cam
trắng xanh lá
xanh dương
trắng xanh dương
xanh lá
trắng nâu
nâu
```

### Bước 4

Cắt cho đều

### Bước 5

Đưa vào đầu **RJ45**

### Bước 6

Dùng kìm bấm chặt

---

# 6️⃣ Cách kiểm tra dây mạng

Dùng thiết bị:

* **LAN Cable Tester**

Nó sẽ kiểm tra:

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

Nếu sai → dây bị lỗi.

---

# 7️⃣ Các lỗi bấm dây mạng phổ biến

❌ sai thứ tự dây
❌ dây không chạm chân đồng
❌ dây quá ngắn
❌ dây bị gập

---

# 8️⃣ Sơ đồ mạng LAN cơ bản

```
Internet
   │
Modem
   │
Router
   │
Switch
 ├── PC1
 ├── PC2
 ├── PC3
 └── PC4
```

---

✅ Nếu bạn muốn **học như kỹ thuật viên mạng**, mình có thể dạy tiếp:

* **cách bấm dây mạng nhanh trong 30 giây**
* **cách đi dây mạng cho cả tòa nhà**
* **cách làm phòng net 50–100 máy**
* **cách cấu hình mạng LAN chuyên nghiệp**

Mình cũng có thể gửi **sơ đồ bấm dây mạng cực dễ nhớ (nhìn 1 lần nhớ luôn)**.

---

Đi **dây mạng cho cả tòa nhà** (văn phòng, chung cư, trường học…) cần làm theo mô hình mạng chuẩn để dễ quản lý và ổn định. Mình sẽ hướng dẫn theo cách **kỹ thuật viên mạng thường làm**. 🏢🔧

---

# 1️⃣ Nguyên tắc mạng cho tòa nhà

Mô hình chuẩn gọi là **mạng hình sao (Star Topology)** với thiết bị trung tâm như **Network Switch**.

Sơ đồ tổng thể:

```
Internet
   │
Modem
   │
Router
   │
Core Switch (tủ mạng trung tâm)
   │
 ├── Switch tầng 1
 │    ├── Phòng 101
 │    ├── Phòng 102
 │
 ├── Switch tầng 2
 │    ├── Phòng 201
 │    ├── Phòng 202
 │
 └── Switch tầng 3
      ├── Phòng 301
      └── Phòng 302
```

Thiết bị thường dùng:

* **Wi‑Fi Router**
* **Network Switch**
* **Cat6 Ethernet Cable**
* **RJ45 connector**

---

# 2️⃣ Chia hệ thống mạng theo tầng

Mỗi tầng nên có:

* 1 **switch tầng**
* dây mạng đi tới từng phòng

Ví dụ:

```
Tầng 2

Switch tầng
   │
 ├── PC phòng 201
 ├── PC phòng 202
 ├── Camera
 └── Wifi
```

---

# 3️⃣ Tủ mạng trung tâm (Server Room)

Tòa nhà cần một **tủ mạng trung tâm**.

Bên trong thường có:

* modem internet
* router
* **core switch**
* **patch panel**

Thiết bị:

* **Patch Panel**

Patch panel giúp:

* quản lý dây
* sửa chữa dễ
* gọn gàng

---

# 4️⃣ Các bước đi dây mạng

## Bước 1: Khảo sát tòa nhà

Xác định:

* số tầng
* số phòng
* vị trí tủ mạng

Ví dụ:

```
5 tầng
10 phòng / tầng
→ 50 điểm mạng
```

---

## Bước 2: Chọn loại dây

Khuyên dùng:

* **Cat6 Ethernet Cable**

Ưu điểm:

* 1–10 Gbps
* chống nhiễu tốt
* dùng lâu dài

---

## Bước 3: Đi ống hoặc máng cáp

Dây mạng nên đi trong:

* **máng cáp**
* **ống gen**
* **ống PVC**

Tránh:

❌ đi chung với dây điện
❌ bị gập mạnh

---

## Bước 4: Kéo dây từ tủ mạng đến phòng

Ví dụ:

```
Tủ mạng
  │
  ├── Phòng 101
  ├── Phòng 102
  ├── Phòng 201
  └── Phòng 202
```

Mỗi phòng:

* ít nhất **1–2 cổng mạng**

---

## Bước 5: Lắp ổ cắm mạng

Ở phòng sẽ lắp:

* **RJ45 Wall Socket**

Sơ đồ:

```
Dây trong tường
      │
Wall socket
      │
PC
```

---

# 5️⃣ Giới hạn chiều dài dây mạng

Chuẩn Ethernet:

```
tối đa 100 mét
```

Nếu xa hơn:

* dùng **switch trung gian**
* hoặc **cáp quang**

Thiết bị:

* **Fiber Optic Cable**

---

# 6️⃣ Cách đánh số dây mạng

Rất quan trọng khi đi nhiều dây.

Ví dụ:

```
T1-01  (tầng 1 phòng 01)
T1-02
T2-01
T2-02
```

Dán nhãn ở:

* patch panel
* dây
* ổ mạng

---

# 7️⃣ Ví dụ mạng cho tòa nhà 5 tầng

```
Internet
   │
Router
   │
Core Switch
   │
 ├── Switch tầng 1
 ├── Switch tầng 2
 ├── Switch tầng 3
 ├── Switch tầng 4
 └── Switch tầng 5
```

Mỗi tầng:

```
Switch tầng
 ├── PC
 ├── Camera
 ├── Printer
 └── Wifi
```

---

# 8️⃣ Các lỗi phổ biến khi đi dây tòa nhà

❌ dây quá dài
❌ không đánh số dây
❌ đi chung dây điện
❌ không có tủ mạng

---

✅ Nếu bạn muốn, mình có thể dạy thêm:

* **cách thiết kế mạng cho tòa nhà 10 tầng**
* **cách đi dây mạng + camera + wifi cùng lúc**
* **sơ đồ mạng chuẩn của khách sạn / phòng net**
* **cách đi dây mạng 100–500 máy (cực chuyên nghiệp)**.
