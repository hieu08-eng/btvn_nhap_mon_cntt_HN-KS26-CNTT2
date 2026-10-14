### **Phần 1: Phân tích**

Chỉ ra sự nhầm lẫn của An về mặt tư duy khi sử dụng lệnh tìm kiếm trong PowerShell. Giải thích sự khác biệt giữa `Get-ChildItem` và `Select-String`.

An nhầm giữa việc phân biệt tìm tên tệp và tìm nội dung trong tệp

- select-string : tìm nội dung, từ khoá bên trong tệp  
- get-childitem : tìm tệp và thư mục

### **Phần 2: Hoàn thiện**

Viết lại câu lệnh chuẩn trên **PowerShell** để lọc từ khóa `error` (không phân biệt hoa thường) và hiển thị kèm số thứ tự dòng để kỹ sư dễ tra cứu.

lệnh  
select-string “access.log” “error”