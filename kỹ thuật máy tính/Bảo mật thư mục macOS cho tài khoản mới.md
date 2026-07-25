Trên macOS, hệ thống đã tự động bảo vệ dữ liệu cá nhân giữa các tài khoản khác nhau. Nếu thư mục của bạn nằm trong thư mục cá nhân (Home folder) của bạn, tài khoản mới **mặc định sẽ không thể đọc hay mở được**.

Để đảm bảo an toàn tuyệt đối, bạn chỉ cần thực hiện 2 bước dưới đây:

---

## Các bước thực hiện

1. **Tạo tài khoản mới thuộc loại Tiêu chuẩn (Standard):** Tránh cấp quyền Quản trị viên.
1. Vào **Cài đặt hệ thống** (System Settings) > **Người dùng & Nhóm** (Users & Groups).
2. Chọn **Thêm tài khoản...** (Add Account) ở góc dưới.
3. Tại mục **Loại tài khoản** (Account Type), hãy chọn **Tiêu chuẩn** (Standard). *(Lưu ý: Không chọn Quản trị viên, vì quyền Admin có thể vượt qua rào cản bảo mật).*
4. Điền tên, mật khẩu cho người dùng mới rồi chọn **Tạo người dùng**.


2. **Kiểm tra vị trí và khóa quyền truy cập thư mục:** Đặt quyền No Access.
1. Đảm bảo thư mục cần bảo mật nằm trong thư mục cá nhân của bạn (ví dụ: *Tài liệu (Documents)*, *Màn hình nền (Desktop)* hoặc trực tiếp trong thư mục tên bạn).
2. Nhấp chuột phải vào thư mục đó > chọn **Lấy thông tin** (Get Info) — hoặc bấm tổ hợp phím `Cmd + I`.
3. Cuộn xuống phần **Chia sẻ & Quyền** (Sharing & Permissions) ở dưới cùng:
* Mục **everyone** (Mọi người): Chuyển thành **Không có quyền truy cập** (No Access).
* Mục tên bạn: Giữ nguyên **Đọc & Ghi** (Read & Write).




---

> **Lưu ý quan trọng:**
> * **Không đặt thư mục ở nơi dùng chung:** Đảm bảo thư mục **không** nằm trong thư mục `Công cộng` (Public) hoặc `Dùng chung` (Shared).
> * **Nếu dùng ổ cứng ngoài:** Nhấp chuột phải vào ổ cứng > chọn *Get Info* > bỏ tích ở ô *"Bỏ qua quyền trên ổ đĩa này"* (Ignore ownership on this volume) để phân quyền có hiệu lực.
> 
>