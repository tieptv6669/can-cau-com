Dưới đây là **sơ đồ mạng mẫu cho một công ty khoảng 100 nhân viên**. Đây là mô hình rất phổ biến trong doanh nghiệp vừa, sử dụng các công nghệ như **VLAN**, **NAT**, **DHCP** và được cấu hình trên hệ điều hành thiết bị mạng như **Cisco IOS** hoặc **MikroTik RouterOS**.

---

# 1. Sơ đồ tổng thể mạng công ty 100 người

```
                 INTERNET
                     │
               ISP MODEM
                     │
                 ROUTER
            (Firewall + NAT)
                     │
               CORE SWITCH
                     │
        ┌────────────┼────────────┐
        │            │            │
   ACCESS SWITCH  ACCESS SWITCH  ACCESS SWITCH
      (Tầng 1)        (Tầng 2)       (Tầng 3)
        │              │              │
     PCs + WiFi     PCs + WiFi     PCs + WiFi
        │              │              │
     Printers       Cameras        IP Phones

                │
             SERVER
     (File / AD / Backup / NAS)
```

---

# 2. Các thành phần chính của hệ thống

### 1. Router (cổng ra internet)

Chức năng:

* Kết nối internet
* Cấu hình **NAT**
* Firewall
* VPN cho nhân viên từ xa

Ví dụ thiết bị:

* MikroTik
* Cisco
* Fortigate

---

### 2. Core Switch (switch trung tâm)

Đây là switch quan trọng nhất.

Chức năng:

* Routing nội bộ
* Quản lý **VLAN**
* Kết nối các switch tầng

---

### 3. Access Switch (switch tầng)

Mỗi tầng 1 switch:

* 24 – 48 port
* Cắm cho máy tính nhân viên
* Access point wifi
* Máy in

---

### 4. WiFi Access Point

Mỗi tầng:

* 3 – 5 AP

Thiết bị phổ biến:

* Ubiquiti
* Aruba
* TP-Link Omada

---

### 5. Server nội bộ

Ví dụ server:

* File server
* Backup server
* Domain controller
* NAS

Hệ điều hành thường dùng:

* **Windows Server**
* **Ubuntu Server**

---

# 3. Ví dụ chia VLAN cho công ty

| VLAN    | Phòng ban  | IP              |
| ------- | ---------- | --------------- |
| VLAN 10 | IT         | 192.168.10.0/24 |
| VLAN 20 | Kế toán    | 192.168.20.0/24 |
| VLAN 30 | Nhân sự    | 192.168.30.0/24 |
| VLAN 40 | Camera     | 192.168.40.0/24 |
| VLAN 50 | WiFi khách | 192.168.50.0/24 |

---

# 4. Luồng hoạt động của mạng

Ví dụ nhân viên truy cập internet:

```
PC → Access Switch → Core Switch → Router → Internet
```

Ví dụ truy cập file server:

```
PC → Access Switch → Core Switch → Server
```

---

# 5. Băng thông đề xuất cho công ty 100 người

Internet:

* 300 Mbps – 1 Gbps

Switch backbone:

* 10 Gbps uplink

---

# 6. Số thiết bị thường có

| Thiết bị      | Số lượng |
| ------------- | -------- |
| Router        | 1        |
| Core switch   | 1        |
| Access switch | 3–4      |
| Access point  | 8–12     |
| Server        | 1–3      |

---

💡 **Một nguyên tắc thiết kế mạng doanh nghiệp:**

> Không bao giờ để toàn bộ mạng trong **1 VLAN duy nhất**.

Vì:

* khó quản lý
* bảo mật kém
* broadcast lớn

---

✅ Nếu bạn muốn, tôi có thể vẽ thêm cho bạn:

* **Sơ đồ mạng chuẩn của một công ty 500 nhân viên**
* **Sơ đồ mạng của một Data Center nhỏ**
* **10 mô hình mạng mà kỹ sư mạng chuyên nghiệp phải biết** (rất hữu ích nếu bạn muốn lên trình Network Engineer).
