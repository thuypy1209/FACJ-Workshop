---
title : "Dọn dẹp tài nguyên"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

### Dọn dẹp tài nguyên 

**Mục tiêu:**
Xóa toàn bộ các tài nguyên AWS đã tạo trong suốt quá trình triển khai hệ thống Traveloka-Serverless nhằm tránh việc tiếp tục phát sinh chi phí không mong muốn trên tài khoản AWS.

**Các bước thực hiện dọn dẹp:**

**Bước 1: Xóa Frontend & S3 Buckets**
1. Truy cập vào dịch vụ **Amazon S3**, tìm đến bucket lưu trữ mã nguồn frontend (`traveloka-clone-frontend`).
2. Chọn bucket và nhấn **Empty** để xóa sạch các tệp tĩnh bên trong.
3. Nhấn **Delete** để xóa hoàn toàn S3 bucket.

![Xóa S3 Bucket](/images/5-Workshop/5.6-Cleanup/delete-s3.png)

**Bước 2: Xóa CloudFront Distribution**
1. Truy cập dịch vụ **Amazon CloudFront**, chọn phân phối (Distribution) đang sử dụng cho dự án.
2. Trước tiên, chọn **Disable** để vô hiệu hóa CloudFront và chờ đến khi trạng thái chuyển sang *Disabled*.
3. Sau đó, nhấn chọn **Delete** để xóa hoàn toàn phân phối.

![Xóa CloudFront Distribution](/images/5-Workshop/5.6-Cleanup/delete-cloudfront.png)

**Bước 3: Xóa Serverless Backend (API Gateway & Lambda)**
1. Truy cập dịch vụ **API Gateway**, chọn API `Traveloka-Core-API`, chọn menu *Actions* và nhấn **Delete API**.
2. Truy cập dịch vụ **AWS Lambda**, chọn hàm `Traveloka-Booking-Handler`, chọn *Actions* và nhấn **Delete**.

![Xóa Backend Lambda và API Gateway](/images/5-Workshop/5.6-Cleanup/delete-API.png)
![Xóa Backend Lambda và API Gateway](/images/5-Workshop/5.6-Cleanup/delete-Lambda.png)

**Bước 4: Xóa Database & Xác thực (DynamoDB & Cognito)**
1. Truy cập dịch vụ **Amazon DynamoDB** > **Tables**, chọn bảng `Traveloka-Bookings` và nhấn **Delete table**.
2. Truy cập dịch vụ **Amazon Cognito** > **User pools**, chọn user pool `Traveloka-Users` và nhấn **Delete user pool**.

![Xóa Database và Cognito](/images/5-Workshop/5.6-Cleanup/delete-db-auth.png)

