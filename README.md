# 🛒 WEBSITE BÁN LINH KIỆN ĐIỆN TỬ GAMING GEAR
> **Đồ án môn học:** Chuyên đề ASP.NET (Học kỳ III, Năm học 2025-2026)  
> **Trường:** Đại học Trà Vinh – Trường Kỹ thuật và Công nghệ – Khoa Công nghệ Thông tin.

---

## 👥 1. Giới thiệu Thành viên & Giảng viên hướng dẫn

### Giảng viên hướng dẫn
* **TS. Đoàn Phước Miền** 

### Sinh viên thực hiện (Lớp: DK24TT8016)
| Họ và Tên | Mã số sinh viên (MSSV) | Vai trò / Nhiệm vụ trong dự án |
| :--- | :---: | :--- |
| **Trần Minh Tân** | `170124289` | Trưởng nhóm, phát triển Backend (C#), thiết kế Cơ sở dữ liệu và xử lý Logic hệ thống. |
| **Nguyễn Thanh Thuận** | `170124189` | Thành viên, thiết kế Giao diện (Frontend Bootstrap), xây dựng luồng UI/UX và tích hợp hệ thống. |

---

## 🛠️ 2. Công nghệ và Kiến trúc áp dụng

Hệ thống được phát triển theo mô hình chuẩn công nghiệp, đảm bảo hiệu năng và khả năng bảo mật đa tầng:

* **Backend:** Ngôn ngữ C#, nền tảng **ASP.NET Core / .NET Framework** áp dụng mô hình kiến trúc **MVC (Model - View - Controller)** giúp tách biệt rõ ràng giữa logic nghiệp vụ và tầng hiển thị.
* **Database:** **SQL Server Express** – Cơ sở dữ liệu được thiết kế chuẩn hóa gồm 12 bảng chính, tối ưu hóa truy vấn thông qua *Stored Procedures, Triggers, và Views*, đảm bảo tính toàn vẹn dữ liệu.
* **Frontend:** **Bootstrap Framework**, HTML5, CSS3, JavaScript – Thiết kế theo chuẩn giao diện phản hồi (**Responsive Design**), tối ưu hóa trải nghiệm UI/UX mượt mà trên cả Máy tính (Desktop) và Điện thoại (Mobile).

---

## ⚙️ 3. Phân hệ chức năng cốt lõi

1.  **Phân hệ Tài khoản:** Đăng ký, Đăng nhập/Đăng xuất, Quản lý thông tin cá nhân, Đổi mật khẩu, và Cơ chế Quên mật khẩu mã hóa an toàn qua ResetToken.
2.  **Phân hệ Sản phẩm & Kho:** Phân loại danh mục đa cấp (*Category -> Sub_Category*), tìm kiếm thông minh, quản lý chi tiết sản phẩm, và cập nhật tồn kho theo thời gian thực.
3.  **Phân hệ Mua hàng & Xử lý Đơn hàng:** Giỏ hàng trực quan (Thêm/Sửa/Xóa), Luồng đặt hàng khép kín (*Cart -> Order -> Order_Detail*), theo dõi hành trình đơn hàng và hỗ trợ hủy đơn.
4.  **Phân hệ Chiến lược Marketing:** Tích hợp bộ quy tắc khuyến mãi tự động áp dụng mã giảm giá (*Voucher, Promotion*) và quà tặng kèm theo (*Gift_Rule*).
5.  **Tương tác & Cộng đồng:** Hệ thống đánh giá (*Review*) sản phẩm chấm điểm, danh sách sản phẩm yêu thích (*Wishlist*), và tích hợp **Chatbot hỗ trợ trực tuyến**.
6.  6.  **Trang Quản trị (Admin Dashboard):** Thống kê doanh thu, báo cáo sản phẩm bán chạy, phê duyệt đơn hàng, quản lý kho và điều hành người dùng (Khóa/Mở khóa tài khoản).

---

## 💻 4. Hướng dẫn Cài đặt và Triển khai dự án

Để chạy thử nghiệm dự án này trên máy tính cá nhân, bạn hãy thực hiện theo các bước sau:

### Yêu cầu hệ thống trước khi cài đặt:
* [Visual Studio 2022](https://visualstudio.microsoft.com/) (đã cài đặt gói *.NET desktop development* và *ASP.NET and web development*)
* [Microsoft SQL Server Express](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) (Phiên bản 2019 hoặc mới hơn)
* [SQL Server Management Studio (SSMS)](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms) để quản lý file dữ liệu.

### Bước 1: Clone dự án về máy tính
Mở terminal hoặc Git Bash và chạy lệnh:

bash
git clone [https://github.com/170124289-sketch/ASPNET-DK24TT8016-tranminhtan-shopbanlinhkiendientu.git](https://github.com/170124289-sketch/ASPNET-DK24TT8016-tranminhtan-shopbanlinhkiendientu.git)
cd ASPNET-DK24TT8016-tranminhtan-shopbanlinhkiendientu
### Bước 2: Cấu hình và Khởi tạo Cơ sở dữ liệu

1. Mở phần mềm **SSMS (SQL Server Management Studio)** và kết nối vào Server của bạn (thường là `.\SQLEXPRESS`).
2. Tạo một Database mới tên là `ShopBanLinhKien` hoặc tùy chọn.
3. Tìm file script SQL đính kèm trong thư mục source code dự án (thường nằm ở thư mục `Database` hoặc thư mục gốc có đuôi `.sql`).
4. Mở file script bằng SSMS, nhấn **Execute (F5)** để tự động khởi tạo cấu trúc 12 bảng, cấu hình khóa ngoại và nạp dữ liệu mẫu ban đầu.

### Bước 3: Cấu hình Connection String trong Code

1. Mở thư mục dự án bằng **Visual Studio 2022** bằng cách double-click vào file `.sln`.
2. Tìm đến tệp cấu hình cấu trúc dự án (như `appsettings.json` hoặc tệp `Web.config` tùy phiên bản framework).
3. Chỉnh sửa lại chuỗi kết nối cơ sở dữ liệu (`ConnectionString`) cho khớp với cấu hình máy tính của bạn:
json
"ConnectionStrings": {
  "DefaultConnection": "Server=.\\SQLEXPRESS;Database=ShopBanLinhKien;Trusted_Connection=True;MultipleActiveResultSets=true;TrustServerCertificate=True;"
}


### Bước 4: Chạy dự án

1. Trong Visual Studio, nhấn nút **Build** (hoặc tổ hợp phím `Ctrl + Shift + B`) để trình biên dịch tải các package NuGet cần thiết và kiểm tra lỗi.
2. Nhấn nút **Start / IIS Express** (hoặc phím `F5`) để chạy dự án. Trình duyệt web sẽ tự động mở lên kèm theo giao diện trang chủ của Website Bán Linh Kiện Điện Tử.

