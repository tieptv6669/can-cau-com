# Địa chỉ IP 

Hiện nay có **một số loại địa chỉ IP phổ biến** được sử dụng trong mạng máy tính và Internet. Chúng thường được phân loại theo **phiên bản**, **phạm vi sử dụng**, và **cách cấp phát**.

---

# 1. Phân loại theo phiên bản IP

## 1.1 IPv4

Đây là **loại địa chỉ IP phổ biến nhất từ trước đến nay**.

**Đặc điểm:**

* Dài **32 bit**
* Viết dưới dạng **4 số thập phân** cách nhau bằng dấu chấm
* Mỗi số từ **0 – 255**

**Ví dụ:**

```
192.168.1.1
8.8.8.8
172.16.254.1
```

**Tổng số địa chỉ:**

* Khoảng **4.3 tỷ địa chỉ**

**Nhược điểm:**

* Hiện nay **gần như đã cạn kiệt** do Internet phát triển quá nhanh.

---

## 1.2 IPv6

Đây là **phiên bản mới của IP** được tạo ra để thay thế IPv4.

**Đặc điểm:**

* Dài **128 bit**
* Viết bằng **hệ thập lục phân**
* Ngăn cách bằng dấu `:`

**Ví dụ:**

```
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

**Ưu điểm:**

* Số lượng địa chỉ cực lớn
* Bảo mật tốt hơn
* Hiệu quả hơn trong định tuyến

**Tổng số địa chỉ:**

* Khoảng **340 undecillion** địa chỉ (3.4 × 10^38)

---

# 2. Phân loại theo phạm vi sử dụng

## 2.1 Public IP

**Public IP** là địa chỉ IP **công khai trên Internet**.

Đặc điểm:

* Do **ISP (nhà cung cấp Internet)** cấp
* Dùng để giao tiếp trên Internet

Ví dụ:

```
8.8.8.8 (Google DNS)
```

---

## 2.2 Private IP

**Private IP** là địa chỉ **dùng trong mạng nội bộ (LAN)**.

Không thể truy cập trực tiếp từ Internet.

**Dải địa chỉ Private phổ biến:**

| Dải IP                        | Mục đích                  |
| ----------------------------- | ------------------------- |
| 10.0.0.0 – 10.255.255.255     | Mạng lớn                  |
| 172.16.0.0 – 172.31.255.255   | Mạng trung                |
| 192.168.0.0 – 192.168.255.255 | Mạng gia đình / văn phòng |

Ví dụ:

```
192.168.1.10
```

---

# 3. Phân loại theo cách cấp phát

## 3.1 Static IP (IP tĩnh)

Địa chỉ IP **không thay đổi**.

Thường dùng cho:

* Server
* Website
* Camera
* Máy chủ doanh nghiệp

Ví dụ:

```
203.113.130.10
```

---

## 3.2 Dynamic IP (IP động)

Địa chỉ IP **tự động thay đổi** khi thiết bị kết nối Internet.

Được cấp bởi **DHCP server**.

Thường dùng cho:

* Máy tính cá nhân
* Điện thoại
* Thiết bị gia đình

---

# 4. Một số loại IP đặc biệt

Ngoài ra còn có các loại sau:

| Loại IP      | Ý nghĩa                           |
| ------------ | --------------------------------- |
| Loopback IP  | Kiểm tra máy chính nó (127.0.0.1) |
| Broadcast IP | Gửi dữ liệu đến toàn mạng         |
| Multicast IP | Gửi đến một nhóm thiết bị         |
| APIPA        | IP tự gán khi DHCP lỗi            |

---

✅ **Tóm tắt nhanh**

| Loại       | Mục đích              |
| ---------- | --------------------- |
| IPv4       | Chuẩn IP cũ, phổ biến |
| IPv6       | Chuẩn IP mới          |
| Public IP  | Dùng trên Internet    |
| Private IP | Dùng trong mạng LAN   |
| Static IP  | IP cố định            |
| Dynamic IP | IP thay đổi           |

---

💡 Nếu bạn muốn, tôi có thể giải thích thêm một số chủ đề rất hay liên quan như:

* **5 lớp địa chỉ IP (Class A, B, C, D, E)**
* **Cách đọc địa chỉ IP trong mạng LAN**
* **Subnet Mask là gì**
* **NAT hoạt động như thế nào**

Đây là các kiến thức **cực quan trọng khi học mạng LAN/WAN**.

---

Trong chuẩn **IPv4**, địa chỉ IP ban đầu được chia thành **5 lớp (Classes)** để dễ quản lý và phân bổ mạng. Các lớp này là **Class A, B, C, D, E**.

---

# 1. Class A – Mạng rất lớn

**Đặc điểm:**

* Dùng cho các **tổ chức cực lớn hoặc nhà cung cấp mạng**
* **Byte đầu tiên** xác định Network

**Dải địa chỉ:**

```
1.0.0.0 → 126.255.255.255
```

**Cấu trúc:**

```
Network.Host.Host.Host
```

**Subnet Mask mặc định**

```
255.0.0.0
```

**Ví dụ:**

```
10.0.0.1
25.10.5.2
```

**Số lượng:**

* 126 mạng
* Mỗi mạng có khoảng **16 triệu host**

---

# 2. Class B – Mạng trung bình

Thường dùng cho **doanh nghiệp, trường học lớn**.

**Dải địa chỉ:**

```
128.0.0.0 → 191.255.255.255
```

**Cấu trúc:**

```
Network.Network.Host.Host
```

**Subnet Mask mặc định**

```
255.255.0.0
```

**Ví dụ:**

```
172.16.0.1
150.10.20.3
```

**Số lượng:**

* 16.384 mạng
* Mỗi mạng có **65.534 host**

---

# 3. Class C – Mạng nhỏ

Đây là loại **phổ biến nhất trong mạng LAN gia đình hoặc văn phòng**.

**Dải địa chỉ:**

```
192.0.0.0 → 223.255.255.255
```

**Cấu trúc:**

```
Network.Network.Network.Host
```

**Subnet Mask mặc định**

```
255.255.255.0
```

**Ví dụ:**

```
192.168.1.1
200.10.10.5
```

**Số lượng:**

* hơn **2 triệu mạng**
* mỗi mạng **254 host**

---

# 4. Class D – Multicast

Không dùng để cấp IP cho thiết bị.

**Mục đích:**

* **Truyền dữ liệu đến nhiều thiết bị cùng lúc**

Ví dụ:

* truyền video
* truyền hội nghị trực tuyến

**Dải địa chỉ:**

```
224.0.0.0 → 239.255.255.255
```

---

# 5. Class E – Nghiên cứu

Không dùng cho mạng Internet thông thường.

**Mục đích:**

* **Thử nghiệm và nghiên cứu**

**Dải địa chỉ:**

```
240.0.0.0 → 255.255.255.255
```

---

# Bảng so sánh nhanh

| Class | Dải IP    | Subnet Mask   | Số Host   | Mục đích     |
| ----- | --------- | ------------- | --------- | ------------ |
| A     | 1 – 126   | 255.0.0.0     | ~16 triệu | Mạng rất lớn |
| B     | 128 – 191 | 255.255.0.0   | ~65k      | Mạng trung   |
| C     | 192 – 223 | 255.255.255.0 | 254       | Mạng nhỏ     |
| D     | 224 – 239 | Không dùng    | -         | Multicast    |
| E     | 240 – 255 | Không dùng    | -         | Nghiên cứu   |

---

💡 **Mẹo nhớ cực nhanh (dựa vào số đầu tiên):**

| Số đầu IP | Class |
| --------- | ----- |
| 1 – 126   | A     |
| 128 – 191 | B     |
| 192 – 223 | C     |
| 224 – 239 | D     |
| 240 – 255 | E     |

---

✔ Ví dụ nhận dạng nhanh:

| IP          | Class |
| ----------- | ----- |
| 10.1.1.1    | A     |
| 172.16.1.1  | B     |
| 192.168.1.1 | C     |
| 230.1.1.1   | D     |

---

Nếu bạn muốn, tôi có thể giải thích thêm **3 thứ rất quan trọng khi học IP mà nhiều người mới học rất hay nhầm:**

1️⃣ **Subnet Mask hoạt động như thế nào**
2️⃣ **Network ID – Host ID là gì**
3️⃣ **Tại sao địa chỉ 127.0.0.1 lại đặc biệt**

Những phần này giúp bạn **hiểu mạng LAN/WAN sâu hơn rất nhiều.**

---

## Subnet Mask là gì?

**Subnet Mask** là một giá trị dùng để **xác định phần nào của địa chỉ IP là Network (mạng) và phần nào là Host (thiết bị)** trong một mạng máy tính.

Nó hoạt động cùng với địa chỉ **IPv4** để giúp router và thiết bị mạng biết **thiết bị nào nằm cùng mạng và thiết bị nào thuộc mạng khác**.

---

## 1. Ý tưởng đơn giản

Một địa chỉ IP có **2 phần chính**:

| Phần       | Ý nghĩa                      |
| ---------- | ---------------------------- |
| Network ID | Xác định mạng                |
| Host ID    | Xác định thiết bị trong mạng |

**Subnet Mask** giúp tách 2 phần này.

Ví dụ:

| IP Address   | Subnet Mask   |
| ------------ | ------------- |
| 192.168.1.10 | 255.255.255.0 |

Trong trường hợp này:

```
Network : 192.168.1
Host    : 10
```

---

## 2. Cách Subnet Mask hoạt động (theo bit)

Địa chỉ IP và Subnet Mask đều có **32 bit**.

Ví dụ:

IP Address

```
192.168.1.10
11000000.10101000.00000001.00001010
```

Subnet Mask

```
255.255.255.0
11111111.11111111.11111111.00000000
```

Quy tắc:

* **Bit = 1 → phần Network**
* **Bit = 0 → phần Host**

---

## 3. Subnet Mask phổ biến

| Subnet Mask   | CIDR | Số host   |
| ------------- | ---- | --------- |
| 255.0.0.0     | /8   | ~16 triệu |
| 255.255.0.0   | /16  | ~65k      |
| 255.255.255.0 | /24  | 254       |

Ví dụ:

```
192.168.1.0/24
```

Ý nghĩa:

* **24 bit cho Network**
* **8 bit cho Host**

---

## 4. Ví dụ thực tế mạng LAN

Giả sử mạng:

```
Network: 192.168.1.0
Subnet Mask: 255.255.255.0
```

Các thiết bị có thể là:

```
192.168.1.1  Router
192.168.1.2  PC
192.168.1.3  Laptop
192.168.1.4  Printer
```

Tất cả đều thuộc **cùng một mạng LAN**.

---

## 5. Tại sao cần Subnet Mask?

Subnet Mask giúp:

1. **Phân chia mạng thành các subnet nhỏ**
2. **Quản lý mạng hiệu quả**
3. **Giảm lưu lượng broadcast**
4. **Tăng bảo mật mạng**

---

## 6. Ví dụ dễ hiểu (ví như địa chỉ nhà)

| Thành phần | Ví dụ     |
| ---------- | --------- |
| Network    | Thành phố |
| Subnet     | Quận      |
| Host       | Số nhà    |

IP giống như:

```
Thành phố.Quận.Phường.Số nhà
```

Subnet Mask xác định **đâu là khu vực và đâu là số nhà**.

---

## 7. Ví dụ nhận biết cùng mạng hay không

Thiết bị A

```
192.168.1.10
255.255.255.0
```

Thiết bị B

```
192.168.1.20
255.255.255.0
```

→ **Cùng mạng**

Nhưng nếu:

```
192.168.2.20
```

→ **khác mạng** → cần **Router** để giao tiếp.

---

💡 **Mẹo nhớ nhanh**

```
Subnet Mask = công cụ chia Network và Host
```

---

Nếu bạn muốn, tôi có thể giải thích thêm **3 phần cực quan trọng trong Subnetting mà nhiều người học mạng rất thích:**

* **Network Address – Broadcast Address là gì**
* **Cách tính số host trong một subnet**
* **Cách chia subnet (Subnetting) cực nhanh chỉ trong 30 giây**.

---

Dưới đây là **3 kiến thức quan trọng nhất khi học Subnetting** trong mạng **IPv4**. Mình sẽ giải thích theo cách **dễ hiểu + có ví dụ thực tế**.

---

# 1. Network Address là gì?

**Network Address** là địa chỉ **đại diện cho toàn bộ mạng**.

* Đây là **địa chỉ đầu tiên của subnet**
* **Không gán cho thiết bị**

### Ví dụ

Network:

```
192.168.1.0/24
```

Subnet mask:

```
255.255.255.0
```

| Loại            | Địa chỉ         |
| --------------- | --------------- |
| Network Address | **192.168.1.0** |
| Host đầu tiên   | 192.168.1.1     |
| Host cuối       | 192.168.1.254   |
| Broadcast       | 192.168.1.255   |

👉 **192.168.1.0** là Network Address.

---

# 2. Broadcast Address là gì?

**Broadcast Address** là địa chỉ dùng để **gửi dữ liệu tới toàn bộ thiết bị trong mạng**.

* Là **địa chỉ cuối cùng của subnet**
* Không gán cho thiết bị.

### Ví dụ

```
192.168.1.255
```

Khi gửi dữ liệu tới địa chỉ này → **mọi thiết bị trong mạng đều nhận được**.

Ví dụ:

* ARP request
* tìm thiết bị trong LAN

---

# 3. Cách tính số Host trong một Subnet

Công thức cực quan trọng:

```
Số host = 2^(số bit host) - 2
```

Trừ **2 địa chỉ** vì:

* 1 Network Address
* 1 Broadcast Address

---

### Ví dụ 1

Subnet:

```
/24
```

IPv4 có **32 bit**

```
Host bits = 32 - 24 = 8
```

Tính:

```
2^8 - 2 = 254 host
```

---

### Ví dụ 2

Subnet:

```
/26
```

```
Host bits = 32 - 26 = 6
```

```
2^6 - 2 = 62 host
```

---

# 4. Cách chia Subnet cực nhanh (30 giây)

Ví dụ mạng:

```
192.168.1.0/24
```

Muốn chia thành **4 mạng nhỏ**.

---

## Bước 1 — Xác định số subnet

Muốn:

```
4 subnet
```

Ta cần:

```
2^2 = 4
```

→ mượn **2 bit**

---

## Bước 2 — Subnet mask mới

```
/24 + 2 = /26
```

Subnet mask mới:

```
255.255.255.192
```

---

## Bước 3 — Tìm bước nhảy (magic number)

```
256 - 192 = 64
```

→ bước nhảy = **64**

---

## Bước 4 — Liệt kê các subnet

| Subnet | Network       | Host range | Broadcast |
| ------ | ------------- | ---------- | --------- |
| 1      | 192.168.1.0   | 1–62       | 63        |
| 2      | 192.168.1.64  | 65–126     | 127       |
| 3      | 192.168.1.128 | 129–190    | 191       |
| 4      | 192.168.1.192 | 193–254    | 255       |

---

# 5. Mẹo Subnetting cực nhanh (IT thường dùng)

Nhớ bảng này:

| CIDR | Subnet Mask     | Host |
| ---- | --------------- | ---- |
| /24  | 255.255.255.0   | 254  |
| /25  | 255.255.255.128 | 126  |
| /26  | 255.255.255.192 | 62   |
| /27  | 255.255.255.224 | 30   |
| /28  | 255.255.255.240 | 14   |
| /29  | 255.255.255.248 | 6    |

---

# 6. Ví dụ thực tế mạng công ty

Công ty có mạng:

```
192.168.10.0/24
```

Muốn chia cho:

* Phòng IT
* Phòng kế toán
* Phòng nhân sự
* Phòng marketing

Ta chia thành:

```
/26
```

→ 4 subnet → mỗi phòng một mạng riêng.

---

# Tóm tắt nhanh

| Khái niệm         | Ý nghĩa                        |
| ----------------- | ------------------------------ |
| Network Address   | Địa chỉ đầu tiên của mạng      |
| Broadcast Address | Địa chỉ cuối gửi cho toàn mạng |
| Host formula      | 2^(host bits) - 2              |
| Subnetting        | Chia mạng lớn thành mạng nhỏ   |

---

💡 Nếu bạn muốn, tôi có thể dạy thêm **3 kỹ thuật subnetting mà dân Network dùng rất nhiều**:

1️⃣ **Cách nhận biết subnet chỉ trong 3 giây**
2️⃣ **Bảng subnetting thần thánh giúp làm bài thi CCNA cực nhanh**
3️⃣ **Cách nhìn IP là biết ngay Network / Broadcast / Host** (kỹ thuật rất hay).

---

Để **hiểu bản chất của Subnetting (chia subnet)**, ta cần quay lại nguyên lý của địa chỉ **IPv4**:
IP gồm **32 bit**, chia thành:

```
Network bits | Host bits
```

**Subnetting** thực chất là **lấy bớt một số bit của phần Host để làm Network**, từ đó tạo ra **nhiều mạng con (subnet)**.

---

# 1. Bản chất của Subnetting

Ban đầu:

```
Network | Host
```

Sau khi chia subnet:

```
Network | Subnet | Host
```

Tức là:

* **mượn một số bit của Host**
* chuyển thành **Subnet bits**

---

# 2. Ví dụ gốc để hiểu bản chất

Giả sử có mạng:

```
192.168.1.0/24
```

Nghĩa là:

* 24 bit cho Network
* 8 bit cho Host

Biểu diễn nhị phân:

```
Network bits      Host bits
11111111.11111111.11111111.00000000
```

---

# 3. Muốn chia thành 4 subnet

Ta cần **4 mạng con**.

Số bit cần mượn:

```
2^n ≥ số subnet
```

```
2^2 = 4
```

→ mượn **2 bit**

---

# 4. Cấu trúc bit sau khi mượn

Ban đầu:

```
11111111.11111111.11111111.00000000
```

Sau khi mượn 2 bit:

```
11111111.11111111.11111111.11000000
```

Subnet mask mới:

```
255.255.255.192
```

CIDR:

```
/26
```

---

# 5. Hiểu cách tạo subnet từ bit

Hai bit subnet có thể tạo các giá trị:

```
00
01
10
11
```

→ 4 subnet

---

# 6. Viết đầy đủ dạng nhị phân

Subnet 1

```
192.168.1.00000000
```

Subnet 2

```
192.168.1.01000000
```

Subnet 3

```
192.168.1.10000000
```

Subnet 4

```
192.168.1.11000000
```

---

# 7. Đổi sang hệ thập phân

| Subnet | Network Address |
| ------ | --------------- |
| 00     | 192.168.1.0     |
| 01     | 192.168.1.64    |
| 10     | 192.168.1.128   |
| 11     | 192.168.1.192   |

Đây chính là **các subnet thật sự**.

---

# 8. Tại sao bước nhảy là 64?

Host bits còn lại:

```
8 - 2 = 6
```

Số địa chỉ trong mỗi subnet:

```
2^6 = 64
```

Do đó:

```
0
64
128
192
```

---

# 9. Số host trong mỗi subnet

Công thức:

```
2^(host bits) - 2
```

```
2^6 - 2 = 62 host
```

Trừ 2 vì:

* Network address
* Broadcast address

---

# 10. Tổng kết bản chất Subnetting

Subnetting thực chất chỉ là:

1️⃣ **mượn bit từ Host**

2️⃣ **tạo các tổ hợp nhị phân mới**

3️⃣ **mỗi tổ hợp tạo ra một subnet**

---

# 11. Sơ đồ trực quan

Ban đầu:

```
Network (24) | Host (8)
```

Sau subnet:

```
Network (24) | Subnet (2) | Host (6)
```

---

# 12. Tư duy quan trọng khi học subnet

Không cần mẹo nếu hiểu 4 câu này:

1️⃣ IPv4 có **32 bit**
2️⃣ **Network + Host = 32 bit**
3️⃣ **Subnet = bit mượn từ Host**
4️⃣ **Số subnet = 2^(bit mượn)**

---

💡 Nếu bạn muốn, tôi có thể chỉ cho bạn **một cách nhìn subnetting rất trực quan (dân Network chuyên nghiệp thường dạy)**:

> **Hiểu subnetting bằng sơ đồ nhị phân 8 bit của một octet**

Cách này giúp bạn **nhìn IP là biết ngay subnet chỉ trong vài giây mà vẫn hiểu bản chất.**
