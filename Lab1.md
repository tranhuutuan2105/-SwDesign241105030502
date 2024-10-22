# Lab1

## 1. Phân tích kiến trúc
### Đề xuất Kiến trúc: Tôi chọn kiến trúc "Microservices" cho hệ thống "Payroll System" :

### Các thành phần trong kiến trúc :
**Dịch vụ Giao Diện Người Dùng (User Interface Service):**

- Ý nghĩa: Đây là lớp tương tác với người dùng, bao gồm giao diện web hoặc ứng dụng di động. Dịch vụ này giúp người dùng thực hiện các tác vụ như xem thông tin thanh toán và quản lý thời gian làm việc.
- Lý do: Tách biệt giao diện người dùng giúp dễ dàng thay đổi giao diện mà không ảnh hưởng đến các chức năng phía sau.

**Dịch vụ Thanh Toán (Payment Service):**

- Ý nghĩa: Chịu trách nhiệm xử lý các hoạt động liên quan đến thanh toán, bao gồm tính toán tiền lương, áp dụng thuế và phúc lợi.
- Lý do: Tách biệt logic nghiệp vụ thanh toán giúp dễ dàng bảo trì và phát triển thêm các tính năng mới mà không ảnh hưởng đến các dịch vụ khác.

**Dịch vụ Thời Gian (Timecard Service):**
- Ý nghĩa: Quản lý thông tin thời gian làm việc của nhân viên, cho phép nhập và chỉnh sửa giờ làm việc.
- Lý do: Việc tách biệt quản lý thời gian giúp dễ dàng cập nhật và kiểm tra thông tin mà không ảnh hưởng đến hệ thống thanh toán.

**Dịch vụ Dữ Liệu (Data Service):**

- Ý nghĩa: Chịu trách nhiệm lưu trữ và truy xuất dữ liệu từ cơ sở dữ liệu, bao gồm thông tin nhân viên, bảng lương và thời gian làm việc.
- Lý do: Tách biệt dữ liệu giúp giảm thiểu rủi ro và cải thiện hiệu suất, cũng như dễ dàng thực hiện các hoạt động sao lưu và khôi phục dữ liệu.

  ### BIỂU ĐỒ PACKAGE :
  
  ![](https://www.planttext.com/api/plantuml/png/V99D2i8m44RtESNWlbUGYcvS5CGVN4WNqtIKO9g4D1MAU38N7iahsBI2chRkmfVtlSn0dlT7N3gqhYeaOmRv6Ky4arr95fRAaJqY9zYGlGXE4xWoWCEUiizTwfD4Pq8Ip8oHWgCJMgNizgLROLsGSe6dIQsM4kOeUINVjIvlwGHLq_R7NzjM5CJHve7EnwET1JeC-3PQaz6bSDhMBH_i1b4q7PbpQET_-92uD_6uj8yEFTEnlSLwxH6EnQHo_n5U0000__y30000)
