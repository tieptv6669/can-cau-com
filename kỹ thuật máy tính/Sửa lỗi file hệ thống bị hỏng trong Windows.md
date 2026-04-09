Lệnh:

```
DISM /Online /Cleanup-Image /RestoreHealth
```

là một lệnh trong **Windows** dùng để **sửa lỗi file hệ thống bị hỏng trong Windows Image**. Lệnh này sử dụng công cụ **Deployment Image Servicing and Management (DISM)**.

---

## 1️⃣ Ý nghĩa từng phần của lệnh

### `DISM`

* Viết tắt của **Deployment Image Servicing and Management**
* Công cụ của Windows để **quản lý và sửa chữa Windows Image** (file hệ thống của Windows).

---

### `/Online`

* Chỉ định rằng bạn đang **sửa hệ điều hành Windows đang chạy hiện tại**.
* Không phải sửa file image offline (ví dụ file `.wim`).

---

### `/Cleanup-Image`

* Yêu cầu DISM **kiểm tra và sửa lỗi trong Windows image**.
* Windows image ở đây là **bộ file hệ thống cốt lõi của Windows**.

---

### `/RestoreHealth`

* Tùy chọn này sẽ:

1. **Quét tìm file hệ thống bị hỏng**
2. **Tự động tải file chuẩn từ Windows Update**
3. **Thay thế file bị lỗi**

---

## 2️⃣ Khi nào nên dùng lệnh này

Thường dùng khi:

* Windows bị lỗi hệ thống
* Lệnh **System File Checker (`sfc /scannow`) không sửa được
* Windows Update lỗi
* Máy hay crash / lỗi DLL
* Một số chức năng Windows không hoạt động

---

## 3️⃣ Cách chạy đúng

1. Mở **Command Prompt với quyền Administrator**

2. Chạy lệnh:

```
DISM /Online /Cleanup-Image /RestoreHealth
```

3. Đợi khoảng **5–20 phút** tùy máy.

Nếu thành công sẽ hiện:

```
The restore operation completed successfully.
```

---

## 4️⃣ Thứ tự sửa lỗi Windows chuẩn

Kỹ thuật viên thường dùng theo thứ tự:

```
DISM /Online /Cleanup-Image /CheckHealth
```

↓

```
DISM /Online /Cleanup-Image /ScanHealth
```

↓

```
DISM /Online /Cleanup-Image /RestoreHealth
```

↓

```
sfc /scannow
```

---

## 5️⃣ Lưu ý quan trọng

* Cần **Internet** vì Windows có thể tải file từ Windows Update.
* Phải chạy **CMD với quyền Admin**.
* Không tắt máy giữa chừng.

---

💡 **Tip:**
Nếu Windows lỗi nặng, nên chạy:

```
DISM /Online /Cleanup-Image /RestoreHealth
```

rồi tiếp:

```
sfc /scannow
```

→ Đây là **combo sửa lỗi Windows phổ biến nhất**.

---

Nếu bạn muốn, mình có thể giải thích thêm:

* **Vì sao Windows hay bị corrupt system files**
* **Khi nào DISM không sửa được và phải dùng ISO Windows**
* **5 lệnh CMD cực mạnh để sửa Windows**.
