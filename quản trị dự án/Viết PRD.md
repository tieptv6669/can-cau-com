Nếu bạn nghĩ “dùng AI để viết PRD = đưa prompt → nhận tài liệu hoàn chỉnh”, thì nên bỏ ý đó ngay từ đầu 😄. PM giỏi không **outsource tư duy** cho AI — họ dùng AI như một “copilot” để tăng tốc suy nghĩ, kiểm tra logic và làm rõ sản phẩm.

Dưới đây là cách một PM thực thụ sử dụng AI để viết PRD hiệu quả (theo workflow thực tế, không phải lý thuyết suông):

---

# 1. Tư duy đúng: AI là *thinking partner*, không phải ghostwriter

PRD (Product Requirements Document) gồm 3 phần khó nhất:

* Xác định **problem đúng**
* Chọn **scope hợp lý**
* Viết **logic rõ ràng, không mâu thuẫn**

👉 AI giúp:

* brainstorm nhanh
* kiểm tra lỗ hổng logic
* diễn đạt lại rõ ràng

👉 AI KHÔNG làm thay:

* product sense
* decision trade-off
* ưu tiên roadmap

---

# 2. Workflow chuẩn: Viết PRD với AI (7 bước)

## Bước 1 — Làm rõ problem (quan trọng nhất)

❌ Sai:

> “Viết PRD cho app học tiếng Anh”

✅ Đúng (prompt tốt):

```
Tôi đang xây sản phẩm X cho đối tượng Y.
User đang gặp vấn đề Z.
Hãy giúp tôi:
- phân tích root cause
- đưa ra 3 góc nhìn khác nhau về problem này
- chỉ ra assumption nào cần validate
```

👉 Output bạn cần:

* Problem statement rõ
* Không bị “solution bias”

---

## Bước 2 — Define user & use case

Prompt:

```
Dựa trên problem này, hãy:
- xác định 2–3 user persona chính
- mô tả use case cụ thể theo từng persona
- viết user journey ngắn gọn
```

👉 Lúc này bạn đã có:

* Context cho PRD
* Không viết feature một cách mơ hồ

---

## Bước 3 — Brainstorm solution (có kiểm soát)

Prompt:

```
Đề xuất 5 hướng giải pháp khác nhau cho problem này.
Với mỗi giải pháp:
- ưu điểm
- nhược điểm
- độ phức tạp implement
```

👉 Tip của PM giỏi:

* Không chọn ngay
* Bắt AI “tranh luận ngược”

Prompt nâng cao:

```
Hãy đóng vai CTO và phản biện từng giải pháp trên
```

---

## Bước 4 — Define scope (MVP mindset)

Prompt:

```
Tôi chọn giải pháp A.
Hãy:
- đề xuất MVP scope (cái gì nên có / không nên có)
- chia thành must-have vs nice-to-have
- cảnh báo feature creep
```

👉 Đây là nơi AI cực mạnh:

* giúp bạn không overbuild
* giữ sản phẩm lean

---

## Bước 5 — Viết PRD structure

Prompt:

```
Tạo cấu trúc PRD chuyên nghiệp bao gồm:
- Background
- Problem Statement
- Goals & Metrics
- User Stories
- Functional Requirements
- Non-functional Requirements
- Out of Scope
- Risks
```

👉 Không copy nguyên — dùng làm skeleton

---

## Bước 6 — Viết từng phần với AI (quan trọng)

### Ví dụ: User Story

Prompt:

```
Viết user stories theo format:
As a [user], I want [goal], so that [benefit]

Dựa trên:
- persona X
- use case Y
```

---

### Ví dụ: Functional Requirements

Prompt:

```
Chuyển các user stories này thành functional requirements chi tiết:
- rõ input / output
- edge cases
- error handling
```

---

### Ví dụ: Metrics

Prompt:

```
Đề xuất các metrics để đo thành công của feature này:
- north star metric
- leading indicators
- guardrail metrics
```

---

## Bước 7 — Review như một senior PM

Đây là bước mà người mới hay bỏ qua ❗

Prompt cực mạnh:

```
Hãy review PRD này như một Senior PM tại Big Tech:
- chỉ ra điểm mơ hồ
- logic chưa chặt
- risk chưa được đề cập
- phần nào có thể gây hiểu nhầm cho dev
```

👉 Sau đó:

* iterate lại 2–3 vòng
* PRD sẽ “xịn” hơn 80% PM bình thường

---

# 3. 5 kỹ thuật nâng cao (PM giỏi hay dùng)

## 1. AI Debate Method

```
Hãy chia thành 2 bên:
- 1 bên ủng hộ feature này
- 1 bên phản đối

Tranh luận với nhau
```

👉 giúp tránh quyết định cảm tính

---

## 2. Pre-mortem

```
Giả sử feature này thất bại sau 3 tháng.
Hãy phân tích lý do
```

👉 cực kỳ thực tế

---

## 3. Edge case mining

```
Liệt kê 15 edge cases mà dev có thể gặp
```

---

## 4. Simplification

```
Làm đơn giản PRD này xuống mức junior dev vẫn hiểu
```

---

## 5. Translation (PM → Dev → Business)

```
Rewrite PRD này cho:
- developer
- business stakeholder
```

---

# 4. Template PRD “AI-friendly” (bạn có thể dùng ngay)

```
1. Background
2. Problem Statement
3. Goals & Success Metrics
4. Target Users
5. Use Cases
6. Solution Overview
7. Scope (MVP)
8. User Stories
9. Functional Requirements
10. Non-functional Requirements
11. Edge Cases
12. Out of Scope
13. Risks & Assumptions
```

---

# 5. Sai lầm phổ biến

* Dùng 1 prompt → expect PRD hoàn chỉnh
* Không validate output của AI
* Viết PRD mà không rõ problem
* Nhồi quá nhiều feature (feature creep)
* Không define metrics

---

# Kết luận

PM giỏi dùng AI theo kiểu:

> “Tôi suy nghĩ → AI mở rộng → tôi quyết định → AI refine”

Chứ không phải:

> “AI viết → tôi copy”

---

Nếu bạn muốn, mình có thể:

* Viết cho bạn **1 PRD hoàn chỉnh từ A–Z** (bạn chỉ cần đưa ý tưởng)
* Hoặc đóng vai **Senior PM review PRD của bạn**

Bạn muốn thử theo cách nào?
