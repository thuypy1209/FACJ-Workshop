---
title : "Giới thiệu"
date : 2026-07-01 
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

### Mục tiêu của workshop này

Traveloka-Serverless là một ứng dụng dịch vụ du lịch trực tuyến (OTA) toàn diện, mô phỏng nền tảng đặt vé máy bay và phòng khách sạn, được xây dựng hoàn toàn trên nền tảng Amazon Web Services (AWS) sử dụng kiến trúc đám mây gốc (Cloud-Native Serverless Architecture).

Workshop này sẽ hướng dẫn bạn toàn bộ quy trình cung cấp cơ sở hạ tầng phi máy chủ, cấu hình luồng dữ liệu, xử lý bảo mật kết nối (CORS/OAC), quản lý định danh người dùng và thiết lập tường lửa bảo vệ hệ thống — tất cả đều tuân theo các thực tiễn tốt nhất (Best Practices) về kỹ thuật điện toán đám mây hiện đại.

### Mục tiêu học tập

- Hiểu và thiết kế hệ thống theo mô hình kiến trúc Serverless (Phi máy chủ) tối ưu chi phí vận hành.
- Xây dựng hệ thống RESTful API hiệu năng cao, tự động mở rộng quy mô bằng Amazon API Gateway và AWS Lambda (Node.js).
- Thiết kế, tối ưu hóa cấu trúc bảng dữ liệu NoSQL trên Amazon DynamoDB duy trì độ trễ ở mức một chữ số mili-giây.
- Lưu trữ giao diện người dùng ReactJS an toàn trên Amazon S3 và tăng tốc phân phối nội dung toàn cầu thông qua mạng lưới CDN Amazon CloudFront.
- Làm chủ cơ chế khóa bảo mật tài nguyên tĩnh Origin Access Control (OAC) và cấu hình chính sách chia sẻ tài nguyên CORS kiểm soát chặt chẽ luồng gọi API.
- Quản lý định danh, xác thực và phân quyền người dùng tập trung bằng AWS Cognito User Pools kết hợp mã Token JWT.
-Bảo vệ toàn bộ hệ thống khỏi các cuộc tấn công Web phổ biến (SQL Injection, XSS) và giảm thiểu rủi ro DDoS bằng tường lửa AWS WAF.

### Các dịch vụ AWS được sử dụng
| Dịch vụ | Mục đích |
|---------|----------|
| AWS Lambda | Điện toán phi máy chủ (Serverless Compute) để chạy mã nguồn logic Backend (Node.js) kích hoạt theo sự kiện, tự động co giãn theo tải thực tế.  |
| Amazon API Gateway | Cửa ngõ quản lý RESTful API, chịu trách nhiệm định tuyến Requests, kiểm soát lưu lượng và kết nối Frontend với các hàm Lambda Backend. |
| Amazon DynamoDB | Cơ sở dữ liệu NoSQL phi máy chủ, lưu trữ toàn bộ thông tin khách sạn, du thuyền, đơn đặt chỗ với hiệu năng cao và độ trễ cực thấp. |
| AWS Cognito | Dịch vụ quản lý định danh và xác thực người dùng (User Pools), tự động mã hóa mật khẩu và phát hành mã bảo mật JWT. |
| Amazon S3 | Kho lưu trữ Object tĩnh phi máy chủ dùng để lưu trữ toàn bộ mã nguồn giao diện ứng dụng (ReactJS Frontend sau khi Build). |
| Amazon CloudFront | Mạng lưới phân phối nội dung toàn cầu (CDN) giúp tăng tốc độ tải trang, giảm độ trễ tối đa kết hợp tính năng Kiểm soát truy cập nguồn gốc (OAC) để bảo vệ S3 Bucket. |
| AWS WAF | Tường lửa ứng dụng Web (Web Application Firewall) áp dụng Web ACLs bảo vệ CloudFront và API Gateway khỏi các lỗ hổng bảo mật Web. |
| Amazon Route 53 | Hệ thống quản lý tên miền (DNS) toàn cầu có độ tin cậy cao, định tuyến tên miền chính thức của dự án về CloudFront. |

### Công cụ & Khung công nghệ (Tools & Frameworks)

| Công cụ | Mục đích |
|---------|----------|
| ReactJS & Vite | Khung ứng dụng một trang (SPA) phía Frontend giúp xây dựng giao diện người dùng Traveloka mượt mà, tối ưu tốc độ render. |
|Node.js | Môi trường thực thi mã nguồn JavaScript phía Backend chạy trên các hàm AWS Lambda. |
| JWT (JSON Web Token) |Chuẩn mã hóa chuỗi vô nghĩa định danh phiên làm việc bảo mật giữa Frontend và Backend sau khi đăng nhập thành công. |
| ReactJS | Framework ứng dụng Single Page Application |
| CORS | Cơ chế bảo mật phía trình duyệt được cấu hình trên API Gateway nhằm kiểm soát các Domain được phép truy xuất dữ liệu hệ thống. |

### Tổng quan về Kiến trúc
| Thành phần | Mô tả |
|------------|-------|
| Mạng & Lưu trữ tĩnh| Ứng dụng một trang (SPA) ReactJS được đóng gói và lưu trữ biệt lập bên trong Amazon S3, sử dụng chính sách chặn truy cập công khai trực tiếp. |
| Phân phối | Amazon CloudFront tạo các điểm lưu bộ nhớ đệm (Edge Locations) để đẩy tốc độ hiển thị giao diện Frontend lên mức tối đa và giao tiếp với S3 thông qua giao thức bảo mật OAC.|
| Phần tính toán & API | Toàn bộ RESTful API được phơi ra qua Amazon API Gateway, xử lý logic nghiệp vụ hoàn toàn bằng mã nguồn Node.js chạy trên các môi trường Runtime ngắn hạn của AWS Lambda |
| Cơ sở dữ liệu & Xác thực | Dữ liệu ứng dụng lưu giữ tại Amazon DynamoDB dạng NoSQL. Phiên đăng ký/đăng nhập và hồ sơ bảo mật của người dùng được ủy quyền quản lý qua AWS Cognito.|
| Bảo vệ hệ thống | Lớp lá chắn bảo mật ngoài cùng áp dụng AWS WAF (sử dụng gói luật tiêu chuẩn Core Rule Set và SQL Injection Protection) kết hợp chính sách khóa Domain CORS chặt chẽ trên API Gateway.
![Sơ đồ kiến trúc](/images/5-Workshop/5.1-Introduction/images/Diagram.png)

# Lộ trình Workshop


| Giai đoạn | Mục tiêu |
|-----------|----------|
| **1. Chuẩn bị (Prerequisites)** | Thiết lập tài khoản AWS, GitHub và cài đặt các công cụ cần thiết |
| **2. Lưu trữ & Tăng tốc Frontend** | Đóng gói ứng dụng React, lưu trữ mã nguồn tĩnh lên Amazon S3, cấu hình Amazon CloudFront và bảo mật bằng OAC. |
| **3. Cơ sở dữ liệu & Xác thực** | Thiết lập bảng dữ liệu NoSQL trên Amazon DynamoDB và cấu hình quản lý định danh người dùng qua AWS Cognito. |
| **4. Triển khai Backend Serverless** |Xây dựng và triển khai các hàm xử lý logic bằng AWS Lambda, thiết lập cổng giao tiếp RESTful API qua Amazon API Gateway. |
| **5. Thông tuyến dữ liệu & Bảo mật** | Cấu hình CORS trên API Gateway để Frontend kết nối thành công, đồng thời triển khai tường lửa AWS WAF bảo vệ toàn bộ hệ thống. |
| **6. Dọn dẹp tài nguyên** | Xóa toàn bộ tài nguyên AWS an toàn nhằm tránh phát sinh chi phí ngoài ý muốn |


