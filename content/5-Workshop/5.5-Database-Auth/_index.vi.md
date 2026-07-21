---
title : "Database-Auth"
date : 2026-07-01
weight : 5
chapter : false
pre : " <b> 5.5 </b> "
---

###  Giai đoạn 3 – Cơ sở dữ liệu & Xác thực (DynamoDB & Cognito)

**Mục tiêu:**
Thiết lập lớp lưu trữ dữ liệu (Data Layer) hiệu năng cao và hệ thống quản lý định danh người dùng (Identity Provider) an toàn. Mục tiêu là tách biệt hoàn toàn việc lưu trữ trạng thái và xác thực ra khỏi logic tính toán (Lambda), đảm bảo kiến trúc Stateless chuẩn Serverless.

**Mô tả kiến trúc:**
*   **Amazon DynamoDB (Cơ sở dữ liệu NoSQL):** Được sử dụng để lưu trữ thông tin chuyến bay, phòng khách sạn và lịch sử đặt vé (Bookings). Với cơ chế On-Demand, hệ thống có thể đáp ứng hàng chục ngàn truy vấn đặt vé cùng lúc mà không lo nghẽn thắt cổ chai ở tầng Database.
*   **Amazon Cognito (User Pools):** Quản lý toàn bộ vòng đời của người dùng (Đăng ký, Đăng nhập, Quên mật khẩu). Sau khi người dùng xác thực thành công từ giao diện ReactJS, Cognito sẽ cấp các chuẩn Token (JSON Web Token - JWT). Các token này sẽ được gửi kèm trong các request tới API Gateway để xác thực quyền gọi API.