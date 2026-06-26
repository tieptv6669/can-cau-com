Tự build PC không quá khó, nhưng nếu làm lần đầu thì bạn nên đi theo quy trình rõ ràng để tránh mua nhầm linh kiện hoặc lắp không tương thích.

## 1. Xác định nhu cầu trước khi mua

Bạn cần biết PC dùng để làm gì:

| Nhu cầu               | CPU                       | RAM     | GPU                |
| --------------------- | ------------------------- | ------- | ------------------ |
| Văn phòng, học tập    | Core i3 / Ryzen 3         | 16GB    | iGPU               |
| Lập trình             | Core i5 / Ryzen 5         | 16–32GB | Không bắt buộc     |
| Chỉnh sửa ảnh/video   | Core i5/i7 hoặc Ryzen 5/7 | 32GB    | RTX 4060 trở lên   |
| Chơi game Full HD     | Core i5 / Ryzen 5         | 16GB    | RTX 4060 / RX 7600 |
| Stream, AI, dựng phim | Core i7/i9 hoặc Ryzen 7/9 | 32–64GB | RTX 4070 trở lên   |

---

## 2. Chọn CPU trước

CPU là nền tảng quyết định mainboard.

Ví dụ:

* Intel Core i5-14400F → Main socket LGA1700
* AMD Ryzen 5 7500F → Main socket AM5

Hiện nay nếu build mới hoàn toàn, nhiều người đánh giá nền tảng AMD AM5 có khả năng nâng cấp lâu dài hơn.

---

## 3. Chọn Mainboard tương thích

Ví dụ:

### Intel

* H610: giá rẻ
* B760: phổ biến nhất
* Z790: ép xung

### AMD

* A620: giá rẻ
* B650: đáng mua nhất
* X670: cao cấp

Kinh nghiệm:

* Không nên tiết kiệm quá mức ở mainboard.
* Main tốt giúp nguồn điện CPU ổn định và nâng cấp dễ hơn.

---

## 4. Chọn RAM

Năm 2026:

* Tối thiểu: 16GB
* Khuyến nghị: 32GB

Ưu tiên:

* 2 thanh RAM (Dual Channel)
* Ví dụ:

  * 2×8GB
  * 2×16GB

Không nên mua 1 thanh duy nhất nếu còn khe cắm đủ.

---

## 5. Chọn SSD

Hiện nay nên dùng SSD NVMe M.2.

Dung lượng:

* 500GB: tối thiểu
* 1TB: hợp lý nhất
* 2TB: nếu lưu nhiều game/video

Các hãng phổ biến:

* Samsung
* Western Digital
* Kingston
* Crucial

---

## 6. Chọn Card đồ họa (GPU)

Nguyên tắc:

* Game → ưu tiên GPU
* Lập trình → ưu tiên CPU và RAM
* Dựng phim → cân bằng CPU + GPU

Ví dụ:

### Khoảng 15–20 triệu

* NVIDIA GeForce RTX 4060

### Khoảng 20–30 triệu

* NVIDIA GeForce RTX 5070

### AI, Render nặng

* NVIDIA GeForce RTX 5080

---

## 7. Đừng tiết kiệm nguồn (PSU)

Đây là lỗi phổ biến nhất của người mới.

Nên chọn:

* 650W–750W cho cấu hình tầm trung
* 850W trở lên cho máy mạnh

Ưu tiên chuẩn:

* 80 Plus Bronze
* 80 Plus Gold

Hãng phổ biến:

* Corsair
* Seasonic
* Cooler Master
* MSI

---

## 8. Chọn Case đủ rộng

Kiểm tra:

* Hỗ trợ kích thước mainboard
* Hỗ trợ chiều dài GPU
* Có luồng gió tốt

Nhiều người mua GPU dài rồi mới phát hiện không nhét vừa case.

---

## 9. Khi lắp ráp

Thứ tự dễ nhất:

1. Gắn CPU
2. Gắn RAM
3. Gắn SSD
4. Gắn tản nhiệt CPU
5. Đặt main vào case
6. Lắp nguồn
7. Lắp GPU
8. Cắm dây nguồn

Nhớ:

* Tháo điện hoàn toàn trước khi thao tác.
* Không dùng lực mạnh.
* Nếu linh kiện không vào đúng vị trí thì thường là đang lắp sai chiều.

---

## 10. Những lỗi người mới hay gặp

❌ Mua CPU không tương thích mainboard.

❌ Mua RAM DDR5 cho main DDR4.

❌ Nguồn công suất thấp.

❌ Case quá nhỏ.

❌ Không bật XMP/EXPO sau khi cài Windows.

❌ Quên cắm dây nguồn CPU 8-pin.

❌ Cắm màn hình vào cổng trên main thay vì GPU.

---

## Một cấu hình "ngon - bổ - rẻ" năm 2026 (~20 triệu)

* CPU: Ryzen 5 7500F
* Main: B650
* RAM: 32GB DDR5
* SSD: NVMe 1TB
* GPU: RTX 4060
* PSU: 650W 80+ Bronze
* Case: Mid Tower có ít nhất 3 quạt

Cấu hình này đủ để:

* Lập trình
* Photoshop
* Premiere
* Chơi hầu hết game ở Full HD/2K
