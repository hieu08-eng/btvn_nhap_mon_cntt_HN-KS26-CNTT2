báo cáo phân tích : 

1\. Vẽ sơ đồ 3 bước (stdout → | → stdin) mô tả luồng dữ liệu chạy trong câu lệnh PowerShell của bạn.

gc access.log (stdout) | (pipe) select-string “TIME OUT” (stdin) | (pipe) Measure-Object \-Line (stdin) 

### Triển khai:

2\. Viết câu lệnh PowerShell nối 3 bước (**Đọc file | Lọc chữ | Đếm dòng**) hoàn chỉnh, cho ra một con số duy nhất.

gc access.log | select-string "TIMEOUT" | Measure-Object \-Line 

