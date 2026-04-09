Sử dụng **Cloudflare** làm **reverse proxy** giúp website đứng sau Cloudflare được **bảo vệ, tăng tốc và ẩn server thật**. Khi bật Cloudflare, toàn bộ traffic sẽ đi qua Cloudflare trước rồi mới tới server gốc (origin). ⚙️

---

# 1️⃣ Ẩn IP thật của server (Origin Protection) 🛡️

Flow khi dùng Cloudflare:

```
User → Cloudflare → Origin Server
```

Người dùng chỉ thấy IP của Cloudflare.

Ví dụ DNS:

```
example.com → Cloudflare IP
```

Không thấy:

```
Origin server IP
```

### Lợi ích

* Tránh bị **direct attack**
* khó **DDoS vào origin**
* khó **scan port server thật**

---

# 2️⃣ Chống DDoS 🌐

Cloudflare có hệ thống **DDoS mitigation**.

Nó có thể:

* lọc bot
* rate limit
* block IP
* challenge CAPTCHA

Ví dụ:

```
Client → Cloudflare → filter → Server
```

Server không phải xử lý hàng triệu request.

---

# 3️⃣ Web Application Firewall (WAF) 🔥

Cloudflare có **WAF rules** để chặn:

* SQL Injection
* XSS
* Command Injection
* Path Traversal
* exploit phổ biến

Ví dụ request:

```
?id=1' OR 1=1--
```

Cloudflare có thể:

```
block request
```

trước khi tới server.

---

# 4️⃣ CDN (Content Delivery Network) ⚡

Cloudflare có **edge servers trên toàn thế giới**.

Nội dung static như:

* image
* CSS
* JS
* font

được cache ở edge.

Flow:

```
User (Vietnam)
   ↓
Cloudflare edge (Singapore / Hong Kong)
   ↓
cache response
```

Không cần tới origin server.

### Lợi ích

* load nhanh hơn
* giảm tải server

---

# 5️⃣ SSL/TLS termination 🔐

Cloudflare xử lý HTTPS:

```
User → HTTPS → Cloudflare
Cloudflare → HTTP/HTTPS → Origin
```

Các mode:

* Flexible
* Full
* Full (Strict)

Lợi ích:

* dễ bật HTTPS
* giảm CPU server

---

# 6️⃣ Load balancing & routing 🌍

Cloudflare có thể:

* load balance nhiều server
* health check
* failover

Ví dụ:

```
User → Cloudflare
        ↓
   server1
   server2
   server3
```

---

# 7️⃣ Cache & optimization 🚀

Cloudflare có thể:

* compress HTML
* minify JS/CSS
* Brotli compression
* HTTP/2 / HTTP/3

Ví dụ header bạn gửi:

```
Server: cloudflare
Cf-Cache-Status: DYNAMIC
```

---

# 8️⃣ Rate limiting 🚫

Có thể giới hạn request:

Ví dụ:

```
/login → 10 request / minute
```

Nếu vượt:

```
429 Too Many Requests
```

---

# 9️⃣ Bot protection 🤖

Cloudflare có:

* Bot management
* challenge JS
* fingerprint detection

Ví dụ:

```
Checking your browser...
```

---

# 🔟 Analytics & monitoring 📊

Cloudflare cung cấp:

* traffic analytics
* attack logs
* performance metrics

---

# Tổng kiến trúc khi dùng Cloudflare

```
User
  │
  │ HTTPS
  ▼
Cloudflare Edge
  │
  │ filtered + cached
  ▼
Origin Server
```

---

✅ **Tóm lại**

Dùng Cloudflare làm reverse proxy để:

1️⃣ Ẩn IP server
2️⃣ Chống DDoS
3️⃣ WAF chống exploit
4️⃣ CDN tăng tốc
5️⃣ SSL termination
6️⃣ Load balancing
7️⃣ Cache & optimization

---

💡 Nếu bạn đang học **pentest / bug bounty**, Cloudflare cũng tạo ra nhiều challenge thú vị. Mình có thể chỉ thêm:

* **7 cách tìm IP origin sau Cloudflare (pentest thực tế)**
* **cách bypass Cloudflare WAF khi test SQLi/XSS**
* **cách nhận biết site dùng Cloudflare chỉ qua 1 request**.
