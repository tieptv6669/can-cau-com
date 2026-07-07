### Xem kích thước của từng thư mục con trong thư mục hiện tại

```bash
du -sh */
```

Ví dụ kết quả:

```text
1.2G    Documents/
450M    Downloads/
25G     Photos/
```

* `-s`: chỉ hiển thị tổng dung lượng của từng thư mục.
* `-h`: hiển thị theo đơn vị dễ đọc (KB, MB, GB).

---

### Sắp xếp theo dung lượng từ nhỏ đến lớn

```bash
du -sh * | sort -h
```

Hoặc từ lớn đến nhỏ:

```bash
du -sh * | sort -hr
```

---

### Xem cả file và thư mục

```bash
du -sh *
```

---

### Chỉ xem các thư mục con cấp 1 của một đường dẫn cụ thể

Ví dụ thư mục `/Users/me/Downloads`:

```bash
du -sh /Users/me/Downloads/*
```

Hoặc:

```bash
cd /Users/me/Downloads
du -sh */
```

---

### Cách nhanh để tìm thư mục nào chiếm nhiều dung lượng nhất

```bash
du -sh * | sort -hr | head -20
```

Hiển thị 20 mục lớn nhất.

---

### Nếu muốn xem dạng cây (tree) đẹp hơn

Cài `ncdu`:

```bash
brew install ncdu
```

Sau đó chạy:

```bash
ncdu .
```

`ncdu` cho phép duyệt tương tác, sắp xếp theo dung lượng và rất tiện khi tìm thư mục/file đang chiếm ổ đĩa. Đây thường là công cụ được dùng nhiều nhất khi cần phân tích dung lượng trên macOS hoặc Linux.
