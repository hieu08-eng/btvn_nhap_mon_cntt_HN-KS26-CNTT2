\#\# Phần 1: Phân tích bài toán (I/O)

\#\#\# 1\. Bảng xác định thông số VLOOKUP cho các cột  
| Cột cần điền | Lookup\_value (Giá trị dò tìm) | Table\_array (Vùng tra cứu) | Col\_index\_num (Số thứ tự cột) |  
| :--- | :--- | :--- | :--- |  
| \*\*Cột D (Tên Tác Giả)\*\* | Ô chứa mã tác giả (ví dụ: \`C2\`) | \`'DanhMucTacGia'\!$A$1:$E$100\` | \`2\` |  
| \*\*Cột E (Phòng trình bày)\*\* | Ô chứa mã tác giả (ví dụ: \`C2\`) | \`'DanhMucTacGia'\!$A$1:$E$100\` | \`4\` |  
| \*\*Cột F (Thù lao)\*\* | Ô chứa mã tác giả (ví dụ: \`C2\`) | \`'DanhMucTacGia'\!$A$1:$E$100\` | \`5\` |

\#\#\# 2\. Đề xuất giải pháp xử lý bẫy dữ liệu  
\* \*\*Xử lý Bẫy 1 (Khoảng trắng thừa):\*\* Sử dụng hàm \`TRIM()\` bao bọc giá trị dò tìm (\`TRIM(C2)\`) để tự động cắt bỏ các khoảng trắng vô hình trước khi đem đi so khớp.  
\* \*\*Xử lý Bẫy 2 (Dữ liệu không tồn tại gây lỗi \`\#N/A\`):\*\* Sử dụng hàm \`IFERROR()\` bọc bên ngoài toàn bộ hàm VLOOKUP. Cú pháp: \`IFERROR(VLOOKUP(...), "Chưa cập nhật")\` để khi không tìm thấy mã, ô sẽ hiển thị thông báo thân thiện thay vì báo lỗi.  
\* \*\*Xử lý Bẫy 3 (Trôi vùng tra cứu khi kéo công thức):\*\* Thêm dấu đô la (\`\$\`) vào trước tên cột và số hàng của vùng tra cứu (ví dụ: \`$A$1:$E$100\`) để cố định tuyệt đối bảng danh mục.

\#\#\# 3\. Thiết kế các bước thực hiện trong Excel  
\* \*\*Bước 1:\*\* Đặt chuột tại ô \*\*D2\*\* (cột Tên Tác Giả của sheet \`DanhSachBaoCao\`).  
\* \*\*Bước 2:\*\* Xây dựng cấu trúc hàm \`VLOOKUP\` kết hợp với \`TRIM\` để tra cứu cột tên tác giả (cột số 2\) từ sheet \`DanhMucTacGia\`.  
\* \*\*Bước 3:\*\* Lồng toàn bộ công thức vào trong hàm \`IFERROR\` để trả về chuỗi \`"Chưa cập nhật"\` nếu phát sinh lỗi.  
\* \*\*Bước 4:\*\* Thêm các dấu cố định tuyệt đối \`\$\` vào vùng dữ liệu tham chiếu để chuẩn bị kéo công thức.  
\* \*\*Bước 5:\*\* Kéo (fill handle) công thức từ ô D2 xuống hết danh sách (đến dòng 81).  
\* \*\*Bước 6:\*\* Sao chép công thức sang cột E (Phòng) và cột F (Thù lao), sau đó chỉ cần chỉnh sửa lại thông số \`Col\_index\_num\` thành \`4\` và \`5\`.

\---

\#\# Phần 2: Triển khai & Chống lỗi

\#\#\# 4\. Công thức hoàn chỉnh cho ô D2 (Tên Tác Giả)  
\`\`\`excel  
\=IFERROR(VLOOKUP(TRIM(C2), 'DanhMucTacGia'\!$A$1:$E$100, 2, FALSE), "Chưa cập nhật")

### 5\. Công thức cho ô E2 (Phòng) và F2 (Thù lao) & Giải thích

* Công thức ô E2 (Phòng trình bày):  
* Excel

\=IFERROR(VLOOKUP(TRIM(C2), 'DanhMucTacGia'\!$A$1:$E$100, 4, FALSE), "Chưa cập nhật")

*   
*   
* Công thức ô F2 (Thù lao):  
* Excel

\=IFERROR(VLOOKUP(TRIM(C2), 'DanhMucTacGia'\!$A$1:$E$100, 5, FALSE), "Chưa cập nhật")

*   
*   
* Giải thích: Vì cả 3 cột thông tin (Tên tác giả, Phòng, Thù lao) đều chung một nguồn dữ liệu gốc ('DanhMucTacGia'\!$A$1:$E$100\) và dựa trên cùng một mã tra cứu (TRIM(C2)), ta chỉ cần thay đổi số thứ tự cột cần lấy dữ liệu (Col\_index\_num lần lượt là 2, 4, 5\) mà không cần phải viết lại toàn bộ cấu trúc hàm.

### 6\. Giải thích hiện tượng khi bỏ dấu \$ trong Table\_array

* Hiện tượng: Nếu ta viết A1:E100 mà thiếu dấu \$ (địa chỉ tương đối), khi kéo công thức trượt xuống các dòng bên dưới, Excel sẽ tự động dịch chuyển tỉ lệ tọa độ của bảng tra cứu theo.  
* Ví dụ cụ thể:  
  * Tại ô D2, công thức dò tìm trong vùng: 'DanhMucTacGia'\!A1:E100.  
  * Khi kéo xuống ô D5, vùng tra cứu sẽ bị trôi thành: 'DanhMucTacGia'\!A4:E103.  
  * Điều này làm cho các dòng dữ liệu nằm ở đầu bảng DanhMucTacGia bị lệch ra ngoài vùng tìm kiếm, dẫn đến kết quả trả về bị sai lệch hoặc hiển thị lỗi \#N/A mặc dù dữ liệu thực tế vẫn tồn tại.

