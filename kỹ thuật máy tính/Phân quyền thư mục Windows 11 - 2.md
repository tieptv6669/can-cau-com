Được. Trên Windows 11, nếu bạn muốn **liệt kê chính xác tất cả user account đang tồn tại trên máy**, có vài cách. Tôi khuyên dùng **CMD hoặc PowerShell**.

### Cách 1 — CMD: đơn giản nhất

Mở **Command Prompt** và chạy:

```cmd
net user
```

Bạn sẽ nhận được dạng:

```text
User accounts for \\MY-PC

-------------------------------------------------------------------------------
Admin                    Guest                    DefaultAccount
Tiep                     WDAGUtilityAccount
The command completed successfully.
```

Đây là danh sách các **local user account** trên máy.

---

### Cách 2 — PowerShell: chi tiết hơn

Mở PowerShell và chạy:

```powershell
Get-LocalUser
```

Bạn sẽ thấy:

```text
Name                 Enabled Description
----                 ------- -----------
Admin                True
Guest                False
Tiep                 True
DefaultAccount       False
WDAGUtilityAccount   False
```

Nếu chỉ muốn lấy username:

```powershell
Get-LocalUser | Select-Object -ExpandProperty Name
```

Kết quả:

```text
Admin
Guest
Tiep
DefaultAccount
WDAGUtilityAccount
```

### Cách 3 — Muốn biết user nào là Administrator

Chạy:

```cmd
net localgroup Administrators
```

Ví dụ:

```text
Members

-------------------------------------------------------------------------------
Admin
Tiep
The command completed successfully.
```

Như vậy bạn biết chính xác **account nào thuộc nhóm Administrator**.

---

### Nếu mục đích của bạn là phân quyền thư mục

Tôi khuyên bạn chạy **3 lệnh này** rồi gửi kết quả cho tôi:

```cmd
whoami
```

```cmd
net user
```

```cmd
net localgroup Administrators
```

Từ 3 kết quả này, tôi có thể chỉ cho bạn **chính xác nên giữ/xóa username nào trong Security của thư mục**, để đạt cấu hình:

> 🔒 **Chỉ Admin được truy cập thư mục → user thường hoàn toàn không truy cập được.**
