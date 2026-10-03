### 1. Danh sách user trên máy của bạn

Bạn đang có **6 local accounts**:

| Username             | Enabled | Administrator? |
| -------------------- | ------: | -------------: |
| `Administrator`      |       ❌ |              ✅ |
| `DefaultAccount`     |       ❌ |              ❌ |
| `Guest`              |       ❌ |              ❌ |
| `Thinkpad t14 gen 2` |       ✅ |              ✅ |
| `Tiep's Guest`       |       ✅ |              ❌ |
| `WDAGUtilityAccount` |       ❌ |              ❌ |

Kết quả:

```powershell
Get-LocalUser
```

và:

```cmd
net user
```

của bạn **hoàn toàn khớp nhau**.

---

### 2. Điểm quan trọng nhất: máy bạn có 2 Administrator

Lệnh:

```cmd
net localgroup Administrators
```

cho thấy:

```text
Administrator
Thinkpad t14 gen 2
```

Như vậy có **2 account thuộc nhóm `Administrators`**:

```text
Administrator
Thinkpad t14 gen 2
```

Trong đó:

```text
Administrator      → Disabled
Thinkpad t14 gen 2 → Enabled
```

Do đó **tài khoản Administrator built-in hiện đang bị vô hiệu hóa**.

Tài khoản bạn đang sử dụng nhiều khả năng là:

```text
Thinkpad t14 gen 2
```

và tài khoản này có quyền Administrator.

Bạn có thể xác nhận bằng:

```powershell
whoami
```

và:

```powershell
whoami /groups
```

---

## 3. User bạn cần đặc biệt chú ý: `Tiep's Guest`

Bạn có:

```text
Tiep's Guest       True
```

nhưng nó **không nằm trong Administrators**.

Điều đó có nghĩa cấu trúc hiện tại của bạn đại khái là:

```text
                    Windows 11
                        │
          ┌─────────────┴─────────────┐
          │                           │
   Administrators                 Regular users
          │                           │
   ┌──────┴──────┐                    │
   │             │                    │
Administrator   Thinkpad          Tiep's Guest
   (disabled)   t14 gen 2
```

Vì vậy, nếu mục tiêu của bạn là:

> **Thư mục X chỉ `Thinkpad t14 gen 2` được truy cập, `Tiep's Guest` không được truy cập.**

thì chúng ta **không nhất thiết phải quan tâm đến tất cả 6 user**.

Chúng ta cần thiết lập NTFS ACL sao cho:

```text
Thinkpad t14 gen 2    → Full Control
SYSTEM                → Full Control
Tiep's Guest          → No access
```

và xử lý inheritance đúng cách.

---

### 4. Nhưng có một điểm tôi muốn bạn kiểm tra trước

Để tránh cấu hình sai quyền, hãy chạy **3 lệnh sau** và gửi nguyên kết quả cho tôi:

```powershell
whoami
```

```powershell
whoami /user
```

```powershell
whoami /groups
```

Đặc biệt `whoami /user` sẽ cho chúng ta **SID chính xác của tài khoản bạn đang đăng nhập**, còn `whoami /groups` sẽ xác nhận nó đang thuộc những nhóm nào.

Sau đó tôi có thể đưa cho bạn **chính xác các lệnh `icacls` để khóa một thư mục chỉ cho tài khoản `Thinkpad t14 gen 2`**, thay vì hướng dẫn chung chung.
