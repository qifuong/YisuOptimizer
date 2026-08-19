
# Yisu Optimizer Ver 2.0

**Yisu Optimizer** là công cụ tối ưu hóa bộ nhớ RAM và theo dõi phần cứng hệ thống chuyên nghiệp dành cho nền tảng Windows. Ứng dụng được thiết kế tối ưu cho việc chơi game, chạy giả lập và sử dụng máy tính trong thời gian dài.

---

## 🚀 Tính năng chính

- **Dọn RAM thủ công & nhanh chóng:** Cung cấp hai cơ chế là *Dọn RAM Ngay* (xử lý Working Set theo tiến trình và Standby RAM) và *Dọn RAM Thủ Công* (xóa toàn diện Working Sets, Modified Page List, Standby List và Priority 0 Standby List).
- **Chế độ Smart RAM (Tự động thông minh):** Theo dõi mức sử dụng RAM theo thời gian thực để tự động tối ưu dựa theo các ngưỡng:
  - **Dưới 70%:** Bình thường.
  - **70% - 79%:** Đang theo dõi.
  - **80% - 89%:** Tự động tối ưu nhẹ.
  - **Từ 90% trở lên:** Tự động tối ưu mạnh.
- **Chế độ tối ưu định kỳ linh hoạt:**
  - **Game PC:** Chu kỳ tự động kiểm tra mỗi 1 giờ.
  - **Giả lập (EMU):** Chu kỳ tự động kiểm tra mỗi 10 phút.
  - **Tùy chỉnh (Auto):** Cho phép tự cấu hình khoảng thời gian quét theo giây.
- **Dashboard theo dõi hệ thống trực quan:** Theo dõi thời gian thực các thông số phần cứng bao gồm CPU, RAM, Disk (Ổ cứng) và Network (Tốc độ mạng Download/Upload).
- **Hỗ trợ giao diện Sáng / Tối (Dark/Light Mode):** Tùy biến giao diện linh hoạt và tự động lưu trạng thái vào file cấu hình.
- **Khay hệ thống (System Tray):** Cho phép ẩn/hiện cửa sổ giao diện nhanh chóng và tích hợp sẵn menu điều khiển ngầm.
- **Khởi động cùng Windows:** Tích hợp tính năng bật/tắt khởi động cùng hệ thống thông qua Windows Registry.

---

## ⚙️ Yêu cầu hệ thống

- **Hệ điều hành:** Windows 10 hoặc phiên bản mới hơn.
- **Quyền hạn:** Bắt buộc chạy với quyền **Administrator** (`#RequireAdmin`) để có thể thao tác với bộ nhớ đệm và tiến trình hệ thống.
- **Thành phần phụ thuộc:** Chương trình tự động giải nén tệp `Cache.bin` (thực chất là công cụ `EmptyStandbyList.exe`) kèm thuộc tính ẩn (`+HS`) để xử lý dọn dẹp Standby List.

---

## 🔬 Nguyên lý hoạt động

Ứng dụng kết hợp hai phương pháp tối ưu an toàn cho hệ thống:

1. **EmptyStandbyList (thông qua `Cache.bin`):**
   - Xóa bỏ các dữ liệu lưu trữ tạm thời trong Standby Memory, Modified Page List, Low Priority Standby List và Priority 0 Standby.
2. **EmptyWorkingSet (thông qua Windows API `psapi.dll`):**
   - Thu hồi bộ nhớ RAM đang bị chiếm dụng bởi các tiến trình ứng dụng.
   - **Bảo vệ hệ thống:** Tự động bỏ qua các tiến trình hệ thống cốt lõi quan trọng của Windows (`system`, `idle`, `csrss.exe`, `winlogon.exe`) nhằm đảm bảo sự ổn định tuyệt đối cho hệ điều hành.

---

## 📁 Cấu hình (`config.ini`)

Mọi thiết lập của người dùng sẽ được tự động lưu lại vào tệp `config.ini` nằm cùng thư mục với chương trình:

```ini
[Settings]
Mode=PC
CheckInterval=300
DarkMode=1

```

---

## 👨‍💻 Thông tin tác giả & Hỗ trợ

* **Phát triển bởi:** **Yisu** (Phiên bản: `2.0.0.0`)
* **Facebook:** [LeeQiFuong](https://www.facebook.com/LeeQiFuong/)

---

## 📜 Giấy phép

Dự án được cung cấp với mục đích học tập, nghiên cứu và tối ưu hóa hiệu năng hệ thống Windows. Người dùng tự chịu trách nhiệm khi sử dụng trên thiết bị cá nhân.

```
