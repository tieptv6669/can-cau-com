Dưới đây là **toàn bộ kiến thức quan trọng mà một Network Technician cần biết** khi cấu hình **DHCP, DNS và NAT**. Mình sẽ dạy theo **logic thực tế của kỹ sư mạng**:
1️⃣ Khái niệm → 2️⃣ Cách hoạt động → 3️⃣ Cấu hình thực tế → 4️⃣ Troubleshooting → 5️⃣ Best Practices.

---

# 1. DHCP (Dynamic Host Configuration Protocol)

## 1.1 DHCP là gì

**DHCP** là giao thức giúp **tự động cấp IP cho thiết bị trong mạng**.

Nếu không có DHCP thì phải **cấu hình IP thủ công** cho từng máy.

DHCP cấp:

* IP address
* Subnet mask
* Default gateway
* DNS server
* Lease time

Ví dụ:

| Thiết bị   | IP           |
| ---------- | ------------ |
| Laptop     | 192.168.1.10 |
| Điện thoại | 192.168.1.11 |
| Máy in     | 192.168.1.12 |

---

## 1.2 Quy trình DHCP (DORA)

DHCP hoạt động theo **4 bước**:

| Bước | Tên         | Ý nghĩa                |
| ---- | ----------- | ---------------------- |
| 1    | Discover    | Client tìm DHCP server |
| 2    | Offer       | Server đề nghị cấp IP  |
| 3    | Request     | Client yêu cầu IP      |
| 4    | Acknowledge | Server xác nhận        |

Quy trình gọi là:

**DORA Process**

```
Client → DHCP Discover → Broadcast
Server → DHCP Offer
Client → DHCP Request
Server → DHCP ACK
```

---

## 1.3 Port DHCP

| Protocol | Port        |
| -------- | ----------- |
| UDP      | 67 (server) |
| UDP      | 68 (client) |

---

## 1.4 DHCP Scope

Scope là **range IP mà DHCP được phép cấp**

Ví dụ:

```
192.168.1.100 → 192.168.1.200
```

---

## 1.5 DHCP Reservation

Gán **IP cố định theo MAC Address**

Ví dụ:

```
MAC: AA:BB:CC:DD:EE:FF
IP: 192.168.1.50
```

Dùng cho:

* Printer
* Server
* Camera

---

## 1.6 DHCP Relay

Nếu **DHCP server ở mạng khác**, router sẽ chuyển tiếp request.

Router đóng vai trò **DHCP Relay Agent**

Cisco:

```
ip helper-address 192.168.10.5
```

---

## 1.7 Cấu hình DHCP trên Cisco

### Bước 1: loại trừ IP

```
ip dhcp excluded-address 192.168.1.1 192.168.1.20
```

---

### Bước 2: tạo DHCP Pool

```
ip dhcp pool LAN
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 8.8.8.8
lease 7
```

---

## 1.8 Lệnh kiểm tra DHCP

```
show ip dhcp binding
show ip dhcp pool
show running-config
```

---

## 1.9 Troubleshoot DHCP

Các lỗi phổ biến:

### Client không nhận IP

Kiểm tra:

```
ipconfig /renew
```

Kiểm tra DHCP server:

```
show ip dhcp binding
```

---

### DHCP scope hết IP

Kiểm tra:

```
show ip dhcp pool
```

---

### DHCP relay sai

Kiểm tra:

```
ip helper-address
```

---

# 2. DNS (Domain Name System)

## 2.1 DNS là gì

DNS là **hệ thống chuyển đổi domain thành IP**

Ví dụ:

```
google.com → 142.250.190.14
```

Nếu không có DNS:

Bạn phải nhớ IP của mọi website.

---

## 2.2 Quy trình DNS

Khi truy cập:

```
www.google.com
```

Quy trình:

```
Client
 ↓
Local DNS
 ↓
Root Server
 ↓
TLD Server (.com)
 ↓
Authoritative DNS
 ↓
IP trả về
```

---

## 2.3 Các loại DNS Server

| Loại              | Chức năng           |
| ----------------- | ------------------- |
| Recursive DNS     | tìm IP thay client  |
| Authoritative DNS | chứa bản ghi domain |
| Caching DNS       | lưu cache           |

---

## 2.4 DNS Record quan trọng

| Record | Chức năng      |
| ------ | -------------- |
| A      | domain → IPv4  |
| AAAA   | domain → IPv6  |
| CNAME  | alias domain   |
| MX     | mail server    |
| NS     | name server    |
| PTR    | reverse lookup |
| TXT    | verification   |

---

## 2.5 Ví dụ DNS Record

```
example.com     A       192.168.1.10
www             CNAME   example.com
mail            MX      mail.example.com
```

---

## 2.6 DNS Port

| Protocol | Port |
| -------- | ---- |
| UDP      | 53   |
| TCP      | 53   |

UDP cho query thường
TCP cho zone transfer

---

## 2.7 Kiểm tra DNS

### Windows

```
nslookup google.com
```

### Linux

```
dig google.com
```

---

## 2.8 DNS Cache

Client sẽ cache DNS.

Xóa cache:

Windows

```
ipconfig /flushdns
```

---

## 2.9 Troubleshoot DNS

### Không resolve domain

Kiểm tra:

```
nslookup google.com
```

Nếu lỗi:

```
DNS server unreachable
```

---

### DNS sai record

Kiểm tra:

```
dig domain.com
```

---

# 3. NAT (Network Address Translation)

## 3.1 NAT là gì

NAT chuyển đổi:

```
Private IP → Public IP
```

Ví dụ:

```
192.168.1.10 → 203.0.113.5
```

Giúp:

* tiết kiệm IPv4
* ẩn IP nội bộ

---

## 3.2 Private IP Range

| Range                         |
| ----------------------------- |
| 10.0.0.0 – 10.255.255.255     |
| 172.16.0.0 – 172.31.255.255   |
| 192.168.0.0 – 192.168.255.255 |

---

## 3.3 Các loại NAT

### Static NAT

1 private IP ↔ 1 public IP

```
192.168.1.10 → 203.0.113.10
```

---

### Dynamic NAT

pool public IP

```
192.168.1.x → 203.0.113.10-20
```

---

### PAT (Port Address Translation)

Còn gọi:

**NAT overload**

Nhiều private IP → 1 public IP

```
192.168.1.10:5000
192.168.1.11:5001
→
203.0.113.5
```

---

## 3.4 Cấu hình NAT trên Cisco

### Bước 1: xác định inside / outside

```
interface g0/0
ip nat inside

interface g0/1
ip nat outside
```

---

### Bước 2: ACL

```
access-list 1 permit 192.168.1.0 0.0.0.255
```

---

### Bước 3: NAT overload

```
ip nat inside source list 1 interface g0/1 overload
```

---

## 3.5 Static NAT

```
ip nat inside source static 192.168.1.10 203.0.113.10
```

---

## 3.6 Port Forwarding

Ví dụ mở web server

```
203.0.113.10:80 → 192.168.1.10:80
```

Cisco

```
ip nat inside source static tcp 192.168.1.10 80 203.0.113.10 80
```

---

## 3.7 Kiểm tra NAT

```
show ip nat translations
show ip nat statistics
```

---

## 3.8 Troubleshoot NAT

### Internet không vào được

Kiểm tra:

```
show ip nat translations
```

---

### NAT table đầy

Kiểm tra:

```
show ip nat statistics
```

---

# 4. Kiến trúc thực tế của mạng doanh nghiệp

```
Internet
   |
Public IP
   |
Firewall
   |
Router (NAT)
   |
Switch
   |
LAN
   |
DHCP Server
DNS Server
Clients
```

---

# 5. Những kỹ năng bắt buộc của Network Technician

Bạn phải biết:

### DHCP

* DHCP scope
* DHCP relay
* lease time
* reservation
* troubleshoot IP conflict

---

### DNS

* DNS record
* nslookup
* dig
* reverse DNS
* DNS propagation

---

### NAT

* Static NAT
* Dynamic NAT
* PAT
* Port forwarding

---

# 6. 10 lỗi phổ biến nhất trong mạng

1️⃣ DHCP scope hết IP
2️⃣ DHCP relay sai
3️⃣ DNS server down
4️⃣ DNS cache lỗi
5️⃣ NAT rule sai
6️⃣ Port forwarding sai
7️⃣ IP conflict
8️⃣ Subnet mask sai
9️⃣ Gateway sai
🔟 Firewall block

---

# 7. Công cụ Network Technician phải biết

| Tool      | Chức năng      |
| --------- | -------------- |
| ping      | test kết nối   |
| tracert   | xem đường đi   |
| nslookup  | kiểm tra DNS   |
| dig       | DNS chuyên sâu |
| ipconfig  | xem IP         |
| netstat   | kiểm tra port  |
| Wireshark | bắt packet     |

---

# Nếu bạn muốn, tôi có thể dạy thêm:

* **Toàn bộ cấu hình mạng từ A → Z như kỹ sư Cisco**
* **Network troubleshooting như chuyên gia**
* **CCNA level networking**
* **cách debug mạng trong doanh nghiệp**
* **phân tích packet bằng Wireshark**

Tôi cũng có thể vẽ cho bạn:

**sơ đồ mạng chuẩn của doanh nghiệp (rất dễ hiểu)**.

---

Mình sẽ giải thích **kỹ và thực tế như cách một Network Engineer triển khai trong doanh nghiệp**. Ba khái niệm này rất quan trọng vì **90% lỗi DHCP trong hệ thống đều liên quan đến chúng**.

---

# 1. DHCP Pool (trái tim của DHCP)

## DHCP Pool là gì

**DHCP Pool** là **tập hợp các địa chỉ IP mà DHCP server được phép cấp phát cho client**.

Hiểu đơn giản:

> DHCP Pool = kho IP để phát cho thiết bị trong mạng.

Ví dụ mạng:

```
Network: 192.168.1.0/24
Subnet mask: 255.255.255.0
```

Tổng IP:

```
192.168.1.0 → 192.168.1.255
```

Nhưng DHCP không cấp hết. Thường chỉ cấp một **range**.

Ví dụ DHCP Pool:

```
192.168.1.100 → 192.168.1.200
```

---

## Ví dụ thực tế

Mạng văn phòng:

| Thiết bị  | IP           |
| --------- | ------------ |
| Router    | 192.168.1.1  |
| Switch    | 192.168.1.2  |
| Server    | 192.168.1.10 |
| Printer   | 192.168.1.20 |
| Client PC | DHCP         |

DHCP Pool có thể là:

```
192.168.1.100 → 192.168.1.250
```

---

## Cấu hình DHCP Pool trên Cisco

```bash
ip dhcp pool LAN
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 8.8.8.8
lease 7
```

Ý nghĩa:

| dòng           | ý nghĩa            |
| -------------- | ------------------ |
| network        | network cấp IP     |
| default-router | gateway cho client |
| dns-server     | DNS client dùng    |
| lease          | thời gian giữ IP   |

---

## DHCP Pool hoạt động thế nào

Khi client gửi **DHCP Discover**

Server sẽ:

1. kiểm tra pool
2. tìm IP chưa dùng
3. gửi Offer

Ví dụ:

```
Laptop mới kết nối
↓
DHCP Discover
↓
Server chọn IP 192.168.1.101
↓
DHCP Offer
```

---

# 2. DHCP Reservation (IP cố định bằng DHCP)

## DHCP Reservation là gì

**DHCP Reservation** là:

> DHCP server luôn cấp **một IP cố định cho một thiết bị dựa trên MAC address**

Khác với Static IP.

| Static IP          | Reservation             |
| ------------------ | ----------------------- |
| config trên client | config trên DHCP server |

---

## Ví dụ thực tế

Printer cần IP cố định.

Printer:

```
MAC: AA:BB:CC:DD:EE:FF
```

Reservation:

```
MAC → 192.168.1.50
```

Khi printer xin IP:

```
DHCP Discover
↓
Server thấy MAC
↓
Server cấp IP 192.168.1.50
```

---

## Vì sao cần DHCP Reservation

Các thiết bị sau cần IP cố định:

| thiết bị | lý do                         |
| -------- | ----------------------------- |
| Printer  | máy tính phải luôn in đúng IP |
| Camera   | NVR phải biết IP              |
| Server   | DNS / Web                     |
| NAS      | lưu trữ                       |

---

## Lợi ích lớn của DHCP Reservation

### 1 Quản lý tập trung

Không cần cấu hình trên từng thiết bị.

### 2 Tránh sai cấu hình

Client luôn lấy đúng IP.

### 3 Dễ thay đổi

Chỉ cần sửa trên DHCP server.

---

## Ví dụ cấu hình Cisco

```bash
ip dhcp pool PRINTER
host 192.168.1.50 255.255.255.0
client-identifier 01AA.BBCC.DDEE.FF
default-router 192.168.1.1
```

---

# 3. DHCP Relay (khi DHCP server khác mạng)

Đây là khái niệm **rất quan trọng trong hệ thống lớn**.

---

## Vấn đề của DHCP

DHCP Discover là **broadcast**.

Broadcast:

```
255.255.255.255
```

Router **không forward broadcast**.

Vì vậy nếu:

```
Client network ≠ DHCP server network
```

→ client sẽ **không tìm được DHCP server**.

---

## Ví dụ hệ thống thật

```
VLAN10: 192.168.10.0/24
VLAN20: 192.168.20.0/24

DHCP Server: 192.168.1.10
```

Topology

```
Client VLAN10
     |
     |
   Router
     |
DHCP Server
```

Client gửi:

```
DHCP Discover (broadcast)
```

Router **chặn broadcast**

→ DHCP không hoạt động.

---

## DHCP Relay giải quyết vấn đề này

Router sẽ **chuyển broadcast thành unicast** gửi đến DHCP server.

Router đóng vai trò:

```
DHCP Relay Agent
```

---

## Quy trình DHCP Relay

```
Client → DHCP Discover (broadcast)
↓
Router nhận
↓
Router chuyển thành unicast
↓
DHCP Server
↓
DHCP Offer
↓
Router
↓
Client
```

---

## Cấu hình DHCP Relay trên Cisco

Trên interface của client network:

```bash
interface vlan 10
ip helper-address 192.168.1.10
```

Ý nghĩa:

```
Forward DHCP request → 192.168.1.10
```

---

## ip helper-address làm gì

Nó forward nhiều loại broadcast:

| Protocol | Port |
| -------- | ---- |
| DHCP     | 67   |
| TFTP     | 69   |
| DNS      | 53   |
| NetBIOS  | 137  |

Nhưng phổ biến nhất là **DHCP relay**.

---

# 4. Tại sao phải loại trừ IP (DHCP Excluded Address)

Đây là câu hỏi **rất quan trọng trong thực tế vận hành**.

---

## Nếu không loại trừ IP

DHCP có thể cấp IP cho:

```
Router
Server
Printer
Firewall
```

Ví dụ:

```
Router: 192.168.1.1
```

DHCP cấp IP này cho client.

→ **IP conflict xảy ra**

---

## Ví dụ thực tế

Router:

```
192.168.1.1
```

DHCP pool:

```
192.168.1.1 → 192.168.1.200
```

Laptop nhận:

```
192.168.1.1
```

→ mạng **sập ngay lập tức**.

---

## Vì vậy phải exclude

Ví dụ:

```
Router
Server
Printer
Camera
```

---

## Cấu hình loại trừ IP

Cisco:

```bash
ip dhcp excluded-address 192.168.1.1 192.168.1.50
```

DHCP chỉ cấp:

```
192.168.1.51 → 192.168.1.254
```

---

## Thiết kế DHCP chuẩn trong doanh nghiệp

Ví dụ mạng:

```
192.168.1.0/24
```

Thiết kế tốt:

| range   | dùng cho       |
| ------- | -------------- |
| 1–20    | router, switch |
| 21–50   | server         |
| 51–80   | printer        |
| 81–99   | reserved       |
| 100–254 | DHCP clients   |

---

# 5. Tổng kết dễ nhớ

| Khái niệm        | Ý nghĩa                                   |
| ---------------- | ----------------------------------------- |
| DHCP Pool        | kho IP cấp cho client                     |
| DHCP Reservation | IP cố định theo MAC                       |
| DHCP Relay       | cho DHCP hoạt động qua router             |
| Excluded IP      | tránh DHCP cấp IP cho thiết bị quan trọng |

---

# 6. Một Network Technician giỏi sẽ luôn kiểm tra

Khi DHCP lỗi họ sẽ check theo thứ tự:

```
1 DHCP server chạy chưa
2 DHCP pool còn IP không
3 DHCP relay đúng chưa
4 IP conflict không
5 VLAN đúng chưa
```

---

Nếu bạn muốn, mình có thể dạy thêm phần **Network Technician nâng cao cực quan trọng**:

* **VLAN + DHCP hoạt động thế nào**
* **DHCP snooping (chống DHCP giả mạo)**
* **Packet DHCP trong Wireshark**
* **cách debug DHCP như kỹ sư CCNA/CCNP**

Đây là những kiến thức **90% Network Technician mới thường không biết nhưng cực quan trọng**.
