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
- Tính Tổng Doanh Thu
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

  - Trường MaQuanLy là Primary Key vì MaQuanLy bảm đảm tính duy nhất và toàn vẹn của dữ liệu trong bảng => MaQuanLy không được phép Null. Kiểu dữ liệu là nvarchar(50)
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
  - Trường TongTien: BIGINT. Có CK không cho phép nhập giá trị nhỏ hơn hoặc bằng 0. 
  
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
## Các Chức Năng
  - Thêm Đơn Hàng

    ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/e4018c3b-4d76-4d3c-94b9-7de99f0617a0)
    - Kết Quả:
      
      ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/f460d44a-fb0d-4ca0-9472-dc147725fb4d)
      ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/d0e492f1-b688-4cd4-85a8-058bea3b9868)
- Xóa Đơn Hàng
    - Tạo Trigger để khi xóa 1 trường tại bảng DonHang thì sẽ xóa 1 trường cùng MaDonHang ở bảng ChiTietDonHang

      ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/50da4b9b-ebe5-4554-8924-8d9e70bb7c3d)
    - Kết quả:
      - Chạy lệnh: "delete from DONHANG where SOHOADON='a102'"

        ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/0aea5f54-183d-4780-a965-f8ed784044f8)
        ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/a35a4927-4e38-416e-9822-3899c17abded)
- Sửa Đơn Hàng
  - Thông tin cũ:
  
    ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/c1468bad-4d7e-4c2e-baf7-bd8495a16627)
  - Thông tin mới:

    ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/a9c667c8-9e4a-43fd-8051-c8a0a589322c)
- Thêm Sản Phẩm
  
  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/b3d98cf5-12ef-4077-8f7b-5e7eaa78f667)
- Sửa Sản Phẩm

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/55e5bc1d-3c62-4fde-9e3f-f02218ede0f5)
- Xóa Sản Phẩm

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/34f49cca-3de8-4a61-bcd3-ab83f5f10476)
- THêm Thông Tin Khách Hàng
  
  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/f63bb21a-2aa0-4ce8-934e-5ceb23130253)

- Sửa Thông Tin Khách Hàng
  
  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/dbe54eee-5271-45e9-b786-c9ddf3a22c61)
- Xóa Thông Tin Khách Hàng

  
  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/605b8355-33cb-4f51-aca8-465d533dc48c)
- Xóa Thông Tin Khách Hàng
  
  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/55ca79e4-5522-4c1e-b3e4-06b7a6646a9b)
- Thêm Thôn tin nhà cung cấp

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/e95e2daf-5660-4fc8-b2f4-def2584e8387)
- Sửa thông tin nhà cung cấp

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/13f92ccb-663d-4883-b332-93a96f87bedc)
- Xóa thông tin nhà cung cáp

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/8e3f6f3e-5279-4d41-b91c-eed62c0c4312)
- Thêm thông tin nhân viên

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/8fe7e1ef-5a38-4d57-ba85-1f4bbbdffd4b)
- Sửa thông tin nhân viên

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/636b244e-106f-43f2-b0f3-ea4974840ccc)
- Xóa thông tin nhân viên

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/b0ad5ea1-a37d-4938-ad46-9d61b912a241)
- Thêm Phiếu thông kê

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/8387ecc2-17bf-43c4-803d-604f58bce8f5)
- Sửa Phiếu Thống Kê

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/4a9cb0b8-c8f4-4f1d-a709-bd1d38a5dd72)
- Xóa Phiếu Thống Kê

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/bd768f63-a7d3-41c3-b868-5747a3d58376)

## Các Báo Cáo
- Báo cáo sản phẩm sắp hết hạn

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/a0495a95-7227-46a0-a301-7a81e021d426)
  - Kết quả:

    ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/f2a1e1ff-02ee-4a07-86d8-ebf25feec56f)
- Báo cáo sản phẩm tồn kho

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/556977e8-66ae-4c37-a0b8-d32a4a9b100a)
  - Kết quả:

    ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/2aad092c-80df-4264-b7d7-1df876c30f08)

- Tính Tổng doanh thu

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/7dd06ed5-37fa-4d20-a617-d2b831e2f439)
  - Kết quả:

  ![image](https://github.com/Chung2310/TL_HQTCSDL/assets/131289318/e155fc24-b4bd-4407-a0b5-7c8fe31f4a23)
