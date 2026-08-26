# B1. Đọc và phân tích yêu cầu sơ khởi của khách hàng – Business Contract

## 1. Thông tin dự án

- **Khách hàng:** Công ty ABC
- **Tên hệ thống:** CAB System – Nền tảng đặt xe
- **Thời gian thực hiện:** 7 tuần
- **Mục tiêu:** Xây dựng nền tảng đặt xe có khả năng phục vụ số lượng lớn khách hàng và tài xế, đồng thời có khả năng mở rộng trong tương lai.

## 2. Các vấn đề hiện tại

- Việc phân công tài xế chủ yếu được thực hiện thủ công.
- Khách hàng khó theo dõi trạng thái chuyến đi.
- Thông tin thanh toán chưa được quản lý tập trung.
- Bộ phận vận hành gặp khó khăn khi hệ thống mở rộng.

## 3. Yêu cầu chính của hệ thống

### 3.1. Đặt xe

- Khách hàng đăng ký và đăng nhập.
- Nhập điểm đón và điểm đến.
- Chọn loại xe.
- Gửi yêu cầu đặt xe.
- Theo dõi trạng thái yêu cầu đặt xe.

### 3.2. Tự động tìm và phân công tài xế

- Hệ thống tự động tìm tài xế phù hợp.
- Xác định tài xế dựa trên vị trí, trạng thái sẵn sàng và các tiêu chí vận hành.
- Ưu tiên tài xế phù hợp và gần khách hàng.
- Gửi yêu cầu chuyến cho tài xế.
- Nếu tài xế từ chối hoặc không phản hồi, hệ thống tiếp tục tìm tài xế khác.
- Khách hàng không cần tạo lại yêu cầu.
- Nếu không tìm được tài xế, hệ thống thông báo cho khách hàng.

### 3.3. Thực hiện và theo dõi chuyến đi

- Tài xế nhận hoặc từ chối chuyến.
- Tài xế cập nhật trạng thái chuyến.
- Khách hàng theo dõi trạng thái chuyến.
- Khách hàng biết tài xế đã nhận chuyến và thời gian dự kiến tài xế đến.
- Sau khi hoàn thành chuyến, hệ thống cập nhật trạng thái hoàn thành.

### 3.4. Tính cước và thanh toán

- Tính số tiền khách hàng phải trả.
- Hỗ trợ thanh toán tiền mặt.
- Hỗ trợ thanh toán điện tử.
- Tích hợp với nhà cung cấp thanh toán bên ngoài.
- Không lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán.
- Thông báo khi thanh toán điện tử thất bại và cho phép xử lý lại.

### 3.5. Thông báo

- Thông báo cho khách hàng khi yêu cầu đặt xe được tiếp nhận.
- Thông báo khi tài xế nhận chuyến.
- Thông báo khi tài xế đến điểm đón.
- Thông báo khi chuyến hoàn thành.
- Thông báo kết quả thanh toán.
- Thông báo cho tài xế khi có chuyến mới hoặc có thay đổi liên quan đến chuyến đang thực hiện.

### 3.6. Quản lý vận hành

- Quản lý khách hàng.
- Quản lý tài xế.
- Quản lý phương tiện.
- Quản lý chuyến đi.
- Theo dõi các chuyến đang diễn ra.
- Kiểm tra trạng thái tài xế.
- Hỗ trợ xử lý các chuyến bị lỗi.
- Tra cứu lịch sử giao dịch.
- Phân quyền các chức năng quản trị.

### 3.7. Báo cáo

Hệ thống cần cung cấp các báo cáo:

- Số lượng chuyến.
- Doanh thu.
- Tỷ lệ chuyến hoàn thành.
- Tỷ lệ hủy.
- Hiệu quả hoạt động của tài xế.

## 4. Yêu cầu phi chức năng

- Hệ thống hoạt động ổn định khi nhu cầu tăng cao.
- Các thành phần có khả năng mở rộng độc lập.
- Lỗi ở thanh toán hoặc thông báo không làm toàn bộ hệ thống ngừng hoạt động.
- Có thể triển khai chức năng mới từng phần.
- Khách hàng và tài xế phải được xác thực.
- Kiểm soát quyền truy cập đối với chức năng quản trị.
- Bảo vệ thông tin cá nhân, thông tin phương tiện, dữ liệu vị trí và dữ liệu giao dịch.
- Lưu vết các thao tác quan trọng.

## 5. Những nội dung khách hàng chưa chốt

- Cách tính cước cụ thể.
- Tiêu chí ưu tiên tài xế.
- Thời gian tài xế phải phản hồi.
- Chính sách hủy chuyến.
- Cách xử lý khi mất kết nối mạng.
- Thời gian lưu trữ dữ liệu.

## 6. Quy trình nghiệp vụ chính

**Đặt xe → Tìm tài xế → Phân công tài xế → Thực hiện chuyến → Tính cước → Thanh toán → Thông báo → Đánh giá**
