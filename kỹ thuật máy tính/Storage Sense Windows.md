Trên Windows có một tính năng khá “ẩn” tên là **Storage Sense** — tự động dọn file rác, file tạm, Recycle Bin và cả file tải xuống theo lịch mà rất nhiều người chưa từng bật.

## Cách bật nhanh Storage Sense

### Windows 11

1. Mở **Settings**
2. Vào **System → Storage**
3. Bật **Storage Sense**

### Windows 10

1. **Settings**
2. **System → Storage**
3. Bật **Storage Sense**

## Nó tự dọn được gì?

* File tạm của hệ thống
* Cache update Windows
* Thùng rác sau X ngày
* File trong Downloads sau X ngày
* File OneDrive chưa dùng lâu

## Thiết lập đáng dùng

Sau khi bật:

* Chọn **Configure Storage Sense**
* Đặt:

  * Recycle Bin: 30 ngày
  * Downloads: chỉ bật nếu bạn ít lưu file
  * Run Storage Sense: Every month

## Vì sao hữu ích?

Nhiều máy Windows chậm dần theo thời gian vì:

* File cache tích tụ
* Update cũ không bị xóa
* Temp files chiếm hàng chục GB

Storage Sense xử lý phần lớn việc này tự động mà không cần cài phần mềm “cleaner” bên ngoài.

## Một tính năng khác cũng ít người biết

Windows còn có:

### **Disk Cleanup nâng cao**

Nhấn:

```bat
cleanmgr /sageset:1
```

rồi:

```bat
cleanmgr /sagerun:1
```

Nó cho phép xóa sâu:

* Windows Update cũ
* Driver package cũ
* Temporary installation files
* Memory dump files

Ngoài ra còn một “tính năng ẩn” khác giúp máy mượt hơn mà Microsoft gần như không quảng bá: **Delivery Optimization cache cleanup** và **Startup Apps impact manager**.
