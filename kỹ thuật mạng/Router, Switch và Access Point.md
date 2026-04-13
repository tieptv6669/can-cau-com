Một **kỹ thuật viên mạng (Network Technician)** cần nắm khá toàn diện về **Router, Switch và Access Point** vì đây là **3 thiết bị cốt lõi của hạ tầng mạng LAN/WAN/Wi-Fi**. Dưới đây là **bản đồ kiến thức đầy đủ và thực tế nhất** mà một kỹ thuật viên mạng nên biết.

---

# 1. Router – Bộ định tuyến

Router dùng để **kết nối nhiều mạng khác nhau và định tuyến gói tin**.

## 1.1 Kiến thức cơ bản cần biết

* Router hoạt động ở **Layer 3 (Network Layer)** trong mô hình **OSI Model**
* Chức năng chính:

  * Routing (định tuyến)
  * NAT
  * DHCP
  * Firewall cơ bản
  * VPN

---

## 1.2 Các khái niệm quan trọng

### Địa chỉ IP

* IPv4
* IPv6
* Subnet Mask
* CIDR

Ví dụ:

```
192.168.1.0/24
```

### Default Gateway

* Router là **cổng mặc định** để thiết bị ra ngoài mạng.

---

### NAT (Network Address Translation)

Router chuyển đổi IP nội bộ → IP internet.

Các loại NAT:

* Static NAT
* Dynamic NAT
* PAT (NAT overload)

---

### DHCP

Router có thể cấp IP tự động.

Các thành phần:

* IP range
* Gateway
* DNS
* Lease time

---

### Routing

Các loại định tuyến:

1. **Static Route**
2. **Dynamic Routing**

Các giao thức định tuyến phổ biến:

* RIP
* OSPF
* BGP
* EIGRP

---

### Access Control List (ACL)

Dùng để **lọc traffic**

Ví dụ:

```
deny 192.168.1.10
allow 192.168.1.0/24
```

---

### VPN

Các loại VPN phổ biến:

* IPSec
* OpenVPN
* L2TP
* PPTP

---

## 1.3 Cấu hình router cơ bản

Một kỹ thuật viên cần biết:

* cấu hình IP interface
* cấu hình DHCP
* cấu hình NAT
* cấu hình Static route
* port forwarding
* cấu hình VPN

---

# 2. Switch – Bộ chuyển mạch

Switch dùng để **kết nối các thiết bị trong cùng một mạng LAN**.

Switch hoạt động ở **Layer 2 của OSI Model**

---

## 2.1 MAC Address

Switch sử dụng **MAC address** để chuyển tiếp frame.

Ví dụ:

```
00:1A:2B:3C:4D:5E
```

Switch có:

**MAC Address Table (CAM table)**

---

## 2.2 VLAN (Virtual LAN)

VLAN chia mạng LAN thành nhiều mạng nhỏ.

Ví dụ:

| VLAN | Phòng   |
| ---- | ------- |
| 10   | IT      |
| 20   | Kế toán |
| 30   | Khách   |

---

### Các loại VLAN

* Data VLAN
* Voice VLAN
* Management VLAN
* Native VLAN

---

### Trunk và Access Port

Access port
→ 1 VLAN

Trunk port
→ nhiều VLAN

Chuẩn trunk:

* IEEE 802.1Q

---

## 2.3 Spanning Tree Protocol

Ngăn **loop mạng**.

Giao thức:

* STP
* RSTP
* MSTP

---

## 2.4 Link Aggregation

Gộp nhiều port thành 1 đường.

Chuẩn:

* IEEE 802.3ad

---

## 2.5 Switch nâng cao

Kỹ thuật viên nên biết:

* Port Security
* Storm Control
* QoS
* IGMP Snooping
* DHCP Snooping
* Dynamic ARP Inspection

---

# 3. Access Point – Thiết bị phát WiFi

Access Point dùng để **kết nối thiết bị không dây vào mạng LAN**.

---

## 3.1 Chuẩn WiFi

Các chuẩn:

* IEEE 802.11a
* IEEE 802.11b
* IEEE 802.11g
* IEEE 802.11n
* IEEE 802.11ac
* IEEE 802.11ax (WiFi 6)

---

## 3.2 Tần số WiFi

2.4 GHz

* xa hơn
* nhiễu nhiều

5 GHz

* nhanh hơn
* phạm vi ngắn hơn

---

## 3.3 Bảo mật WiFi

Các chuẩn:

* WEP
* WPA
* WPA2
* WPA3

---

## 3.4 Channel và nhiễu sóng

WiFi cần cấu hình:

* Channel
* Bandwidth
* Power

Ví dụ:

2.4GHz:

```
Channel 1
Channel 6
Channel 11
```

---

## 3.5 Roaming WiFi

Các chuẩn:

* 802.11k
* 802.11r
* 802.11v

---

# 4. Những kỹ năng thực tế bắt buộc

Một kỹ thuật viên mạng cần làm được:

### 1. Thiết kế mạng

* chia subnet
* thiết kế VLAN
* thiết kế WiFi coverage

---

### 2. Cấu hình thiết bị

Ví dụ:

* Cisco
* MikroTik
* Ubiquiti
* TP-Link
* Juniper Networks

---

### 3. Xử lý sự cố mạng

Các lỗi phổ biến:

* loop mạng
* trùng IP
* DHCP lỗi
* wifi nhiễu
* packet loss
* broadcast storm

---

### 4. Công cụ kiểm tra mạng

Kỹ thuật viên phải biết:

* ping
* tracert
* nslookup
* ipconfig
* wireshark

---

# 5. Kiến thức mạng nâng cao (nên biết)

* QoS
* MPLS
* SD-WAN
* Load Balancing
* High Availability
* Network Monitoring

Công cụ monitoring:

* Zabbix
* PRTG Network Monitor
* SolarWinds Network Performance Monitor

---

# 6. Chứng chỉ mạng phổ biến

Nếu muốn chuyên nghiệp:

* CCNA
* CCNP
* CompTIA Network+
* MikroTik MTCNA

---

✅ **Tóm lại**

Một kỹ thuật viên mạng giỏi phải nắm:

1️⃣ IP, subnet, routing
2️⃣ VLAN, switching
3️⃣ WiFi và RF
4️⃣ Security
5️⃣ Troubleshooting
6️⃣ Cấu hình thiết bị thực tế

---

💡 Nếu bạn muốn, tôi có thể chỉ cho bạn thêm:

* **Roadmap học Network từ số 0 → chuyên gia (rất rõ ràng)**
* **50 lệnh Router/Switch quan trọng nhất kỹ thuật viên phải thuộc**
* **Cách thiết kế mạng cho công ty 100–500 người** (rất thực tế).
