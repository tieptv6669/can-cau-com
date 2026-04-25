Sprint Planning là một trong những nghi thức quan trọng nhất trong Scrum. Nếu làm đúng, nó giúp cả team biết rõ “mình sẽ làm gì” và “làm như thế nào” trong Sprint sắp tới. Nếu làm qua loa, Sprint gần như chắc chắn sẽ hỗn loạn.

Mình sẽ giải thích theo cách thực tế nhất, như một PM/PO đang vận hành team 👇

---

## 1. Sprint Planning là gì?

Sprint Planning là buổi họp đầu mỗi Sprint, nơi team cùng nhau:

* Xác định **mục tiêu Sprint (Sprint Goal)**
* Chọn **các công việc (User Stories / Tasks)** sẽ làm
* Lên kế hoạch **cách thực hiện**

👉 Kết quả cuối cùng:

* Một **Sprint Backlog rõ ràng**
* Cả team hiểu và cam kết

---

## 2. Ai tham gia?

Trong Scrum chuẩn:

* **Product Owner (PO)** → mang business vào
* **Scrum Master (SM)** → điều phối
* **Development Team** → estimate + commit

---

## 3. Sprint Planning diễn ra như thế nào?

### Bước 1: Xác định Sprint Goal (QUAN TRỌNG NHẤT)

PO sẽ trả lời:

> “Sprint này chúng ta muốn đạt được điều gì?”

Ví dụ:

* “User có thể đăng ký tài khoản bằng Google”
* “Giảm thời gian load trang xuống < 2s”

⚠️ Sai lầm phổ biến:

* Chỉ chọn task mà **không có mục tiêu rõ ràng**

---

### Bước 2: Chọn công việc từ Product Backlog

PO giới thiệu các item ưu tiên cao trong Product Backlog.

Team sẽ:

* Hỏi lại để hiểu rõ
* Phân tích yêu cầu
* Làm rõ acceptance criteria

---

### Bước 3: Estimate (ước lượng)

Team dev sẽ estimate effort bằng:

* Story points (Fibonacci: 1, 2, 3, 5, 8…)
* Hoặc giờ/ngày (ít khuyến khích)

Các kỹ thuật hay dùng:

* Planning Poker
* T-shirt sizing

👉 Mục tiêu:

* Không cần chính xác tuyệt đối
* Chỉ cần đủ tốt để **dự đoán capacity**

---

### Bước 4: Chốt Sprint Backlog

Dựa vào:

* Velocity (tốc độ team trước đó)
* Capacity (người nghỉ, thời gian thực tế)

Team sẽ chọn số lượng task phù hợp để đưa vào Sprint Backlog.

⚠️ PM/PO KHÔNG được ép commit

---

### Bước 5: Break down task (nếu cần)

Các user story lớn sẽ được chia thành:

* Task nhỏ hơn (dev, test, UI…)

👉 Giúp:

* Dễ tracking
* Dễ assign
* Dễ estimate lại nếu cần

---

## 4. Thời lượng bao lâu?

Theo Scrum Guide:

* Sprint 2 tuần → Planning tối đa ~4 giờ

Nhưng thực tế:

* Team nhỏ: 1.5 – 2.5 giờ là hợp lý

---

## 5. Output của Sprint Planning

Sau buổi này, bạn PHẢI có:

1. **Sprint Goal rõ ràng**
2. **Danh sách task đã commit**
3. **Estimate cho từng task**
4. **Hiểu cách triển khai**

Nếu thiếu 1 trong 4 → Planning chưa đạt

---

## 6. Sai lầm phổ biến (PM rất hay mắc)

### ❌ 1. Biến Planning thành buổi “giao việc”

→ Team không có tiếng nói → mất ownership

### ❌ 2. Requirement chưa rõ vẫn đưa vào Sprint

→ Dev phải đoán → bug + delay

### ❌ 3. Over-commit

→ Sprint nào cũng fail → mất niềm tin

### ❌ 4. Không có Sprint Goal

→ Team làm việc rời rạc, không có hướng

---

## 7. Tips thực chiến từ PM

* Luôn chuẩn bị backlog trước (refinement)
* Ưu tiên ít nhưng rõ ràng
* Focus vào outcome, không chỉ output
* Để dev phản biện (rất quan trọng)
* Track velocity đều đặn

---

## 8. Ví dụ thực tế

Sprint Goal:

> “User có thể reset password qua email”

Sprint Backlog:

* API gửi email reset
* UI form nhập email
* Token validation
* Test cases

---

## 9. Một câu chốt bạn nên nhớ

> Sprint Planning không phải để “làm nhiều nhất có thể”, mà để “commit đúng những gì có thể làm tốt nhất”.

---

Nếu bạn muốn, mình có thể:

* Giả lập 1 buổi Sprint Planning thực tế cho bạn
* Hoặc review quy trình team bạn đang làm và chỉ ra điểm sai 👍
