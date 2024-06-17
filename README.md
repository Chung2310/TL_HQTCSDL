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
- Bảng ThanhToan(MaHinhThucThanhToan, TenHinhThucThanhToan);
- Bảng DonHang(SoHoaDon, MaKhachHang, MaNhanVien, NgayBan, MaHinhThucThanhToan);
- Bảng ChiTietDonHang(SoHoaDon, MaSanPham, SoLuong, GiamGia, TongTien);
- Bảng KhachHang(MaKhachHang, TenKhachHang, GioiTinh, DiaChi, SDT);
- Bảng SanPham(MaSanPham, TenSanPham, MaNhaCC, SoLuong, GiaBan, NgaySanXuat, HanSuDung);
- Bảng NhaCungCap(MaNhaCC, TenNhaCC, DiaChi, SDT, Email, NguoiDaiDien);
