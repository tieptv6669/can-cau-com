Mình sẽ dạy bạn **từ cơ bản → nâng cao**, theo đúng cách mà kỹ thuật mạng thường học. Sau khi đọc xong bạn có thể **tự cấu hình router, đặt IP tĩnh, quản lý Wi-Fi trong nhà hoặc công ty nhỏ**.

---

# 1. Cấu hình Router cấp IP (DHCP)

## 1.1 IP là gì?

**IP (Internet Protocol Address)** là địa chỉ để thiết bị giao tiếp trong mạng.

Ví dụ mạng gia đình thường dùng dạng:

```
192.168.1.x
```

Ví dụ:

| Thiết bị   | IP           |
| ---------- | ------------ |
| Router     | 192.168.1.1  |
| Điện thoại | 192.168.1.10 |
| Laptop     | 192.168.1.11 |
| Camera     | 192.168.1.20 |

Router sẽ **tự cấp IP cho thiết bị** bằng hệ thống gọi là **DHCP**.

---

## 1.2 DHCP là gì?

DHCP = **Dynamic Host Configuration Protocol**

Nhiệm vụ:

Router **tự cấp IP, Gateway, DNS** cho thiết bị.

Ví dụ router cấp:

```
IP: 192.168.1.15
Gateway: 192.168.1.1
DNS: 8.8.8.8
```

---

## 1.3 Cách cấu hình DHCP trên router

Bước 1: đăng nhập router

Mở trình duyệt:

```
192.168.1.1
```

hoặc

```
192.168.0.1
```

Tài khoản phổ biến:

```
admin / admin
admin / password
```

---

Bước 2: tìm mục

```
LAN
DHCP Server
```

---

Bước 3: cấu hình

Ví dụ:

```
DHCP: Enable

Start IP: 192.168.1.100
End IP: 192.168.1.200

Gateway: 192.168.1.1
DNS: 8.8.8.8
```

Ý nghĩa:

| mục      | nghĩa                |
| -------- | -------------------- |
| Start IP | IP bắt đầu cấp       |
| End IP   | IP kết thúc          |
| Gateway  | địa chỉ router       |
| DNS      | server phân giải tên |

---

# 2. Đặt IP tĩnh (Static IP)

Có 2 cách.

---

# Cách 1: đặt IP tĩnh trên máy

Ví dụ trên Windows

Control Panel → Network

```
Change adapter settings
```

Chọn:

```
Ethernet / Wifi
```

Properties → IPv4

Chọn:

```
Use the following IP address
```

Ví dụ:

```
IP address: 192.168.1.10
Subnet mask: 255.255.255.0
Gateway: 192.168.1.1

DNS: 8.8.8.8
```

---

## Lưu ý quan trọng

IP tĩnh **không được trùng với DHCP**

Ví dụ:

DHCP:

```
192.168.1.100 → 192.168.1.200
```

Thì IP tĩnh nên đặt:

```
192.168.1.2
192.168.1.10
192.168.1.50
```

---

# Cách 2: đặt IP tĩnh trong Router (DHCP Reservation)

Cách này **tốt hơn**.

Router sẽ luôn cấp **cùng 1 IP cho 1 thiết bị**.

Vào:

```
DHCP
Address Reservation
```

Thêm:

```
MAC: 3C-52-82-AB-22-11
IP: 192.168.1.10
```

Router sẽ luôn cấp IP đó.

---

# 3. Cấu hình Wifi

## 3.1 Tên wifi (SSID)

Trong router vào:

```
Wireless
SSID
```

Ví dụ:

```
SSID: MyHomeWifi
```

---

## 3.2 Mật khẩu wifi

Security:

```
WPA2-PSK
```

Password:

```
12345678
```

---

## 3.3 Băng tần Wifi

Router thường có:

| loại   | tốc độ | khoảng cách |
| ------ | ------ | ----------- |
| 2.4GHz | chậm     | xa        |
| 5GHz   | nhanh  | gần         |

Khuyên dùng:

```
2.4GHz: MyHome
5GHz: MyHome_5G
```

---

## 3.4 Kênh Wifi (Channel)

Nếu wifi chậm nên chỉnh channel.

2.4GHz tốt nhất:

```
1
6
11
```

5GHz:

```
36
40
44
48
```

---

# 4. Cấu hình mạng chuẩn cho gia đình

Ví dụ setup chuẩn:

Router IP:

```
192.168.1.1
```

DHCP:

```
192.168.1.100 → 192.168.1.200
```

IP tĩnh cho thiết bị quan trọng:

| thiết bị | IP           |
| -------- | ------------ |
| Camera   | 192.168.1.10 |
| NAS      | 192.168.1.20 |
| Server   | 192.168.1.30 |

Wifi:

```
MyHome
MyHome_5G
```

---

# 5. Các lỗi phổ biến

### Không vào được mạng

Nguyên nhân:

* IP trùng
* Gateway sai
* DHCP tắt

---

### Wifi chậm

Nguyên nhân:

* quá nhiều thiết bị
* channel trùng
* router yếu

---

### Không vào được router

Thử:

```
192.168.0.1
192.168.1.1
192.168.31.1
```

---

# 6. Kiến thức nâng cao (dân IT mạng phải biết)

Nếu bạn muốn học sâu hơn:

* NAT
* Port Forwarding
* VLAN
* PPPoE
* QoS
* Mesh Wifi
* Firewall
* VPN
* Static Route

---

💡 Nếu bạn muốn, mình có thể dạy tiếp **3 cấp độ cực kỳ quan trọng** mà dân IT mạng thường học:

1️⃣ **Sơ đồ mạng từ A → Z (hiểu bản chất internet)**
2️⃣ **Cấu hình router chuyên nghiệp như kỹ thuật mạng**
3️⃣ **Cách hack não wifi và tối ưu tốc độ mạng gấp 3 lần**

Mình có thể dạy bạn **toàn bộ kiến thức mạng trong 1 lộ trình cực dễ hiểu**.

---

**Kênh Wi-Fi (Channel)** có thể hiểu **rất đơn giản như “làn đường trên đường cao tốc”**. 🚗

---

# 1. Ví dụ cực dễ hiểu

Hãy tưởng tượng:

* Internet = **đường cao tốc**
* Wi-Fi = **xe chạy trên đường**
* Channel = **làn đường**

Nếu:

* 1 làn có **quá nhiều xe** → **kẹt xe**
* Wi-Fi cũng vậy → **mạng chậm** 📶🐌

Ví dụ:

| Router       | Channel |
| ------------ | ------- |
| Nhà bạn      | 6       |
| Nhà bên trái | 6       |
| Nhà bên phải | 6       |

👉 Tất cả dùng **cùng kênh** → Wi-Fi **bị nhiễu**.

---

# 2. Wi-Fi có bao nhiêu Channel?

## Wi-Fi 2.4GHz

Có khoảng **13 kênh**.

Nhưng thực tế chỉ nên dùng:

```
1
6
11
```

Lý do:

Các kênh khác **bị chồng sóng lên nhau**.

Ví dụ:

```
1 2 3 4 5 6 7 8 9 10 11
```

Kênh 3 sẽ **đè lên kênh 1 và 6**.

---

## Wi-Fi 5GHz

Có nhiều kênh hơn:

```
36
40
44
48
149
153
157
161
```

Ưu điểm:

* ít nhiễu
* tốc độ cao hơn 🚀

---

# 3. Vì sao Channel quan trọng?

Nếu chọn **sai channel** sẽ xảy ra:

❌ Wi-Fi chậm
❌ Ping cao
❌ Mạng chập chờn
❌ Video bị lag

---

# 4. Ví dụ thực tế

Chung cư có 20 router.

```
Router 1 → channel 6
Router 2 → channel 6
Router 3 → channel 6
Router 4 → channel 6
```

➡ sóng bị **đè lên nhau**

Giống:

```
5 xe chạy chung 1 làn
```

Nếu phân ra:

```
Router 1 → channel 1
Router 2 → channel 6
Router 3 → channel 11
```

➡ mạng **mượt hơn nhiều**

---

# 5. Cách chỉnh Channel

Vào router:

```
192.168.1.1
```

Tìm mục:

```
Wireless
Channel
```

Chọn:

```
Auto
```

hoặc

```
1 / 6 / 11
```

---

# 6. Cách tìm Channel tốt nhất (dân IT hay làm)

Dùng app:

* WiFi Analyzer
* NetSpot
* Fing

App sẽ cho bạn thấy:

```
wifi nào dùng channel nào
```

Bạn chỉ cần chọn **channel ít người dùng nhất**.

---

# 7. Mẹo giúp Wi-Fi nhanh hơn

✔ 2.4GHz → channel **1 / 6 / 11**
✔ 5GHz → **36 / 40 / 44 / 48**
✔ không đặt router sát tường
✔ không để gần lò vi sóng

---

✅ **Tóm lại cực dễ nhớ:**

```
Channel = làn đường WiFi
Ít thiết bị cùng làn = mạng nhanh hơn
```

---

Nếu bạn muốn, mình có thể giải thích thêm những thứ **cực quan trọng mà nhiều người không biết về Wi-Fi** như:

* **Channel Width (20MHz / 40MHz / 80MHz)**
* **Tại sao Wi-Fi đầy vạch nhưng vẫn chậm**
* **Vị trí đặt router giúp mạng mạnh gấp 3 lần**
* **Sự khác nhau giữa router 300Mbps – 1200Mbps – 3000Mbps**

Những kiến thức này **90% người dùng internet không biết**.

---

Câu hỏi này rất hay 👍 — vì **đây là kiến thức nền tảng của Wi-Fi**. Mình sẽ giải thích theo cách **dễ hình dung nhất**.

---

# 1. Vì sao 2.4GHz có 13 kênh?

Băng tần **2.4GHz** được chia thành nhiều **dải tần nhỏ** gọi là **channel**.

Ví dụ một phần dải tần:

| Channel | Tần số trung tâm |
| ------- | ---------------- |
| 1       | 2.412 GHz        |
| 2       | 2.417 GHz        |
| 3       | 2.422 GHz        |
| ...     | ...              |
| 11      | 2.462 GHz        |
| 13      | 2.472 GHz        |

Mỗi kênh cách nhau **5 MHz**.

---

# 2. Vấn đề: Wi-Fi rộng hơn 1 kênh

Tín hiệu Wi-Fi **không chỉ chiếm 5 MHz**.

Thông thường nó cần khoảng:

```
20 MHz
```

Điều này nghĩa là **1 router sẽ chiếm nhiều kênh cùng lúc**.

---

# 3. Ví dụ kênh bị chồng lên nhau

Nếu bạn dùng **Channel 3**
thì sóng sẽ lan ra:

```
Channel 1 2 3 4 5
```

Nếu nhà bên cạnh dùng **Channel 6**

```
Channel 4 5 6 7 8
```

➡ Hai Wi-Fi **đè lên nhau**
➡ gây **nhiễu (interference)**

---

# 4. Các kênh không chồng lên nhau

Trong băng tần 2.4GHz chỉ có **3 kênh không bị chồng sóng**:

```
1
6
11
```

Minh họa đơn giản:

```
1 ----- 
      6 -----
            11 -----
```

Ba kênh này **không đè lên nhau** nên được dùng nhiều nhất.

---

# 5. Vậy các kênh khác dùng để làm gì?

Các kênh **2,3,4,5,7,8,9,10,12,13** không phải vô dụng.

Chúng được dùng trong một số trường hợp:

### 1️⃣ Hệ thống ít thiết bị

Nếu xung quanh **không có Wi-Fi khác**,
bạn dùng channel nào cũng được.

---

### 2️⃣ Chuẩn Wi-Fi cũ

Một số thiết bị cũ có thể chọn các kênh này.

---

### 3️⃣ Các quốc gia khác nhau

Quy định mỗi nước khác nhau.

Ví dụ:

| Quốc gia | Channel |
| -------- | ------- |
| Mỹ       | 1 – 11  |
| Châu Âu  | 1 – 13  |
| Nhật     | 1 – 14  |

---

### 4️⃣ Hệ thống mạng chuyên dụng

Một số hệ thống:

* IoT
* thiết bị công nghiệp
* thiết bị đo đạc

có thể dùng các kênh khác.

---

# 6. Ví dụ dễ hiểu hơn

Giả sử bạn có 3 router.

### Cách tốt

```
Router A → Channel 1
Router B → Channel 6
Router C → Channel 11
```

➡ ít nhiễu

---

### Cách tệ

```
Router A → Channel 3
Router B → Channel 4
Router C → Channel 5
```

➡ tất cả **đè lên nhau**

---

# 7. Tóm tắt cực ngắn

2.4GHz có **13 kênh**

Nhưng vì **sóng rộng 20MHz**, nên:

```
chỉ có 3 kênh không chồng lên nhau
```

đó là:

```
1
6
11
```

---

✅ **Quy tắc vàng của Wi-Fi 2.4GHz**

```
Chỉ nên dùng: 1 – 6 – 11
```

---

Nếu bạn muốn, mình có thể giải thích thêm **một kiến thức cực hay mà nhiều kỹ sư mạng mới cũng không hiểu rõ**:

* **20MHz vs 40MHz Channel Width**
* tại sao bật **40MHz trên 2.4GHz lại làm Wi-Fi chậm hơn**
* cách dân IT **tối ưu Wi-Fi cho chung cư đông người**.
