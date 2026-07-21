---
title : "ses-email-service-setup"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.4.3 </b> "
---

#### Cấu hình Amazon SES (Thông báo Email)

**Mục tiêu:** 
Xác thực địa chỉ email gửi đi với Amazon SES để hệ thống có quyền tự động gửi email E-ticket cho người dùng khi hoàn tất đặt vé.

**Các bước thực hành:**

**Bước 1: Xác thực địa chỉ Email (Verify Identity)**
1. Trong AWS Management Console, tìm kiếm dịch vụ **Amazon SES** và điều hướng tới **Identities**.
2. Nhấn **Create identity**, chọn Identity type là **Email address**.
3. Nhập địa chỉ email mà hệ thống sẽ dùng để gửi thông báo (VD: `noreply.traveloka.clone@gmail.com` hoặc email test của bạn) và nhấn **Create identity**.
![tạo địa chỉ email trên SES](/images/5-Workshop/5.4-Backend-Serverless/5.4.3-ses-email-service-setup/verify-ses-email1.png)
![Xác thực địa chỉ email trên SES](/images/5-Workshop/5.4-Backend-Serverless/5.4.3-ses-email-service-setup/verify-ses-email.png)

4. Truy cập vào hòm thư của địa chỉ email vừa nhập, mở email từ AWS và nhấn vào đường link để xác nhận quyền sở hữu.

![Trạng thái xác thực thành công](/images/5-Workshop/5.4-Backend-Serverless/5.4.3-ses-email-service-setup/ses-verified-success.png)


**Bước 2: Tích hợp AWS SDK v3 vào Lambda**
Sau khi xác thực thành công, mã nguồn Node.js trong hàm `Traveloka-Booking-Handler` đã có thể sử dụng thư viện `@aws-sdk/client-ses` để gửi lệnh `SendEmailCommand`.

![Đoạn code tích hợp SES trong Lambda](/images/5-Workshop/5.4-Backend-Serverless/5.4.3-ses-email-service-setup/lambda-ses-code.png)




