# Individual reflection — Nguyễn Hoàng Việt Hùng (2A202600164)

## 1. Role
 + prompt engineer. Phụ trách cấu hình flow, implement chatbot và viết system prompt.

## 2. Đóng góp cụ thể
- Thiết kế agent flow gồm 5 node: Mood Parsin -> Clarify Node -> Toolcalling -> Selection -> Suggestion
- Viết system prompt cho mỗi node, phải sửa nhiều lần để node hoàn thành đúng nhiệm vụ

## 3. SPEC mạnh/yếu
- Mạnh nhất: failure modes — nhóm nghĩ ra được case "triệu chứng chung chung"
  mà AI gợi ý quá rộng, và có mitigation cụ thể (hỏi thêm câu follow-up)
- Yếu nhất: ROI — 3 kịch bản thực ra chỉ khác số user, assumption gần giống nhau.
  Nên tách assumption rõ hơn (VD: conservative = chỉ dùng ở 1 chi nhánh,
  optimistic = rollout toàn hệ thống)

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