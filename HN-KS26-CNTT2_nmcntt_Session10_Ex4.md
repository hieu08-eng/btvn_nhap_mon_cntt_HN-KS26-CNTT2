## Phần 1 – Hoàn thiện SRS bằng Heading Styles và Auto TOC

### 1. Cấu trúc phân cấp tiêu đề (3 cấp)
* **Heading 1:** 1. Giới thiệu dự án
  * **Heading 2:** 1.1. Mục tiêu
  * **Heading 2:** 1.2. Đối tượng sử dụng
* **Heading 1:** 2. Chức năng hệ thống
  * **Heading 2:** 2.1. Quản lý mượn sách
    * **Heading 3:** 2.1.1. Luồng mượn sách qua thẻ sinh viên
  * **Heading 2:** 2.2. Quản lý trả sách
* **Heading 1:** 3. Yêu cầu bảo mật

### 2. Nội dung mô tả chi tiết
* **Dưới mục 2. Chức năng hệ thống (Yêu cầu chức năng - Functional Requirements):**
  > Hệ thống cho phép sinh viên tra cứu và đăng ký mượn sách trực tuyến bằng mã thẻ sinh viên một cách nhanh chóng. Đồng thời, thủ thư có thể dễ dàng cập nhật trạng thái mượn trả, kiểm soát hạn nộp và tự động ghi nhận lịch sử giao dịch của người dùng.
* **Dưới mục 3. Yêu cầu bảo mật (Yêu cầu phi chức năng - Non-functional Requirements):**
  > Toàn bộ dữ liệu thông tin cá nhân của sinh viên và lịch sử mượn sách phải được mã hóa an toàn nhằm ngăn chặn các hành vi truy cập trái phép. Hệ thống cần đảm bảo thời gian phản hồi truy vấn dưới 2 giây và duy trì độ ổn định liên tục 24/7 để phục vụ người dùng.

### 3. Hướng dẫn thao tác Auto TOC trong Word
* **Bước 1:** Bôi đen từng dòng tiêu đề và gán đúng định dạng cấp độ trong thẻ *Home → Styles* (chọn `Heading 1`, `Heading 2`, `Heading 3`).
* **Bước 2:** Di chuyển con trỏ chuột lên đầu trang tài liệu, vào thẻ *References → Table of Contents* và chọn mẫu mục lục tự động (Automatic Table).
* **Bước 3:** Thêm một đoạn văn bản bất kỳ hoặc dùng lệnh ngắt trang (`Ctrl + Enter`) để đẩy mục "3. Yêu cầu bảo mật" sang trang tiếp theo.
* **Bước 4:** Nhấp chuột phải vào bảng mục lục vừa tạo, chọn **Update Field → Update entire table** để cập nhật lại chính xác số trang mới sau khi thay đổi.

---

## Phần 2 – Chuẩn hóa dữ liệu và AutoFilter

### 1. Bảng chỉ ra 3 lỗi vi phạm 5 Quy tắc Vàng
| Lỗi | Vị trí (hàng) | Quy tắc bị vi phạm |
| :---: | :---: | :--- |
| **1** | Hàng 1 | **Vi phạm quy tắc Không merge ô:** Ô `A1:E1` bị gộp chung làm tiêu đề lớn, làm hỏng cấu trúc bảng dữ liệu phẳng của Database. |
| **2** | Hàng 5 | **Vi phạm quy tắc Không có hàng trống:** Tồn tại một dòng trống hoàn toàn giữa các record, gây ngắt quãng vùng dữ liệu khi thao tác lọc hoặc tính toán. |
| **3** | Hàng 6 | **Vi phạm quy tắc Không đưa dòng tổng cộng vào vùng dữ liệu:** Dòng "Tổng cộng" nằm lọt thỏm giữa danh sách mượn sách, khiến các hàm tính toán tổng tự động bị sai lệch. |

### 2. Bảng dữ liệu sau khi chuẩn hóa
| MSSV | Họ Tên | Mã Sách | Ngày Mượn | Tình Trạng |
| :--- | :--- | :--- | :--- | :--- |
| SV001 | Nguyễn Văn An | S001 | 01/10/2026 | Đang mượn |
| SV002 | Trần Thị Bình | S002 | 03/10/2026 | Quá hạn |
| SV003 | Lê Văn Cường | S003 | 10/10/2026 | Đã trả |
| SV004 | Phạm Thu Hà | S099 | 12/10/2026 | Đang mượn |

*(Lưu ý: Tiêu đề lớn "DANH SÁCH MƯỢN SÁCH THÁNG 10" được đưa lên phía trên bảng, dòng tổng cộng "2 phiếu" được dịch chuyển xuống phía dưới cùng của bảng).*

### 3. Phân biệt Record và Field
* **Field (Cột / Trường dữ liệu):** Là các thuộc tính đơn lẻ cấu thành nên bảng. Ví dụ: Cột `MSSV`, `Họ Tên`, hay `Mã Sách` là các Field đại diện cho thông tin cụ thể.
* **Record (Dòng / Bản ghi):** Là tập hợp đầy đủ thông tin của một đối tượng cụ thể. Ví dụ: Dòng dữ liệu `SV001 | Nguyễn Văn An | S001 | 01/10/2026 | Đang mượn` chính là 1 Record hoàn chỉnh của sinh viên Nguyễn Văn An.

### 4. Thao tác bật AutoFilter và lọc dữ liệu
* **Cách bật:** Nhấp chuột vào bất kỳ ô nào trong vùng dữ liệu, nhấn tổ hợp phím `Ctrl + Shift + L` để xuất hiện các mũi tên lọc ở hàng tiêu đề.
* **Cách lọc trạng thái "Quá hạn":** 
  1. Nhấp vào mũi tên lọc ở cột **Tình Trạng**.
  2. Bỏ chọn tất cả các mục, sau đó tích chọn vào ô có chữ **"Quá hạn"**.
  3. Nhấn **OK** để hệ thống hiển thị danh sách các sinh viên đang bị quá hạn nộp sách.

---

## Phần 3 – Nối dữ liệu bằng VLOOKUP

### 1. Công thức VLOOKUP cơ bản cho ô thêm cột Tên Sách
* Giả sử cột Tên Sách là cột mới thêm, mã sách nằm ở cột C. Công thức tra cứu từ sheet `DanhMucSach` (cột Mã Sách là cột 1, Tên Sách là cột 2):
  ```excel
  =VLOOKUP(C3, DanhMucSach!$A$2:$C$4, 2, FALSE)
2. Nguyên nhân lỗi ở dòng Mã Sách S099 (Hàng 8)
Lỗi trả về: #N/A

Nguyên nhân: Do mã sách S099 hoàn toàn không tồn tại trong bảng tra cứu DanhMucSach (chỉ có từ S001 đến S003). Do tham số cuối cùng đặt là 0 (hoặc FALSE) để tìm kiếm chính xác tuyệt đối, khi không tìm thấy mã khớp, Excel lập tức báo lỗi #N/A (Not Available).

3. Công thức hoàn chỉnh bọc IFERROR
Để khắc phục lỗi hiển thị xấu xí và thay bằng thông báo thân thiện, em sử dụng hàm IFERROR bọc bên ngoài như sau:

Excel
=IFERROR(VLOOKUP(C3, DanhMucSach!$A$2:$C$4, 2, FALSE), "Không tìm thấy sách")
Phần 4 – Slide báo cáo tiến độ
1. Nội dung Slide báo cáo tiến độ (Áp dụng nguyên lý 1 Slide – 1 Thông điệp)
Assertion Title (Tiêu đề kết luận):

"Đã chuẩn hóa thành công cơ sở dữ liệu mượn sách và xử lý triệt để 100% mã lỗi phát sinh nhờ hàm IFERROR."

Content Area (Con số / Kết luận nổi bật):

Tổng số bản ghi xử lý: 4 sinh viên mượn sách.

Tỷ lệ lỗi dữ liệu đã khắc phục: 1 mã ngoài danh mục (S099) được kiểm soát an toàn bằng thông báo "Không tìm thấy sách".

Loại biểu đồ lựa chọn & Lý do:

Loại biểu đồ: Donut Chart (Biểu đồ vành khuyên) hoặc Bar Chart (Biểu đồ cột).

Lý do chọn: Dùng để phân loại tỷ lệ sách theo các trạng thái (Đang mượn, Quá hạn, Đã trả). Biểu đồ giúp người xem (giảng viên/nhà đầu tư) nhìn nhận trực quan ngay lập tức tình trạng mượn sách của tháng chỉ trong vòng chưa đầy 3 giây mà không cần phải dò từng dòng số liệu.

2. Áp dụng Rule 10/20/30
Quy tắc 10 slide: Slide báo cáo kết quả này là slide số 3 trong tổng số 10 slide của toàn bộ bài thuyết trình đồ án.

Quy tắc 20 phút: Tổng thời gian thuyết trình toàn bộ bài là 20 phút, và riêng slide tổng kết kỹ thuật này sẽ được trình bày gọn gàng trong vòng 2 phút.
