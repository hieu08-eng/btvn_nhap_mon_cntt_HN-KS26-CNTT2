### Phần 1: Thiết kế kiến trúc

1. Header block: \# Thông tin script (Tên, tác giả, ngày tạo dạng comment \#)  
2. Biến cấu hình: \$duong\_dan\_log \= "server.log" (Khai báo các đường dẫn tệp bằng biến \$variable)  
3. Thông báo tiến trình: Dùng Write-Host để báo trạng thái chạy của script ra màn hình.  
4. Logic xử lý: Đọc log (Get-Content) ➔ Lọc lỗi (Select-String) ➔ Ghi kết quả nối tiếp vào file báo cáo (\>\>).

### Phần 2: Sản phẩm (Tệp mã nguồn `auto_report.ps1`**)**

Bạn tạo tệp auto\_report.ps1 với nội dung đơn giản sau:

PowerShell  
\<\#  
.SYNOPSIS  
    Script tu dong loc loi 404  
\#\>

\$log \= "server.log"  
\$report \= "daily\_report.txt"

Write-Host "=== HE THONG TU DONG LOC LOG \===" \-ForegroundColor Cyan  
Write-Host "Dang quet loi 404..." \-ForegroundColor Yellow

"=== HE THONG TU DONG LOC LOG \===" | Out-File \-FilePath \$report \-Encoding utf8  
Get-Content \$log | Select-String "404" | Add-Content \-Path \$report \-Encoding utf8

Write-Host "Hoan tat\!" \-ForegroundColor Green  
