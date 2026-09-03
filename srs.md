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

---

# B2. Xác định các Stakeholder

## 1. Bảng Stakeholder

| Stakeholder | Vai trò của Stakeholder |
|---|---|
| **Customer** | Đăng ký, đặt xe, theo dõi chuyến đi, thanh toán và đánh giá tài xế. |
| **Driver** | Quản lý hồ sơ, phương tiện, nhận hoặc từ chối chuyến và cập nhật trạng thái chuyến. |
| **Operation Staff** | Quản lý khách hàng, tài xế, phương tiện và chuyến đi; theo dõi chuyến đang diễn ra và xử lý sự cố. |
| **Business Management** | Theo dõi báo cáo về số lượng chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả hoạt động của tài xế. |
| **Payment Provider** | Cung cấp dịch vụ thanh toán điện tử và xử lý các giao dịch thanh toán cho hệ thống. |

## 2. Bảng Stakeholder theo hoạt động

| Stakeholder | Vai trò của Stakeholder |
|---|---|
| **Customer** | Tạo yêu cầu đặt xe → theo dõi trạng thái chuyến → thanh toán → đánh giá tài xế. |
| **Driver** | Nhận yêu cầu chuyến → chấp nhận/từ chối → thực hiện chuyến → cập nhật trạng thái. |
| **Operation Staff** | Quản lý dữ liệu → theo dõi chuyến → kiểm tra trạng thái tài xế → xử lý các chuyến bị lỗi. |
| **Business Management** | Theo dõi báo cáo → xem doanh thu → đánh giá hiệu quả hoạt động. |
| **Payment Provider** | Tiếp nhận yêu cầu thanh toán → xử lý giao dịch → trả kết quả thanh toán cho hệ thống. |

## 3. Stakeholder Matrix

### Ma trận Power – Interest

|  | **Interest thấp** | **Interest cao** |
|---|---|---|
| **Power cao** | **Keep Satisfied** | **Manage Closely** |
| **Power thấp** | **Monitor** | **Keep Informed** |

### Phân loại Stakeholder

#### Manage Closely

- **Operation Staff**
- **Business Management**

#### Keep Satisfied

- **Payment Provider**

#### Keep Informed

- **Customer**
- **Driver**

#### Monitor

- Chưa xác định stakeholder cụ thể từ yêu cầu khách hàng.

## 4. Sơ đồ Stakeholder Matrix

```text
                         STAKEHOLDER MATRIX

                    MỨC ĐỘ QUAN TÂM (INTEREST)
                   Thấp                       Cao
              ┌────────────────────┬────────────────────────┐
              │                    │                        │
              │   KEEP SATISFIED   │    MANAGE CLOSELY      │
              │                    │                        │
 POWER CAO    │  Payment Provider  │  Operation Staff       │
              │                    │  Business Management   │
              │                    │                        │
              ├────────────────────┼────────────────────────┤
              │                    │                        │
              │      MONITOR       │    KEEP INFORMED       │
              │                    │                        │
 POWER THẤP   │  Chưa xác định     │  Customer              │
              │                    │  Driver                │
              │                    │                        │
              └────────────────────┴────────────────────────┘
```

---

# B3. Xác định Business Goals

## BG01 – Tự động hóa việc tìm và phân công tài xế

**Lý do:** Việc phân công tài xế hiện tại chủ yếu được thực hiện thủ công, nên hệ thống cần tự động hóa quá trình này.

## BG02 – Giảm thời gian tìm tài xế

**Lý do:** Hệ thống cần nhanh chóng tìm tài xế phù hợp sau khi khách hàng gửi yêu cầu đặt xe, giúp giảm thời gian chờ.

## BG03 – Tìm đúng tài xế phù hợp

**Lý do:** Hệ thống cần dựa trên vị trí, trạng thái sẵn sàng và các tiêu chí vận hành để xác định tài xế phù hợp.

## BG04 – Ưu tiên tài xế gần khách hàng

**Lý do:** Hệ thống được yêu cầu ưu tiên những tài xế phù hợp và gần khách hàng để hỗ trợ quá trình đón khách.

## BG05 – Duy trì quá trình tìm tài xế

**Lý do:** Khi tài xế từ chối hoặc không phản hồi, hệ thống phải tiếp tục tìm tài xế khác thay vì kết thúc yêu cầu đặt xe.

## BG06 – Giảm phụ thuộc vào nhân viên vận hành

**Lý do:** Tự động tìm và phân công tài xế giúp giảm việc nhân viên phải thực hiện phân công thủ công.

## BG07 – Cải thiện trải nghiệm khách hàng

**Lý do:** Khách hàng có thể theo dõi quá trình tìm tài xế và biết được trạng thái yêu cầu đặt xe.

## BG08 – Thông báo rõ ràng khi không tìm được tài xế

**Lý do:** Nếu không có tài xế phù hợp, hệ thống cần thông báo cho khách hàng để khách hàng biết kết quả yêu cầu.

## BG09 – Hỗ trợ mở rộng quy mô phục vụ

**Lý do:** Hệ thống được định hướng phục vụ số lượng lớn khách hàng và tài xế, vì vậy quá trình tìm tài xế cần được tự động hóa để hỗ trợ khả năng mở rộng.

---

# B4. Xác định phạm vi yêu cầu

## 1. Phạm vi của MVP

MVP tập trung vào quy trình chính của CAB System:

**Đặt xe → Tìm tài xế → Phân công tài xế → Thực hiện chuyến → Tính cước → Thanh toán → Hoàn thành chuyến**

## 2. Các yêu cầu phải làm

### Module 1 – Quản lý tài khoản

- Đăng ký tài khoản.
- Đăng nhập.
- Cập nhật thông tin cá nhân.
- Xác thực khách hàng và tài xế.

### Module 2 – Đặt xe

- Nhập điểm đón.
- Nhập điểm đến.
- Chọn loại xe.
- Gửi yêu cầu đặt xe.
- Theo dõi trạng thái yêu cầu.

### Module 3 – Tự động tìm và phân công tài xế

- Tự động tìm tài xế phù hợp.
- Xác định tài xế dựa trên vị trí.
- Kiểm tra trạng thái sẵn sàng của tài xế.
- Ưu tiên tài xế phù hợp và gần khách hàng.
- Gửi yêu cầu chuyến cho tài xế.
- Tiếp tục tìm tài xế khác nếu tài xế từ chối hoặc không phản hồi.
- Không yêu cầu khách hàng tạo lại yêu cầu.
- Thông báo cho khách hàng nếu không tìm được tài xế.

### Module 4 – Quản lý chuyến đi

- Tài xế nhận hoặc từ chối chuyến.
- Cập nhật trạng thái chuyến.
- Theo dõi chuyến đi.
- Cập nhật trạng thái tài xế.
- Hoàn thành chuyến.

### Module 5 – Tính cước và thanh toán

- Tính số tiền khách hàng phải trả.
- Thanh toán bằng tiền mặt.
- Thanh toán điện tử.
- Tích hợp với nhà cung cấp thanh toán bên ngoài.
- Thông báo kết quả thanh toán.
- Xử lý trường hợp thanh toán điện tử thất bại.

### Module 6 – Thông báo

- Thông báo khi yêu cầu đặt xe được tiếp nhận.
- Thông báo khi tài xế nhận chuyến.
- Thông báo khi tài xế đến điểm đón.
- Thông báo khi chuyến hoàn thành.
- Thông báo kết quả thanh toán.
- Thông báo cho tài xế khi có chuyến mới.
- Thông báo khi có thay đổi liên quan đến chuyến đang thực hiện.

### Module 7 – Quản lý vận hành

- Quản lý khách hàng.
- Quản lý tài xế.
- Quản lý phương tiện.
- Quản lý chuyến đi.
- Theo dõi các chuyến đang diễn ra.
- Kiểm tra trạng thái tài xế.
- Xử lý các chuyến bị lỗi.
- Tra cứu lịch sử giao dịch.
- Phân quyền quản trị.

### Module 8 – Lịch sử và đánh giá

- Xem lịch sử chuyến đi.
- Xem số tiền phải trả.
- Đánh giá tài xế sau khi hoàn thành chuyến.

## 3. Những thứ không nên làm trong MVP

- Không xây dựng các chức năng chưa được khách hàng yêu cầu.
- Không tự quyết định cách tính cước khi khách hàng chưa chốt.
- Không tự quyết định tiêu chí ưu tiên tài xế khi khách hàng chưa xác nhận.
- Không tự quyết định thời gian tài xế phải phản hồi.
- Không tự quyết định chính sách hủy chuyến.
- Không xây dựng thêm các phương thức thanh toán chưa được yêu cầu.
- Không xây dựng thêm các kênh thông báo chưa có yêu cầu cụ thể.
- Không lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán.
- Không xây dựng hệ thống báo cáo quá phức tạp trong MVP.
- Không mở rộng sang các dịch vụ đặt xe khác ngoài phạm vi yêu cầu hiện tại.
- Không triển khai các tính năng mở rộng chưa cần thiết cho phiên bản MVP.

## 4. Các nội dung cần xác nhận trước khi triển khai

- Cách tính cước cụ thể.
- Tiêu chí ưu tiên tài xế.
- Thời gian tài xế phải phản hồi.
- Chính sách hủy chuyến.
- Cách xử lý khi mất kết nối mạng.
- Thời gian lưu trữ dữ liệu.

---

# B5. Chuyển đổi thành Business Requirements

## 1. Mục đích

Chuyển các Business Goals và phạm vi MVP thành các Business Requirements cụ thể, làm cơ sở để xác định yêu cầu chức năng của hệ thống.

## 2. Business Requirements

| Mã BR | Business Requirement |
|---|---|
| **BR01** | Hệ thống phải hỗ trợ khách hàng đăng ký và đăng nhập tài khoản. |
| **BR02** | Hệ thống phải cho phép khách hàng quản lý thông tin cá nhân. |
| **BR03** | Hệ thống phải cho phép khách hàng nhập điểm đón, điểm đến và loại xe. |
| **BR04** | Hệ thống phải tiếp nhận và quản lý yêu cầu đặt xe. |
| **BR05** | Hệ thống phải cho phép khách hàng theo dõi trạng thái yêu cầu đặt xe. |
| **BR06** | Hệ thống phải tự động tìm tài xế phù hợp. |
| **BR07** | Hệ thống phải dựa trên vị trí và trạng thái sẵn sàng của tài xế khi tìm kiếm. |
| **BR08** | Hệ thống phải ưu tiên tài xế phù hợp và gần khách hàng. |
| **BR09** | Hệ thống phải gửi yêu cầu chuyến đến tài xế được lựa chọn. |
| **BR10** | Hệ thống phải tiếp tục tìm tài xế khác khi tài xế từ chối hoặc không phản hồi. |
| **BR11** | Hệ thống phải thông báo khi không tìm được tài xế. |
| **BR12** | Hệ thống phải hỗ trợ tài xế nhận hoặc từ chối chuyến. |
| **BR13** | Hệ thống phải cho phép tài xế cập nhật trạng thái chuyến. |
| **BR14** | Hệ thống phải hỗ trợ khách hàng theo dõi chuyến đi và thông tin tài xế. |
| **BR15** | Hệ thống phải cung cấp thời gian dự kiến tài xế đến. |
| **BR16** | Hệ thống phải cập nhật chuyến khi hoàn thành. |
| **BR17** | Hệ thống phải tính số tiền khách hàng cần thanh toán. |
| **BR18** | Hệ thống phải hỗ trợ thanh toán tiền mặt và thanh toán điện tử. |
| **BR19** | Hệ thống phải tích hợp với nhà cung cấp thanh toán bên ngoài. |
| **BR20** | Hệ thống phải thông báo kết quả giao dịch và hỗ trợ xử lý thanh toán thất bại. |
| **BR21** | Hệ thống phải cung cấp các thông báo liên quan đến chuyến đi và thanh toán. |
| **BR22** | Hệ thống phải hỗ trợ quản lý khách hàng, tài xế và phương tiện. |
| **BR23** | Hệ thống phải hỗ trợ quản lý và theo dõi chuyến đi. |
| **BR24** | Hệ thống phải hỗ trợ kiểm tra trạng thái tài xế và xử lý chuyến bị lỗi. |
| **BR25** | Hệ thống phải hỗ trợ tra cứu lịch sử chuyến đi và giao dịch. |
| **BR26** | Hệ thống phải kiểm soát quyền truy cập các chức năng quản trị. |
| **BR27** | Hệ thống phải cung cấp báo cáo hoạt động và doanh thu. |
| **BR28** | Hệ thống phải cung cấp báo cáo về tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả tài xế. |
| **BR29** | Hệ thống phải bảo vệ dữ liệu cá nhân, phương tiện, vị trí và giao dịch. |
| **BR30** | Hệ thống phải có khả năng mở rộng để phục vụ số lượng lớn người dùng. |

---

# B6. Xác định Functional Requirements

## 1. Functional Requirements

| Mã | Functional Requirement |
|---|---|
| **FR01** | Đăng ký, đăng nhập và quản lý thông tin tài khoản. |
| **FR02** | Nhập điểm đón, điểm đến và chọn loại xe. |
| **FR03** | Tạo yêu cầu đặt xe và theo dõi trạng thái yêu cầu. |
| **FR04** | Tự động tìm tài xế phù hợp dựa trên vị trí và trạng thái sẵn sàng. |
| **FR05** | Ưu tiên tài xế phù hợp và gần khách hàng. |
| **FR06** | Gửi yêu cầu chuyến đến tài xế được lựa chọn. |
| **FR07** | Tự động tìm tài xế khác khi tài xế từ chối hoặc không phản hồi. |
| **FR08** | Thông báo cho khách hàng khi không tìm được tài xế. |
| **FR09** | Tài xế nhận hoặc từ chối chuyến. |
| **FR10** | Tài xế cập nhật trạng thái chuyến và trạng thái hoạt động. |
| **FR11** | Khách hàng theo dõi trạng thái chuyến và thông tin tài xế. |
| **FR12** | Hiển thị thời gian dự kiến tài xế đến. |
| **FR13** | Cập nhật trạng thái chuyến khi hoàn thành. |
| **FR14** | Tính số tiền khách hàng phải thanh toán. |
| **FR15** | Hỗ trợ thanh toán bằng tiền mặt và thanh toán điện tử. |
| **FR16** | Gửi và nhận kết quả giao dịch từ nhà cung cấp thanh toán. |
| **FR17** | Thông báo các sự kiện liên quan đến chuyến đi và thanh toán. |
| **FR18** | Quản lý khách hàng, tài xế và phương tiện. |
| **FR19** | Quản lý và theo dõi các chuyến đang diễn ra. |
| **FR20** | Kiểm tra trạng thái tài xế và xử lý chuyến bị lỗi. |
| **FR21** | Tra cứu lịch sử chuyến đi và giao dịch. |
| **FR22** | Quản lý quyền truy cập các chức năng quản trị. |
| **FR23** | Xem báo cáo số lượng chuyến, doanh thu, tỷ lệ hoàn thành và tỷ lệ hủy. |
| **FR24** | Xem báo cáo hiệu quả hoạt động của tài xế. |
| **FR25** | Đánh giá tài xế sau khi hoàn thành chuyến. |

## 2. Functional Requirements trọng tâm

### Tự động tìm và phân công tài xế

- **FR04:** Tự động tìm tài xế phù hợp dựa trên vị trí và trạng thái sẵn sàng.
- **FR05:** Ưu tiên tài xế phù hợp và gần khách hàng.
- **FR06:** Gửi yêu cầu chuyến đến tài xế.
- **FR07:** Tiếp tục tìm tài xế khác khi tài xế từ chối hoặc không phản hồi.
- **FR08:** Thông báo cho khách hàng nếu không tìm được tài xế.

---

# B7. Xác định Non-Functional Requirements

## 1. Hiệu năng và khả năng mở rộng

- **NFR01:** Hệ thống phải hoạt động ổn định khi nhu cầu sử dụng tăng cao.
- **NFR02:** Hệ thống phải có khả năng phục vụ số lượng lớn khách hàng và tài xế.
- **NFR03:** Các thành phần của hệ thống phải có khả năng mở rộng độc lập.

## 2. Tính ổn định và khả năng chịu lỗi

- **NFR04:** Lỗi ở chức năng thanh toán không được làm toàn bộ hệ thống ngừng hoạt động.
- **NFR05:** Lỗi ở chức năng thông báo không được làm toàn bộ hệ thống ngừng hoạt động.
- **NFR06:** Hệ thống phải có khả năng tiếp tục hoạt động khi một thành phần gặp sự cố.
- **NFR07:** Hệ thống phải cho phép triển khai chức năng mới từng phần.

## 3. Xác thực và phân quyền

- **NFR08:** Khách hàng phải được xác thực khi sử dụng hệ thống.
- **NFR09:** Tài xế phải được xác thực khi sử dụng hệ thống.
- **NFR10:** Các chức năng quản trị phải được kiểm soát quyền truy cập.
- **NFR11:** Hệ thống phải phân biệt quyền sử dụng giữa các nhóm người dùng.

## 4. Bảo mật dữ liệu

- **NFR12:** Hệ thống phải bảo vệ thông tin cá nhân của khách hàng.
- **NFR13:** Hệ thống phải bảo vệ thông tin tài xế và phương tiện.
- **NFR14:** Hệ thống phải bảo vệ dữ liệu vị trí.
- **NFR15:** Hệ thống phải bảo vệ dữ liệu giao dịch.
- **NFR16:** Hệ thống không được lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán.

## 5. Lưu vết và kiểm tra

- **NFR17:** Hệ thống phải lưu vết các thao tác quan trọng.
- **NFR18:** Dữ liệu lưu vết phải hỗ trợ việc kiểm tra và xử lý khi xảy ra sự cố.

---

# B8. Xác định Use Case

## 1. Actor

- **Customer**
- **Driver**
- **Operation Staff**
- **Business Management**
- **Payment Provider**

## 2. Use Case của Customer

- Đăng ký, đăng nhập và quản lý tài khoản.
- Đặt xe.
- Theo dõi chuyến đi.
- Thanh toán.
- Xem lịch sử chuyến đi.
- Đánh giá tài xế.

## 3. Use Case của Driver

- Quản lý hồ sơ và phương tiện.
- Cập nhật trạng thái hoạt động.
- Nhận hoặc từ chối chuyến.
- Cập nhật trạng thái chuyến.
- Thực hiện chuyến.

## 4. Use Case của Operation Staff

- Quản lý khách hàng, tài xế và phương tiện.
- Quản lý chuyến đi.
- Theo dõi chuyến đang diễn ra.
- Kiểm tra trạng thái tài xế.
- Xử lý chuyến bị lỗi.
- Tra cứu lịch sử giao dịch.
- Quản lý quyền truy cập.

## 5. Use Case của Business Management

- Xem báo cáo hoạt động.
- Xem báo cáo doanh thu.
- Xem hiệu quả hoạt động của tài xế.

## 6. Use Case của Payment Provider

- Xử lý thanh toán điện tử.
- Trả kết quả giao dịch.

## 7. Use Case trọng tâm – Tự động tìm tài xế

**Customer → Đặt xe**

↓

**System → Tự động tìm tài xế phù hợp**

↓

**System → Ưu tiên tài xế phù hợp và gần khách hàng**

↓

**System → Gửi yêu cầu chuyến**

↓

**Driver → Chấp nhận / Từ chối**

- Nếu **chấp nhận** → Phân công tài xế.
- Nếu **từ chối / không phản hồi** → Tìm tài xế khác.
- Nếu **không tìm được tài xế** → Thông báo cho Customer.

---

# B9. Đặc tả Use Case – Tự động tìm tài xế

## UC01 – Tự động tìm tài xế

- **Actor chính:** Customer
- **Actor liên quan:** Driver
- **Functional Requirements:** FR04, FR05, FR06, FR07, FR08
- **Mục tiêu:** Tự động tìm và phân công tài xế phù hợp cho yêu cầu đặt xe.

### Điều kiện bắt đầu

- Customer đã đăng nhập.
- Customer đã nhập điểm đón, điểm đến và loại xe.
- Customer đã gửi yêu cầu đặt xe.

### Luồng chính

1. Customer gửi yêu cầu đặt xe.
2. Hệ thống tiếp nhận yêu cầu.
3. Hệ thống tìm các tài xế đang sẵn sàng.
4. Hệ thống kiểm tra vị trí và mức độ phù hợp.
5. Hệ thống ưu tiên tài xế phù hợp và gần Customer.
6. Hệ thống gửi yêu cầu chuyến cho Driver.
7. Driver chấp nhận chuyến.
8. Hệ thống xác nhận phân công.
9. Hệ thống thông báo cho Customer.

### Luồng thay thế

#### Driver từ chối

1. Driver từ chối chuyến.
2. Hệ thống loại Driver khỏi lần tìm hiện tại.
3. Hệ thống tiếp tục tìm Driver khác.
4. Gửi yêu cầu đến Driver tiếp theo.

#### Driver không phản hồi

1. Driver không phản hồi.
2. Hệ thống tiếp tục tìm Driver khác.
3. Customer không cần tạo lại yêu cầu.

#### Không tìm được Driver

1. Không có Driver phù hợp.
2. Hệ thống thông báo cho Customer.
3. Yêu cầu đặt xe kết thúc.

### Kết quả

- **Thành công:** Yêu cầu được phân công cho Driver.
- **Thất bại:** Không tìm được Driver và Customer được thông báo.

---

# B10. Xác định Business Rules

## BR01 – Điều kiện tìm tài xế

- Chỉ tìm các tài xế đang ở trạng thái sẵn sàng nhận chuyến.
- Hệ thống phải dựa trên vị trí của tài xế để tìm kiếm.
- Hệ thống phải xét các tiêu chí phù hợp theo yêu cầu vận hành.

## BR02 – Quy tắc ưu tiên tài xế

- Ưu tiên tài xế phù hợp với yêu cầu chuyến.
- Ưu tiên tài xế gần vị trí đón khách.

## BR03 – Quy tắc gửi yêu cầu chuyến

- Hệ thống gửi yêu cầu chuyến cho tài xế được lựa chọn.
- Tài xế có quyền chấp nhận hoặc từ chối chuyến.

## BR04 – Quy tắc khi tài xế từ chối

- Nếu tài xế từ chối, hệ thống phải tiếp tục tìm tài xế khác.
- Khách hàng không cần tạo lại yêu cầu đặt xe.

## BR05 – Quy tắc khi tài xế không phản hồi

- Nếu tài xế không phản hồi trong thời gian quy định, hệ thống phải tiếp tục tìm tài xế khác.
- Thời gian phản hồi cụ thể cần được khách hàng xác nhận.

## BR06 – Quy tắc khi không tìm được tài xế

- Nếu không tìm được tài xế phù hợp, hệ thống phải thông báo cho khách hàng.
- Yêu cầu đặt xe không được tự động chuyển sang tài xế không phù hợp.

## BR07 – Quy tắc trạng thái chuyến

- Tài xế phải cập nhật trạng thái chuyến theo từng giai đoạn.
- Trạng thái chuyến phải được cập nhật để khách hàng có thể theo dõi.

## BR08 – Quy tắc thanh toán

- Hệ thống hỗ trợ thanh toán bằng tiền mặt.
- Hệ thống hỗ trợ thanh toán điện tử.
- Thanh toán điện tử phải được thực hiện thông qua nhà cung cấp thanh toán bên ngoài.
- Không lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán.

## BR09 – Quy tắc phân quyền

- Khách hàng, tài xế và nhân viên vận hành phải có quyền sử dụng phù hợp với vai trò.
- Các chức năng quản trị phải được kiểm soát quyền truy cập.

## BR10 – Các Business Rules chưa được xác định

- Cách tính cước cụ thể.
- Tiêu chí ưu tiên tài xế cụ thể.
- Thời gian tài xế phải phản hồi.
- Chính sách hủy chuyến.
- Cách xử lý khi mất kết nối mạng.
- Thời gian lưu trữ dữ liệu.

---

# B11. Xác định Activity Flow

## 1. Quy trình đặt xe và tự động tìm tài xế

**Customer**

→ Đăng nhập hệ thống

→ Nhập điểm đón và điểm đến

→ Chọn loại xe

→ Gửi yêu cầu đặt xe

**System**

→ Tiếp nhận yêu cầu

→ Kiểm tra tài xế phù hợp

→ Kiểm tra vị trí và trạng thái sẵn sàng của tài xế

→ Chọn tài xế phù hợp và gần khách hàng

→ Gửi yêu cầu chuyến cho Driver

**Driver**

→ Nhận yêu cầu chuyến

→ Chấp nhận / Từ chối

### Nếu Driver chấp nhận

→ System phân công chuyến

→ Thông báo cho Customer

→ Driver đến điểm đón

→ Đón Customer

→ Thực hiện chuyến

→ Hoàn thành chuyến

### Nếu Driver từ chối hoặc không phản hồi

→ System tiếp tục tìm Driver khác

→ Gửi yêu cầu cho Driver tiếp theo

→ Lặp lại quá trình tìm tài xế

### Nếu không tìm được Driver

→ System thông báo cho Customer

→ Kết thúc yêu cầu đặt xe

## 2. Luồng tổng quát

```text
[Customer gửi yêu cầu đặt xe]
              ↓
      [System tiếp nhận]
              ↓
    [Tìm tài xế phù hợp]
              ↓
 [Kiểm tra vị trí + trạng thái]
              ↓
      [Chọn Driver phù hợp]
              ↓
       [Gửi yêu cầu chuyến]
              ↓
       ┌──────┴──────┐
       ↓             ↓
 [Chấp nhận]   [Từ chối/Không phản hồi]
       ↓             ↓
 [Phân công]   [Tìm Driver khác]
       ↓             ↓
 [Thông báo] ←───────┘
       ↓
 [Thực hiện chuyến]
       ↓
 [Hoàn thành chuyến]
```

---

# B12. Traceability giữa Business Goal và Functional Requirement

## 1. Mục đích

Liên kết các **Business Goal (BG)** với các **Functional Requirement (FR)** tương ứng để đảm bảo các mục tiêu kinh doanh đều được hỗ trợ bởi chức năng của hệ thống.

## 2. Ma trận Traceability

| Business Goal | Functional Requirement |
|---|---|
| **BG01 – Tự động hóa việc tìm và phân công tài xế** | FR04, FR06, FR07 |
| **BG02 – Giảm thời gian tìm tài xế** | FR04, FR05 |
| **BG03 – Tìm đúng tài xế phù hợp** | FR04, FR05 |
| **BG04 – Ưu tiên tài xế gần khách hàng** | FR05 |
| **BG05 – Duy trì quá trình tìm tài xế** | FR07 |
| **BG06 – Giảm phụ thuộc vào nhân viên vận hành** | FR04, FR06, FR07 |
| **BG07 – Cải thiện trải nghiệm khách hàng** | FR03, FR08, FR11, FR12 |
| **BG08 – Thông báo khi không tìm được tài xế** | FR08 |
| **BG09 – Hỗ trợ mở rộng quy mô phục vụ** | FR04, FR05, FR07 |

## 3. Traceability trọng tâm

**BG01**

→ FR04: Tự động tìm tài xế

→ FR06: Gửi yêu cầu chuyến

→ FR07: Tìm tài xế khác

**BG02**

→ FR04: Tự động tìm tài xế

→ FR05: Ưu tiên tài xế phù hợp và gần khách hàng

**BG03**

→ FR04: Xác định tài xế phù hợp

→ FR05: Ưu tiên tài xế phù hợp

**BG04**

→ FR05: Ưu tiên tài xế gần khách hàng

**BG05**

→ FR07: Tiếp tục tìm tài xế khác

**BG06**

→ FR04: Tự động tìm tài xế

→ FR06: Gửi yêu cầu chuyến

→ FR07: Tự động tìm tài xế khác

**BG07**

→ FR03: Theo dõi trạng thái yêu cầu

→ FR08: Thông báo khi không tìm được tài xế

→ FR11: Theo dõi trạng thái chuyến

→ FR12: Hiển thị thời gian dự kiến

**BG08**

→ FR08: Thông báo khi không tìm được tài xế

**BG09**

→ FR04: Tự động tìm tài xế

→ FR05: Ưu tiên tài xế

→ FR07: Tiếp tục tìm tài xế khác

---

# B13. Acceptance Criteria

## AC01 – Đặt xe

- Customer có thể nhập điểm đón và điểm đến.
- Customer có thể chọn loại xe.
- Customer có thể gửi yêu cầu đặt xe.
- Hệ thống phải tạo yêu cầu và cho phép theo dõi trạng thái.

## AC02 – Tự động tìm tài xế

- Hệ thống tự động tìm tài xế sau khi nhận yêu cầu.
- Chỉ xem xét tài xế đang sẵn sàng.
- Hệ thống phải xét vị trí tài xế.
- Hệ thống phải ưu tiên tài xế phù hợp và gần khách hàng.

## AC03 – Phân công tài xế

- Hệ thống gửi yêu cầu chuyến đến tài xế.
- Tài xế có thể chấp nhận hoặc từ chối.
- Khi tài xế chấp nhận, hệ thống xác nhận phân công.
- Customer được thông báo khi tài xế nhận chuyến.

## AC04 – Từ chối hoặc không phản hồi

- Khi tài xế từ chối, hệ thống phải tìm tài xế khác.
- Khi tài xế không phản hồi, hệ thống phải tìm tài xế khác.
- Customer không cần tạo lại yêu cầu.

## AC05 – Không tìm được tài xế

- Hệ thống phải thông báo cho Customer.
- Customer phải nhận được kết quả rõ ràng.

## AC06 – Theo dõi chuyến

- Customer có thể theo dõi trạng thái chuyến.
- Customer có thể xem thông tin tài xế.
- Customer có thể xem thời gian dự kiến tài xế đến.
- Driver có thể cập nhật trạng thái chuyến.
- Hệ thống cập nhật trạng thái khi chuyến hoàn thành.

## AC07 – Thanh toán

- Hệ thống tính được số tiền cần thanh toán.
- Hỗ trợ tiền mặt và thanh toán điện tử.
- Hệ thống hiển thị kết quả giao dịch.
- Thanh toán thất bại phải được thông báo.

## AC08 – Quản lý vận hành

- Operation Staff có thể quản lý Customer, Driver và phương tiện.
- Operation Staff có thể quản lý chuyến.
- Operation Staff có thể theo dõi chuyến đang diễn ra.
- Operation Staff có thể xử lý chuyến bị lỗi.

## AC09 – Bảo mật và phân quyền

- Customer và Driver phải được xác thực.
- Chức năng quản trị phải được phân quyền.
- Dữ liệu cá nhân, vị trí và giao dịch phải được bảo vệ.
- Hệ thống không lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán.

---

# B14. Tổng hợp và kiểm tra yêu cầu

## 1. Kiểm tra phạm vi

- Các chức năng trong MVP phải nằm trong phạm vi đã xác định ở B4.
- Không đưa các yêu cầu chưa được khách hàng chốt vào phạm vi chính thức.
- Các yêu cầu về tính cước, ưu tiên tài xế, thời gian phản hồi, hủy chuyến, mất kết nối và lưu trữ dữ liệu cần được khách hàng xác nhận.

## 2. Kiểm tra tính đầy đủ

- Đảm bảo quy trình chính được hỗ trợ đầy đủ:

**Đặt xe → Tìm tài xế → Phân công tài xế → Thực hiện chuyến → Tính cước → Thanh toán → Thông báo → Đánh giá**

- Đảm bảo Customer có các chức năng cần thiết để đặt và theo dõi chuyến.
- Đảm bảo Driver có các chức năng cần thiết để nhận và thực hiện chuyến.
- Đảm bảo Operation Staff có chức năng quản lý và xử lý sự cố.
- Đảm bảo hệ thống có chức năng thanh toán, thông báo và báo cáo.

## 3. Kiểm tra yêu cầu tự động tìm tài xế

- Hệ thống phải tự động tìm tài xế phù hợp.
- Phải xét vị trí và trạng thái sẵn sàng của tài xế.
- Phải ưu tiên tài xế phù hợp và gần khách hàng.
- Nếu tài xế từ chối hoặc không phản hồi, hệ thống phải tiếp tục tìm tài xế khác.
- Customer không phải tạo lại yêu cầu.
- Nếu không tìm được tài xế, hệ thống phải thông báo cho Customer.

## 4. Kiểm tra tính nhất quán

- Business Goal phải được liên kết với Business Requirement.
- Business Requirement phải được chuyển thành Functional Requirement.
- Functional Requirement phải có Use Case tương ứng.
- Use Case phải có luồng xử lý phù hợp.
- Acceptance Criteria phải kiểm tra được các yêu cầu quan trọng.
- Các yêu cầu phải phù hợp với phạm vi MVP.

## 5. Kiểm tra Traceability

| Thành phần | Kết quả |
|---|---|
| Business Contract → Business Goal | Đã xác định |
| Business Goal → Business Requirement | Đã liên kết |
| Business Requirement → Functional Requirement | Đã chuyển đổi |
| Functional Requirement → Use Case | Đã xác định |
| Use Case → Business Rules | Đã xác định |
| Functional Requirement → Acceptance Criteria | Đã kiểm tra |
| MVP → Functional Requirement | Phù hợp |
| Functional Requirement → Business Goal | Có Traceability |

## 6. Các yêu cầu cần xác nhận

- Cách tính cước cụ thể.
- Tiêu chí ưu tiên tài xế.
- Thời gian tài xế phải phản hồi.
- Chính sách hủy chuyến.
- Cách xử lý khi mất kết nối mạng.
- Thời gian lưu trữ dữ liệu.

## 7. Kết luận

CAB System trong phạm vi MVP tập trung vào quy trình:

**Đặt xe → Tự động tìm tài xế → Phân công tài xế → Thực hiện chuyến → Tính cước → Thanh toán → Thông báo → Đánh giá**

Trong đó, chức năng **tự động tìm và phân công tài xế** là trọng tâm của hệ thống.

Các yêu cầu đã được liên kết từ:

**Business Contract**

→ **Business Goals**

→ **Business Requirements**

→ **Functional Requirements**

→ **Use Cases**

→ **Business Rules**

→ **Acceptance Criteria**

nhằm đảm bảo yêu cầu có tính nhất quán và có thể truy vết từ mục tiêu kinh doanh đến chức năng cụ thể của hệ thống.
