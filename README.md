# ITRMS - Internal Task & Resource Management System

## Tổng quan (Overview)
**ITRMS** là một ứng dụng web monolithic được xây dựng bằng **Spring Boot** nhằm mục đích quản lý dự án, công việc và nhân sự nội bộ. Hệ thống phân quyền chặt chẽ theo vai trò (Role-based access control), cho phép Quản trị viên (Admin) tạo dự án, phân bổ thành viên và giao việc. Trong khi đó, Thành viên (Member) có thể theo dõi dự án mình tham gia và tiến độ công việc được giao.

## Công nghệ sử dụng (Tech Stack)
- **Backend:** Java 24, Spring Boot 4.0.1 (Web MVC, Data JPA, Security, Validation).
- **Giao diện (Frontend):** Thymeleaf (Server-side rendering), HTML/CSS.
- **Cơ sở dữ liệu:** PostgreSQL.
- **Bảo mật & Xác thực:** Spring Security (Form Login) và JWT (JSON Web Tokens).
- **Tiện ích:** Lombok, Spring HATEOAS.

## Tính năng chính (Key Features)
- **Xác thực & Phân quyền:** Đăng nhập, đăng ký và phân quyền truy cập riêng biệt cho luồng `ADMIN` và luồng `MEMBER`.
- **Quản lý Dự án (Project Management):** Admin có quyền tạo các dự án mới, xem chi tiết và quản lý tiến độ.
- **Quản lý Nhân sự (Resource Management):** Chỉ định thành viên vào các dự án cụ thể thông qua bảng trung gian.
- **Quản lý Công việc (Task Management):** Khởi tạo Task, thiết lập mức độ ưu tiên, hạn chót và giao trực tiếp cho một thành viên trong một dự án cụ thể.
- **Dashboard: Trang tổng quan thống kê riêng biệt cho quản lý và nhân viên.

## Cấu trúc mã nguồn (Project Structure)
- `config/`: Cấu hình Security (phân quyền route, mã hóa password) và Custom Success Handler.
- `controller/`: Chứa các Web Controller điều hướng request (PageController, AdminController, TaskController,...).
- `entity/`: Định nghĩa các thực thể CSDL (`User`, `Admin`, `Member`, `Project`, `MemberProject`, `Task`).
- `repository/`: Các interface JPA giao tiếp với PostgreSQL.
- `service/`: Tầng xử lý logic nghiệp vụ.
- `resources/templates/`: Chứa toàn bộ mã nguồn giao diện Thymeleaf (`.html`).

## Hướng dẫn cài đặt (Setup & Installation)

1. Yêu cầu hệ thống: **Java 24**, **PostgreSQL** và **Maven**.
2. Clone dự án về máy:
   ```bash
   git clone https://github.com/dokiet999/ITRMS.git
   ```
3. Tạo cơ sở dữ liệu có tên `itrms` trong PostgreSQL.
4. Kiểm tra và thay đổi thông tin kết nối CSDL trong file `src/main/resources/application.properties` nếu cần thiết:
   ```properties
   spring.datasource.url=jdbc:postgresql://localhost:5432/itrms
   spring.datasource.username=postgres
   spring.datasource.password=ngocquang04
   ```
5. Chạy dự án:
   ```bash
   ./mvnw spring-boot:run
   ```
6. Truy cập ứng dụng tại: `http://localhost:8080/login`
