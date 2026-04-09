Dưới đây là **bản tổng hợp toàn bộ nội dung chúng ta đã trao đổi** về mạng LAN, truyền file và các công cụ. Mình sắp xếp lại theo **từng chủ đề rõ ràng** để bạn dễ lưu lại và đọc lại khi cần. 📚

---

# 1. Hai máy nối bằng dây mạng có tạo thành LAN không?

✅ **Có.**

Chỉ cần:

* 2 máy tính
* 1 dây mạng Ethernet (RJ45)

Sơ đồ:

```
Máy A ───────── Máy B
```

Điều kiện:

* Hai máy đặt **IP cùng lớp mạng**

Ví dụ:

| Máy   | IP          | Subnet        |
| ----- | ----------- | ------------- |
| Máy A | 192.168.1.1 | 255.255.255.0 |
| Máy B | 192.168.1.2 | 255.255.255.0 |

Sau khi kết nối có thể:

* chia sẻ file
* chơi game LAN
* remote desktop
* chia sẻ máy in

---

# 2. Nếu 3–4 máy thì nối dây kiểu gì?

Không thể **nối dây kiểu bắc cầu** trực tiếp.

Ethernet cần **thiết bị trung tâm**.

### Cách chuẩn

Dùng **switch hoặc router**.

Sơ đồ:

```
        ┌── Máy 1
        │
Máy 2 ──┼── Switch ── Máy 3
        │
        └── Máy 4
```

Thiết bị ví dụ:

* TP-Link TL-SG105
* TP-Link TL-SF1005D

Switch 5 cổng rất rẻ và ổn định.

---

# 3. Tốc độ truyền file trong LAN

Nếu dùng **Gigabit LAN**

| Kết nối   | Tốc độ      |
| --------- | ----------- |
| USB 2.0   | 20–30 MB/s  |
| USB 3.0   | 80–150 MB/s |
| LAN 1Gbps | 80–110 MB/s |

Vì vậy **LAN thường nhanh hơn USB 2.0 10–20 lần**.

---

# 4. Các cách truyền file trong mạng LAN

## Cách 1 — Windows File Sharing (SMB)

Bật:

* Network Discovery
* File Sharing

Truy cập:

```
\\192.168.1.10
```

Ưu điểm:

* đơn giản
* không cần phần mềm

---

## Cách 2 — Map Network Drive

Biến thư mục mạng thành ổ đĩa.

Ví dụ:

```
\\192.168.1.10\Data
```

Sau đó nó xuất hiện như **ổ cứng bình thường**.

---

## Cách 3 — Phần mềm truyền file LAN

Ví dụ:

* Feem
* LAN Share
* Send Anywhere

Chỉ cần **kéo thả file**.

---

## Cách 4 — FTP Server (ổn định cho file lớn)

Dùng:

* FileZilla Server
* FileZilla Client

### Quy trình

1. Cài server
2. Tạo user
3. Chọn thư mục chia sẻ
4. Máy khác kết nối

Ví dụ:

```
Host: 192.168.1.10
Username: lan
Password: 123456
Port: 21
```

Giao diện có 2 bên:

```
Trái  = máy bạn
Phải = máy server
```

Kéo file để truyền.

---

# 5. Một máy vừa là client vừa là server được không?

✅ **Được.**

Một máy có thể:

```
vừa cung cấp dữ liệu (server)
vừa nhận dữ liệu (client)
```

Ví dụ:

Máy A

```
FileZilla Server
FileZilla Client
```

Điều này rất phổ biến trong mạng.

---

# 6. Truyền file tự động bằng Syncthing

Phần mềm:

* Syncthing

Đây là hệ thống **peer-to-peer**.

Không cần server trung tâm.

---

## Cách dùng Syncthing

### Bước 1

Cài Syncthing trên các máy.

Mở giao diện:

```
http://127.0.0.1:8384
```

---

### Bước 2

Lấy **Device ID**

Ví dụ:

```
ABCD123-EFGH456-IJKL789
```

---

### Bước 3

Kết nối máy

Add Remote Device.

---

### Bước 4

Tạo thư mục chia sẻ

Ví dụ:

```
D:\Share
```

---

### Bước 5

Máy kia Accept.

---

### Bước 6

File tự đồng bộ.

Ví dụ:

```
Máy A: D:\Share
Máy B: D:\Receive
```

Nếu thêm file ở A → B nhận ngay.

---

# 7. Mạng Syncthing kiểu Mesh

Ví dụ 4 máy:

```
A
B
C
D
```

Kết nối:

```
A ↔ B
A ↔ C
A ↔ D
B ↔ C
B ↔ D
C ↔ D
```

Ưu điểm:

* tốc độ cao
* không cần server
* truyền song song

---

# 8. Mẹo để truyền file nhanh nhất

1️⃣ Dùng **cáp Cat6**
2️⃣ Dùng **switch gigabit**
3️⃣ Truyền **file lớn thay vì nhiều file nhỏ**
4️⃣ Nén file trước khi gửi

---

# 9. Kiến thức quan trọng rút ra

### LAN nhỏ

```
2 máy → nối trực tiếp
```

### LAN nhiều máy

```
3+ máy → cần switch
```

### Truyền file nhanh

Ưu tiên:

```
Syncthing
SMB
FTP
```

---

# 10. Kiến trúc mạng đơn giản

### Mạng LAN phổ biến

```
        Router/Switch
        │ │ │ │
        A B C D
```

### Mesh (Syncthing)

```
A ↔ B
↕   ↕
C ↔ D
```

---

💡 Nếu bạn muốn, mình có thể **viết lại bản tài liệu hoàn chỉnh hơn (~10–15 trang)** gồm:

* sơ đồ mạng LAN
* cách cấu hình IP
* cách build NAS trong mạng
* cách truyền file **300–900MB/s**

để bạn **lưu làm tài liệu học mạng máy tính cơ bản**.
