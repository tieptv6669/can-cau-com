Mình sẽ dạy bạn **Routing cơ bản** và **Switch Layer 2** theo cách dễ hiểu nhất – giống như nền tảng của một **Network Engineer**.

---

# 1. Switch Layer 2 là gì?

**Switch Layer 2** hoạt động ở **Layer 2 – Data Link Layer** của mô hình **OSI Model**.

### Nhiệm vụ chính

Switch Layer 2 dùng để **kết nối các thiết bị trong cùng một mạng LAN**.

Ví dụ thiết bị:

* PC
* Laptop
* Printer
* Camera
* Server

### Switch hoạt động dựa vào

👉 **MAC Address**

Ví dụ MAC:

```
00:1A:2B:3C:4D:5E
```

Mỗi thiết bị mạng đều có **MAC Address duy nhất**.

---

# 2. Switch Layer 2 hoạt động như thế nào?

Switch sử dụng **MAC Address Table**.

Ví dụ:

| Port | MAC Address |
| ---- | ----------- |
| 1    | PC1         |
| 2    | PC2         |
| 3    | Printer     |

### Quá trình gửi dữ liệu

**Bước 1 – Learning**

Switch học MAC của thiết bị khi chúng gửi dữ liệu.

**Bước 2 – Forwarding**

Nếu Switch biết MAC đích → gửi đúng port.

**Bước 3 – Flooding**

Nếu chưa biết MAC → gửi ra tất cả port.

---

### Ví dụ thực tế

```
PC1 → Switch → PC2
```

Switch kiểm tra MAC Table:

```
MAC PC2 → Port 2
```

→ gửi thẳng Port 2.

---

# 3. Broadcast trong Layer 2

Layer 2 có khái niệm **Broadcast**.

Ví dụ:

```
FF:FF:FF:FF:FF:FF
```

Switch sẽ gửi **broadcast ra toàn bộ port**.

Ví dụ dùng cho:

* ARP request
* DHCP discover

---

# 4. VLAN (Virtual LAN)

VLAN giúp **chia một switch thành nhiều mạng logic**.

Ví dụ:

| VLAN    | Department |
| ------- | ---------- |
| VLAN 10 | HR         |
| VLAN 20 | IT         |
| VLAN 30 | Finance    |

Sơ đồ:

```
Switch
 ├─ VLAN10 → HR
 ├─ VLAN20 → IT
 └─ VLAN30 → Finance
```

Ưu điểm:

* tăng **security**
* giảm **broadcast**
* quản lý mạng tốt hơn

---

# 5. Routing là gì?

**Routing** là quá trình **chuyển dữ liệu giữa các mạng khác nhau**.

Thiết bị thực hiện:

👉 **Router**

Router hoạt động ở **Layer 3 – Network Layer**.

Router dựa vào:

👉 **IP Address**

Ví dụ:

```
192.168.1.10
192.168.2.20
```

---

# 6. Router hoạt động như thế nào?

Router sử dụng **Routing Table**

Ví dụ:

| Network     | Next Hop |
| ----------- | -------- |
| 192.168.1.0 | Direct   |
| 192.168.2.0 | 10.0.0.2 |

Router sẽ:

1️⃣ Kiểm tra **destination IP**
2️⃣ So với **Routing Table**
3️⃣ Chuyển gói tin sang **next hop**

---

# 7. Ví dụ Routing đơn giản

```
Network A              Network B
192.168.1.0            192.168.2.0

PC1 ---- Router ---- PC2
```

PC1:

```
192.168.1.10
```

PC2:

```
192.168.2.20
```

PC1 muốn gửi dữ liệu → phải qua **Router**.

---

# 8. Static Routing

Router có thể cấu hình **static route**.

Ví dụ:

```
ip route 192.168.2.0 255.255.255.0 10.0.0.2
```

Ý nghĩa:

```
Network đích: 192.168.2.0
Next hop: 10.0.0.2
```

---

# 9. Dynamic Routing

Router có thể tự học route bằng các giao thức:

* RIP
* OSPF
* BGP

Ví dụ:

* **RIP** → mạng nhỏ
* **OSPF** → enterprise
* **BGP** → Internet

---

# 10. Sự khác nhau giữa Switch L2 và Router

| Switch Layer 2  | Router        |
| --------------- | ------------- |
| Dựa vào MAC     | Dựa vào IP    |
| Trong cùng mạng | Giữa các mạng |
| LAN             | LAN / WAN     |
| Nhanh           | Chậm hơn      |

---

# 11. Sơ đồ mạng cơ bản

```
PC1
   \
PC2 --- Switch L2 --- Router --- Internet
   /
PC3
```

Vai trò:

**Switch**

* kết nối thiết bị LAN

**Router**

* kết nối ra mạng khác / Internet

---

# 12. Kiến thức tiếp theo nên học

Nếu bạn muốn giỏi networking, nên học tiếp:

1️⃣ **ARP**
2️⃣ **Subnetting**
3️⃣ **Default Gateway**
4️⃣ **Switch Layer 3**
5️⃣ **NAT**
6️⃣ **VLAN Trunking**
7️⃣ **STP**

---

💡 Nếu bạn muốn, mình có thể dạy bạn tiếp:

**"Network cơ bản theo lộ trình CCNA trong 7 ngày"**

bao gồm:

* IP Address
* Subnetting
* VLAN
* Routing
* NAT
* Internet hoạt động thế nào

(giải thích cực dễ hiểu bằng sơ đồ thực tế).
