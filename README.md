## Thông tin cá nhân
- Họ và Tên: Phạm Mai Quốc Khánh
- MSSV: K215480106105
- Lớp: K57KMT
- Môn học: Hệ quản trị cơ sở dữ liệu
## Tên bài toán
- Đề tài: Quản lý Khách sạn
 ## Các chức năng
Bài toán quản lý khách sạn nhằm quản lí phòng và thông tin khách hàng một cách thuận tiện và dễ dàng.
- Quản lý thông tin khách hàng: Thêm khách hàng, sửa thông tin khách hàng, xóa khách hàng, liệt kê danh sách khách hàng.
- Quản lý thông tin phòng: Thêm phòng, cập nhật trạng thái phòng, xóa phòng, liệt kê các phòng.
- Quản lý dịch vụ: Các phòng sử dụng dịch vụ, các mức giá của dịch vụ.
- Quản lý nhân viên, người quản lý: Thêm thông tin nhân viên, sửa thông tin nhân viên, xóa thông tin nhân viên,...
- Quản lý việc thanh toán: các hóa đơn thanh toán.
  ## Báo cáo
- Báo cáo danh sách phòng trống
- Báo cáo danh sách khách hàng 
- Hóa đơn.
  ## Các bảng của hệ thống
  - Bảng Phong( MaPhong, SoPhong, LoaiPhong, GiaPhong, TinhTrangPhong)
       - ![image](https://github.com/PhamMaiQuocKhanh/H-qu-n-tr-c-s-d-li-u/assets/168647678/4597b5c1-1c11-45ea-adb3-5c4425d3a4ca)
         - Trường MaPhong là trường chính (PRIMARY KEY) của bảng, dùng để định danh duy nhất cho từng dòng trong bảng Phong.
         -  Trường SoPhong là số phòng, có ràng buộc UNIQUE để đảm bảo mỗi số phòng là duy nhất trong bảng.
         -  Trường LoaiPhong lưu trữ loại phòng, có độ dài tối đa là 50 ký tự.
         -  Trường GiaPhong lưu trữ giá phòng dưới dạng số thập phân có 10 chữ số tổng cộng, trong đó 2 chữ số là phần thập phân.
         -  Trường TinhTrangPhong lưu trữ tình trạng của phòng, có độ dài tối đa là 50 ký tự.
  -  Bảng NhanVien( MaNhanVien, HoTen, ChucVu, PhongBan, Luong, NgayVaoLam )
     -  ![image](https://github.com/PhamMaiQuocKhanh/H-qu-n-tr-c-s-d-li-u/assets/168647678/5aa70fd6-3ae5-4c0f-be58-d73d6f62ece6)
         -  Trường MaNhanVien là trường chính (PRIMARY KEY) của bảng, dùng để định danh duy nhất cho từng dòng trong bảng NhanVien.
         -  Trường HoTen lưu trữ họ và tên của nhân viên, có độ dài tối đa là 100 ký tự.
         -  Trường ChucVu lưu trữ chức vụ của nhân viên, ví dụ như 'Lễ Tân', 'Quản Gia', 'Bảo Vệ',... Độ dài tối đa là 50 ký tự.
         -  Trường PhongBan lưu trữ phòng ban mà nhân viên thuộc về, ví dụ 'Lễ Tân', 'Văn Phòng', 'Nhà Hàng',... Độ dài tối đa là 50 ký tự.
         -  Trường Luong lưu trữ mức lương của nhân viên dưới dạng số thập phân có 10 chữ số tổng cộng, trong đó 2 chữ số là phần thập phân.
         -  Trường NgayVaoLam: date
  - Bảng KhachHang(MaKhachHang, HoTen, GioiTinh, NgaySinh, Email, DienThoai, DiaChi )
     - ![image](https://github.com/PhamMaiQuocKhanh/H-qu-n-tr-c-s-d-li-u/assets/168647678/1275052d-9b37-4dac-9007-43a7043ecf41)
         - Trường MaKhachHang là trường chính (PRIMARY KEY) của bảng, dùng để định danh duy nhất cho từng khách hàng.
         - Trường HoTen lưu trữ họ tên của khách hàng, với độ dài tối đa là 100 ký tự.
         - Trường GioiTinh lưu trữ giới tính của khách hàng, có thể là 'Nam' hoặc 'Nữ' hoặc các giá trị khác tương ứng, với độ dài tối đa là 10 ký tự.
         - Trường NgaySinh lưu trữ ngày sinh của khách hàng, dưới dạng kiểu dữ liệu DATE.
         - Trường Email lưu trữ địa chỉ email của khách hàng, với độ dài tối đa là 100 ký tự.
         - Trường DienThoai lưu trữ số điện thoại của khách hàng, với độ dài tối đa là 20 ký tự.
         - Trường DiaChi lưu trữ địa chỉ của khách hàng, với độ dài tối đa là 255 ký tự.
  - Bảng DatPhong( MaDatPhong, MaKhachHang, MaPhong, NgayDat, NgayNhanPhong, NgayTraPhong )
     - ![image](https://github.com/PhamMaiQuocKhanh/H-qu-n-tr-c-s-d-li-u/assets/168647678/85d2b6b3-bc2c-4924-acf3-6f15832ffd4d)
         - Trường MaDatPhong là trường chính (PRIMARY KEY) của bảng, dùng để định danh duy nhất cho mỗi lần đặt phòng.
         - Trường MaKhachHang là khóa ngoại (FOREIGN KEY) tham chiếu đến trường MaKhachHang trong bảng KhachHang.
         - Trường MaPhong là khóa ngoại (FOREIGN KEY) tham chiếu đến trường MaPhong trong bảng Phong.
         - Trường NgayDat lưu trữ ngày khách hàng đặt phòng, sử dụng kiểu dữ liệu DATE để biểu diễn ngày tháng năm.
         - Trường NgayNhanPhong lưu trữ ngày dự kiến nhận phòng, sử dụng kiểu dữ liệu DATE.
         - Trường NgayTraPhong lưu trữ ngày dự kiến trả phòng, sử dụng kiểu dữ liệu DATE.
         - FOREIGN KEY (MaKhachHang) REFERENCES KhachHang(MaKhachHang), Ràng buộc khóa ngoại để đảm bảo MaKhachHang trong DatPhong phải tồn tại trong bảng KhachHang.
         - FOREIGN KEY (MaPhong) REFERENCES Phong(MaPhong), Ràng buộc khóa ngoại để đảm bảo MaPhong trong DatPhong phải tồn tại trong bảng Phong.
  - Bảng HoaDon (MaHoaDon, MaDatPhong, DichVu, TienDichVu, ThanhTien)
     - ![image](https://github.com/PhamMaiQuocKhanh/H-qu-n-tr-c-s-d-li-u/assets/168647678/9a4088e4-1cea-4df5-b023-8010e921a815)
         - Trường MaHoaDon là khóa chính của bảng HoaDon, được tạo tự động với mỗi bản ghi mới (IDENTITY). Đây là kiểu dữ liệu INT.
         - Trường MaDatPhong lưu trữ mã đặt phòng, dùng để liên kết với bảng DatPhong.
         - Trường DichVu lưu trữ thông tin về dịch vụ sử dụng trong đặt phòng, có độ dài tối đa là 255 ký tự.
         - Trường TienDichVu lưu trữ số tiền chi tiêu cho các dịch vụ, có kiểu dữ liệu DECIMAL(10, 2) để lưu giữ số tiền với 10 chữ số và 2 chữ số thập phân.
         - Trường ThanhTien lưu trữ tổng thành tiền của hóa đơn, có kiểu dữ liệu DECIMAL(10, 2).
         - FOREIGN KEY (MaDatPhong) REFERENCES DatPhong(MaDatPhong), Ràng buộc ngoại khoá trên trường MaDatPhong, liên kết với bảng DatPhong theo trường MaDatPhong của bảng DatPhong.
  - Tạo Trigger Tính Tiền hóa đơn: Nếu khách hàng thuê dưới 1 ngày thì tiền phòng = giá phòng, còn khách hàng thuê phòng nhiều hơn 1 ngày thì lấy số ngày ở * với giá phòng.
     - ![image](https://github.com/PhamMaiQuocKhanh/H-qu-n-tr-c-s-d-li-u/assets/168647678/19f95e20-df42-42a4-9526-ecd5dac2ef08)

 
## Các Chức Năng
  - Thêm phòng
     - ![image](https://github.com/PhamMaiQuocKhanh/H-qu-n-tr-c-s-d-li-u/assets/168647678/b9ddfef9-cd3e-4685-8a1f-3f2f3259ab46)
     - Kết quá
         -![image](https://github.com/PhamMaiQuocKhanh/H-qu-n-tr-c-s-d-li-u/assets/168647678/feffd9e7-4612-46f1-b398-ff72ee4f684a)
  - Xóa Phòng
        -![image](https://github.com/PhamMaiQuocKhanh/QuanLiKhachSan/assets/168647678/f08a1eaa-a970-44cc-ac17-ef1c1f852b86)
   - Tạo view phòng còn trống
         - ![image](https://github.com/PhamMaiQuocKhanh/QuanLiKhachSan/assets/168647678/04cca8be-d97a-49c3-914a-850e9b2f1735)
  -Thêm thông tin khách hàng
         -Tạo Tringger thêm thông tin khách hàng.Trigger này giúp đảm bảo tính nhất quán dữ liệu bằng cách tự động thêm thông tin khách hàng vào khi có đặt phòng mới.
       -![image](https://github.com/PhamMaiQuocKhanh/QuanLiKhachSan/assets/168647678/402ac872-158b-4c68-a2ae-91ee9900fdb0)
     - Kết quả khi thêm 1 khách hàng mới ( khách hàng số 3)
       - ![image](https://github.com/PhamMaiQuocKhanh/QuanLiKhachSan/assets/168647678/5323952b-7039-4632-ab5a-1ef53a49cf7c)
 ## Các Báo Cáo
 - Danh sách khách hàng
     - ![image](https://github.com/PhamMaiQuocKhanh/QuanLiKhachSan/assets/168647678/9f327705-274c-41d1-b141-f778eb439b11)
 - Danh sách phòng còn trống
     -  ![image](https://github.com/PhamMaiQuocKhanh/QuanLiKhachSan/assets/168647678/67050414-9648-4996-8991-c10e05b98a8e)
 - Hóa Đơn
     - ![image](https://github.com/PhamMaiQuocKhanh/QuanLiKhachSan/assets/168647678/32b38ad0-4507-4215-aa3c-654f717f8896)
- Danh Sách khách hàng thuê phòng
     - ![image](https://github.com/PhamMaiQuocKhanh/QuanLiKhachSan/assets/168647678/011b9c38-e5ee-4750-b13d-767eabebceb6)
- Danh sách nhân viên
     - ![image](https://github.com/PhamMaiQuocKhanh/QuanLiKhachSan/assets/168647678/84de64e1-ff8e-4c34-8b7d-b00294f5e1e2)
       





 


 
  

       
