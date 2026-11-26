# QuanLyThuVien
# Phần mềm quản lý thư viện

Đồ án phần mềm Java: xây dựng phần mềm quản lý thư viện bằng Java Swing, kết nối cơ sở dữ liệu SQL Server.

## Thông tin sinh viên

- Họ và tên: Nguyễn Văn Dũng
- Mã sinh viên: 3025101107
- Lớp: TH30.18

## Chức năng

- **Quản lý sách:** thêm, sửa, xóa, tìm kiếm theo mã, tên, tác giả, thể loại.
- **Quản lý độc giả:** thêm, sửa, xóa, tìm kiếm theo mã, họ tên, số điện thoại.
- **Mượn / trả sách:** lập phiếu mượn (tự trừ số lượng trong kho), trả sách (tự cộng lại kho), tìm kiếm phiếu mượn.

## Công nghệ sử dụng

- Ngôn ngữ: Java 17, giao diện Java Swing
- Cơ sở dữ liệu: Microsoft SQL Server
- Kết nối: JDBC (mssql-jdbc)
- Quản lý thư viện: Maven

## Cơ sở dữ liệu

Cơ sở dữ liệu `QuanLyThuVien` gồm 5 bảng:

- `TheLoai`: thể loại sách
- `Sach`: thông tin sách (khóa ngoại tới `TheLoai`)
- `DocGia`: thông tin độc giả
- `PhieuMuon`: phiếu mượn (khóa ngoại tới `DocGia`)
- `ChiTietPhieuMuon`: chi tiết phiếu mượn (khóa ngoại tới `PhieuMuon` và `Sach`)

Script tạo cơ sở dữ liệu và dữ liệu mẫu nằm trong thư mục `sql/`.

## Hướng dẫn chạy

1. Mở SQL Server Management Studio, chạy file `sql/QuanLyThuVien.sql`.
2. Bật giao thức TCP/IP cho SQL Server (cổng 1433) và chế độ đăng nhập SQL Server Authentication.
3. Mở file `src/main/java/thuvien/DBConnection.java`, sửa `USER` và `PASSWORD` cho đúng với máy của bạn.
4. Mở thư mục dự án như một Maven project (NetBeans, IntelliJ hoặc Eclipse) và chạy lớp `thuvien.MainForm`.
   Hoặc dùng dòng lệnh: `mvn compile exec:java`

## Cấu trúc thư mục

- `sql/QuanLyThuVien.sql`: script tạo cơ sở dữ liệu
- `src/main/java/thuvien/DBConnection.java`: kết nối SQL Server
- `src/main/java/thuvien/MainForm.java`: form chính
- `src/main/java/thuvien/SachForm.java`: form quản lý sách
- `src/main/java/thuvien/DocGiaForm.java`: form quản lý độc giả
- `src/main/java/thuvien/MuonTraForm.java`: form mượn / trả sách
- `src/main/java/thuvien/Item.java`: lớp phụ cho ComboBox
- `pom.xml`: cấu hình Maven
