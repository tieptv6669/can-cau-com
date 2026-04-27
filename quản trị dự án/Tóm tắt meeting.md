Nếu bạn muốn dùng AI để **tóm tắt meeting như một PM chuyên nghiệp**, thì mục tiêu không phải là “rút ngắn nội dung” — mà là **biến meeting thành quyết định + hành động rõ ràng**.

Dưới đây là cách làm thực chiến, từ basic → advanced:

---

# 1. Hiểu đúng: Tóm tắt meeting ≠ ghi chép

Một bản tóm tắt tốt phải trả lời được:

* Quyết định gì đã được đưa ra?
* Ai làm gì?
* Deadline khi nào?
* Có risk/blocker nào không?

👉 Nếu thiếu mấy cái này → bản tóm tắt vô dụng.

---

# 2. Workflow chuẩn dùng AI

## Bước 1: Chuẩn bị input

Bạn có thể đưa cho AI:

* Transcript (từ Zoom, Meet, ghi âm)
* Note thô (gạch đầu dòng)
* Chat log

---

## Bước 2: Dùng prompt đúng (rất quan trọng)

### Prompt chuẩn PM:

```id="sum1"
Bạn là Project Manager.

Dưới đây là nội dung meeting:
[meeting notes / transcript]

Hãy tóm tắt thành:
1. Key Decisions
2. Action Items (ai làm gì + deadline)
3. Risks / Blockers
4. Open Questions
5. Next Steps

Viết ngắn gọn, rõ ràng, dạng bullet point.
```

---

# 3. Biến AI thành “Meeting Assistant xịn”

## Cách nâng cấp prompt:

```id="sum2"
Hãy đóng vai:
- CEO → chỉ quan tâm quyết định
- PM → quan tâm tiến độ & action
- Tech Lead → quan tâm vấn đề kỹ thuật

Sau đó tổng hợp thành 1 bản summary duy nhất.
```

👉 Cách này giúp bạn không bỏ sót góc nhìn.

---

# 4. Template output chuẩn (bạn nên dùng)

**📌 MEETING SUMMARY**

**1. Key Decisions**

* ...

**2. Action Items**

* [Tên] → Việc cần làm → Deadline

**3. Risks / Blockers**

* ...

**4. Open Questions**

* ...

**5. Next Steps**

* ...

---

# 5. Dùng AI để tự động hóa hoàn toàn (pro level)

## 🔹 Cách 1: Ghi âm → AI → Summary

* Ghi âm bằng điện thoại / Zoom
* Dùng:

  * Otter.ai
  * Notion AI
  * ChatGPT

👉 Copy transcript → dán vào prompt ở trên

---

## 🔹 Cách 2: Live note + AI refine

Trong meeting:

* Bạn ghi note thô kiểu:

  ```
  - A nói delay backend
  - B cần thêm dev
  - chưa chốt deadline
  ```

Sau meeting:
→ đưa vào AI → biến thành summary chuẩn

---

## 🔹 Cách 3: Auto follow-up (ít người dùng nhưng cực mạnh)

```id="sum3"
Dựa vào summary trên,
hãy viết email follow-up chuyên nghiệp cho team,
ngắn gọn, rõ action và deadline.
```

---

# 6. Kỹ thuật nâng cao (PM giỏi hay dùng)

## 🔥 A. Extract hidden insights

```id="sum4"
Từ meeting này,
có conflict ngầm, risk tiềm ẩn hoặc vấn đề chưa nói rõ nào không?
```

---

## 🔥 B. Detect accountability issue

```id="sum5"
Có action item nào chưa rõ owner hoặc deadline không?
```

---

## 🔥 C. Compress siêu ngắn (cho sếp)

```id="sum6"
Tóm tắt meeting này trong 3 dòng cho CEO.
```

---

# 7. Sai lầm phổ biến

* ❌ Chỉ yêu cầu “tóm tắt” (quá mơ hồ)
* ❌ Không yêu cầu action items
* ❌ Không kiểm tra lại output
* ❌ Không chuẩn hóa format

---

# 8. Workflow chuẩn bạn nên áp dụng

1. Ghi âm / ghi chú
2. Đưa vào AI → summary chuẩn
3. Extract action items
4. Gửi follow-up ngay sau meeting
5. Track trong Notion / Excel

---

# 9. Nếu bạn muốn nâng level nhanh

Hãy gửi cho tôi:

* 1 đoạn note meeting thực tế

Tôi sẽ:
👉 Tóm tắt lại cho bạn theo chuẩn PM xịn
👉 Chỉ ra insight + risk mà bạn có thể chưa thấy
