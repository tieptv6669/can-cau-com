**Syncthing** là một phần mềm đồng bộ hóa dữ liệu tập tin liên tục (Continuous File Synchronization), mã nguồn mở và miễn phí, hoạt động theo mô hình **Peer-to-Peer (P2P)**.

Khác với Google Drive, Dropbox hay OneDrive, Syncthing **không lưu trữ dữ liệu của bạn trên bất kỳ máy chủ trung gian nào**. Thay vào đó, dữ liệu được truyền trực tiếp và mã hóa hoàn toàn giữa các thiết bị của chính bạn (máy tính, điện thoại, máy chủ NAS, VPS).

---

## 1. Cơ chế hoạt động kỹ thuật

* **Mô hình ngang hàng (P2P):** Các thiết bị kết nối trực tiếp với nhau. Nếu 2 máy tính nằm trong cùng mạng LAN, dữ liệu sẽ truyền qua mạng nội bộ với tốc độ tối đa của phần cứng (1Gbps hoặc hơn) mà không phụ thuộc vào tốc độ Internet.
* **Đồng bộ theo khối dữ liệu (Block-level Sync):** Khi một tập tin lớn bị sửa đổi, Syncthing chỉ chia nhỏ tập tin thành các khối (chunks) và chỉ truyền những phần bị thay đổi thay vì truyền lại toàn bộ tập tin.
* **Định danh thiết bị (Device ID):** Mỗi cài đặt Syncthing tạo ra một khóa mã hóa duy nhất dài 63 ký tự (Device ID). Để kết nối 2 thiết bị, hai bên phải xác nhận Device ID của nhau (mô hình Zero-Trust).
* **Giao thức BEP (Block Exchange Protocol):** Mọi lưu lượng truyền qua mạng đều được mã hóa bằng TLS với bảo mật Perfect Forward Secrecy, chống nghe lén hay can thiệp dữ liệu trên đường truyền.
* **Xử lý NAT & Firewall:** Khi các thiết bị ở ngoài mạng khác nhau, Syncthing sử dụng **Global Discovery Servers** để tìm thấy nhau và mở cổng qua UPnP/NAT-PMP. Nếu mạng bị chặn nghiêm ngặt, dữ liệu sẽ đi qua các **Relay Server** cộng đồng (vẫn được mã hóa đầu-cuối E2EE, máy chủ Relay không thể đọc được nội dung).

---

## 2. So sánh Syncthing và Dịch vụ Cloud Truyền thống

| Tiêu chí | Syncthing | Google Drive / Dropbox |
| --- | --- | --- |
| **Quyền riêng tư** | **Tuyệt đối.** Dữ liệu chỉ nằm trên thiết bị của bạn. | Dữ liệu nằm trên máy chủ công ty công nghệ. |
| **Chi phí** | Miễn phí 100%, không giới hạn dung lượng (phụ thuộc ổ cứng). | Phải trả phí hàng tháng khi hết dung lượng miễn phí. |
| **Tốc độ trong LAN** | Cực nhanh (giới hạn bởi bằng thông LAN/ổ cứng). | Bị giới hạn bởi tốc độ Upload/Download Internet. |
| **Yêu cầu kết nối** | Cần ít nhất 2 thiết bị cùng online để đồng bộ. | Chỉ cần 1 thiết bị online để đẩy dữ liệu lên Cloud. |
| **Chia sẻ công khai** | Không hỗ trợ tạo link tải public cho người ngoài. | Dễ dàng tạo link chia sẻ công khai. |

---

## 3. Các tính năng nổi bật

* **Phân quyền đồng bộ linh hoạt:**
* **Send & Receive:** Đồng bộ 2 chiều.
* **Send Only:** Thiết bị nguồn chỉ gửi dữ liệu đi, không nhận thay đổi từ máy khác.
* **Receive Only:** Thiết bị nhận chỉ đọc, bỏ qua các chỉnh sửa cục bộ.


* **Quản lý phiên bản tệp (File Versioning):** Hỗ trợ lưu trữ các bản sao cũ khi tệp bị xóa hoặc đè lên (Staggered, Trash Can, Simple, External).
* **File Ignore (`.stignore`):** Sử dụng cú pháp tương tự `.gitignore` để bỏ qua các thư mục tạm, tệp rác (ví dụ: `node_modules`, `thumbs.db`).
* **Hỗ trợ đa nền tảng:** Windows, macOS, Linux, Android, FreeBSD, Synology NAS, Docker.

---

## 4. Các trường hợp sử dụng (Use Cases) tối ưu

1. **Đồng bộ ảnh/video từ điện thoại sang máy tính/NAS:** Tự động sao lưu ảnh chụp từ Android về máy tính ngay khi kết nối Wi-Fi nhà mà không lo hết dung lượng cloud.
2. **Đồng bộ thư viện Obsidian/Logseq:** Quản lý ghi chú Markdown trên nhiều thiết bị cá nhân hoàn toàn miễn phí và riêng tư.
3. **Làm việc đa thiết bị:** Đồng bộ thư mục code, tài liệu công việc giữa PC để bàn ở nhà và Laptop khi đi ra ngoài.
4. **Sao lưu dữ liệu phân tán:** Đặt một máy Raspberry Pi hoặc máy tính cũ ở nhà người thân để làm máy sao lưu tự động từ xa.

---