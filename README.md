# Todo & Note Manager App

Một ứng dụng di động quản lý công việc và ghi chú cá nhân mạnh mẽ được xây dựng bằng **Flutter**, áp dụng các tiêu chuẩn **Clean Architecture** để đảm bảo khả năng mở rộng và dễ dàng bảo trì.

## 🚀 Tính năng nổi bật

- **Quản lý công việc (To-Do):** Tạo, chỉnh sửa, xóa và theo dõi tiến độ công việc một cách dễ dàng.
- **Lời nhắc thông minh:** Hẹn giờ thông báo nhắc nhở các công việc quan trọng ngay trên thiết bị thông qua _Local Notifications_.
- **Ghi chú chuẩn Rich-Text:** Soạn thảo ghi chú với đầy đủ tính năng định dạng (in đậm, in nghiêng, danh sách, hình ảnh...) sử dụng `flutter_quill`.
- **Xem theo Lịch (Calendar View):** Theo dõi công việc trực quan trên giao diện lịch tháng.
- **Hoạt động Offline 100%:** Toàn bộ dữ liệu được lưu trữ an toàn ngay trên thiết bị bằng hệ quản trị cơ sở dữ liệu `Drift` (SQLite). Không cần kết nối mạng để sử dụng cơ bản.

## 🛠️ Công nghệ & Thư viện cốt lõi

* **Framework:** Flutter (phiên bản SDK ^3.11.4)
* **Kiến trúc:** Clean Architecture (chia tách rõ ràng Data, Domain, Presentation)
* **Quản lý trạng thái (State Management):** Riverpod (`flutter_riverpod`, `riverpod_annotation`)
* **Định tuyến (Routing):** Go Router (`go_router`)
* **Chẩn đoán & Database:** Drift (`drift`, `sqlite3_flutter_libs`)
* **UI/UX Tương tác:** `table_calendar`, `flex_color_picker`, `google_fonts`

## 📂 Tổng quan cấu trúc thư mục

Dự án áp dụng chia tách theo module kiến trúc:

```text
lib/
├── core/             📍 Cấu hình hệ thống chung (Theme, Router, Notification)
├── data/             📍 Nơi xử lý Database cục bộ (thiết lập Drift & kết nối)
├── domain/           📍 Nơi chứa các khai báo Object / Blueprint và Logic nghiệp vụ
├── presentation/     📍 Tầng giao diện người dùng (UI)
│   ├── providers/    - Các state controller của Riverpod nối data sang UI
│   ├── screens/      - Các màn hình hiển thị (Todo, Calendar, Notes,...)
│   └── widgets/      - Các thành phần UI có thể tái sử dụng (Buttons, Cards,...)
└── main.dart         📍 Điểm vào (Entry Point) của toàn bộ ứng dụng
```

## ⚙️ Hướng dẫn cài đặt & Khởi chạy

**1. Clone dự án về máy:**
```bash
git clone <đường-dẫn-repo-của-bạn>
cd to_do_list
```

**2. Cài đặt các thư viện (Dependencies):**
```bash
flutter pub get
```

**3. Tạo tự động các file code (BẮT BUỘC):**
Dự án có sử dụng `riverpod_generator` và `drift_dev`, bạn phải chạy lệnh build runner để tạo ra các file logic trước khi chạy code:
```bash
flutter pub run build_runner build --delete-conflicting-outputs
```
*(Hoặc `dart run build_runner watch` nếu đang trong quá trình phát triển liên tục).*

**4. Khởi chạy ứng dụng:**
Cắm thiết bị hoặc bật máy ảo và chạy:
```bash
flutter run
```

---
*Được phát triển với phong cách tối ưu hiệu suất và mang lại UX mượt mà nhất cho người sử dụng.*
