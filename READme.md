# Hệ Thống Giám Sát Cảm Biến IoT

## Hướng dẫn chạy script

```powershell
# Di chuyển đến thư mục chứa script
cd C:\Scripts\IoT-Monitoring

# Khởi động dịch vụ giám sát log hệ thống
python monitor_logs.py --config config.json

```

| Tên thiết bị | Đơn giá (VNĐ) | Loại storage |
| :--- | :--- | :--- |
| SSD Kingston NV2 500GB PCIe 4.0 | 1.150.000 | NVMe PCIe 4.0 |
| HDD Seagate Barracuda 1TB | 1.050.000 | SATA 3 (HDD) |
| SSD Samsung 980 Pro 1TB | 2.250.000 | NVMe PCIe 4.0 |
- [x] Kiểm tra nguồn điện và kết nối mạng của trạm sensor-01
- [ ] Cấu hình lại thông số timeout cho trạm sensor-02
- [x] Vệ sinh bề mặt thiết bị và anten của trạm sensor-03
