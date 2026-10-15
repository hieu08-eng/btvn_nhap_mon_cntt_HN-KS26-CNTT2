Phần 1: Phân tích & Đề xuất (Đa giải pháp)

1\. Phân tích yêu cầu để xác định rõ đầu vào (người dùng muốn gì) và đầu ra (AI cần trả lời thế nào).

2\. Phân tích ưu điểm và nhược điểm của Chiến lược A (văn xuôi) và Chiến lược B (Markdown 3 phần).

câu 1 

- đầu vào : sinh viên IT-101 chưa biết gì về lập trình, nhờ AI giải thích khái niệm "Markdown Parser" theo hướng cơ bản, dễ hiểu, đời thường.   
- Đầu ra : Câu trả lời ngắn gọn, trực quan, không dùng thuật ngữ phức tạp hay code rườm rà. 

câu 2   
Chiến lược A (Văn xuôi):

- Ưu điểm: Nhanh, tự nhiên, dễ gõ như nhắn tin.  
- Nhược điểm: AI dễ bỏ sót các yêu cầu khắt khe

Chiến lược B (Cấu trúc Markdown 3 phần):

- Ưu điểm: Phân tách rõ ràng (Bối cảnh, Khái niệm, Yêu cầu). AI tuân thủ tuyệt đối các ràng buộc.  
- Nhược điểm: soạn thảo lâu hơn chiến lược A.

Phần 2: So sánh & Lựa chọn

3\. Lập bảng so sánh 4 tiêu chí nghiệp vụ cho 2 chiến lược.

4\. Chốt lựa chọn: Bối cảnh nào nên dùng Chiến lược A? Bối cảnh nào nên dùng Chiến lược B? Lý giải dựa trên bảng so sánh.

câu 3 

| tiêu chí  | chiến lược A | chiến lược  |
| :---- | :---- | :---- |
| độ chính xác  | thấp \-\> trung bình | cao |
| token tiêu thụ | thấp | cao hơn chiến lược A không quá nhiều  |
| khả năng làm lại | kém | cao |
| đối với người mới  | dễ dùng với người  | trung bình  |

câu 4

- sử dụng chiến lược A khi hỏi nhanh các câu hỏi giao tiếp thông thường, không quan trọng định dạng.   
- sử dụng chiến lược B khi học tập, ôn thi, hoặc hỏi kiến thức kỹ thuật cần quy chuẩn chặt chẽ. ( ưu tiên tạo thói quen )

Phần 3: Thiết kế & Triển khai

5\. Dựa trên chiến lược bạn đánh giá phù hợp nhất cho sinh viên năm 1, hãy viết 1 Prompt mẫu để hỏi AI về khái niệm 'Token' (thuật ngữ trong Lesson 01).

6\. Trả lời 2 bẫy dữ liệu đã nêu.

câu 5 

\#\# Bối cảnh

Tôi là sinh viên năm 1 IT, chưa có nền tảng lập trình.

\#\# Khái niệm cần giải thích

Token 

\#\# Yêu cầu

\- Giải thích như một giảng viên đại học lâu 

\- Giới hạn trong khoảng 100- từ

\#\# Không cần

\- Công thức toán học phức tạp

\- Code lập trình

câu 6

- Bẫy 1 (Đặt nhầm nội dung sai phần): AI sẽ giảm độ tập trung vào yêu cầu đó vì nó tìm kiếm theo từ khóa heading (\#\# Yêu cầu). Kết quả có thể bị sai lệch (ví dụ: vẫn sinh ra code hoặc viết quá dài).  
- Bẫy 2 (Khi nào dùng Chiến lược A): Dùng khi chat nhanh trên điện thoại hoặc hỏi các câu hỏi chung chung, đời sống không cần kiểm soát nghiêm ngặt đầu ra của AI.

