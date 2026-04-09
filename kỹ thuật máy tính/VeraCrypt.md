# Hướng dẫn cơ bản sử dụng VeraCrypt

## 1. VeraCrypt là gì

VeraCrypt là phần mềm mã hóa miễn phí dùng để bảo vệ dữ liệu bằng mật khẩu. Phần mềm cho phép:

* Tạo ổ đĩa mã hóa ảo
* Mã hóa USB
* Mã hóa toàn bộ ổ cứng

Cách dùng phổ biến nhất là tạo một **file container** chứa dữ liệu đã mã hóa.

---

# 2. File container (.hc) là gì

File container (.hc) là một file đặc biệt dùng để chứa dữ liệu đã được mã hóa.

Có thể hiểu đơn giản: nó giống như **một ổ cứng bí mật nằm bên trong một file**.

Ví dụ:

secret.hc

Khi mở bằng VeraCrypt và nhập đúng mật khẩu, file này sẽ được "mount" thành một ổ đĩa mới trên máy tính.

Ví dụ:

Z:\

Bên trong ổ đĩa đó bạn có thể lưu:

* tài liệu
* hình ảnh
* video
* dữ liệu cá nhân
* file quan trọng

Khi đóng lại (dismount), tất cả dữ liệu sẽ quay lại thành một file duy nhất: secret.hc

---

# 3. Cách tạo file container mã hóa

### Bước 1: Mở VeraCrypt

Chọn:

Create Volume

### Bước 2: Chọn loại volume

Create an encrypted file container

### Bước 3: Chọn kiểu volume

Standard VeraCrypt volume

### Bước 4: Chọn nơi lưu file

Ví dụ:

D:\Secret\mydata.hc

### Bước 5: Chọn thuật toán mã hóa

Có thể để mặc định:

AES + SHA‑512

### Bước 6: Chọn dung lượng

Ví dụ:

1GB
10GB
100GB

### Bước 7: Đặt mật khẩu

Nên dùng mật khẩu mạnh:

* ít nhất 12–20 ký tự
* có chữ hoa
* chữ thường
* số
* ký tự đặc biệt

Ví dụ:

MySecret#2026!Data

### Bước 8: Format

Di chuyển chuột ngẫu nhiên trong cửa sổ để tăng độ bảo mật, sau đó nhấn Format.

Sau khi hoàn tất, file container sẽ được tạo.

---

# 4. Cách mở ổ đĩa mã hóa

1. Mở VeraCrypt
2. Chọn một ký tự ổ đĩa trống (ví dụ Z:)
3. Nhấn Select File
4. Chọn file .hc
5. Nhấn Mount
6. Nhập mật khẩu

Sau đó Windows sẽ xuất hiện ổ đĩa mới (ví dụ Z:).

Bạn có thể sử dụng ổ đĩa này như ổ cứng bình thường.

---

# 5. Cách đóng ổ đĩa

Sau khi sử dụng xong:

1. Mở VeraCrypt
2. Chọn ổ đang mount
3. Nhấn Dismount

Ổ đĩa sẽ biến mất và dữ liệu được khóa lại.

---

# 6. Ưu điểm của file container

* Bảo vệ dữ liệu bằng mã hóa mạnh
* Dễ dàng sao chép hoặc backup
* Có thể lưu trên USB, cloud hoặc ổ cứng
* Người khác chỉ thấy một file dữ liệu bình thường

---

# 7. Ví dụ sử dụng thực tế

Bạn có thể dùng để lưu:

* tài liệu công việc
* mật khẩu
* ví crypto
* dữ liệu cá nhân
* ảnh riêng tư

---

# 8. Lưu ý quan trọng

1. Quên mật khẩu = mất dữ liệu vĩnh viễn
2. Nên sao lưu file container (.hc)
3. Không nên lưu mật khẩu trong máy
4. Nên dùng mật khẩu dài và mạnh

---

# 9. Tính năng nâng cao

Ngoài container, VeraCrypt còn hỗ trợ:

* mã hóa USB
* mã hóa toàn bộ ổ hệ điều hành
* hidden volume (ổ bí mật bên trong ổ bí mật)

---

# Tóm tắt

File .hc là một "kho dữ liệu mã hóa". Khi mở bằng VeraCrypt nó hoạt động như một ổ đĩa bình thường, và khi đóng lại nó chỉ còn là một file duy nhất được bảo vệ bằng mật khẩu.
