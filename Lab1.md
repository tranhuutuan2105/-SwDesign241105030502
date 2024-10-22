# Lab1

## 1. Phân tích kiến trúc
### Đề xuất Kiến trúc: Tôi chọn kiến trúc "MVC" cho hệ thống "Payroll System" :

### Các thành phần trong kiến trúc :
**Model(Mô hình):**

- Ý nghĩa: Chứa dữ liệu và logic nghiệp vụ, quản lý thông tin về nhân viên, thanh toán và thời gian làm việc.
- Lý do: Dễ dàng bảo trì , tái sử dụng, tách biệt khỏi các logic nghiệp vụ.

**Lớp Logic Nghiệp Vụ (Business Logic Layer):**

- Ý nghĩa: Chứa các quy tắc nghiệp vụ và xử lý logic cho các tác vụ như thanh toán và quản lý thời gian.
- Lý do: Đảm bảo rằng tất cả các quy trình nghiệp vụ được thực hiện một cách nhất quán và có thể bảo trì.

**Lớp Truy Xuất Dữ Liệu (Data Access Layer):**
- Ý nghĩa: Quản lý việc truy xuất và lưu trữ dữ liệu từ cơ sở dữ liệu.
- Lý do: Tách biệt logic truy xuất dữ liệu giúp dễ dàng thay đổi nguồn dữ liệu mà không ảnh hưởng đến các lớp khác.

**Lớp Dữ Liệu (Data Layer):**

- Ý nghĩa: Lưu trữ dữ liệu bao gồm thông tin nhân viên, bảng lương và thời gian làm việc.
- Lý do: Cung cấp một cách tổ chức dữ liệu hợp lý và hiệu quả, dễ dàng cho việc quản lý và sao lưu.
  ### BIỂU ĐỒ PACKAGE :
  
  ![](https://www.planttext.com/api/plantuml/png/Z9AnIWCn6CVtFCMVJdNf0pX8bGCf5X7QYb1kY6cy2xtB7KbEAEBWvEm3E1QdegkNeKF1zyWJ-0hcpg6d9tWP0ia_t-_tyP5FknrgGvKfqeGGlHGIAjES664IZZFXogs4KRkI8OzT-IAHElkGWiKPOcSVOVp-92DSq9NAaWIJbJOy9IIdR4aZZjwfe1a2uTzAd4SVRyu-2mIxTr_JduqEUhWZy6i-qrnX90rNDvHnJBYw5Oo7vBx16cUHO9uILxWSbywkqJyfj91SQzJf7kWxIhaqUr9zEnKfPrGj_XPCLR72LU7AjK7Wx2l6bQb0Fw26ufWnxsaR6k5lou-eQMhHzzZgT4trTslpV-ONOZ0umhpBP48SOkBi1WkVoeXqBAhvdGRJ4dIigWtjWLIuci1SkSa96NAvgBxf5m000F__0m00)
## 2. Cơ chế phân tích

  ### Các cơ chế cần giải quyết trong bài toán:

  **Xác thực và phân quyền người dùng (User Authentication and Authorization):**
  - Lý do: Đảm bảo chỉ những người có quyền truy cập mới có thể thực hiện các tác vụ quan trọng.
 
  **Tính toán tiền lương (Payroll Calculation):**
  - Lý do: Cần một thuật toán chính xác để tính toán tiền lương dựa trên thông tin giờ làm việc và quy định công ty.
   
   **Quản lý thông tin nhân viên (Employee Management):**
  - Lý do: Cần có cơ chế để thêm, sửa đổi và xóa thông tin nhân viên một cách hiệu quả.

  **Ghi nhận và lưu trữ thời gian làm việc (Time Tracking and Storage):**
  - Lý do: Đảm bảo thông tin về giờ làm việc được lưu trữ chính xác và có thể truy xuất dễ dàng.
 
  **Báo cáo và phân tích dữ liệu (Reporting and Data Analysis):**
  - Lý do: Cần có khả năng tạo báo cáo để quản lý có thể theo dõi hiệu suất và chi phí.

### Danh Sách Cơ Chế : 
- Danh sách cơ chế:
- Xác thực và phân quyền
- Tính toán tiền lương
- Quản lý thông tin nhân viên
- Ghi nhận thời gian làm việc
- Báo cáo và phân tích dữ liệu
## 3. Phân Tích Ca Sử Dụng Payment
### 3.1 Các lớp phân tích cho ca sử dụng Payment.
**Các lớp phân tích :**

**1. User Interface Layer (Presentation Layer):**
- Nhiệm vụ: Cung cấp giao diện cho người dùng để thực hiện việc xem và xác nhận thông tin thanh toán.
- Thuộc tính: paymentInfo, userInput, displayMessage
**2. Business Logic Layer (Payment Service):**
  - Nhiệm vụ: Xử lý logic liên quan đến việc tính toán tiền lương, áp dụng thuế và phúc lợi.
-   Thuộc tính: calculateTotal(), applyTax(), generatePayslip()
