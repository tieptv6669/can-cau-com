Dưới đây là **bản tổng hợp đầy đủ và gọn gàng** về cách **chia sẻ file giữa Windows 11 và macOS trong cùng mạng LAN** để bạn có thể **lưu lại và dùng sau này**.

---

# Chia sẻ file giữa Windows 11 và macOS trong cùng mạng LAN

## Điều kiện

* Hai máy **kết nối cùng mạng LAN / Wi-Fi**
* Biết **địa chỉ IP của máy cần truy cập**

---

# 1. Chia sẻ file từ Windows → Mac

## Bước 1: Chia sẻ thư mục trên Windows

1. Chuột phải thư mục cần chia sẻ
2. Chọn **Properties**
3. Chọn tab **Sharing**
4. Nhấn **Share…**
5. Thêm user:

```
Everyone
```

6. Chọn quyền:

* **Read**: chỉ xem
* **Read/Write**: đọc và ghi

7. Nhấn **Share**

---

## Bước 2: Lấy IP của máy Windows

Mở **Command Prompt** và gõ:

```
ipconfig
```

Tìm dòng:

```
IPv4 Address
```

Ví dụ:

```
192.168.1.10
```

---

## Bước 3: Truy cập từ Mac

Mở **Finder**

Chọn:

```
Go → Connect to Server
```

Nhập:

```
smb://192.168.1.10
```

Nhấn **Connect**

---

## Bước 4: Nhập tài khoản Windows

Mac sẽ yêu cầu:

```
Username
Password
```

Nhập:

* **Username:** tên đăng nhập Windows
* **Password:** mật khẩu Windows

Ví dụ:

| Windows          | Nhập trên Mac |
| ---------------- | ------------- |
| Username: tiep   | tiep          |
| Password: 123456 | 123456        |

---

## Cách xem Username Windows

Mở **Command Prompt**

```
whoami
```

Ví dụ:

```
DESKTOP-PC\tiep
```

Username là:

```
tiep
```

---

## Tùy chọn: Không cần nhập mật khẩu

Có thể tắt **password protected sharing**

Vào:

```
Control Panel
Network and Sharing Center
Change advanced sharing settings
```

Trong mục **All Networks**

Tắt:

```
Password protected sharing
```

---

# 2. Chia sẻ file từ Mac → Windows

## Bước 1: Bật File Sharing trên Mac

Vào:

```
System Settings
General
Sharing
```

Bật:

```
File Sharing
```

---

## Bước 2: Bật SMB

Trong **File Sharing**

Chọn:

```
Options
```

Tick:

```
Share files and folders using SMB
```

và tick vào **user muốn chia sẻ**

---

## Bước 3: Lấy IP của Mac

Vào:

```
System Settings
Network
Wi-Fi
```

Ví dụ IP:

```
192.168.1.20
```

---

## Bước 4: Truy cập từ Windows

Mở **File Explorer**

Nhập vào thanh địa chỉ:

```
\\192.168.1.20
```

---

## Bước 5: Nhập tài khoản Mac

Windows sẽ yêu cầu:

```
Username
Password
```

Nhập:

* **Username:** tài khoản Mac
* **Password:** mật khẩu đăng nhập Mac

---

# 3. Map thư mục mạng thành ổ đĩa (tiện dùng)

Trên Windows:

Trong **File Explorer**

```
This PC → Map Network Drive
```

Nhập:

```
\\192.168.1.20\Shared
```

Ví dụ gán thành ổ:

```
Z:
```

Sau đó dùng như **ổ cứng bình thường**.

---

# 4. Một số lỗi thường gặp

## Không kết nối được

Kiểm tra:

* Hai máy cùng mạng
* Firewall không chặn
* SMB đã bật

---

## Sai mật khẩu

Nguyên nhân thường gặp:

* nhập sai **username**
* Windows lưu credential cũ

Xóa tại:

```
Control Panel
Credential Manager
Windows Credentials
```

---

# 5. Cách dễ hơn SMB (khuyên dùng)

Một số phần mềm chia sẻ file LAN cực nhanh:

* LocalSend
* Snapdrop
* KDE Connect

Ưu điểm:

* không cần IP
* không cần cấu hình
* kéo thả file
* tự tìm máy trong LAN
* tốc độ rất nhanh

---

# 6. Mẹo tăng tốc truyền file

* dùng **Ethernet (LAN dây)** thay Wi-Fi
* tắt **VPN**
* đảm bảo cùng subnet (ví dụ `192.168.1.x`)

---

✅ **Kết luận**

Có 2 cách chính:

| Cách                  | Độ khó     | Tốc độ    |
| --------------------- | ---------- | --------- |
| SMB (chia sẻ thư mục) | Trung bình | Rất nhanh |
| App LAN (LocalSend…)  | Rất dễ     | Nhanh     |

---

👍 Nếu bạn muốn, mình có thể viết thêm **một bản hướng dẫn ngắn gọn 1 trang (cheat sheet)** để bạn **lưu PDF hoặc ghi chú kỹ thuật** cho Win ↔ Mac.
