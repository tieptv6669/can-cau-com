Nhiều người dùng AI để viết user stories theo kiểu: “viết giúp tôi 10 user stories” → nhận output → copy. Cách đó tạo ra **user stories nghe có vẻ đúng nhưng vô dụng cho dev**.

Cách đúng là: dùng AI để **làm rõ ngữ cảnh + ép logic + kiểm tra thiếu sót**.

Dưới đây là cách một PM giỏi thực sự dùng AI để viết user stories 👇

---

# 1. Hiểu đúng: User Story không phải là câu văn đẹp

Một user story tốt phải:

* Có **ngữ cảnh cụ thể**
* Có **hành vi rõ ràng**
* Có **giá trị đo được**

Format chỉ là phần nhỏ:

> As a [user], I want [goal], so that [benefit]

👉 Sai lầm lớn: tập trung vào format, bỏ qua logic

---

# 2. Workflow chuẩn khi dùng AI

## Bước 1 — Feed context (đây là bước quyết định 80%)

❌ Prompt yếu:

> Viết user stories cho app học tiếng Anh

✅ Prompt đúng:

```text
Tôi đang xây feature X.
User là: sinh viên năm nhất, trình độ tiếng Anh cơ bản.
Problem: họ không duy trì được thói quen học mỗi ngày.

Use case:
- học 10 phút mỗi ngày
- nhận nhắc nhở
- theo dõi tiến độ

Hãy giúp tôi viết user stories
```

👉 AI chỉ tốt khi bạn cho nó “nguyên liệu tốt”

---

## Bước 2 — Generate version 1 (để có raw material)

Prompt:

```text
Viết 5–7 user stories theo format chuẩn.
Mỗi story phải:
- cụ thể, không mơ hồ
- gắn với hành động rõ ràng
- không overlap nhau
```

👉 Đừng expect perfect — đây chỉ là bản nháp

---

## Bước 3 — Ép AI làm rõ (step quan trọng nhất)

Prompt:

```text
Với mỗi user story:
- chỉ ra phần nào còn mơ hồ
- đề xuất cách viết lại rõ hơn
```

👉 Đây là lúc AI thực sự “có ích”

---

## Bước 4 — Thêm Acceptance Criteria (bắt buộc)

User story không có AC = vô dụng cho dev

Prompt:

```text
Với mỗi user story trên, hãy viết acceptance criteria theo format:
Given / When / Then

Bao gồm:
- happy path
- edge cases
```

---

## Bước 5 — Kiểm tra overlap & gap

Prompt cực mạnh:

```text
Phân tích các user stories này:
- có trùng lặp không?
- có thiếu use case nào không?
- có flow nào bị đứt đoạn không?
```

---

## Bước 6 — Convert sang ngôn ngữ dev (nâng cao)

Prompt:

```text
Chuyển các user stories này thành các task mà developer có thể implement ngay
```

---

# 3. Ví dụ thực tế (so sánh)

## ❌ Output AI kiểu “người mới”

* As a user, I want to learn English so that I improve my skills
  👉 quá chung chung → dev không làm được gì

---

## ✅ Output sau khi refine với AI

* As a student, I want to receive a daily reminder at 8PM so that I don’t forget to practice English

Acceptance Criteria:

* Given user bật notification
* When đến 8PM
* Then hệ thống gửi push notification
* When user click notification
* Then mở trực tiếp bài học hôm đó

👉 dev đọc là code được ngay

---

# 4. 5 kỹ thuật nâng cao (PM xịn hay dùng)

## 1. AI làm QA (rất mạnh)

```text
Bạn là QA engineer.
Hãy tìm bug tiềm ẩn trong các user stories này
```

---

## 2. Edge case mining

```text
Liệt kê các edge cases cho từng user story
```

---

## 3. Role play user thật

```text
Đóng vai user khó tính và critique các user stories này
```

---

## 4. Prioritization

```text
Sắp xếp các user stories theo mức độ impact vs effort
```

---

## 5. Simplify

```text
Viết lại các user stories này để junior dev hiểu ngay lập tức
```

---

# 5. Checklist: User Story tốt

Trước khi chốt, hỏi AI (hoặc tự hỏi):

* Có **cụ thể user nào không?**
* Có **action rõ ràng không?**
* Có **value rõ không?**
* Dev đọc có **biết làm gì không?**
* Có **acceptance criteria chưa?**

---

# 6. Sai lầm phổ biến

* Viết quá generic (“user muốn cải thiện…”)
* Không có acceptance criteria
* Viết trùng nhau
* Không gắn với flow thực tế
* Dùng AI nhưng không kiểm tra lại

---

# Kết luận

Cách dùng AI đúng:

> “AI giúp tôi nghĩ rõ hơn và viết chính xác hơn”

Không phải:

> “AI viết hộ tôi”

---

Nếu bạn muốn, mình có thể:

* Biến **ý tưởng của bạn → bộ user stories + AC hoàn chỉnh**
* Hoặc **review user stories bạn đã viết như một Senior PM**

Bạn muốn thử luôn với 1 feature cụ thể không?
