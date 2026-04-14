Mình sẽ hướng dẫn theo **tư duy mạng cơ bản + cách cấu hình thực tế (Cisco phổ biến)** để bạn dễ hiểu và áp dụng.

---

# 1. Gán IP cho Router

Router thường được gán IP cho **interface (cổng mạng)** để giao tiếp với các mạng khác.

### Ví dụ

Router nối với mạng LAN `192.168.1.0`

* IP router: `192.168.1.1`
* Subnet mask: `255.255.255.0`

### Cấu hình trên router Cisco

```
enable
configure terminal

interface gigabitEthernet0/0
ip address 192.168.1.1 255.255.255.0
no shutdown

exit
```

### Giải thích

* `interface g0/0` → chọn cổng
* `ip address` → gán IP
* `no shutdown` → bật cổng

Router sẽ trở thành **gateway của mạng LAN**.

---

# 2. Gán IP cho Switch Layer 3

Switch layer 3 có thể hoạt động như router và gán IP cho **VLAN interface (SVI)**.

### Ví dụ

VLAN 10 mạng `192.168.10.0`

IP gateway VLAN:

```
192.168.10.1
```

### Cấu hình

```
enable
configure terminal

interface vlan 10
ip address 192.168.10.1 255.255.255.0
no shutdown
```

Sau đó bật routing:

```
ip routing
```

### Nếu muốn gán port vào VLAN

```
interface fastEthernet0/1
switchport mode access
switchport access vlan 10
```

---

# 3. Đặt Subnet Mask

Subnet mask xác định **phạm vi mạng**.

Ví dụ phổ biến:

| Network | Subnet Mask     | Số host |
| ------- | --------------- | ------- |
| /24     | 255.255.255.0   | 254     |
| /25     | 255.255.255.128 | 126     |
| /26     | 255.255.255.192 | 62      |
| /27     | 255.255.255.224 | 30      |

### Ví dụ cấu hình

```
ip address 192.168.1.1 255.255.255.0
```

Hoặc dạng CIDR

```
192.168.1.1/24
```

---

# 4. Cấu hình Gateway

Gateway là **địa chỉ router để đi ra mạng khác (internet)**.

### Ví dụ

PC:

```
IP: 192.168.1.10
Subnet: 255.255.255.0
Gateway: 192.168.1.1
```

### Trên Switch layer 2

```
ip default-gateway 192.168.1.1
```

### Trên Router

Router dùng **default route**

```
ip route 0.0.0.0 0.0.0.0 192.168.1.254
```

---

# 5. Ví dụ mạng hoàn chỉnh

```
Internet
   |
Router
IP: 192.168.1.1
   |
Switch L3
VLAN10: 192.168.10.1
   |
PC
IP: 192.168.10.10
Gateway: 192.168.10.1
```

---

# 6. Các lệnh kiểm tra

### Kiểm tra IP interface

```
show ip interface brief
```

### Kiểm tra routing

```
show ip route
```

### Ping thử

```
ping 192.168.1.1
```

---

💡 Nếu bạn muốn, mình có thể dạy thêm:

* **Cách chia subnet cực nhanh trong 30 giây (network engineer nào cũng dùng)**
* **Cấu hình VLAN + Inter VLAN routing trên switch layer 3**
* **Mô hình mạng doanh nghiệp hoàn chỉnh (Router + Switch + DHCP + NAT + Internet)**

Mình có thể vẽ **sơ đồ mạng trực quan rất dễ hiểu** cho bạn.

---

Mình sẽ giải thích theo **logic hoạt động của mạng**, để bạn hiểu bản chất chứ không chỉ nhớ lệnh.

---

# 1. Gán port vào VLAN để làm gì?

**VLAN (Virtual LAN)** dùng để **chia 1 switch vật lý thành nhiều mạng logic khác nhau**.

Khi bạn **gán port vào VLAN**, bạn đang nói rằng:

> Thiết bị cắm vào port đó sẽ thuộc mạng nào.

### Ví dụ

Switch có 24 port.

Ta chia thành 2 VLAN:

| VLAN    | Phòng ban | Port  |
| ------- | --------- | ----- |
| VLAN 10 | Kế toán   | 1–10  |
| VLAN 20 | Kỹ thuật  | 11–20 |

Cấu hình:

```
interface fastEthernet0/1
switchport mode access
switchport access vlan 10
```

→ Máy tính cắm vào **port 1** sẽ thuộc **mạng VLAN 10**.

### Lợi ích của VLAN

1️⃣ **Tăng bảo mật**
Máy VLAN 10 không thể truy cập VLAN 20.

2️⃣ **Giảm broadcast**

3️⃣ **Quản lý mạng dễ hơn**

4️⃣ **Chia mạng theo phòng ban**

---

# 2. Đặt Subnet Mask ở thiết bị nào?

Subnet Mask được đặt ở **thiết bị có IP**.

### Các thiết bị cần Subnet Mask

| Thiết bị         | Có cần subnet mask       |
| ---------------- | ------------------------ |
| PC               | ✅ Có                     |
| Server           | ✅ Có                     |
| Router interface | ✅ Có                     |
| Switch layer 3   | ✅ Có                     |
| Switch layer 2   | ❌ Không (trừ IP quản lý) |

---

### Ví dụ

PC:

```
IP address: 192.168.1.10
Subnet mask: 255.255.255.0
Gateway: 192.168.1.1
```

Router:

```
interface g0/0
ip address 192.168.1.1 255.255.255.0
```

Switch layer 3:

```
interface vlan 10
ip address 192.168.10.1 255.255.255.0
```

---

# 3. Switch Layer 2 và Switch Layer 3 khác nhau như thế nào?

Đây là kiến thức rất quan trọng trong mạng.

| Đặc điểm          | Switch Layer 2 | Switch Layer 3            |
| ----------------- | -------------- | ------------------------- |
| Hoạt động theo    | MAC address    | IP address                |
| Chức năng         | Switching      | Switching + Routing       |
| Routing giữa VLAN | ❌ Không        | ✅ Có                      |
| Bảng sử dụng      | MAC table      | MAC table + Routing table |
| Tốc độ            | Rất nhanh      | Nhanh                     |

---

## Switch Layer 2

Chỉ **chuyển frame trong cùng mạng**.

Ví dụ:

```
PC1 → Switch → PC2
```

Switch đọc **MAC address** để gửi dữ liệu.

Không thể định tuyến giữa VLAN.

---

## Switch Layer 3

Switch layer 3 có thêm **routing giống router**.

Ví dụ:

```
VLAN10 → Switch L3 → VLAN20
```

Switch L3 sẽ routing giữa các VLAN.

Phải bật:

```
ip routing
```

---

# Ví dụ mạng thực tế

```
          Router
             |
        Switch Layer 3
        |            |
     VLAN10       VLAN20
    (Kế toán)     (IT)
```

Switch L3 sẽ cho phép:

```
VLAN10 ↔ VLAN20
```

---

# Tóm tắt cực dễ nhớ

**Gán port vào VLAN**

→ để xác định thiết bị thuộc mạng nào.

**Subnet mask**

→ đặt ở tất cả thiết bị có IP.

**Switch L2**

→ chỉ chuyển dữ liệu trong cùng mạng.

**Switch L3**

→ có thể định tuyến giữa các mạng.

---

💡 Nếu bạn muốn mình có thể giải thích thêm một số thứ **rất quan trọng trong mạng mà nhiều người mới học hay nhầm**:

* **Sự khác nhau giữa Hub – Switch – Router**
* **Access port vs Trunk port**
* **Broadcast domain vs Collision domain**
* **Tại sao VLAN phải cần router hoặc switch layer 3 để liên lạc**

Mình có thể giải thích bằng **sơ đồ mạng cực dễ hiểu (10 phút là nắm được)**.

---

Câu trả lời ngắn gọn: **Có thể cấu hình bằng UI hoặc CLI**, **không bắt buộc phải CLI**, nhưng trong thực tế **kỹ sư mạng thường dùng CLI nhiều hơn**.

Mình sẽ giải thích rõ từng trường hợp.

---

# 1. Cấu hình Router / Switch bằng UI (Web Interface)

Nhiều thiết bị mạng cho phép cấu hình qua **giao diện web (GUI)** giống như cấu hình modem wifi ở nhà.

### Ví dụ

Các hãng thường có giao diện web:

* TP-Link
* MikroTik
* Ubiquiti

Bạn chỉ cần:

1️⃣ Mở trình duyệt
2️⃣ Nhập IP thiết bị

```
http://192.168.1.1
```

3️⃣ Đăng nhập
4️⃣ Cấu hình bằng menu

### Ví dụ cấu hình trong UI

* VLAN
* IP address
* DHCP
* NAT
* Routing

👉 Phù hợp cho:

* Người mới học mạng
* Quản trị mạng nhỏ
* Router gia đình / doanh nghiệp nhỏ

---

# 2. Cấu hình bằng CLI (Command Line)

CLI là cách cấu hình bằng **lệnh trong terminal**.

Đây là cách phổ biến khi dùng thiết bị của:

* Cisco
* Juniper Networks
* Huawei

Ví dụ cấu hình IP:

```
enable
configure terminal
interface g0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
```

---

# 3. Vì sao kỹ sư mạng thích CLI hơn?

Trong hệ thống lớn, **CLI mạnh hơn GUI**.

### 1️⃣ Cấu hình nhanh

CLI:

```
interface range g0/1-24
switchport access vlan 10
```

→ cấu hình **24 port cùng lúc**

---

### 2️⃣ Tự động hóa

CLI có thể dùng với:

* Script
* Automation
* Ansible
* Python

---

### 3️⃣ GUI đôi khi không có đủ tính năng

Một số tính năng nâng cao chỉ có trong CLI.

---

### 4️⃣ Xử lý sự cố nhanh

Kỹ sư mạng thường dùng:

```
show ip route
show interface
show mac address-table
```

---

# 4. Trong thực tế người ta dùng gì?

| Môi trường       | Cách cấu hình |
| ---------------- | ------------- |
| Mạng gia đình    | UI            |
| Doanh nghiệp nhỏ | UI + CLI      |
| Data center      | CLI           |
| ISP              | CLI           |

---

# 5. Cách truy cập CLI của Router / Switch

Có 3 cách phổ biến:

### 1️⃣ Console cable

Kết nối trực tiếp bằng cáp console.

---

### 2️⃣ SSH

```
ssh admin@192.168.1.1
```

---

### 3️⃣ Telnet (ít dùng vì không bảo mật)

```
telnet 192.168.1.1
```

---

# Tóm lại

| Câu hỏi                         | Trả lời  |
| ------------------------------- | -------- |
| Có cấu hình bằng UI được không? | ✅ Có     |
| Có bắt buộc CLI không?          | ❌ Không  |
| Trong hệ thống lớn dùng gì?     | CLI      |
| Người mới nên học gì?           | UI → CLI |

---

💡 Nếu bạn muốn mình có thể chỉ thêm **3 kỹ năng mạng cực quan trọng mà kỹ sư network nào cũng phải biết**:

1️⃣ **Cách đọc bảng routing trong 10 giây**
2️⃣ **Cách debug mạng khi không ping được**
3️⃣ **Cách thiết kế IP + VLAN cho cả công ty**

Những kiến thức này giúp bạn **hiểu mạng nhanh gấp 10 lần so với học từng lệnh riêng lẻ**.

---

Câu hỏi này rất thực tế khi cấu hình mạng 👍. Có **3 cách phổ biến** để biết **cổng vật lý tương ứng với interface nào** trên router/switch.

---

# 1. Xem danh sách interface bằng lệnh

Trên nhiều thiết bị của Cisco, bạn dùng:

```
show ip interface brief
```

Ví dụ kết quả:

```
Interface              IP-Address      Status
GigabitEthernet0/0     192.168.1.1     up
GigabitEthernet0/1     unassigned      down
GigabitEthernet0/2     unassigned      down
```

Ý nghĩa:

| Interface          | Cổng vật lý |
| ------------------ | ----------- |
| GigabitEthernet0/0 | Port 1      |
| GigabitEthernet0/1 | Port 2      |
| GigabitEthernet0/2 | Port 3      |

Thông thường **số cuối cùng chính là số cổng**.

---

# 2. Cắm dây và xem cổng nào “up”

Cách đơn giản nhất trong thực tế.

### Bước 1

Cắm dây mạng vào một port.

### Bước 2

Chạy lệnh:

```
show ip interface brief
```

Hoặc:

```
show interfaces status
```

Cổng nào hiện **up/up** thì đó là cổng đang cắm dây.

Ví dụ:

```
GigabitEthernet0/1   up   up
```

→ dây đang cắm ở **Gi0/1**

---

# 3. Xem trực tiếp trên thiết bị

Trên switch thường có **label in sẵn**:

```
Gi0/1
Gi0/2
Gi0/3
Gi0/4
```

Các port trên mặt switch tương ứng với interface.

---

# 4. Hiểu cấu trúc tên interface

Ví dụ:

```
GigabitEthernet0/1
```

Ý nghĩa:

| Phần            | Ý nghĩa   |
| --------------- | --------- |
| GigabitEthernet | Loại cổng |
| 0               | Slot      |
| 1               | Port      |

---

### Ví dụ khác

```
GigabitEthernet1/0/24
```

| Phần | Ý nghĩa        |
| ---- | -------------- |
| 1    | Module / stack |
| 0    | Slot           |
| 24   | Port           |

---

# 5. Dùng lệnh CDP / LLDP để biết thiết bị kết nối

Nếu switch nối với switch khác, dùng:

```
show cdp neighbors
```

hoặc

```
show lldp neighbors
```

Bạn sẽ thấy:

```
Device ID      Local Interface
Switch-B       Gi0/1
```

→ thiết bị kia nối vào **Gi0/1**

---

# 6. Cách chuyên gia network xác định port nhanh

Trong thực tế họ thường làm:

1️⃣ Cắm dây
2️⃣ Chạy lệnh

```
show interface status
```

3️⃣ Port nào **up** → đó là port đang dùng

Cách này mất **2–3 giây**.

---

✅ **Tóm lại**

Có 3 cách xác định interface:

1. `show ip interface brief`
2. Cắm dây và xem port nào **up**
3. Nhìn label trên switch

---

💡 Nếu bạn muốn, mình có thể chỉ thêm một kỹ năng rất hay mà **kỹ sư mạng dùng hàng ngày**:

**Cách tìm chính xác máy tính đang cắm ở cổng switch nào trong 10 giây**
(dùng MAC address + bảng MAC của switch).

Đây là kỹ thuật **network admin dùng để truy ra máy gây lỗi hoặc máy đang dùng mạng trái phép.**
