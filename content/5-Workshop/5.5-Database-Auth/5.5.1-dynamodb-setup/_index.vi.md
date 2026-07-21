---
title : "dynamodb-setup"
date : 2026-07-01
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

####  Khởi tạo Cơ sở dữ liệu NoSQL với Amazon DynamoDB

**Mục tiêu:** 
Tạo các bảng cơ sở dữ liệu phi quan hệ (NoSQL) phi máy chủ để lưu trữ và truy xuất dữ liệu đặt vé với độ trễ tính bằng mili-giây.

**Các bước thực hành:**

**Bước 1: Tạo bảng DynamoDB**
1. Truy cập vào **AWS Management Console**, tìm kiếm dịch vụ **DynamoDB** và chọn **Tables** > **Create table**.
2. Nhập thông tin chi tiết cho bảng lưu trữ giao dịch:
   * **Table name:** `Traveloka-Bookings`
   * **Partition key (Khóa phân vùng):** Nhập `bookingId` và chọn kiểu dữ liệu là **String**. Khóa này sẽ dùng để định danh duy nhất mỗi giao dịch đặt vé.
![Create table ](/images/5-Workshop/5.5-Database-Auth/5.5.1-dynamodb-setup/create-dynamodb-table1.png)
![Tạo bảng DynamoDB](/images/5-Workshop/5.5-Database-Auth/5.5.1-dynamodb-setup/create-dynamodb-table.png)

**Bước 2: Cấu hình Capacity Settings (Chế độ thanh toán)**
1. Tại phần **Table settings**, thay vì chọn *Default settings*, hãy chọn **Customize settings**.
2. Cuộn xuống phần **Read/write capacity settings** và chọn **On-demand**.
3. Cuộn xuống cuối trang và nhấn **Create table**. 
4. Lặp lại các bước trên để tạo thêm các bảng khác cho dự án nếu cần (VD: `Traveloka-Flights`, `Traveloka-Hotels`).

![Cấu hình On-Demand Capacity](/images/5-Workshop/5.5-Database-Auth/5.5.1-dynamodb-setup/dynamodb-capacity-settings.png)
