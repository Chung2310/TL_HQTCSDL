## Thông tin cá nhân
- Họ và Tên: Đỗ Đức Chung
- MSSV: K215480106085
- Lớp: K57KMT
- Môn học: Hệ quản trị cơ sở dữ liệu
## Tên bài toán
- Đề tài: Quản lý nhà thuốc An Khang
## Các chức năng
Bài toán quản lý sản phẩm trong nhà thuốc nhằm đảm bảo quản lý hiệu quả và tối ưu hóa kho hàng
- Quản lý thông tin sản phẩm: Thêm sản phẩm, sửa thông tin sản phẩm, xóa sản phẩm, liệt kê hàng hóa.
- Quản lý thông tin đơn hàng: Thêm đơn hàng, sửa đơn hàng, xóa đơn hàng, liệt kê đơn hàng.
- Quản lý thông tin khách hàng: Thêm thông tin khách hàng, sửa thông tin khách hàng, xóa thông tin khách hàng, liệt kê danh sách các mặt hàng mà khách hàng đã mua
- Quản lý thông tin nhà cung cấp: Thêm thông tin nhà cung cấp, sửa thông tin nhà cung cấp, xóa thông tin nhà cung cấp, liệt kê danh sách các mặt hàng mà nhà cung cấp đó đã cung cấp
- Quản lý nhân viên, người quản lý: Thêm thông tin nhân viên, sửa thông tin nhân viên, xóa thông tin nhân viên, liệt kê các hóa đơn mà nhân viên đã bán,...
- Quản lý việc thông kê sản phẩm: Thêm phiếu thông kê, sửa thông tin phiếu thông kê, xóa phiếu thống kê,...
## Báo cáo
- Báo cáo sản phẩm sắp hết hạn
- Báo cáo các sản phẩm tồn kho
- Báo cáo tổng tiền của một hóa đơn 
## Các bảng của hệ thống
- Bảng NhanVien(MaNhanVien, TenNhanVien, GioiTinh, NgaySinh, DiaChi, SDT, LuongCoBan, PhuCap, TaiKhoan, MatKhau, MaQuanLy);
- Bảng QuanLy(MaQuanLy, TenQuanLy, NgaySinh, SDT, DiaChi, TaiKhoan, MatKhau);
- Bảng PhieuThongKe(SoPhieuThongKe, MaNhanVien, NgayThongKe);
- Bảng ChiTietPhieuThongKe(SoPhieuThongKe, MaSanPham, SoLuongDaBan, TongTien);
  - Hình ảnh bảng
  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/d16982f3-092f-46b9-a786-9cba4c411d93)
  - Mô tả bảng:
      - Trường SoPhieuThongKe là Primary Key vì SoHoaDon bảm đảm tính duy nhất và toàn vẹn của dữ liệu trong bảng => SoPhieuThongKe không được phép Null. Kiểu dữ liệu là nvarchar(50)
      - Trường MaSanPham là Foreign Key vì MaSanPham đảm bảo mỗi quan hệ giữa các bảng được duy trì chính xác. Kiểu dữ liệu là nvarchar(50)
      - Trường SoLuongDaBan có kiểu INT. Có CK không cho phép nhập giá trị nhỏ hơn hoặc bằng 0.
      - Trường TongTien có kiểu BIGINT. Có CK không cho phép nhập giá trị nhỏ hơn hoặc bằng 0.  Giá trị của trường sẽ được tính toán thông qua 1 PROCEDURE có tên là CalculatorTongTienTheoNgay. TongTien = ChiTietDonHang.SoLuong * SanPham.GiaBan.
- Bảng ThanhToan(MaHinhThucThanhToan, TenHinhThucThanhToan);
- Bảng DonHang(SoHoaDon, MaKhachHang, MaNhanVien, NgayBan, MaHinhThucThanhToan);
- Bảng ChiTietDonHang(SoHoaDon, MaSanPham, SoLuong, GiamGia, TongTien);
  - Hình ảnh bảng
  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/3bbc28a8-50f1-42dc-b857-e1de01ec1c7c)
  - Mô tả bảng:
      - Trường SoHoaDon là Primary Key vì SoHoaDon bảm đảm tính duy nhất và toàn vẹn của dữ liệu trong bảng => SoHoaDon không được phép Null. Kiểu dữ liệu là nvarchar(50)
      - Trường MaSanPham là Foreign Key vì MaSanPham đảm bảo mỗi quan hệ giữa các bảng được duy trì chính xác. Kiểu dữ liệu là nvarchar(50)
      - Trường SoLuongBan có kiểu INT. Có CK không cho phép nhập giá trị nhỏ hơn hoặc bằng 0.
      - Trường GiamGia có kiểu BIGINT. Có CK không cho phép nhập giá trị nhỏ hơn hoặc bằng 0.
      - Trường TongTien có kiểu BIGINT. Có CK không cho phép nhập giá trị nhỏ hơn hoặc bằng 0. Giá trị của trường sẽ được tính toán thông qua 1 PROCEDURE có tên là CalculatorTongTien. TongTien = ChiTietDonHang.SoLuong * SanPham.GiaBan.
      ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/b9374c9b-ebfd-4206-8c96-4e576a459c39)
      ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/c2c1e79d-fd68-4bee-8a4d-8cc5eeea2573)
- Bảng KhachHang(MaKhachHang, TenKhachHang, GioiTinh, DiaChi, SDT);
- Bảng SanPham(MaSanPham, TenSanPham, MaNhaCC, SoLuong, GiaBan, NgaySanXuat, HanSuDung);
- Bảng NhaCungCap(MaNhaCC, TenNhaCC, DiaChi, SDT, Email, NguoiDaiDien);
