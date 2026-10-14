### **Phần 1: So sánh**

Lập bảng so sánh hai toán tử về:

* Cơ chế hoạt động trong PowerShell.  
* Rủi ro mất dữ liệu.  
* Ngữ cảnh sử dụng thực tế (Ca sáng vs Theo dõi 24/7).  
* Encoding file đầu ra (dựa trên phần "Kiến thức mở rộng" ở mục 3).

| tiêu chí | \>  | \>\> |
| :---- | :---- | :---- |
| cơ chế | xóa sạch tệp bị ghi đè và thêm nội dung mới | giữ nguyên và tiếp tục ở cuối tệ |
| rủi ro mất dữ liệu | rất  | thấp |
| ngữ cảnh  | tạo mới báo cáo mỗi ngày | hệ thống chạy lâu dài tích lũy |
| encoding | mặc định UTF-16 | giống toán tử \> |

### **Phần 2: Lựa chọn**

Chốt giải pháp tối ưu cho việc ghi nhật ký lỗi phát sinh liên tục trong ngày và lập luận lý do. Có thể đề xuất thêm cách dùng `Add-Content` hoặc `Out-File -Append -Encoding utf8` nếu phù hợp.

giải pháp tốt nhất là dùng add-content và chỉ định UTF-8

lệnh PS

Get-Content server.log | Select-String "ERROR" | Add-Content daily\_report.txt \-Encoding utf8

