phần 1

- Sử dụng mô hình Pipeline: Đọc tệp ➔ Lọc từ khóa ➔ Đếm kết quả  
- Thực hiện bằng duy nhất **1 dòng lệnh** trên **PowerShell**

Đọc tệp log

    ↓

Lọc dòng chứa "TIMEOUT"

    ↓

Loại dòng chứa "NOT TIMEOUT"

    ↓

Đếm số dòng còn lại

    ↓

Trả về một con số tổng

phần 2 

lệnh PS

gc access.log | select-string “TIME OUT” | mearsure-object

