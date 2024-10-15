# Lab0

## Biểu đồ lớp
![](https://www.planttext.com/api/plantuml/png/T99DQiCm48NtEiNWLHg8QRTQ1HeQGvRs1GRPM0Es52mfK4hFqYDqqQKNNVGaFa6lK1d_ACQr5aAyDynyUj9l-tqq5Xlhweg92es1YqGX4rGbl37eLuspn26r3QboC6oXDXnLucjAId8ueIq6BITybhIiC_f4XSganc2yin4aGxfuHmMEILarSHnUAers4Fo9_Y-jzQJl7ZZSDEKZBrup3xApVXjRBVp6sIr_nZqJ-ji86N0dPPrDS48-HcUX-nYmT2BfvzuD2yyJFKLmE43q6CVxAAJ5mNJj1yYk_NHiLfV5Coi7yVF5ZeNA-m_m1m00__y30000)

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
![](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWfB7mztj2Y4P3tTFp4jN22nzk6jndeBFuRqAVkc75-KfU1nUa9Ukf53DfG04S3tkcOdv2YwPG9rvC3aGY4OI1-e_jk7XxhcP2Yw7T-Qbn-9Gb06o92ppyAeyY8fQBbIR8XxkNWjo3eerIAuCERmWKy4x8nyaW6G7J9i2nBA7kxkJCsAn6k2TSNXXSWR4dzYT0DIzNi47vDvI55Su7rke4Fnmztm590Mut8DLBKwhyOMZWgwk7O4Gm1d267enNO3JP8XU8lsCqmuyfc1n2zPO9DeXjLmEgNafeBGE0000__y30000)

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
![](https://www.planttext.com/api/plantuml/png/V50xZi8m4ErzYYd35KYnI3Gh8L53cGq6MoIJADX2r2cfg6WtrGeaYXLKIK5XBk8JS0KcJbW-nRgmPppllPbvr-hSMwWWKpgEc0jOToXiUKX1cJt2PNF9SGRello_MaotWZabE-qpEGLlP8eGbB3LR_sO4v6Kn8yE9Hp1wvjZXm6TRb_ebQtoMjgMPmIL1OGDXJcWy1cF5XoyWHDe2P_ImMljzLtwonG9HBRQIhy1ZSrUGsZB7ztEIjMoa4-ZDC2CfpnGBdIyVtPznxpk_123fP0HVtLWthOLvXi5XCqs72ToIYOdAUjHN3j-0m00__y30000)

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


