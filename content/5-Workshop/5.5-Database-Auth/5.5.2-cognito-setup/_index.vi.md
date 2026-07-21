---
title : "cognito-setup"
date : 2026-07-01
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

####  Thiết lập định danh người dùng với AWS Cognito

**Mục tiêu:** 
Thiết lập hệ thống xác thực (Authentication) bảo mật không cần tự quản lý cơ sở dữ liệu mật khẩu, tích hợp sẵn quy trình cấp phát JWT (JSON Web Token).

**Các bước thực hành:**

**Bước 1: Khởi tạo Cognito User Pool**
1. Truy cập dịch vụ **Amazon Cognito**, chọn **Create user pool**.
2. Tại phần **Configure sign-in experience**:
   * Đánh dấu chọn **Email** (Người dùng sẽ đăng nhập bằng Email thay vì Username).
   * Nhấn **Next**.

![Create user pool](/images/5-Workshop/5.5-Database-Auth/5.5.2-cognito-setup/cognito-signin-experience1.png)

![Configure sign-in experience](/images/5-Workshop/5.5-Database-Auth/5.5.2-cognito-setup/cognito-signin-experience2.png)


**Bước 2: Cấu hình bảo mật và Đăng ký**
1. Tại phần **Configure security requirements**:
   * Thiết lập **Password policy** (Độ khó của mật khẩu) theo chuẩn mặc định của AWS.
   * Chọn **No MFA** (Không yêu cầu xác thực 2 lớp) để đơn giản hóa quá trình test, hoặc **Optional MFA** nếu muốn tăng cường bảo mật.
2. Tại phần **Configure sign-up experience**:
   * Đánh dấu vào các thuộc tính (Required attributes) mà người dùng bắt buộc phải cung cấp khi đăng ký tài khoản (VD: `name`, `phone_number`).
   * Nhấn **Next**.

![Cấu hình thuộc tính đăng ký](/images/5-Workshop/5.5-Database-Auth/5.5.2-cognito-setup/cognito-signup-attributes.png)

**Bước 3: Tích hợp ứng dụng (App Client)**
1. Tại phần **Integrate your app**:
   * Nhập **User pool name** (VD: `Traveloka-Users`).
   * Chọn **Public client** ở phần App client type.
   * Nhập **App client name** (VD: `Traveloka-React-Frontend`).
   * **Đặc biệt quan trọng:** KHÔNG chọn "Generate client secret" (Vì ReactJS là SPA chạy trên trình duyệt, việc nhúng Client Secret vào Frontend sẽ làm lộ thông tin bảo mật).
2. Nhấn **Next**, kiểm tra lại toàn bộ cấu hình ở màn hình Review và nhấn **Create user pool**.

![Tạo Cognito App Client](/images/5-Workshop/5.5-Database-Auth/5.5.2-cognito-setup/cognito-app-client.png)

