# Individual reflection — Nguyễn Hoàng Việt Hùng (2A202600164)

## 1. Role
 + agent workflow, prompt engineer, backend support

## 2. Đóng góp cụ thể
- Thiết kế agent flow gồm 5 node: Mood Parsin -> Clarify Node -> Toolcalling -> Selection -> Suggestion
- Viết system prompt cho mỗi node, phải sửa nhiều lần để node hoàn thành đúng nhiệm vụ

## 3. SPEC mạnh/yếu
Điểm mạnh nhất (The Strongest Points)
- Định nghĩa rõ ràng "Kill Criteria" (Tiêu chí khai tử)
Việc đo lường rõ ràng Unit Economics (Chi phí trên mỗi đơn vị xử lý) chứng tỏ team hiểu rõ bài toán kinh doanh chứ không chỉ biết code AI.

Điểm yếu nhất (The Weakest Points & Cần cải thiện)
- Mâu thuẫn ở "Correction Path" (Luồng sửa lỗi) và "Session Memory"

- Ở Phần 2, spec mô tả luồng người dùng nhắn "Phim này bạo lực quá, tôi cần nhãn PG-13" và AI trả lời lại. Nhưng ở Phần 6, phần Giới hạn lại ghi: "Chưa có Session Memory hoàn chỉnh (chỉ giải quyết tốt Single-turn query)". Không có bộ nhớ (Memory), khi người dùng chat câu thứ 2 (sửa lỗi), Agent sẽ không biết "phim này" là phim nào, dẫn đến đứt gãy hội thoại. Luồng Correction Path hiện tại mô tả mang tính lý thuyết nhưng thực tế kỹ thuật MVP chưa đáp ứng được.

- Cách cải thiện: Cần bổ sung ngay một cơ chế lưu trữ Context ngắn hạn (ví dụ: truyền lại mảng top_k cũ vào input của lượt chat mới) để AI có ngữ cảnh sửa sai.

## 4. Đóng góp khác
- Test prompt với những kịch bản khác nhau, ghi kết quả vào prompt-tests.jsonm, log vào prompt-tests-log.log, screenshot vào prompt-tests-screenshot folder.
- Từ cấu trúc flow tạo prompt để sinh slide bằng Gamma.ai
- Hỗ trợ backend
## 5. Điều học được
- Tư duy phải thay đổi. Trước đây em thường tư duy theo hướng mình phải làm chức năng này, chức này hay, chức năng này cao siêu mà không nghĩ đến user. Sản phẩm phải phục vụ user, bắt được nỗi đau của họ. Hackathon này nhóm em chỉ build 1 chức năng duy nhất nhưng cũng cảm thấy hài lòng vì nó đã đúng khá chính xác nhu cầu người dùng 

## 6. Nếu làm lại
- Với tư duy đã thay đổi, em sẽ ngay lập tức hoàn thành các kịch bản chính xác hơn về người dùng thay vì mất thời gian vào những thứ rule-base hay các sản phẩm truyền thống khác có khả năng thực hiện.
- Cấu hình thêm augmentaion, làm lại sẽ hoàn thành chức năng nhanh hơn có thể tối ưu được UX

## 7. AI giúp gì / AI sai gì
- **Giúp:** Dùng Gemini để implement workflow theo các node đã được xác định trong workflow
- **Sai/mislead:** ban đầu Gemini làm cho bước brainstorming phình quá to, hầu như những chức năng, usecase được đề xuất không khả thi hoặc không mới
  Bài học: Phải bước tự nhận thức về sản phẩm không dựa dẫm vào AI.
