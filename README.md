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

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/8ab65837-bc8d-44a6-b89b-c317f719438a)

  - Trường MaNhanVien là Primary Key vì MaNhanVien bảm đảm tính duy nhất và toàn vẹn của dữ liệu trong bảng => MaNhanVien không được phép Null. Kiểu dữ liệu là nvarchar(50)
  - Trường TenNhanVien: nvarchar(50)
  - Trường GioiTinh: nvarchar(10)
  - Trường NgaySinh: datetime
  - Trường DiaChi: nvarchar(100)
  - Trường SDT: nvarchar(10)
  - Trường LuongCoBan: BigInt
  - Trường PhuCap: BigInt
  - Trường TaiKhoan: nvarchar(50)
  - Trường MatKhau: nvarchar(50)
  - Trường MaQuanLy: nvarchar(50)
    
- Bảng QuanLy(MaQuanLy, TenQuanLy, NgaySinh, SDT, DiaChi, TaiKhoan, MatKhau);
  
  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/e2b849b2-6e7f-4fb9-bcd0-21df091d59fe)

  - Trường MaNhanVien là Primary Key vì MaNhanVien bảm đảm tính duy nhất và toàn vẹn của dữ liệu trong bảng => MaNhanVien không được phép Null. Kiểu dữ liệu là nvarchar(50)
  - Trường TenQuanLy: nvarchar(50)
  - Trường NgaySinh: datetime
  - Trường SDT: nvarchar(50)
  - TRường DiaChi: nvarchar(100)
  - Trường TaiKhoan: nvarchar(50)
  - Trường MatKhau: nvarchar(50)
    
- Bảng PhieuThongKe(SoPhieuThongKe, MaNhanVien, NgayThongKe);

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/15b00cc8-90bd-4393-bf34-37aff250efd1)

  - Trường SoPhieuThongKe là Primary Key vì SoPhieuThongKe bảm đảm tính duy nhất và toàn vẹn của dữ liệu trong bảng => SoPhieuThongKe không được phép Null. Kiểu dữ liệu là nvarchar(50)
  - Trường MaNhanVien là Foreign Key vì MaSanPham đảm bảo mỗi quan hệ giữa bảng PhieuThongKe và bảng ChiTietPhieuThongKe. Kiểu dữ liệu là nvarchar(50)
  - Trường NgayThongKe: datetime
    
- Bảng ChiTietPhieuThongKe(SoPhieuThongKe, MaSanPham, SoLuongDaBan, TongTien);
 
   ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/dd050de1-118b-4d60-825e-463c96a4ef34)

  - Trường SoPhieuThongKe là Primary Key vì SoPhieuThongKe bảm đảm tính duy nhất và toàn vẹn của dữ liệu trong bảng => SoPhieuThongKe không được phép Null. Kiểu dữ liệu là nvarchar(50)
  - Trường MaSanPham là Foreign Key vì MaSanPham đảm bảo mỗi quan hệ giữa bảng SanPham và bảng ChiTietPhieuThongKe. Kiểu dữ liệu là nvarchar(50)
  - Trường SoLuongDaBan: int. Có CK không cho phép nhập giá trị nhỏ hơn hoặc bằng 0.
  - Trường TongTien: BIGINT. Có CK không cho phép nhập giá trị nhỏ hơn hoặc bằng 0. 

    ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/22f1edf4-0794-42c6-b4fc-61313e3d38d7)
        
- Bảng ThanhToan(MaHinhThucThanhToan, TenHinhThucThanhToan);

    ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/aca9ede8-dad8-413c-9ff0-d4d2fbd052de)

  - Trường MaHinhThucThanhToan là Primary Key vì MaHinhThucThanhToan bảm đảm tính duy nhất và toàn vẹn của dữ liệu trong bảng => MaHinhThucThanhToan không được phép Null. Kiểu dữ liệu là nvarchar(50)
  - Trường TenHinhThucThanhToan: nvarchar(50)
    
- Bảng DonHang(SoHoaDon, MaKhachHang, MaNhanVien, NgayBan, MaHinhThucThanhToan);

    ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/fc0bca99-b5aa-45d3-a766-7c5b994d9974)

  - Trường SoHoaDon là Primary Key vì SoHoaDon bảm đảm tính duy nhất và toàn vẹn của dữ liệu trong bảng => SoHoaDon không được phép Null. Kiểu dữ liệu là nvarchar(50)
  - Trường MaKhachHang là Foreign Key vì MaKhachHang đảm bảo mỗi quan hệ giữa bảng DonHang và KhachHang. Kiểu dữ liệu là nvarchar(50)
  - Trường MaNhanVien là Foreign Key vì MaNhanVien đảm bảo mỗi quan hệ giữa bảng DonHang và NhanVien. Kiểu dữ liệu là nvarchar(50)
  - Trường NgayBan: datetime
  - Trường MaHinhThucThanhToan là Foreign Key vì MaHinhThucThanhToan đảm bảo mỗi quan hệ giữa bảng DonHang và ThanhToan. Kiểu dữ liệu là nvarchar(50)
    
- Bảng ChiTietDonHang(SoHoaDon, MaSanPham, SoLuong, GiamGia, TongTien);

    ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/3744ba82-e57b-47f9-85ed-daffe56ff783)

  - Trường SoHoaDon là Primary Key vì SoHoaDon bảm đảm tính duy nhất và toàn vẹn của dữ liệu trong bảng => SoHoaDon không được phép Null. Kiểu dữ liệu là nvarchar(50)
  - Trường MaSanPham là Foreign Key vì MaSanPham đảm bảo mỗi quan hệ giữa các bảng được duy trì chính xác. Kiểu dữ liệu là nvarchar(50)
  - Trường SoLuongBan: int. Có CK không cho phép nhập giá trị nhỏ hơn hoặc bằng 0.
  - Trường GiamGia: BIGINT. Có CK không cho phép nhập giá trị nhỏ hơn hoặc bằng 0.
  - Trường TongTien: BIGINT. Có CK không cho phép nhập giá trị nhỏ hơn hoặc bằng 0. Giá trị của trường sẽ được tính toán thông qua 1 PROCEDURE có tên là CalculatorTongTien. TongTien = ChiTietDonHang.SoLuong * SanPham.GiaBan.
    
  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/270b9f08-394c-4685-ac56-177571c4cbbd)
  
- Bảng KhachHang(MaKhachHang, TenKhachHang, GioiTinh, DiaChi, SDT);

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/aeaac41e-a7ed-4296-8f65-06ebb71de89f)

  - Trường MaKhachHang là Primary Key vì MaKhachHang bảm đảm tính duy nhất và toàn vẹn của dữ liệu trong bảng => MaKhachHang không được phép Null. Kiểu dữ liệu là nvarchar(50)
  - Trường TenKhachHang: nvarchar(50)
  - Trường GioiTinh: nvarchar(10)
  - Trường DiaChi: nvarchar(100)
  - Trường SDT: nvarchar(10)
    
- Bảng SanPham(MaSanPham, TenSanPham, MaNhaCC, SoLuong, GiaBan, NgaySanXuat, HanSuDung);

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/d3f2eeb2-2bb8-43ce-8e03-a53ab0522f45)

  - Trường MaSanPham là Primary Key vì MaSanPham bảm đảm tính duy nhất và toàn vẹn của dữ liệu trong bảng => MaSanPham không được phép Null. Kiểu dữ liệu là nvarchar(50)
  - Trường TenSanPham: nvarchar(50)
  - TRường MaNhaCC Trường MaSanPham là Foreign Key vì MaSanPham đảm bảo mỗi quan hệ giữa bảng SanPham và NhaCC. Kiểu dữ liệu là nvarchar(50)
  - Trường SoLuong: int. Có CK không cho phép nhập giá trị nhỏ hơn 0
  - Trường GiaBan: Bigint. Có CK không cho phép nhập trị nhỏ hơn 0
  - Trường NgaySanXuat: datetime
  - Trường HanSuDung: datetime. Tạo 1 trigger để kiểm soát dữ liệu của Trường NgaySanXuat và HanSuDung để NgaySanXuat luôn là ngày trước HanSuDung

    ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/7c62be47-c817-4071-be86-47aade156f6f)

- Bảng NhaCungCap(MaNhaCC, TenNhaCC, DiaChi, SDT, Email, NguoiDaiDien);

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/210f702e-98ee-458d-b7a6-4d95adf38c6e)

  - Trường MaNhaCC là Primary Key vì MaNhaCC bảm đảm tính duy nhất và toàn vẹn của dữ liệu trong bảng => MaNhaCC không được phép Null. Kiểu dữ liệu là nvarchar(50)
  - Trường TenNhaCC: nvarchar(50)
  - Trường DiaChi: nvarchar(100)
  - Trường SDT: nvarchar(10)
  - Trường Email: nvarchar(50)
  - Trường NguoiDaiDien: nvarchar(50)
