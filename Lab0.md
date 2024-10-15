# Lab0

## Biểu đồ lớp
![](https://www.planttext.com/api/plantuml/png/T99DQiCm48NtEiNWLLf8IBTQb4136yWoli0W6skeFIgML0YbwnwZHoXTQz6p-0IzGcNy8qmQBOJvtdZcwKc_uMTd7RREDxKGgaPhuQXHwGDo1My2-jNWZ2ISN4jS3O8h-Oh25PvFn5h27bqvi8BmGTEopfezbPnhWqbudupaICUeSF8naOicNi9ZRT0D87xH_wMDcVZgHiAheMBqYozvDB9oSHjRBVJMkslwRFU9C9v6wMHt8fVP92NbOqsUkey1QwyE_Tmqp3uJGsjiAKIwgEmkW_KQikrcSvkbt2JOBdo2xiANXtinysNvx5l6ULtuLg2f2nyS_n2xael-QVm1003__mC0)

## Mô Tả Biểu Đồ Lớp - Hệ Thống Quản Lý Ngân Hàng

### Tóm Tắt

Biểu đồ lớp mô tả các thành phần chính trong hệ thống quản lý ngân hàng, bao gồm các lớp `KhachHang`, `TaiKhoan`, và `GiaoDich`. Mỗi lớp có các thuộc tính và phương thức riêng, phục vụ cho các chức năng quản lý thông tin khách hàng, tài khoản ngân hàng và các giao dịch.

### Chi Tiết Các Lớp

1. **KhachHang**
   - **Thuộc Tính**:
     - `maKhachHang: String`: Mã định danh của khách hàng.
     - `tenKhachHang: String`: Tên của khách hàng.
     - `ngaySinh: Date`: Ngày sinh của khách hàng.
     - `diaChi: String`: Địa chỉ của khách hàng.
     - `soDienThoai: String`: Số điện thoại của khách hàng.
   - **Mô Tả**: Lớp này đại diện cho thông tin của khách hàng trong hệ thống.

2. **TaiKhoan**
   - **Thuộc Tính**:
     - `maTaiKhoan: String`: Mã định danh của tài khoản.
     - `soDu: Float`: Số dư hiện tại của tài khoản.
     - `loaiTaiKhoan: String`: Loại tài khoản (tiết kiệm, thanh toán, v.v.).
   - **Phương Thức**:
     - `moTaiKhoan(): void`: Mở tài khoản mới.
     - `napTien(tien: Float): void`: Nạp tiền vào tài khoản.
     - `rutTien(tien: Float): void`: Rút tiền từ tài khoản.
   - **Mô Tả**: Lớp này quản lý các thông tin liên quan đến tài khoản ngân hàng của khách hàng.

3. **GiaoDich**
   - **Thuộc Tính**:
     - `maGiaoDich: String`: Mã định danh của giao dịch.
     - `ngayGiaoDich: Date`: Ngày thực hiện giao dịch.
     - `soTien: Float`: Số tiền giao dịch.
   - **Phương Thức**:
     - `thucHien(): void`: Thực hiện giao dịch.
   - **Mô Tả**: Lớp này đại diện cho các giao dịch tài chính của khách hàng trong hệ thống.

### Mối Quan Hệ Giữa Các Lớp

- **KhachHang** và **TaiKhoan**: Một khách hàng có thể sở hữu nhiều tài khoản (1 - 0..*).
- **TaiKhoan** và **GiaoDich**: Một tài khoản có thể có nhiều giao dịch (1 - 0..*).

## BIểu đồ gói 
![](https://www.planttext.com/api/plantuml/png/Z5FDIiD04BxlKmozg8U-G0-bOC12eo06wNNPXkpIP3Sc6R18pvvz0ps8frBF3UAXu7la2Nm5D-bFTfCepYKmizytttmp-Su_Hsb6amoZa92OiZaDVEXT2Ah04KN-A7lmG4072scQGbbmX2-l0bJ2GHdigrLa7DbO5tUF63yzgsjtIAMxyAYOS4NblhBiOkPKtkglIRm3JpXbV4nbS4Gl3SdJ8b-1k_smzLvRRKtEI3N4L25fxEdcPYh1p4YPagVeBWwp_iE7PKlNSI8RxKVDKQj8aNRcxrKhRrlZ5FaQt7ARQBjphcwKWwxmiSkX4D7ZIWQUa7_ihURedCOWwHAPpeM4HAK-EO7B8dyIrQw1QwqGQCLh2cpxmhGfssV98UR5vasIzXNs-yFchWUGbYSnA_9N_M18MWTMOshbJL23iuHqc3Q0yEiT8KjAem-WcjH6cSqic7LEltRA4bm0ApQhM4F8o9UpyjVz0G00__y30000)

## Mô Tả Biểu Đồ Gói - Hệ Thống Quản Lý Ngân Hàng

### Tóm Tắt

Biểu đồ gói mô tả cấu trúc tổng thể của hệ thống quản lý ngân hàng, chia thành các gói chính: **Giao Diện**, **Xử Lý**, và **Dữ Liệu**. Mỗi gói chứa các thành phần cụ thể, đảm nhận các chức năng khác nhau trong hệ thống.

### Chi Tiết Các Gói

1. **Giao Diện**
   - **Giao Diện Người Dùng**: Cung cấp giao diện cho khách hàng để thực hiện các giao dịch và quản lý tài khoản.
   - **Giao Diện Nhân Viên**: Cung cấp giao diện cho nhân viên ngân hàng để quản lý thông tin khách hàng và thực hiện các nhiệm vụ liên quan.

2. **Xử Lý**
   - **Quản Lý Tài Khoản**: Chịu trách nhiệm về các chức năng quản lý tài khoản như mở tài khoản, nạp tiền và rút tiền.
   - **Xử Lý Giao Dịch**: Thực hiện các giao dịch tài chính giữa khách hàng và ngân hàng.
   - **Quản Lý Khách Hàng**: Quản lý thông tin của khách hàng, bao gồm thêm, sửa đổi và xóa thông tin khách hàng.

3. **Dữ Liệu**
   - **Cơ Sở Dữ Liệu Tài Khoản**: Lưu trữ thông tin về các tài khoản ngân hàng.
   - **Cơ Sở Dữ Liệu Khách Hàng**: Lưu trữ thông tin về khách hàng, bao gồm thông tin cá nhân và các tài khoản mà họ sở hữu.

### Mối Quan Hệ Giữa Các Thành Phần

- **Giao Diện Người Dùng** sử dụng **Quản Lý Tài Khoản** để thực hiện các thao tác liên quan đến tài khoản.
- **Giao Diện Nhân Viên** sử dụng **Quản Lý Khách Hàng** để quản lý thông tin khách hàng.
- **Quản Lý Tài Khoản** lưu trữ thông tin vào **Cơ Sở Dữ Liệu Tài Khoản**.
- **Quản Lý Khách Hàng** lưu trữ thông tin vào **Cơ Sở Dữ Liệu Khách Hàng**.
- **Xử Lý Giao Dịch** truy cập vào **Cơ Sở Dữ Liệu Tài Khoản** để thực hiện giao dịch.



## Biểu đò ca sử dụng 
![](https://www.planttext.com/api/plantuml/png/f5AzJiCm4Dxz53Uchv0CL6H1IiMKXJ4gBZubSQB4AMBkmC34X9YWOgYer0ccUEZWleYVW5VWuWH2nOJmzDtv-x7F_j3xQQsIIZLvnkeK9LH5pPbhCJyILZyX7EwjVfHNi4IhR-TK7bPKIM7RNHamvfyx1CfivV4cBCqpv8GKfDHuRJfsH2wh75ILa68d1L38ImaPUSFSwWsrXNad3uNoLnOkm8l7xL5wCY4Pb-25vct2W9OVYkQ6eZeJs-ubn5L2ib1qeG7ZMSt1YvpN83X3Hu_9zGw6b5EpBc1czGC6FUd2R1i8RRjfOBZtpBPh_EB7A7jYnKkUA0UTxYz3-XRzPrRZ8U1QOCQF1fVsyEVy69UNk63qzaN9s9Igxazy0W00__y30000)

## Mô Tả Biểu Đồ Ca Hoạt Động - Quy Trình Đăng Nhập

### Tóm Tắt

Biểu đồ ca hoạt động mô tả quy trình đăng nhập của người dùng vào hệ thống quản lý ngân hàng. Quy trình này bao gồm các bước nhập thông tin đăng nhập, xác thực thông tin, và xử lý các tình huống khác nhau dựa trên kết quả xác thực.

### Chi Tiết Quy Trình

1. **Bắt Đầu**: 
   - Quy trình bắt đầu với việc người dùng khởi động việc đăng nhập.

2. **Nhập Thông Tin Đăng Nhập**:
   - Người dùng nhập tên đăng nhập và mật khẩu.

3. **Xác Thực Thông Tin**:
   - Hệ thống kiểm tra tính hợp lệ của thông tin đăng nhập.
   - Nếu thông tin được xác thực thành công:
     - **Chuyển đến Trang Chính**: Người dùng được chuyển đến trang chính của hệ thống.
   - Nếu thông tin không chính xác:
     - **Hiển Thị Thông Báo Lỗi**: Hệ thống hiển thị thông báo lỗi cho người dùng.
     - **Yêu Cầu Nhập Lại Thông Tin**: Người dùng được yêu cầu nhập lại tên đăng nhập và mật khẩu.
     - **Lặp Lại Quy Trình Nhập Thông Tin**: Quy trình này lặp lại cho đến khi thông tin được xác thực thành công.

4. **Kết Thúc**: 
   - Quy trình kết thúc khi người dùng đã đăng nhập thành công vào hệ thống.


