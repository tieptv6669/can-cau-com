**FileVault** là tính năng **mã hóa toàn bộ ổ đĩa** (Full-Disk Encryption) được tích hợp sẵn trên hệ điều hành macOS của Apple.

Nói một cách đơn giản, FileVault sẽ "xáo trộn" toàn bộ dữ liệu trên ổ cứng MacBook của bạn (ảnh, tài liệu, mật khẩu, ứng dụng...) thành chuỗi ký tự không thể đọc được. Chỉ khi bạn nhập đúng mật khẩu tài khoản Mac, dữ liệu mới được giải mã để sử dụng.

---

## 1. FileVault hoạt động như thế nào?

* **Khi máy đang hoạt động:** Bạn sử dụng Mac bình thường. FileVault sẽ âm thầm mã hóa và giải mã dữ liệu ngay lập tức khi bạn lưu hoặc mở tệp mà không làm gián đoạn công việc.
* **Khi máy tắt hoặc khóa màn hình:** Toàn bộ dữ liệu trên ổ cứng được khóa chặt.
* **Nếu máy bị mất hoặc xách tay rơi vào tay kẻ xấu:** Ngay cả khi họ tháo ổ cứng ra hoặc cố gắng kết nối Mac với một máy tính khác, họ cũng không thể truy cập hay lấy dữ liệu nếu không có mật khẩu đăng nhập.

---

## 2. Ưu điểm và Lưu ý quan trọng

| Ưu điểm | Lưu ý quan trọng |
| --- | --- |
| **Bảo mật tuyệt đối:** Sử dụng chuẩn mã hóa cao cấp XTS-AES-128 / AES-256 (tiêu chuẩn bảo mật nghiêm ngặt). | **Mất Recovery Key = Mất dữ liệu:** Nếu quên mật khẩu Mac *và* mất Mã khôi phục (Recovery Key), **ngay cả Apple cũng không thể khôi phục dữ liệu giúp bạn**. |
| **Tự động & mượt mà:** Trên các dòng Mac chip Apple Silicon (M1, M2, M3, M4...), FileVault chạy rất nhanh và hầu như không làm giảm hiệu năng máy. | **Sao lưu định kỳ:** Nên dùng thêm Time Machine hoặc lưu trữ đám mây để phòng trường hợp quên mật khẩu hoặc hỏng ổ cứng. |

---

## 3. Cách kiểm tra hoặc bật/tắt FileVault

1. Mở **System Settings** (Cài đặt hệ thống) trên Mac.
2. Chọn mục **Privacy & Security** (Quyền riêng tư & Bảo mật).
3. Cuộn xuống phần **FileVault**.
4. Chọn **Turn On** (Bật) hoặc **Turn Off** (Tắt) tùy theo nhu cầu.

> 💡 **Lời khuyên:** Nếu bạn thường xuyên mang máy ra ngoài làm việc, lưu trữ thông tin cá nhân quan trọng hoặc dữ liệu công việc, **bạn nên bật FileVault**.