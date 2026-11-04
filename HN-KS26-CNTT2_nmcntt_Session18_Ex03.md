

## 1. Báo cáo phân tích (Mô hình IPO)

Trong tình huống máy tính cá nhân bị nghi ngờ nhiễm mã độc **Infostealer** (chuyên đánh cắp cookies, session token, mật khẩu đã lưu trên trình duyệt), việc xử lý cần tuân thủ nghiêm ngặt nguyên tắc: **Cô lập trước - Xử lý sau**.

### **Input (Dấu hiệu nhận diện sự cố)**
* **Hành vi tài khoản bất thường:** Tài khoản Facebook, Google liên tục bị đăng xuất, xuất hiện các phiên đăng nhập lạ (Active Sessions) từ các quốc gia hoặc thiết bị khác mà bản thân không hề thực hiện.
* **Cảnh báo bảo mật:** Nhận được email hoặc thông báo đổi mật khẩu, mã OTP khôi phục tài khoản xuất hiện liên tục.
* **Tự động phát tán nội dung độc hại:** Tài khoản cá nhân tự động gửi tin nhắn rác cho bạn bè, đăng bài quảng cáo hoặc tự động tạo các commit/repository lạ trên GitHub.
* **Dấu hiệu trên máy tính:** Quạt máy tính chạy lớn ẩn, xuất hiện tiến trình lạ ngốn CPU/RAM, hoặc vừa tải/cài đặt các phần mềm crack, tool bản quyền lậu từ các nguồn không chính thống.

### **Process (Quy trình cấp cứu 4 bước)**
1. **Ngắt kết nối mạng (Isolate):** Rút ngay dây mạng hoặc tắt Wi-Fi của máy tính bị nhiễm để chặn mã độc truyền dữ liệu đánh cắp về máy chủ C2 (Command and Control) của hacker.
2. **Thu hồi quyền truy cập (Revoke Access):** Sử dụng một thiết bị hoàn toàn sạch khác để đăng xuất toàn bộ phiên làm việc cũ và thu hồi các API tokens / OAuth tokens.
3. **Đổi thông tin xác thực (Change Credentials):** Thay đổi mật khẩu mới mạnh hơn cho toàn bộ các tài khoản quan trọng và kích hoạt Xác thực 2 bước (2FA) bằng ứng dụng Authenticator.
4. **Làm sạch hệ thống (Remediate):** Quét virus toàn diện hoặc cài đặt lại hệ điều hành (Format / Reinstall Windows) nếu mã độc đãâm sâu vào hệ thống để đảm bảo an toàn tuyệt đối.

### **Output (Hệ thống sau khi xử lý)**
* **Hệ thống sạch:** Máy tính đã được cách ly, quét sạch mã độc hoặc cài lại win mới tinh.
* **Tài khoản an toàn:** Các phiên đăng nhập cũ bị vô hiệu hóa hoàn toàn, kẻ tấn công bị đá ra khỏi hệ thống.
* **Bảo mật nhiều lớp:** Các tài khoản cốt lõi được bảo vệ bằng mật khẩu mới kết hợp 2FA, sẵn sàng trở lại trạng thái làm việc bình thường.

---

## 2. Triển khai chi tiết các thao tác kỹ thuật

### **A. Đổi mật khẩu từ thiết bị khác (Google / Facebook)**
> **Lưu ý quan trọng:** Tuyệt đối không dùng chiếc máy tính đang nghi nhiễm để đổi mật khẩu, vì mã độc có thể đang keylogger hoặc đọc trực tiếp mật khẩu mới của bạn. Hãy dùng điện thoại cá nhân hoặc một máy tính khác đã được kiểm tra an toàn.

1. Sử dụng thiết bị sạch, truy cập vào trang quản lý tài khoản:
2. Tìm đến mục **Mật khẩu (Password)** và tiến hành đổi mật khẩu mới (kết hợp chữ hoa, chữ thường, số và ký tự đặc biệt).
3. Sau khi đổi xong, kéo xuống phần **Các thiết bị của bạn (Your devices)** / Phiên đăng nhập, chọn **Đăng xuất khỏi tất cả các thiết bị khác (Sign out of all other sessions)** để hủy toàn bộ token phiên làm việc cũ đang bị hacker nắm giữ.

---

### **B. Hướng dẫn "Revoke Token" trên GitHub**
Nếu tài khoản GitHub bị xâm phạm hoặc bạn từng cấp quyền cho các ứng dụng lạ, việc thu hồi token là cực kỳ quan trọng để bảo vệ mã nguồn:

1. Đăng nhập vào GitHub bằng thiết bị an toàn.
2. Nhấn vào avatar ở góc trên bên phải $\rightarrow$ chọn **Settings**.
3. Cuộn xuống menu bên trái dưới cùng, chọn **Developer settings**.
4. Tiến hành kiểm tra và thu hồi tại các mục sau:
   * **Personal access tokens:** Vào mục *Tokens (classic)* hoặc *Fine-grained tokens*, tìm các token nghi ngờ và nhấn **Revoke**.
   * **OAuth Apps:** Kiểm tra danh sách các ứng dụng bên thứ ba liên kết với tài khoản và nhấn **Revoke** với các ứng dụng không rõ nguồn gốc.
   * **GitHub Apps:** Kiểm tra các ứng dụng tích hợp tương tự và thu hồi quyền truy cập.

---
*Bài làm hoàn thành phục vụ môn Nhập Môn Công Nghệ Thông Tin.*
