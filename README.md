# Day 22 Monetization Model

## Case mẫu đã hoàn thiện

Sản phẩm: **AI xác nhận đơn hàng cho shop online Việt Nam**.

Agent nhắn tin xác nhận đơn COD, trả lời câu hỏi đơn giản và cập nhật trạng thái vào OMS. Một job chỉ được tính khi khách xác nhận đơn và OMS ghi `Đã xác nhận`; đơn hủy, không liên lạc được hoặc phải người xử lý không bị tính phí.

> Đây là case mẫu phục vụ lab, không phải dữ liệu vận hành của một shop thật. Các số containment, token/job, HITL, giá trị khách hàng và CAC là giả định. Cần thay bằng log/eval/pilot trước khi bán Outcome.

## Kết luận mô hình

- Budget line: vận hành bán hàng và đội chốt đơn; buyer là chủ shop hoặc Head of Operations.
- Value Metric: Outcome, $0.75 mỗi đơn xác nhận hợp lệ.
- Phương án HITL: Biến thể B, startup chịu chi phí ca ngoại lệ để vẫn giao kết quả.
- Kênh 90 ngày đầu: PLG qua Sapo App Store; không chạy sales-led trước khi chứng minh activation tự phục vụ.
- Pain Moment: 19h-22h, đội chốt đơn đang xử lý đơn mới trong Sapo OMS và Zalo OA.

## Nguồn và ngày kiểm tra

- Anthropic Claude pricing, kiểm tra 09/10/2026: https://platform.claude.com/docs/en/about-claude/pricing
- Intercom Fin: https://fin.ai/pricing
- Zendesk outcome pricing: https://www.zendesk.com/blog/ai/agentic-ai/outcome-based-pricing/

## Việc cần làm trước khi dùng với khách thật

1. Chạy eval 500 đơn có nhãn và thay containment/precision bằng số đo.
2. Hoàn thành Procurement Q&A cho dữ liệu đơn hàng, quyền cập nhật OMS và data exit.
3. Pilot 4 tuần; chỉ giữ Outcome nếu merchant đồng ý định nghĩa đơn xác nhận hợp lệ.
