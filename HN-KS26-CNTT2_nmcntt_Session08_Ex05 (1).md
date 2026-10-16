# Phần 1\. Phân tích: Input/Output và Sơ đồ phần cứng

* Input (Đầu vào): Dữ liệu cảm biến (nhiệt độ, độ ẩm đất, độ ẩm không khí) và lệnh điều khiển thủ công từ người nông dân.  
* Process (Xử lý): Vi điều khiển SoC (CPU) đọc dữ liệu, thực hiện chu kỳ lệnh để so sánh với ngưỡng cài đặt.  
* Output (Đầu ra): Tín hiệu bật/tắt máy bơm nước, van điện từ và hiển thị trạng thái màn hình.  
* Sơ đồ phần cứng:  
  \[ Cảm biến IoT \] \---\> \[ SoC / Vi điều khiển (CPU/RAM) \] \---\> \[ Máy bơm / Van nước \]

## Phần 2\. Triển khai: File README.md

Markdown  
\# Smart-Farm IoT System

\*Hệ thống quản lý và tự động hóa chăm sóc hoa lan thông minh cho trang trại Lan.\*

\---

\#\# 1\. Hướng dẫn cài đặt  
\`\`\`bash  
sudo apt update && sudo apt upgrade \-y  
git clone \[https\://github.com/trang-trai-lan/smart-farm-iot.git\](https\://github.com/trang-trai-lan/smart-farm-iot.git)  
cd smart-farm-iot  
python3 main.py \--config config.json

##  2\. Tính năng chính

* \[x\] Tự động đo đạc nhiệt độ và độ ẩm thời gian thực.  
* \[x\] Kích hoạt hệ thống tưới nước tự động dựa trên cảm biến.  
* \[ \] Gửi báo cáo SMS cho chủ trang trại (Đang phát triển).

##  3\. Bảng thông số phần cứng

| Thành phần | Model | Chức năng |
| :---- | :---- | :---- |
| SoC | ESP32 | Xử lý logic & Wi-Fi |
| Cảm biến | DHT22 | Đo nhiệt độ & độ ẩm |
| Chấp hành | Relay 5V | Điều khiển máy bơm |

##  4\. Chu kỳ lệnh CPU (Fetch \- Decode \- Execute)

Khi nhận lệnh tưới cây, CPU thực hiện:

1. Fetch: Lấy lệnh từ RAM vào thanh ghi.  
2. Decode: Giải mã để nhận biết cần cấp điện cho chân GPIO điều khiển relay máy bơm.  
3. Execute: Phát tín hiệu điện áp điều khiển máy bơm chạy.

##  5\. Quy trình DIKW (Dữ liệu nhiệt độ)

* Data: 38.5 (Số liệu thô).  
* Information: Nhiệt độ khu vực nhà kính đạt 38.5°C.  
* Knowledge: Nhiệt độ cao kết hợp đất khô sẽ làm héo hoa lan.  
* Wisdom: Tự động bật hệ thống tưới phun sương làm mát ngay lập tức.

\---

\#\# Phần 3\. Kiểm thử: Xử lý sự cố RAM đầy

Bổ sung mục sau vào cuối file \`README.md\`:

\`\`\`markdown  
\#\# Lưu ý & Xử lý sự cố (Tràn RAM do Log)  
Nếu thiết bị gặp sự cố đơ máy do RAM đầy do file nhật ký (log):  
1\. Tạm ngắt nguồn điện của thiết bị SoC.  
2\. Kết nối SSH và chạy lệnh dọn dẹp log tạm thời: \`sudo rm \-rf /var/log/smartfarm/\*.log\`.  
3\. Giảm tần suất ghi log (ví dụ: đổi từ 1  
