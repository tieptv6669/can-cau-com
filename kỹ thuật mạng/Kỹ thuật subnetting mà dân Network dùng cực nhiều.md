Ok, mình sẽ dạy bạn **3 kỹ thuật subnetting mà dân Network dùng cực nhiều khi học và làm việc (đặc biệt trong các kỳ thi như Cisco Certified Network Associate (CCNA))**.
Mục tiêu là: **nhìn nhanh – tính nhanh – hiểu bản chất.** 🚀

---

# 1️⃣ Kỹ thuật nhận biết Subnet trong 3 giây

## Ý tưởng cốt lõi

Subnet mask quyết định **bước nhảy (block size)** của subnet.

Công thức cực quan trọng:

```
Block size = 256 - giá trị subnet mask
```

### Ví dụ

IP:

```
192.168.1.75/26
```

Subnet mask /26 =

```
255.255.255.192
```

Octet quan trọng là **192**

Block size:

```
256 - 192 = 64
```

Các subnet sẽ nhảy như sau:

```
0
64
128
192
```

---

### Kiểm tra IP thuộc subnet nào

IP:

```
192.168.1.75
```

Các khoảng:

```
0–63
64–127
128–191
192–255
```

75 nằm trong:

```
64–127
```

➡ Network Address

```
192.168.1.64
```

➡ Broadcast

```
192.168.1.127
```

➡ Host

```
192.168.1.65 – 192.168.1.126
```

📌 **Đây là cách dân network làm trong đầu rất nhanh.**

---

# 2️⃣ Bảng Subnetting "thần thánh" (dân CCNA thuộc lòng)

Chỉ cần nhớ bảng này:

| CIDR | Subnet Mask     | Block Size | Host |
| ---- | --------------- | ---------- | ---- |
| /24  | 255.255.255.0   | 256        | 254  |
| /25  | 255.255.255.128 | 128        | 126  |
| /26  | 255.255.255.192 | 64         | 62   |
| /27  | 255.255.255.224 | 32         | 30   |
| /28  | 255.255.255.240 | 16         | 14   |
| /29  | 255.255.255.248 | 8          | 6    |
| /30  | 255.255.255.252 | 4          | 2    |

---

## Ví dụ siêu nhanh

IP:

```
10.10.10.77/27
```

/27 → block size

```
32
```

Subnet:

```
0
32
64
96
128
160
192
224
```

77 nằm giữa:

```
64–95
```

➡ Network

```
10.10.10.64
```

➡ Broadcast

```
10.10.10.95
```

➡ Host

```
10.10.10.65 – 10.10.10.94
```

---

# 3️⃣ Kỹ thuật nhìn IP là biết ngay Network / Broadcast / Host

Đây là **kỹ thuật cao thủ dùng nhiều nhất**.

## Bước 1

Xác định **block size**

Ví dụ

```
172.16.5.140/28
```

/28 →

```
255.255.255.240
```

Block size

```
256 - 240 = 16
```

---

## Bước 2

Liệt kê subnet

```
0
16
32
48
64
80
96
112
128
144
160
176
192
208
224
240
```

---

## Bước 3

Tìm khoảng chứa IP

IP

```
140
```

Nằm trong

```
128 – 143
```

---

## Kết quả

Network

```
172.16.5.128
```

Broadcast

```
172.16.5.143
```

Host

```
172.16.5.129 – 172.16.5.142
```

---

# 🔥 Mẹo của kỹ sư Network thật sự

Khi nhìn IP họ làm **3 bước trong đầu**:

1️⃣ Xác định **CIDR**
2️⃣ Tính **Block size (256 - subnet)**
3️⃣ Tìm **bội số gần nhất nhỏ hơn IP**

Ví dụ

```
IP = 192.168.10.173/27
```

/27

```
Block = 32
```

Subnet

```
160 – 191
```

➡ Network

```
192.168.10.160
```

➡ Broadcast

```
192.168.10.191
```

---

# 🧠 Bí mật của dân CCNA (90% người học không biết)

Họ **không tính toán nhiều**.

Họ chỉ nhớ **7 block size này**:

```
128
64
32
16
8
4
2
```

Chỉ cần vậy là giải được gần hết bài subnet.

---

✅ Nếu bạn muốn, mình có thể dạy thêm **3 kỹ thuật subnetting cực khủng của kỹ sư Network**:

* **Kỹ thuật Subnetting trong 10 giây (không cần viết ra giấy)**
* **Cách chia 1 network thành 8–16 subnet trong đầu**
* **Kỹ thuật VLSM (Variable Length Subnet Mask) mà các công ty dùng thật**

Mấy kỹ thuật này **giúp bạn làm bài CCNA nhanh hơn 95% người học.** 🚀

---

Đây là một câu hỏi **rất quan trọng trong subnetting** 👍
Vì trong thực tế **số subnet cần thường không phải số đẹp như 4, 8, 16**.

Ví dụ: **cần 7 subnet**.

Nguyên tắc chuẩn mà kỹ sư mạng và các bài thi như Cisco Certified Network Associate (CCNA) dùng là:

# 1️⃣ Quy tắc vàng: Luôn làm tròn lên theo lũy thừa của 2

Subnet được tạo bằng **bit nhị phân**, nên số subnet chỉ có thể là:

```
2
4
8
16
32
64
...
```

Không bao giờ có:

```
7
13
19
```

---

# 2️⃣ Ví dụ: Cần **7 subnet**

Ta tìm số gần nhất **≥ 7**

```
2^2 = 4  (không đủ)
2^3 = 8  (đủ)
```

→ phải dùng **3 bit**

```
2^3 = 8 subnet
```

📌 Nghĩa là:

**Bạn sẽ tạo ra 8 subnet dù chỉ cần 7.**

---

# 3️⃣ Ví dụ thực tế

Network:

```
192.168.1.0/24
```

Cần **7 subnet**

### Bước 1

mượn **3 bit**

```
/24 + 3 = /27
```

Subnet mask

```
255.255.255.224
```

---

### Bước 2

block size

```
256 - 224 = 32
```

---

### Bước 3

các subnet

```
192.168.1.0
192.168.1.32
192.168.1.64
192.168.1.96
192.168.1.128
192.168.1.160
192.168.1.192
192.168.1.224
```

Tổng:

```
8 subnet
```

Bạn chỉ dùng **7 subnet đầu**, subnet còn lại **dự phòng**.

---

# 4️⃣ Đây là cách kỹ sư mạng làm trong thực tế

Ví dụ hệ thống có:

```
7 phòng ban
```

Họ sẽ chia:

```
8 subnet
```

→ còn **1 subnet dự phòng** cho tương lai.

Điều này rất phổ biến trong thiết kế mạng.

---

# 5️⃣ Kỹ thuật tính cực nhanh trong đầu

Chỉ cần nhớ:

| Subnet cần | CIDR |
| ---------- | ---- |
| ≤2         | /25  |
| ≤4         | /26  |
| ≤8         | /27  |
| ≤16        | /28  |
| ≤32        | /29  |

---

Ví dụ:

```
cần 7 subnet
```

Trong đầu:

```
≤8
```

→

```
/27
```

Chỉ mất **2 giây**.

---

# 6️⃣ Một ví dụ nâng cao (giống đề thi CCNA)

Network

```
10.0.0.0/24
```

Yêu cầu

```
7 subnet
```

Trong đầu làm:

```
7 → 8 subnet
8 = 2^3
```

→

```
/24 + 3 = /27
```

→ Done.

---

# 🧠 Bí mật của dân Network (rất ít người dạy)

Thực ra họ **không nghĩ tới số subnet trước**.

Họ nghĩ theo cách này:

```
mượn 1 bit → 2 subnet
mượn 2 bit → 4 subnet
mượn 3 bit → 8 subnet
mượn 4 bit → 16 subnet
```

Chỉ cần vậy là **giải được mọi bài subnetting**.

---

✅ Nếu bạn muốn, mình có thể dạy thêm **một kỹ thuật subnetting cực mạnh mà kỹ sư Network dùng khi thiết kế hệ thống thật**:

**VLSM (Variable Length Subnet Mask)**

Ví dụ:

```
Phòng IT: 120 máy
Phòng Sales: 60 máy
Phòng HR: 20 máy
Phòng Camera: 10 máy
```

→ chia subnet **tối ưu IP** (đây là kỹ thuật dùng trong công ty thật).

Mình có thể dạy bạn cách làm **trong 5 phút hiểu luôn bản chất subnetting**. 🚀
