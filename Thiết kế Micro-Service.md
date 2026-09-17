
# Phân Tách Domain — CAB System

**Thiết kế Microservice**

## 1. Mục đích

Tài liệu này phân tách hệ thống CAB System thành các domain (bounded context) độc lập, dựa trên SRS (Business Requirements, Functional Requirements, Use Case) và bản thiết kế Microservice hiện có. Mục tiêu là xác định ranh giới nghiệp vụ rõ ràng, dữ liệu sở hữu riêng và cơ chế giao tiếp để mỗi domain có thể phát triển, triển khai và vận hành độc lập.

## 2. Bảng phân tách Domain

Các domain được phân loại theo Domain-Driven Design: **Core** (nghiệp vụ lõi, tạo lợi thế cạnh tranh), **Supporting** (hỗ trợ nghiệp vụ nhưng không phải lõi) và **Generic** (chức năng phổ biến, có thể dùng giải pháp có sẵn).

| Domain | Loại | Trách nhiệm chính | FR liên quan | Dữ liệu sở hữu |
|---|---|---|---|---|
| **Booking** | Core | Nhận yêu cầu đặt xe, quản lý vòng đời request (pending/searching/assigned/cancelled) | FR02, FR03 | `bookings` |
| **Matching (Dispatch)** | Core – trọng tâm | Tìm tài xế sẵn sàng, ưu tiên theo vị trí, gửi yêu cầu, retry khi từ chối/timeout | FR04–FR08 | `driver_availability_cache`, `matching_attempts` |
| **Trip** | Core | Vòng đời chuyến đi thực tế: accept → arriving → in-progress → completed, ETA | FR09–FR13 | `trips` |
| **Identity & Access** | Supporting | Đăng ký, đăng nhập, OTP, JWT, refresh token, phân quyền | FR01, NFR08–11 | `auth_db` |
| **User Profile** | Supporting | Hồ sơ Customer & Driver (không gồm credential) | BR02 | `customer_profile`, `driver_profile` |
| **Vehicle** | Supporting | Đăng ký/quản lý phương tiện, loại xe | FR22 | `vehicles` |
| **Pricing (Fare)** | Supporting | Tính cước theo khoảng cách/loại xe/thời gian | FR14 | `fare_rules`, `fare_snapshot` |
| **Payment** | Supporting – nhạy cảm | Thanh toán tiền mặt/điện tử, tích hợp Payment Provider ngoài, xử lý thất bại | FR15, FR16, NFR16 | `transactions` (không lưu số thẻ) |
| **Notification** | Generic | Gửi thông báo (push/SMS) cho mọi sự kiện quan trọng | FR17, NFR05 | `notification_log` |
| **Operation Management** | Supporting (back-office) | Quản lý KH/tài xế/xe từ góc nhìn vận hành, xử lý chuyến lỗi, phân quyền admin | FR18–FR22, NFR10 | BFF gọi domain khác, ít dữ liệu riêng |
| **Reporting & Analytics** | Generic | Báo cáo số chuyến, doanh thu, tỷ lệ hoàn thành/huỷ, hiệu quả tài xế | FR23, FR24 | `reporting_read_model` (CQRS) |
| **Rating** | Supporting | Đánh giá tài xế sau chuyến | FR25 | `ratings` |

## 3. Sơ đồ giao tiếp giữa các Domain qua Event Bus

Ba domain lõi trên luồng chính (Booking, Matching, Trip) chỉ **publish** sự kiện lên Event Bus; ba domain hỗ trợ (Pricing, Payment, Notification) **subscribe** sự kiện từ bus. Không domain nào gọi trực tiếp (đồng bộ) sang domain khác trên luồng nghiệp vụ chính.
