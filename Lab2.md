# LAB2
## Các ca sử dụng cần phân tích trong Payroll System.
- **Quản lý nhân viên (Employee Management)**
- **Quản lý chấm công (Timecard Management)**
- **Tính toán lương (Payroll Calculation)**
- **Xử lý thanh toán (Payment Processing)**
- **Quản lý cơ sở dữ liệu (Database Management)**


## 1.  Quản lý nhân viên (Employee Management)

**Mục đích:**
- Thêm, sửa, và xóa thông tin nhân viên.
- Xem thông tin chi tiết về nhân viên như tên, ID, loại hợp đồng, loại lương, v.v.
  
**Các lớp phân tích:**
- **Employee (Nhân viên):**
  - Thuộc tính: id, name, paymentType, salaryRate, contractType, etc.
  - Nhiệm vụ: Quản lý thông tin về nhân viên.
  
- **EmployeeController (Điều khiển nhân viên):**
  - Nhiệm vụ: Xử lý các yêu cầu thêm, sửa, hoặc xóa nhân viên.
  - Quan hệ: Kết nối với Employee và PayrollDatabase để thao tác trên dữ liệu nhân viên.
  
- **EmployeeView (Giao diện nhân viên):**
  - Nhiệm vụ: Hiển thị giao diện người dùng để thêm, sửa, hoặc xóa nhân viên.
  
- **Biểu đồ lớp phân tích:**
  - EmployeeController sẽ tương tác với Employee và PayrollDatabase để thêm, sửa, hoặc xóa thông tin nhân viên.
  - EmployeeView sẽ gửi yêu cầu từ người dùng (thêm, sửa, xóa) đến EmployeeController.

## 2.  Quản lý chấm công (Timecard Management)

**Mục đích:**
- Thêm, sửa, xóa thẻ chấm công cho nhân viên.
- Cập nhật giờ làm việc của nhân viên mỗi ngày.
  
**Các lớp phân tích:**
- **Timecard (Thẻ chấm công):**
  - Thuộc tính: date, hoursWorked, employeeId.
  - Nhiệm vụ: Quản lý thông tin thẻ chấm công của từng nhân viên.
  
- **TimecardController (Điều khiển thẻ chấm công):**
  - Nhiệm vụ: Điều khiển và xử lý các yêu cầu từ người dùng liên quan đến thẻ chấm công.
  - Quan hệ: Kết nối với Timecard và PayrollDatabase để cập nhật hoặc xóa thẻ chấm công.

  
- **TimecardView (Giao diện thẻ chấm công):**
  - Nhiệm vụ: Hiển thị giao diện người dùng để thêm, sửa, hoặc xem thông tin chấm công.
    
**Biểu đồ lớp phân tích:**
- TimecardController sẽ tương tác với Timecard và PayrollDatabase để thêm, sửa, hoặc xóa thẻ chấm công của nhân viên.
- TimecardView sẽ gửi yêu cầu từ người dùng đến TimecardController.

## 3. Tính toán lương (Payroll Calculation)

**Mục đích:**
- Tính toán lương cho nhân viên dựa trên số giờ làm việc (theo giờ), các khoản thưởng/phạt, các khoản khấu trừ.
- Cập nhật lương và các thông tin liên quan như bảo hiểm, thuế, v.v.
  
**Các lớp phân tích:**
- **PayrollCalculator (Tính toán lương):**
  - Nhiệm vụ: Tính toán tổng lương cho nhân viên dựa trên các yếu tố như số giờ làm việc, mức lương, thưởng, phạt, và các khoản khấu trừ.
  - Thuộc tính: hoursWorked, salaryRate, bonus, penalty, deductions, totalSalary.
  
- **Employee (Nhân viên):**
  -  Quan hệ: PayrollCalculator sẽ truy xuất thông tin nhân viên để tính toán lương.

  
- **PayrollDatabase (Cơ sở dữ liệu lương):**
  - Nhiệm vụ: Lưu trữ và quản lý thông tin lương và các khoản thanh toán..

- **PayrollController (Điều khiển tính toán lương):**
  - Nhiệm vụ: Điều khiển và xử lý các yêu cầu tính toán lương.
  - Quan hệ: PayrollController sẽ liên kết với PayrollCalculator để tính toán và cập nhật lương của nhân viên.
  - 
**Biểu đồ lớp phân tích:**
- PayrollController sẽ kết nối với PayrollCalculator và PayrollDatabase để tính toán và lưu trữ kết quả tính lương.
- PayrollView sẽ hiển thị kết quả tính lương cho người dùng.

## 4. Xử lý thanh toán (Payment Processing)

**Mục đích:**
- Thanh toán lương cho nhân viên qua các hình thức như tiền mặt, chuyển khoản, hoặc séc.
  
**Các lớp phân tích:**
- **Payment (Thanh toán)::**
  - Thuộc tính: amount, paymentDate, paymentMethod (tiền mặt, chuyển khoản, séc).
  - Nhiệm vụ: Quản lý thông tin thanh toán, bao gồm số tiền và phương thức thanh toán.
  
- **PaymentController (Điều khiển thanh toán):**
  - Nhiệm vụ: Điều khiển và xử lý các yêu cầu thanh toán.
  - Quan hệ: Liên kết với Payment và PayrollDatabase để thực hiện thanh toán cho nhân viên.
  
- **Employee (Nhân viên):**
  - Quan hệ: PaymentController sẽ xác định số tiền thanh toán dựa trên thông tin lương của Employee.

- **PaymentView (Giao diện thanh toán):**
  - Nhiệm vụ: Hiển thị giao diện cho người dùng để lựa chọn nhân viên và phương thức thanh toán.
    
**Biểu đồ lớp phân tích:**
- PaymentController sẽ xử lý yêu cầu thanh toán, kết nối với Payment và PayrollDatabase để thực hiện thanh toán.
- PaymentView sẽ giao tiếp với PaymentController để thực hiện thao tác thanh toán.

## 5. Quản lý cơ sở dữ liệu (Database Management)

**Mục đích:**
- Quản lý và lưu trữ tất cả dữ liệu của hệ thống, bao gồm thông tin nhân viên, thẻ chấm công, thông tin thanh toán, và các khoản lương.
  
**Các lớp phân tích:**
- **PayrollDatabase (Cơ sở dữ liệu lương):**
  - Nhiệm vụ: Quản lý tất cả các dữ liệu của hệ thống, bao gồm nhân viên, thẻ chấm công, và các khoản thanh toán.
  - Quan hệ: PayrollDatabase sẽ lưu trữ dữ liệu từ tất cả các lớp khác trong hệ thống (nhân viên, thẻ chấm công, thanh toán).
  
- **DatabaseController (Điều khiển cơ sở dữ liệu):**
  - Nhiệm vụ: Cung cấp các phương thức để truy xuất và thao tác với cơ sở dữ liệu.
  - Quan hệ: DatabaseController sẽ làm việc với PayrollDatabase để thực hiện các thao tác cơ bản như lưu trữ, cập nhật, xóa dữ liệu.

**Biểu đồ lớp phân tích:**
- DatabaseController sẽ tương tác với PayrollDatabase để lưu trữ và truy xuất dữ liệu từ các lớp khác trong hệ thống.
