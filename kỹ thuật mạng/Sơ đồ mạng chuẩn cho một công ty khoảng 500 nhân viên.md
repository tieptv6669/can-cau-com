Dưới đây là **sơ đồ mạng chuẩn cho một công ty khoảng 500 nhân viên**. Mô hình này thường được thiết kế theo kiến trúc **3-tier network architecture** (Core – Distribution – Access) trong lĩnh vực **Computer Networking**.

Các hệ thống doanh nghiệp lớn thường triển khai trên thiết bị chạy **Cisco IOS**, **Juniper Junos** hoặc **MikroTik RouterOS**.

---

# 1. Sơ đồ tổng thể mạng công ty 500 nhân viên

```
                           INTERNET
                               │
                         ISP ROUTER
                               │
                        FIREWALL CLUSTER
                               │
                         CORE SWITCH (2)
                        (Redundancy Pair)
                               │
             ┌─────────────────┼─────────────────┐
             │                 │                 │
      DISTRIBUTION SW     DISTRIBUTION SW   DISTRIBUTION SW
          (Tầng A)            (Tầng B)         (Tầng C)
             │                 │                 │
      ┌──────┼──────┐    ┌─────┼─────┐     ┌─────┼─────┐
      │      │      │    │     │     │     │     │     │
   ACCESS  ACCESS ACCESS ACCESS ACCESS ACCESS ACCESS ACCESS
   SWITCH  SWITCH SWITCH SWITCH SWITCH SWITCH SWITCH SWITCH
      │      │      │      │      │      │      │      │
     PCs    WiFi  Printer PCs   WiFi   VoIP   Camera  IoT

                               │
                          SERVER FARM
                 (AD / File / Database / Backup)
                               │
                            STORAGE
                              NAS
```

---

# 2. Kiến trúc mạng 3 lớp

## 1️⃣ Core Layer

Lớp trung tâm của mạng.

Chức năng:

* Routing tốc độ cao
* Kết nối toàn bộ hệ thống
* Dự phòng (redundancy)

Thiết bị:

* Core switch L3
* Uplink **10Gb – 40Gb**

---

## 2️⃣ Distribution Layer

Lớp phân phối.

Chức năng:

* Routing giữa các **VLAN**
* Chính sách bảo mật
* QoS

Ví dụ:

* VLAN kế toán
* VLAN IT
* VLAN camera

---

## 3️⃣ Access Layer

Lớp kết nối người dùng.

Thiết bị:

* Access switch 24/48 port
* Access point WiFi

Kết nối:

* PC nhân viên
* điện thoại VoIP
* camera
* máy in

---

# 3. Hệ thống VLAN mẫu cho công ty 500 người

| VLAN    | Mục đích       | IP            |
| ------- | -------------- | ------------- |
| VLAN 10 | IT             | 10.10.10.0/24 |
| VLAN 20 | Kế toán        | 10.10.20.0/24 |
| VLAN 30 | Nhân sự        | 10.10.30.0/24 |
| VLAN 40 | Sales          | 10.10.40.0/24 |
| VLAN 50 | Camera         | 10.10.50.0/24 |
| VLAN 60 | VoIP           | 10.10.60.0/24 |
| VLAN 70 | WiFi nhân viên | 10.10.70.0/24 |
| VLAN 80 | WiFi khách     | 10.10.80.0/24 |

---

# 4. Hệ thống server doanh nghiệp

Server thường đặt trong **server room**:

Ví dụ:

* Active Directory
* File server
* Database server
* Email server
* Backup server

Hệ điều hành phổ biến:

* **Windows Server**
* **Ubuntu Server**
* **VMware ESXi**

---

# 5. Bảo mật mạng

Thiết bị bảo mật:

* Firewall
* IDS/IPS

Firewall phổ biến:

* **Fortinet**
* **Palo Alto Networks**
* **Cisco**

Chức năng:

* VPN
* Filtering
* Intrusion prevention

---

# 6. Băng thông hệ thống

| Kết nối             | Băng thông |
| ------------------- | ---------- |
| Internet            | 1 – 5 Gbps |
| Core switch         | 40 Gbps    |
| Distribution uplink | 10 Gbps    |
| Access switch       | 1 Gbps     |

---

# 7. Số thiết bị điển hình

| Thiết bị            | Số lượng |
| ------------------- | -------- |
| Router              | 2        |
| Firewall            | 2        |
| Core switch         | 2        |
| Distribution switch | 4–6      |
| Access switch       | 15–25    |
| Access point        | 40–60    |
| Server              | 5–15     |

---

💡 **Một nguyên tắc thiết kế mạng doanh nghiệp lớn:**

> Luôn có **redundancy (dự phòng)** cho thiết bị quan trọng.

Ví dụ:

* 2 router
* 2 firewall
* 2 core switch

Nếu một thiết bị hỏng → mạng vẫn hoạt động.

---

✅ Nếu bạn muốn, tôi có thể chỉ thêm cực kỳ hữu ích cho nghề mạng:

* **Sơ đồ mạng của Google / Facebook Data Center** (rất khác mạng doanh nghiệp)
* **10 mô hình mạng mà kỹ sư mạng phải biết**
* **Lộ trình từ Network Technician → Network Architect (mức lương rất cao)**.
