Troubleshooting mạng cần làm theo **một quy trình logic**, giống cách các Network Engineer xử lý sự cố. Phương pháp phổ biến là **từ Layer thấp → Layer cao** của OSI Model.

Mình sẽ dạy bạn **4 tình huống rất thường gặp**.

---

# 1. Máy không vào được Internet

## Quy trình kiểm tra chuẩn (5 bước)

### 1️⃣ Kiểm tra kết nối vật lý

* dây LAN có cắm không
* đèn port trên switch có sáng không
* wifi có connect không

Kiểm tra nhanh:

```
ipconfig
```

Nếu thấy:

```
Media disconnected
```

→ **không có kết nối vật lý**

---

### 2️⃣ Kiểm tra IP

```
ipconfig
```

Ví dụ IP hợp lệ:

```
IP: 192.168.1.10
Gateway: 192.168.1.1
```

Nếu IP dạng:

```
169.254.x.x
```

→ máy **không nhận DHCP**

---

### 3️⃣ Ping Gateway

```
ping 192.168.1.1
```

Kết quả:

| Kết quả         | Ý nghĩa           |
| --------------- | ----------------- |
| Reply           | LAN OK            |
| Request timeout | lỗi LAN / Gateway |

---

### 4️⃣ Ping Internet

```
ping 8.8.8.8
```

Nếu **ping được**

→ Internet OK
→ có thể lỗi **DNS**

---

### 5️⃣ Ping Domain

```
ping google.com
```

Nếu lỗi:

```
could not find host
```

→ lỗi **DNS**

---

# 2. Máy không nhận IP

Dấu hiệu:

```
ipconfig
```

ra:

```
169.254.x.x
```

Nguyên nhân phổ biến:

1️⃣ DHCP server lỗi
2️⃣ DHCP hết IP
3️⃣ VLAN sai
4️⃣ dây mạng lỗi
5️⃣ switch port lỗi

---

## Cách xử lý

### Bước 1

Renew IP

```
ipconfig /release
ipconfig /renew
```

---

### Bước 2

Kiểm tra DHCP server

DHCP thường nằm ở:

* Router
* Firewall
* Windows Server

---

### Bước 3

Test IP tĩnh

```
IP: 192.168.1.50
Gateway: 192.168.1.1
DNS: 8.8.8.8
```

Nếu **IP tĩnh vào mạng được**

→ DHCP lỗi

---

# 3. Wifi chập chờn

Nguyên nhân thường gặp:

| Nguyên nhân     | Mô tả                 |
| --------------- | --------------------- |
| Nhiễu sóng      | nhiều wifi xung quanh |
| sóng yếu        | xa Access Point       |
| quá tải         | nhiều user            |
| kênh wifi trùng | channel conflict      |
| firmware lỗi    | router                |

---

## Cách kiểm tra

### 1️⃣ Kiểm tra sóng

Windows:

```
netsh wlan show interfaces
```

Xem:

```
Signal : 80%
```

---

### 2️⃣ Đổi channel Wifi

2.4GHz nên dùng:

```
1
6
11
```

---

### 3️⃣ Kiểm tra số user

Router nhỏ chỉ chịu được:

```
20–30 devices
```

---

### 4️⃣ Test bằng dây LAN

Nếu LAN ổn mà Wifi chập chờn

→ lỗi **Wireless**

---

# 4. Ping không thông

Ping là công cụ cơ bản để kiểm tra network.

```
ping 192.168.1.1
```

---

## Các trường hợp ping lỗi

### 1️⃣ Request timed out

Nguyên nhân:

* firewall chặn
* thiết bị tắt
* network lỗi

---

### 2️⃣ Destination host unreachable

Nguyên nhân:

* sai gateway
* router không có route

---

### 3️⃣ TTL expired

Nguyên nhân:

* routing loop

---

# 5. Công cụ troubleshooting quan trọng

### 1️⃣ ipconfig

Xem IP

```
ipconfig /all
```

---

### 2️⃣ ping

Test kết nối

```
ping 8.8.8.8
```

---

### 3️⃣ tracert

Xem đường đi packet

```
tracert google.com
```

---

### 4️⃣ nslookup

Test DNS

```
nslookup google.com
```

---

# 6. Quy trình troubleshooting chuẩn của Network Engineer

Luôn theo **thứ tự này**:

```
1 Physical
2 Link
3 IP
4 Gateway
5 Internet
6 DNS
```

Hoặc đơn giản:

```
Cable
↓
IP
↓
Gateway
↓
Internet
↓
DNS
```

---

# 7. Ví dụ thực tế troubleshooting

User báo:

```
Không vào được Google
```

Bạn kiểm tra:

```
ping 8.8.8.8
```

Kết quả:

```
Reply
```

Nhưng:

```
ping google.com
```

fail

→ kết luận:

```
DNS lỗi
```

---

# 8. Quy tắc vàng của Network Engineer

**80% lỗi mạng là do:**

1️⃣ dây mạng
2️⃣ cấu hình sai
3️⃣ DHCP
4️⃣ DNS

---

💡 Nếu bạn muốn, mình có thể dạy thêm **10 case troubleshooting thực tế mà Network Engineer gặp mỗi ngày**, ví dụ:

* Ping gateway được nhưng không vào Internet
* Wifi connect nhưng không có mạng
* DHCP cấp sai VLAN
* Ping được IP nhưng không ping được domain
* Mạng chậm bất thường

Những case này sẽ giúp bạn **debug mạng như chuyên gia IT**.

