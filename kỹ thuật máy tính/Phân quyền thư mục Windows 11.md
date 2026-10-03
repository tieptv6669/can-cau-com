Có. Trên **Windows 11**, nếu bạn muốn tạo một thư mục mà **chỉ tài khoản Administrator mới có quyền truy cập**, cách chuẩn nhất là chỉnh **NTFS permissions** của thư mục.

### Cách làm

Ví dụ bạn có thư mục:

`D:\PrivateData`

#### 1. Chuột phải vào thư mục → Properties

Chọn:

**Properties → Security → Advanced**

#### 2. Tắt kế thừa quyền

Trong cửa sổ **Advanced Security Settings**:

* Bấm **Disable inheritance**
* Chọn **Remove all inherited permissions from this object**

Bước này rất quan trọng vì nếu không, user hiện tại có thể vẫn được thừa hưởng quyền từ thư mục cha.

#### 3. Chỉ cấp quyền cho Administrator

Sau khi xóa các quyền cũ, bấm:

**Add → Select a principal**

Nhập:

```text
Administrators
```

hoặc nếu bạn muốn chỉ **một tài khoản cụ thể**:

```text
AdminUser
```

Sau đó chọn:

**Full control**

và áp dụng cho:

```text
This folder, subfolders and files
```

#### 4. Kiểm tra quyền của SYSTEM

Bạn thường **nên giữ**:

```text
SYSTEM
```

với quyền **Full control**.

Windows cần tài khoản SYSTEM cho nhiều hoạt động hệ thống, backup, antivirus, cập nhật, v.v.

Một cấu hình thường gặp sẽ là:

| Principal         | Permission     |
| ----------------- | -------------- |
| `Administrators`  | Full control   |
| `SYSTEM`          | Full control   |
| User thông thường | Không có quyền |

---

### ⚠️ Một điểm rất quan trọng

Nếu mục tiêu của bạn là:

> **User thường không thể mở thư mục, nhưng Administrator có thể mở**

thì **không nên chỉ dùng thuộc tính Hidden**.

`Hidden` chỉ làm thư mục khó nhìn thấy, **không phải bảo mật**.

Bạn cần dùng **Security → NTFS permissions** như trên.

---

### Cách nhanh bằng Command Prompt

Nếu bạn thích dùng command line, có thể dùng `icacls`.

Ví dụ:

```cmd
icacls "D:\PrivateData" /inheritance:r
```

Xóa quyền của user cụ thể:

```cmd
icacls "D:\PrivateData" /remove "Username"
```

Cấp Full Control cho Administrators:

```cmd
icacls "D:\PrivateData" /grant Administrators:(OI)(CI)F
```

Cấp cho SYSTEM:

```cmd
icacls "D:\PrivateData" /grant SYSTEM:(OI)(CI)F
```

Trong đó:

* `(OI)` = áp dụng cho file bên trong
* `(CI)` = áp dụng cho thư mục con
* `F` = Full Control

Bạn có thể kiểm tra kết quả bằng:

```cmd
icacls "D:\PrivateData"
```

---

### Nếu bạn muốn **chỉ duy nhất 1 tài khoản Admin**, không phải mọi Administrator

Ví dụ máy có:

* `Tiep` — user thường
* `Admin` — tài khoản administrator

thì nên cấp quyền cho:

```text
Admin
SYSTEM
```

thay vì:

```text
Administrators
```

Vì nhóm `Administrators` có thể bao gồm **nhiều tài khoản administrator**.

Nếu bạn nói rõ trường hợp của bạn là **máy cá nhân có 1 user thường + 1 user admin**, tôi có thể hướng dẫn bạn cấu hình **từng bước chính xác trên Windows 11**, đồng thời chỉ cách kiểm tra rằng user thường **thực sự không thể truy cập thư mục**.
