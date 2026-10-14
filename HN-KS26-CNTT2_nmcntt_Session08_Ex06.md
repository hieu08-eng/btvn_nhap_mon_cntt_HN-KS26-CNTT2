### Phần 1: Phân tích (Auditing)

* Điểm cực kỳ nguy hiểm: Lệnh Remove-Item \-Path "C:\\\*" \-Recurse \-Force xóa toàn bộ thư mục gốc ổ C:\\, làm hỏng hoàn toàn hệ điều hành Windows (gây màn hình xanh).  
* Ý nghĩa tham số:  
  * \-Path "C:\\\*": Chỉ định phạm vi toàn bộ ổ C:\\.  
  * \-Recurse: Xóa đệ quy tất cả thư mục/tệp con bên trong.  
  * \-Force: Ép buộc xóa cả tệp ẩn/chỉ đọc/đang khóa.  
* 3 Nguyên tắc vàng: Không tin tuyệt đối mã AI, luôn khoanh vùng đường dẫn cụ thể, và dùng \-WhatIf kiểm tra trước.

### Phần 2: Triển khai (safe\_cleanup.ps1)

PowerShell  
\<\#  
.SYNOPSIS  
    Script don dep an toan  
\#\>

Set-Location \-Path ".\\logs"  
Get-Content "system.log" | Select-String "WARNING" | Out-File \-FilePath "issues.txt" \-Encoding utf8  
Remove-Item \-Path ".\\\*.tmp" \-Force  
Write-Host "Don dep thanh cong\!" \-ForegroundColor Green

### Phần 3: Kiểm thử (Verify)

Chạy các lệnh sau trên PowerShell:

1. Xem báo cáo: Get-Content issues.txt  
2. Kiểm tra file tồn tại: Test-Path issues.txt (trả về True)  
3. Kiểm tra file .tmp đã xóa: Get-ChildItem

