# Lab1

## 1. Phân tích kiến trúc
### Đề xuất Kiến trúc: Tôi chọn kiến trúc "MVC" cho hệ thống "Payroll System" :

### Các thành phần trong kiến trúc :
**Kiến trúc MVC (Model-View-Controller) là kiến trúc phù hợp cho hệ thống "Payroll System" vì:**

**Model:** Quản lý dữ liệu và logic nghiệp vụ, xử lý các thao tác liên quan đến nhân viên, thẻ chấm công, và các hình thức thanh toán lương.

**View:** Hiển thị giao diện người dùng (UI), cho phép người dùng nhập thông tin và xem kết quả như báo cáo thanh toán hoặc thông tin chấm công.

**Controller:** Điều khiển luồng dữ liệu giữa View và Model, xử lý các yêu cầu từ người dùng, và cập nhật View sau khi các tác vụ nghiệp vụ trong Model hoàn tất.

**Giải thích lý do lựa chọn kiến trúc**
- Phân tách rõ ràng: Kiến trúc MVC tách biệt rõ ràng giữa giao diện người dùng, logic nghiệp vụ và điều khiển, giúp hệ thống dễ mở rộng và bảo trì.
- Tăng tính tái sử dụng: Thành phần Model chứa logic nghiệp vụ có thể tái sử dụng trong các ứng dụng khác, hoặc thay đổi giao diện mà không cần ảnh hưởng đến các thành phần khác.
- Dễ mở rộng và bảo trì: Khi cần thay đổi logic hoặc giao diện, các thay đổi này sẽ không ảnh hưởng đến toàn bộ hệ thống mà chỉ tác động tới từng lớp riêng biệt.
  ### BIỂU ĐỒ PACKAGE :
  
  ![](https://www.planttext.com/api/plantuml/png/R9912i8m44NtSuh10tW4KTIb82ZkntJGOD98CaMAU38N7iahs1PhKvDb_X_Uptpc_NpDWv2NoXe85rsYTu51j1Z6BTNU6OExEWXRN7Xrri9AAiy0Lr8NEZ5E3ffl4xm3eZ8K0gxjrRYQkTL_ubvRLkIBaTZmBPVIQO-8k7IbjC7iSzp1JUWPwviHEN7InXLiSY49-XyOlrlmYeIEr5JNuEC6S3gTvRuU5zBDP7Q8-kb6qbqW9Oy28QMEmY11na43lbT7c_QGhFb5P3sOSrcq1_S1003__mC0)
## 2. Cơ chế phân tích

  ### Các cơ chế cần giải quyết trong bài toán:

  **Một số cơ chế cần giải quyết trong hệ thống "Payroll System":**

- **Quản lý nhân viên:** Xử lý các thao tác thêm mới, chỉnh sửa, và xoá nhân viên.
- 
- **Quản lý chấm công:** Lưu trữ và xử lý thông tin thẻ chấm công hàng ngày của nhân viên.
- 
- **Thanh toán lương:** Xử lý thanh toán lương theo nhiều hình thức khác nhau như thanh toán bằng tiền mặt, chuyển khoản hoặc séc.
- 
- **Tính toán lương tự động:** Tự động tính toán tổng lương dựa trên số giờ làm việc, các khoản thưởng/phạt và các khoản khấu trừ.
- 

### Danh Sách Cơ Chế : 
- Quản lý nhân viên (Employee Management)
- Quản lý chấm công (Timecard Management)
- Tính toán lương (Payroll Calculation)
- Xử lý thanh toán (Payment Processing)
- Quản lý cơ sở dữ liệu (Database Management)
## 3. Phân Tích Ca Sử Dụng Payment
### 3.1 Các lớp phân tích cho ca sử dụng Payment.
**Các lớp phân tích :**

**Employee (Nhân viên):**

- Nhiệm vụ: Quản lý thông tin về nhân viên như tên, ID, loại lương (lương theo giờ, lương cố định, hoặc lương theo hợp đồng).
- Thuộc tính: id, name, paymentType, salaryRate.
- Quan hệ: Kết nối với lớp Payment để xử lý các yêu cầu thanh toán.

**Payment (Thanh toán):**
- Nhiệm vụ: Quản lý thông tin về các khoản thanh toán, bao gồm số tiền, ngày thanh toán, và phương thức thanh toán.
- Thuộc tính: amount, paymentDate, paymentMethod.
- Quan hệ: Liên kết với Employee để thực hiện thanh toán cho nhân viên.

**PayrollDatabase (Cơ sở dữ liệu lương):**

- Nhiệm vụ: Lưu trữ và quản lý thông tin nhân viên và các khoản thanh toán.
- Quan hệ: Liên kết với các lớp khác để lưu và truy xuất thông tin.

**PaymentController (Điều khiển thanh toán):**

- Nhiệm vụ: Điều khiển và xử lý các yêu cầu thanh toán, kết nối giữa giao diện người dùng và các lớp logic nghiệp vụ.
- Quan hệ: Liên kết với Employee, Payment, và PayrollDatabase để thực hiện luồng thanh toán.

**EmployeeView (Giao diện nhân viên):**

- Nhiệm vụ: Hiển thị giao diện cho người dùng chọn nhân viên và yêu cầu thanh toán.
- Quan hệ: Gửi yêu cầu tới PaymentController.

### Biểu đồ lớp phân tích :
![](https://www.planttext.com/api/plantuml/png/T98zJiD048NxFSKebIbSqBf0aH8A2gGe_FGJUt1Mx8_P7GTPY9DHS2IkmDhUjMmI6g_rPkPzRyV--VfUUqR7hLR2lqe3pdeIB5aHR1Hw3rk9jKCDBzR13ZjDXk79Xog6Hb4EFRUwKROZWWy1a8Ei2f26XtU3cWfuO2TDFGZDwF7ODKlTeqBNxP63NDdse2Z802MgibL1ZUpigaWnn6VYfrmZ7hLj3SzS9kXsSE-VS_MU-6YhMHW8OKvpuCdAQa5pLgbWWuUmX84AK1EdDMHn0M4oIMUkaJrTvXAbrpVMS4yZ5pb7D9LADdjwQybpHX5pDu6NPYd6iwJtwEF6qGktdBxcwde5UNupd6dd_nNd6n7dsVlEQHUNotzD5fbZmt9CY3MPglzrVm400F__0m00)

### Biểu đồ sequence :
![](https://www.planttext.com/api/plantuml/png/R991JiGm34NtEOMNiE02NQ2HcWgneffHktSp7XH8avAue9wD1KVY2ZXbIWlCCldVxzjEFjy_TeanyjWxbPwjXnWIARRi20xqCf8t1DhYOyGUJY52ZLDFdg5912MALw5XkPTp14pGg45mrjW1nLNrWmiJKMlfBQjL-qi-myhWEGRdlWbr-TUJDOsCdUJD3dqnP0wun9zhb6hWvbOwA6GmHsPJjvbBLMrsrMK1-pn-MY7PjPIekfnjke0xsf1obt3LJN2lhrMjLnIFqQ-sX-v96ZX3ga8MwSpea6bjOouL9TBcMa0cnECc_O2l_zMB8WTOThW4oogqJOF3wSSbJt6oiKUsmIkr8t_CF-CB003__mC0)


## 4. Phân tích ca sử dụng Maintain Timecard
**Các lớp phân tích :**
**Employee (Nhân viên):**

- Nhiệm vụ: Quản lý thông tin cơ bản của nhân viên như ID, tên, và danh sách thẻ chấm công.
- Thuộc tính: id, name, timecards.
- Quan hệ: Liên kết với lớp Timecard để thêm thẻ chấm công mới cho nhân viên.

**Timecard (Thẻ chấm công):**

- Nhiệm vụ: Quản lý thông tin về giờ làm việc của nhân viên cho mỗi ngày làm việc, bao gồm ngày làm việc và số giờ làm.
- Thuộc tính: date, hoursWorked.
- Quan hệ: Liên kết với lớp Employee để quản lý các thẻ chấm công của nhân viên.

**PayrollDatabase (Cơ sở dữ liệu lương):**
- Nhiệm vụ: Lưu trữ và quản lý thông tin của nhân viên và thẻ chấm công.
- Quan hệ: Liên kết với các lớp khác để lưu và truy xuất thông tin thẻ chấm công và nhân viên.

**TimecardController (Điều khiển thẻ chấm công):**

- Nhiệm vụ: Điều khiển luồng xử lý khi có yêu cầu từ người dùng liên quan đến quản lý thẻ chấm công.
- Quan hệ: Liên kết với lớp Employee và PayrollDatabase để cập nhật thẻ chấm công cho nhân viên.

**TimecardView (Giao diện thẻ chấm công):**

- Nhiệm vụ: Hiển thị giao diện để người dùng nhập thông tin thẻ chấm công.
- Quan hệ: Gửi yêu cầu tới TimecardController để xử lý việc thêm mới hoặc cập nhật thẻ chấm công.

### Biểu đồ lớp phân tích :
![](https://www.planttext.com/api/plantuml/png/T5B9JiCm4BtxAqOv5THKS8rGLQdbW0GI4jjv4W_1gXrNzgIeGdmP1pw9Ny3PtB3aa2YUUMkIhu_FbMTqN1ij_5PLuAmdmOermLgZzx1HM3eqy6mTtA2gE5nmhmmLw2Gy-833G155YxuqEsqFHF0c059GCeD0QPyhD9J17JjLbUs0Un6VmRNoV368BiCM0AKS1ZCkicXvai7UAYdU1ykOfREKoC5c4-xjySNMpZzPjwKGHTewrtIatkB1MQq36FDGebK0A8c76hE-G30THYt4uvvYEZAxuteotjfMt9YHwst61QbdNtLsyr6BULTX23-f_wZejLVsTMuKH_4H9NwUv3o1D5r2ShPOd2PHHFoJje75yXFxNozI_0ZL0FxoX5XH9Pl_xXi00F__0m00)

### Biểu đồ sequence :
![](https://www.planttext.com/api/plantuml/png/R99DJiCm44RtFiKiMmaka0KgSY900X6Hd_qacLQ6s0xs19IpiU18N04xqAQHkiZ2_fxVDxRoy_MzyuoEHzqB_wOCEEj9iEAUeA3taKnBa2eyEDImjmwUK1aE7vHAKukkWyeJI0od1BOSYB1sW1ugCGInQjM0XazuhUWpfcLzCPRMiBDz_wSevGhASOfPYenDA8n4dgw8J0-zdMYEiei5irQ82gvlmWm956EZrLcy2NQwWdixEhyLPJrpCe6N-1YUWItSTjs95wMCH9ucS4Td_N56s3GJFAHRaQUBXKTd5kovUQMM_oLPibAl9ybcHGBIKTXU-hDZVO4V1DNGXNHnmAFoHtsyRNZUlN9woUVhUw-i4M97fel_mIy0003__mC0)


## 5. Hợp nhất kết quả phân tích:
### Cả hai ca sử dụng Payment và Maintain Timecard đều tương tác với các lớp chính của hệ thống và chia sẻ một số lớp cơ sở dữ liệu để lưu trữ và truy xuất dữ liệu. Các lớp chính bao gồm:

- **Employee** Lớp này đại diện cho nhân viên trong hệ thống, bao gồm thông tin như ID, tên, loại lương, và danh sách thẻ chấm công.
- **PayrollDatabase:** Lớp này quản lý tất cả dữ liệu của hệ thống, bao gồm thông tin nhân viên, thẻ chấm công và thông tin thanh toán.
- **Payment và Timecard:** Hai lớp này quản lý các loại dữ liệu khác nhau—thông tin thanh toán và thẻ chấm công tương ứng.
- **Controllers (PaymentController, TimecardController):** Các lớp điều khiển giúp kết nối giữa giao diện người dùng và logic nghiệp vụ, xử lý các yêu cầu từ người dùng và thực hiện các thao tác cần thiết trên dữ liệu.
- **Views (EmployeeView, TimecardView):** Là giao diện người dùng, cho phép người dùng tương tác với hệ thống để thực hiện các tác vụ khác nhau.

**KẾT LUẬN** : Hệ thống Payroll System với các ca sử dụng Payment và Maintain Timecard được thiết kế dựa trên kiến trúc MVC, cho phép tách biệt rõ ràng giữa giao diện người dùng, logic nghiệp vụ và cơ sở dữ liệu. Phân tích này đã xác định các lớp cần thiết và mối quan hệ giữa chúng, đảm bảo hệ thống hoạt động hiệu quả và đáp ứng các yêu cầu quản lý thanh toán và thẻ chấm công cho nhân viên.
