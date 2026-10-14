### **Phần 1: Phân tích**

Giải thích tại sao máy tính bị "Not Responding" khi mở bằng Notepad và tại sao lệnh `cat` bị lỗi trong môi trường CMD. Giải thích thêm tại sao `cat` lại hoạt động trong PowerShell.

- notepad bị lỗi vì tệp log 800mb quá lớn khiến máy bị tốn RAM và thời gian xử lý  
- lệnh cat bị lỗi trong cmd vì cmd không hỗ trợ lệnh cat  
- lệnh cat chạy trong PS vì nó là alias của lệnh gc

### **Phần 2: Hoàn thiện**

Đưa ra bộ lệnh chuẩn trên **PowerShell** để:

1. Xem toàn bộ nội dung tệp .  
2. Chỉ xem 10 dòng cuối cùng để kiểm tra lỗi mới nhất

lệnh powershell

1. 

gc `server_log_800MB.log`

2. 

`gc sever_log_800MB.log -tail 10 -wait`

