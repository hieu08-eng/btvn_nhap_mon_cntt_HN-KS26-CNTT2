# BÁO CÁO BÀI TẬP LỚN: HỆ THỐNG QUẢN LÝ HẠ TẦNG GREENTECH

## 1\. Cấu trúc thư mục dự án (Thư mục greentech-system)

Dự án được tạo các thư mục cơ bản để lưu trữ tài liệu, code và dữ liệu:

* docs/: Chứa hướng dẫn sử dụng (README.md).  
* scripts/: Chứa file chạy tự động hóa (auto\_report.bat).  
* data/: Chứa file Excel quản lý thiết bị và file nhật ký.  
* backup/: Lưu các báo cáo sự cố được xuất ra.

## 2\. File tự động lọc lỗi (scripts/auto\_report.bat)

Đoạn mã lệnh đơn giản dùng trong Windows để tìm các lỗi CRITICAL và ERROR từ file log:

Code snippet  
@echo off  
color 0A  
echo \===================================  
echo     BAO CAO LOI HE THONG GREENTECH  
echo \===================================

:: Tim kiem loi va ghi vao file bao cao trong thu muc backup  
findstr /C:"CRITICAL" /C:"ERROR" ..\\data\\log-he-thong.log \> ..\\backup\\bao-cao-su-co.txt

echo Da loc xong loi va luu vao thu muc backup\!  
pause

## 3\. Hướng dẫn sử dụng (docs/README.md)

Markdown  
\# Quản lý Hạ tầng GreenTech \- Đồ án Nhập môn CNTT

## Cách chạy chương trình tự động lọc lỗi:  
1\. Mở thư mục \`scripts\`.  
2\. Chạy file \`auto\_report.bat\`.  
3\. Kiểm tra kết quả trong thư mục \`backup/bao-cao-su-co.txt\`.

## Danh sách thiết bị cơ bản:  
\- Cảm biến IoT 01 (RAM 4GB, SSD 128GB)  
\- Cảm biến IoT 02 (RAM 8GB, SSD 256GB)

## 4\. Cách dùng hàm VLOOKUP trong Excel (data/quan-ly-thiet-bi.xlsx)

Ở bảng quản lý trạng thái trạm, để tự động điền tên thiết bị từ mã linh kiện, bạn dùng công thức cơ bản sau tại ô cần điền:

Excel  
=VLOOKUP(A2, 'danh-muc-linh-kien'\!A:D, 2, FALSE)

* A2: Mã linh kiện cần tra cứu.  
* danh-muc-linh-kien\!A:D: Bảng danh mục linh kiện gốc.  
* 2: Lấy cột thứ 2 (Tên thiết bị).  
* FALSE: Tìm kiếm chính xác mã.

