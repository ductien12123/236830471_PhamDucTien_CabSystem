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
              │                    │  Business Management    │
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

# B5. Chuyển đổi thành Business Requirements

## 1. Mục đích

Chuyển các Business Goals và phạm vi MVP đã xác định ở B3, B4 thành các **Business Requirements (BR)** cụ thể, làm cơ sở cho việc xác định các yêu cầu chức năng ở các bước tiếp theo.

## 2. Business Requirements

| Mã BR | Business Requirement |
|---|---|
| **BR01** | Hệ thống phải hỗ trợ khách hàng đăng ký tài khoản. |
| **BR02** | Hệ thống phải hỗ trợ khách hàng đăng nhập. |
| **BR03** | Hệ thống phải cho phép khách hàng cập nhật thông tin cá nhân. |
| **BR04** | Hệ thống phải hỗ trợ khách hàng nhập điểm đón và điểm đến. |
| **BR05** | Hệ thống phải cho phép khách hàng lựa chọn loại xe. |
| **BR06** | Hệ thống phải tiếp nhận yêu cầu đặt xe của khách hàng. |
| **BR07** | Hệ thống phải cho phép khách hàng theo dõi trạng thái yêu cầu đặt xe. |
| **BR08** | Hệ thống phải tự động tìm tài xế phù hợp với yêu cầu đặt xe. |
| **BR09** | Hệ thống phải sử dụng vị trí của tài xế để hỗ trợ việc tìm tài xế. |
| **BR10** | Hệ thống phải kiểm tra trạng thái sẵn sàng của tài xế. |
| **BR11** | Hệ thống phải ưu tiên tài xế phù hợp và gần khách hàng. |
| **BR12** | Hệ thống phải gửi yêu cầu chuyến đến tài xế phù hợp. |
| **BR13** | Hệ thống phải tiếp tục tìm tài xế khác khi tài xế từ chối hoặc không phản hồi. |
| **BR14** | Hệ thống không yêu cầu khách hàng tạo lại yêu cầu khi việc tìm tài xế thất bại ở lần trước. |
| **BR15** | Hệ thống phải thông báo cho khách hàng khi không tìm được tài xế. |
| **BR16** | Hệ thống phải cho phép tài xế nhận hoặc từ chối chuyến. |
| **BR17** | Hệ thống phải cho phép tài xế cập nhật trạng thái chuyến. |
| **BR18** | Hệ thống phải hỗ trợ theo dõi trạng thái chuyến đi. |
| **BR19** | Hệ thống phải cung cấp thời gian dự kiến tài xế đến cho khách hàng. |
| **BR20** | Hệ thống phải cập nhật trạng thái khi chuyến đi hoàn thành. |
| **BR21** | Hệ thống phải tính số tiền khách hàng cần thanh toán. |
| **BR22** | Hệ thống phải hỗ trợ thanh toán bằng tiền mặt. |
| **BR23** | Hệ thống phải hỗ trợ thanh toán điện tử. |
| **BR24** | Hệ thống phải tích hợp với nhà cung cấp thanh toán bên ngoài. |
| **BR25** | Hệ thống phải thông báo kết quả của giao dịch thanh toán. |
| **BR26** | Hệ thống phải xử lý trường hợp thanh toán điện tử thất bại. |
| **BR27** | Hệ thống phải thông báo khi yêu cầu đặt xe được tiếp nhận. |
| **BR28** | Hệ thống phải thông báo khi tài xế nhận chuyến. |
| **BR29** | Hệ thống phải thông báo khi tài xế đến điểm đón. |
| **BR30** | Hệ thống phải thông báo khi chuyến đi hoàn thành. |
| **BR31** | Hệ thống phải thông báo cho tài xế khi có chuyến mới. |
| **BR32** | Hệ thống phải thông báo cho tài xế khi có thay đổi liên quan đến chuyến đang thực hiện. |
| **BR33** | Hệ thống phải hỗ trợ nhân viên vận hành quản lý khách hàng. |
| **BR34** | Hệ thống phải hỗ trợ quản lý tài xế. |
| **BR35** | Hệ thống phải hỗ trợ quản lý phương tiện. |
| **BR36** | Hệ thống phải hỗ trợ quản lý chuyến đi. |
| **BR37** | Hệ thống phải cho phép theo dõi các chuyến đang diễn ra. |
| **BR38** | Hệ thống phải hỗ trợ kiểm tra trạng thái tài xế. |
| **BR39** | Hệ thống phải hỗ trợ xử lý các chuyến bị lỗi. |
| **BR40** | Hệ thống phải hỗ trợ tra cứu lịch sử giao dịch. |
| **BR41** | Hệ thống phải kiểm soát quyền truy cập các chức năng quản trị. |
| **BR42** | Hệ thống phải cung cấp báo cáo về số lượng chuyến và doanh thu. |
| **BR43** | Hệ thống phải cung cấp báo cáo về tỷ lệ hoàn thành và tỷ lệ hủy chuyến. |
| **BR44** | Hệ thống phải cung cấp thông tin về hiệu quả hoạt động của tài xế. |
| **BR45** | Hệ thống phải bảo vệ thông tin cá nhân, thông tin phương tiện, dữ liệu vị trí và dữ liệu giao dịch. |
| **BR46** | Hệ thống phải có khả năng mở rộng để phục vụ số lượng lớn khách hàng và tài xế. |

## 3. Trọng tâm của Business Requirement

Đối với mục tiêu **tự động tìm tài xế**, các Business Requirements quan trọng gồm:

- **BR08:** Tự động tìm tài xế phù hợp.
- **BR09:** Dựa trên vị trí tài xế.
- **BR10:** Kiểm tra trạng thái sẵn sàng.
- **BR11:** Ưu tiên tài xế phù hợp và gần khách hàng.
- **BR12:** Gửi yêu cầu chuyến cho tài xế.
- **BR13:** Tiếp tục tìm tài xế khác khi từ chối hoặc không phản hồi.
- **BR15:** Thông báo cho khách hàng nếu không tìm được tài xế.

# B6. Xác định Functional Requirements

## 1. Functional Requirements chính

| Mã | Functional Requirement |
|---|---|
| **FR01** | Đăng ký tài khoản khách hàng. |
| **FR02** | Đăng nhập hệ thống. |
| **FR03** | Cập nhật thông tin cá nhân. |
| **FR04** | Nhập điểm đón và điểm đến. |
| **FR05** | Chọn loại xe. |
| **FR06** | Gửi yêu cầu đặt xe. |
| **FR07** | Theo dõi trạng thái yêu cầu đặt xe. |
| **FR08** | Tự động tìm tài xế phù hợp. |
| **FR09** | Xác định tài xế dựa trên vị trí. |
| **FR10** | Kiểm tra trạng thái sẵn sàng của tài xế. |
| **FR11** | Ưu tiên tài xế phù hợp và gần khách hàng. |
| **FR12** | Gửi yêu cầu chuyến đến tài xế. |
| **FR13** | Tiếp tục tìm tài xế khác khi tài xế từ chối hoặc không phản hồi. |
| **FR14** | Thông báo cho khách hàng khi không tìm được tài xế. |
| **FR15** | Tài xế nhận hoặc từ chối chuyến. |
| **FR16** | Tài xế cập nhật trạng thái chuyến. |
| **FR17** | Theo dõi trạng thái chuyến đi. |
| **FR18** | Hiển thị thời gian dự kiến tài xế đến. |
| **FR19** | Cập nhật trạng thái khi chuyến hoàn thành. |
| **FR20** | Tính số tiền khách hàng phải trả. |
| **FR21** | Thanh toán bằng tiền mặt. |
| **FR22** | Thanh toán điện tử. |
| **FR23** | Xử lý kết quả thanh toán. |
| **FR24** | Thông báo kết quả thanh toán. |
| **FR25** | Thông báo các sự kiện liên quan đến chuyến đi. |
| **FR26** | Quản lý khách hàng. |
| **FR27** | Quản lý tài xế. |
| **FR28** | Quản lý phương tiện. |
| **FR29** | Quản lý chuyến đi. |
| **FR30** | Theo dõi các chuyến đang diễn ra. |
| **FR31** | Kiểm tra trạng thái tài xế. |
| **FR32** | Xử lý các chuyến bị lỗi. |
| **FR33** | Tra cứu lịch sử giao dịch. |
| **FR34** | Phân quyền chức năng quản trị. |
| **FR35** | Xem lịch sử chuyến đi. |
| **FR36** | Đánh giá tài xế sau khi hoàn thành chuyến. |
| **FR37** | Cung cấp báo cáo số lượng chuyến. |
| **FR38** | Cung cấp báo cáo doanh thu. |
| **FR39** | Cung cấp báo cáo tỷ lệ hoàn thành và tỷ lệ hủy. |
| **FR40** | Cung cấp báo cáo hiệu quả hoạt động của tài xế. |

## 2. Functional Requirements trọng tâm

### Tự động tìm tài xế

- **FR08:** Hệ thống tự động tìm tài xế phù hợp.
- **FR09:** Hệ thống sử dụng vị trí tài xế để tìm kiếm.
- **FR10:** Hệ thống kiểm tra trạng thái sẵn sàng của tài xế.
- **FR11:** Hệ thống ưu tiên tài xế phù hợp và gần khách hàng.
- **FR12:** Hệ thống gửi yêu cầu chuyến đến tài xế.
- **FR13:** Hệ thống tiếp tục tìm tài xế khác nếu tài xế từ chối hoặc không phản hồi.
- **FR14:** Hệ thống thông báo cho khách hàng nếu không tìm được tài xế.

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

# B8. Xác định Use Case

## 1. Actor

- **Customer**
- **Driver**
- **Operation Staff**
- **Business Management**
- **Payment Provider**

## 2. Use Case của Customer

- Đăng ký tài khoản.
- Đăng nhập.
- Cập nhật thông tin cá nhân.
- Đặt xe.
- Theo dõi trạng thái chuyến.
- Xem thông tin tài xế.
- Thanh toán chuyến đi.
- Xem lịch sử chuyến đi.
- Đánh giá tài xế.

## 3. Use Case của Driver

- Đăng ký tài khoản.
- Cập nhật hồ sơ.
- Cập nhật thông tin phương tiện.
- Cập nhật trạng thái hoạt động.
- Nhận yêu cầu chuyến.
- Chấp nhận chuyến.
- Từ chối chuyến.
- Cập nhật trạng thái chuyến.
- Thực hiện chuyến.

## 4. Use Case của Operation Staff

- Quản lý khách hàng.
- Quản lý tài xế.
- Quản lý phương tiện.
- Quản lý chuyến đi.
- Theo dõi chuyến đang diễn ra.
- Kiểm tra trạng thái tài xế.
- Xử lý chuyến bị lỗi.
- Tra cứu lịch sử giao dịch.
- Quản lý quyền truy cập.

## 5. Use Case của Business Management

- Xem báo cáo số lượng chuyến.
- Xem báo cáo doanh thu.
- Xem tỷ lệ chuyến hoàn thành.
- Xem tỷ lệ hủy chuyến.
- Xem hiệu quả hoạt động của tài xế.

## 6. Use Case của Payment Provider

- Tiếp nhận yêu cầu thanh toán.
- Xử lý thanh toán điện tử.
- Trả kết quả giao dịch về hệ thống.

## 7. Use Case trọng tâm – Tự động tìm tài xế

**Customer → Đặt xe**

↓

**Hệ thống → Tự động tìm tài xế**

↓

**Hệ thống → Xác định tài xế phù hợp**

↓

**Hệ thống → Gửi yêu cầu chuyến cho Driver**

↓

**Driver → Chấp nhận / Từ chối**

- Nếu **chấp nhận** → Phân công tài xế.
- Nếu **từ chối / không phản hồi** → Hệ thống tiếp tục tìm tài xế khác.
- Nếu **không còn tài xế phù hợp** → Thông báo cho Customer.
