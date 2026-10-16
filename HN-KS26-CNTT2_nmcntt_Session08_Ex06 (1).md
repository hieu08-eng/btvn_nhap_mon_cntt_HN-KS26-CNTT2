Dưới đây là phiên bản hoàn chỉnh của bài tập Sự cố tài liệu dự án trên GitHub theo chuẩn sinh viên, đã được loại bỏ hoàn toàn emoji:

## Phần 1\. Phân tích: Sai lầm của Nam và Ưu thế của Markdown

### 1\. Hai sai lầm của Nam

* Dùng file Rich Text (.docx) cho mã nguồn: Không hỗ trợ render trực tiếp trên GitHub và không tương thích với các công cụ quản lý mã nguồn.  
* Xung đột Git Conflict toàn cục: Cấu trúc nhị phân thay đổi liên tục khiến hệ thống Git không thể so sánh từng dòng (Git Diff), dẫn đến lỗi hỏng file toàn bộ khi cộng tác nhóm.

### 2\. Ưu thế của Markdown (Plain Text)

* Nhẹ hơn và An toàn hơn: Chỉ chứa văn bản thô, dung lượng cực nhỏ.  
* Đối chiếu bẫy dữ liệu: File Word mất 1 byte là hỏng toàn bộ (do vỡ cấu trúc XML nén), trong khi file Markdown chỉ bị lỗi ký tự nhỏ tại vị trí mất dữ liệu, phần còn lại vẫn đọc bình thường.

## Phần 2\. Hoàn thiện: Chuyển đổi sang Markdown (.md)

Markdown  
# Dự án GreenTech

*Hệ sinh thái nông nghiệp tự động hóa tối ưu hóa nguồn nước.*

## Tính năng chính  
\- \[x\] Giám sát cảm biến IoT thời gian thực.  
\- \[x\] Tự động hóa tưới tiêu.

## Thông số kỹ thuật  
| Thành phần | Model | Chức năng |  
| :--- | :--- | :--- |  
| \*\*SoC\*\* | ESP32 | Xử lý trung tâm |  
| \*\*Cảm biến\*\* | DHT22 | Đo nhiệt độ và độ ẩm |  
