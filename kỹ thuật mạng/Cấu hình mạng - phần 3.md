Mình sẽ giải thích **thật trực quan và dễ hiểu như khi đào tạo Network Technician mới**. Trước tiên cần hiểu **vấn đề của IPv4**, rồi mới thấy tại sao NAT và các loại NAT tồn tại.

---

# 1. Tại sao NAT giúp tiết kiệm IPv4?

## 1.1 Vấn đề của IPv4

IPv4 có tổng số địa chỉ khoảng:

```text
≈ 4.3 tỷ địa chỉ
```

Nhưng Internet có:

* hàng **tỷ thiết bị**
* mỗi người có **nhiều thiết bị** (phone, laptop, TV, IoT)
* doanh nghiệp có **hàng nghìn máy**

Nếu mỗi thiết bị cần **1 public IP riêng**, thì IPv4 sẽ **cạn kiệt rất nhanh**.

---

## 1.2 Ý tưởng của NAT

Thay vì:

```
Mỗi thiết bị = 1 public IP
```

NAT cho phép:

```
Nhiều private IP → dùng chung 1 public IP
```

---

## 1.3 Ví dụ đơn giản

Trong nhà bạn có:

| Thiết bị | Private IP   |
| -------- | ------------ |
| Laptop   | 192.168.1.10 |
| Phone    | 192.168.1.11 |
| Smart TV | 192.168.1.12 |

Router có:

```
Public IP: 203.0.113.5
```

Khi ra Internet:

```
192.168.1.10 → 203.0.113.5
192.168.1.11 → 203.0.113.5
192.168.1.12 → 203.0.113.5
```

Internet **chỉ thấy 1 IP**.

---

## 1.4 Nếu không có NAT

Nhà có 10 thiết bị:

```
10 public IP
```

1 triệu gia đình:

```
10 triệu public IP
```

→ IPv4 **hết rất nhanh**.

---

## 1.5 Vì vậy NAT tiết kiệm IPv4

NAT cho phép:

```
Hàng trăm thiết bị → 1 public IP
```

Đó là lý do **Internet vẫn hoạt động dù IPv4 đã gần cạn**.

---

# 2. Static NAT (NAT tĩnh)

## Ý tưởng

Static NAT là:

```
1 private IP ↔ 1 public IP
```

Mapping **cố định**.

---

## Ví dụ

Server nội bộ:

```
Private IP: 192.168.1.10
```

Public IP:

```
203.0.113.10
```

Mapping:

```
192.168.1.10 ↔ 203.0.113.10
```

---

## Flow hoạt động

Client Internet truy cập:

```
203.0.113.10
```

Router NAT:

```
203.0.113.10 → 192.168.1.10
```

---

## Khi nào dùng Static NAT

Dùng khi cần **truy cập từ Internet vào server nội bộ**

Ví dụ:

| Server      | lý do         |
| ----------- | ------------- |
| Web server  | website       |
| Mail server | email         |
| VPN server  | remote access |

---

## Hình dung đơn giản

Static NAT giống như:

```
Số điện thoại riêng cho 1 người
```

Ai gọi số đó → luôn gặp đúng người.

---

# 3. Dynamic NAT (NAT động)

## Ý tưởng

Dynamic NAT:

```
Nhiều private IP → pool public IP
```

Không cố định.

---

## Ví dụ

Public IP pool:

```
203.0.113.10
203.0.113.11
203.0.113.12
```

Private network:

```
192.168.1.0/24
```

---

## Flow

Laptop A truy cập Internet:

```
192.168.1.10 → 203.0.113.10
```

Laptop B truy cập:

```
192.168.1.11 → 203.0.113.11
```

Laptop C truy cập:

```
192.168.1.12 → 203.0.113.12
```

Nếu pool hết IP:

→ client mới **không ra Internet được**.

---

## Hình dung đơn giản

Dynamic NAT giống như:

```
bãi đỗ xe công ty
```

Ai vào trước → lấy chỗ trước.

Chỗ hết → phải chờ.

---

# 4. PAT (Port Address Translation)

PAT là **loại NAT phổ biến nhất trên thế giới**.

Tên khác:

```
NAT Overload
```

---

## Ý tưởng

PAT cho phép:

```
Hàng trăm private IP → 1 public IP
```

Nhờ **port number**.

---

## Ví dụ

Router:

```
Public IP: 203.0.113.5
```

Ba thiết bị:

```
192.168.1.10
192.168.1.11
192.168.1.12
```

---

## Khi truy cập Internet

Router sẽ đổi **port**.

Ví dụ:

| Private           | Public            |
| ----------------- | ----------------- |
| 192.168.1.10:5000 | 203.0.113.5:10001 |
| 192.168.1.11:5000 | 203.0.113.5:10002 |
| 192.168.1.12:5000 | 203.0.113.5:10003 |

---

## Router lưu NAT table

```
192.168.1.10:5000 → 203.0.113.5:10001
192.168.1.11:5000 → 203.0.113.5:10002
192.168.1.12:5000 → 203.0.113.5:10003
```

Khi server trả dữ liệu:

```
203.0.113.5:10002
```

Router biết:

```
→ 192.168.1.11
```

---

## Vì sao PAT cực kỳ mạnh

Port có khoảng:

```
65535 ports
```

Một public IP có thể phục vụ:

```
hàng nghìn kết nối
```

---

## Hình dung đơn giản

PAT giống như:

```
tổng đài công ty
```

Công ty chỉ có **1 số điện thoại chính**.

Nhưng khi gọi vào:

```
ext 101 → phòng kế toán
ext 102 → phòng IT
ext 103 → phòng sales
```

Port chính là **extension number**.

---

# 5. So sánh 3 loại NAT

| NAT         | mapping       | mục đích       |
| ----------- | ------------- | -------------- |
| Static NAT  | 1 ↔ 1         | publish server |
| Dynamic NAT | nhiều ↔ nhiều | chia pool IP   |
| PAT         | nhiều ↔ 1     | tiết kiệm IP   |

---

# 6. Trong thực tế Internet dùng gì?

99% router gia đình dùng:

```
PAT
```

Ví dụ:

* router WiFi
* modem ISP
* firewall doanh nghiệp

---

# 7. Flow thực tế khi bạn mở website

Bạn mở:

```
youtube.com
```

Laptop:

```
192.168.1.10:51523
```

Router NAT:

```
192.168.1.10:51523 → 203.0.113.5:40001
```

Server trả về:

```
203.0.113.5:40001
```

Router chuyển lại:

```
192.168.1.10:51523
```

---

# 8. Tóm tắt cực dễ nhớ

| Công nghệ   | dễ hiểu                                     |
| ----------- | ------------------------------------------- |
| Static NAT  | 1 nhà ↔ 1 địa chỉ                           |
| Dynamic NAT | nhiều người ↔ nhiều địa chỉ dùng chung      |
| PAT         | nhiều người ↔ 1 địa chỉ nhưng khác số phòng |

---

Nếu bạn muốn, mình có thể dạy tiếp **3 thứ cực quan trọng về NAT mà Network Technician rất hay phải xử lý**:

1️⃣ **Port Forwarding hoạt động như thế nào**
2️⃣ **NAT table và cách debug NAT**
3️⃣ **Tại sao NAT đôi khi làm hỏng VPN / VoIP**

Đây là **những lỗi NAT rất phổ biến trong doanh nghiệp**.
