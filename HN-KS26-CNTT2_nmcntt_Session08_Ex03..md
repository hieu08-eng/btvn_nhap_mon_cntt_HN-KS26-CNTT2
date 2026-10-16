# BÁO CÁO NHANH: TỐI ƯU HÓA TOKEN VỚI MARKDOWN CHO HỆ THỐNG "GREENSTECH"

## Phần 1\. Phân tích bài toán: Cơ chế Token và hiệu quả của AI

* Khái niệm Token: AI xử lý văn bản bằng cách cắt nhỏ thành các đoạn mã gọi là token (có thể là một từ, một phần từ hoặc dấu câu).  
* Vì sao Markdown giúp AI xử lý nhanh và tiết kiệm hơn?  
  * Ít ký tự thừa: Markdown sử dụng ký tự tối giản (\*\*, \#) thay vì các thẻ mở/đóng rườm rà như HTML (\<strong\>, \<div\>).  
  * Tiết kiệm chi phí & tăng tốc độ: Lượng token đầu vào giảm từ 30% \- 50%, giúp giảm chi phí API, tăng tốc độ phản hồi (giảm độ trễ cho người nông dân) và tránh việc bị tràn giới hạn bộ nhớ ngữ cảnh (Context Window).

## Phần 2\. So sánh Markdown vs HTML & Giải pháp

### 1\. Bảng so sánh nhanh

| Tiêu chí | Markdown | HTML |
| :---- | :---- | :---- |
| Cú pháp (Ví dụ in đậm) | \*\*Cây lúa\*\* (11 ký tự) | \<strong\>Cây lúa\</strong\> (23 ký tự) |
| Số token ước tính | Khoảng 2 tokens | Khoảng 5 – 6 tokens |
| Độ dễ đọc (Human-readable) | Cao: Gọn gàng, trực quan như văn bản thô. | Thấp: Bị rối mắt bởi các thẻ lệnh HTML. |
| Hiệu suất của AI | Tối ưu: Tránh nhiễu, AI tập trung vào nội dung tri thức. | Kém hơn: Tốn token cho các thẻ định dạng không cần thiết. |

### 2\. Giải pháp cho hệ thống "GreenTech"

* Đề xuất: Dùng Markdown làm chuẩn lưu trữ tri thức và truyền tải ngầm giữa Backend với AI. Khi hiển thị lên giao diện web/app cho người nông dân, hệ thống sẽ tự động biên dịch sang HTML.  
* Lý do: Giúp hệ thống vận hành với chi phí API thấp nhất, đồng thời giúp đội ngũ kỹ sư đọc hiểu và chỉnh sửa tài liệu hướng dẫn nông nghiệp nhanh chóng, không bị rối mắt.

