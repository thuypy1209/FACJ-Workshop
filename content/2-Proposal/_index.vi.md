---
title: "Bản đề xuất"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---


# IoT Weather Platform for Lab Research  
## Giải pháp Đặt phòng Khách sạn Trực tuyến với Kiến trúc AWS Serverless  

### 1. Tóm tắt điều hành  
Serverless Hotel Booking Application là một nền tảng mô phỏng ứng dụng đặt phòng du lịch (Mini Traveloka Booking ), được thiết kế hoàn toàn trên kiến trúc không máy chủ (100% Serverless) của AWS. Hệ thống cung cấp giao diện người dùng thân thiện để tìm kiếm và xem danh sách phòng khách sạn, kết hợp với các hiệu ứng hình ảnh và thẻ ưu đãi. Bằng cách tận dụng các dịch vụ lõi của AWS (S3, API Gateway, Lambda, DynamoDB), dự án giải quyết bài toán tối ưu chi phí vận hành và tự động mở rộng quy mô, mang lại hiệu năng cao với ngân sách duy trì hàng tháng gần như bằng 0 USD.

### 2. Tuyên bố vấn đề  
*Vấn đề hiện tại*  
Các hệ thống đặt phòng truyền thống thường phải thuê và duy trì máy chủ ảo (VPS/EC2) chạy liên tục 24/7, gây lãng phí tài nguyên lớn trong những khung giờ thấp điểm. Đồng thời, khi bước vào mùa du lịch cao điểm, hệ thống cũ thiếu sự linh hoạt, dễ dẫn đến tình trạng quá tải và sập web. 

*Giải pháp*  
Ứng dụng kiến trúc hướng sự kiện (Event-Driven) của AWS. Giao diện Frontend (ReactJS/Vite) được lưu trữ trên S3. Các luồng xử lý API Backend được quản lý bởi API Gateway, kích hoạt các hàm Lambda (Node.js) để truy xuất dữ liệu từ cơ sở dữ liệu NoSQL DynamoDB.

*Lợi ích và hoàn vốn đầu tư (ROI)*  
Mô hình trả tiền theo mức sử dụng thực tế (Pay-as-you-go) kết hợp với AWS Free Tier giúp loại bỏ hoàn toàn chi phí bảo trì máy chủ cố định. Giải pháp tạo ra một nền tảng hiện đại, tốc độ phản hồi nhanh, thu hồi vốn đầu tư ngay lập tức nhờ cắt giảm chi phí hạ tầng.

### 3. Kiến trúc giải pháp  
Hệ thống vận hành theo cơ chế Serverless, các tài nguyên chỉ được cấp phát khi có Request từ người dùng.

*Dịch vụ AWS sử dụng*  
- *Amazon S3: Lưu trữ mã nguồn tĩnh (HTML, CSS, JS) của Frontend ReactJS và cung cấp Static Website Hosting.  
- *Amazon API Gateway: Đóng vai trò làm điểm vào (entry point) cho RESTful API, quản lý CORS và định tuyến Request.
- *AWS Lambda: Thực thi logic nghiệp vụ bằng Node.js.
- *Amazon DynamoDB: Cơ sở dữ liệu NoSQL (On-demand) lưu trữ thông tin danh sách khách sạn, giá phòng và hình ảnh. 
- *Amazon CloudWatch & SNS: Theo dõi log của hệ thống và tự động gửi email cảnh báo khi API Gateway trả về lỗi 5xx.


### 4. Triển khai kỹ thuật  
*Các giai đoạn triển khai*  
Dự án được chia thành hai phân hệ độc lập để dễ dàng quản lý và nâng cấp:
Backend 
  Backend (AWS Serverless): Khởi tạo bảng dữ liệu Hotels trên DynamoDB. 
  Viết các hàm xử lý logic bằng Node.js tích hợp SDK v3. 
  Kết nối API Gateway với Lambda và thiết lập các Alarm giám sát trên CloudWatch.

Frontend 
 Frontend (ReactJS + Vite): Xây dựng giao diện Component-based (Header, Hero, HotelList).
  Sử dụng Flexbox để dàn trang Responsive. 
  Dùng hook useEffect và lệnh fetch để gọi dữ liệu từ API Gateway AWS và render ra giao diện. 
  Cuối cùng, đóng gói (Build) và đẩy lên S3.


### 5. Lộ trình & Mốc triển khai  
- *Dự án được phát triển và hoàn thiện trong khuôn khổ đợt thực tập: 
  
    - Giai đoạn 1  Phân tích kiến trúc, thiết kế cơ sở dữ liệu trên DynamoDB, viết logic cho AWS Lambda và cấu hình API Gateway.
    - Giai đoạn 2  Dựng khung giao diện ReactJS, CSS Flexbox cho thanh điều hướng và khối tìm kiếm.
    - Giai đoạn 3  Gọi API từ Frontend xuống Backend AWS, xử lý dữ liệu JSON, kiểm tra lỗi và giám sát log qua CloudWatch.
    - Giai đoạn 4  Đóng gói ứng dụng, cấu hình Static Website Hosting trên S3 và bàn giao mã nguồn.


### 6. Ước tính ngân sách  
Được thiết kế để tận dụng tối đa gói miễn phí (AWS Free Tier):

*Chi phí hạ tầng*  
    - AWS Lambda: 1 triệu requests/tháng miễn phí -> $0.
    - Amazon DynamoDB: 25 GB lưu trữ, 25 RCU/WCU miễn phí -> $0.
    - Amazon API Gateway: Miễn phí 1 triệu API calls đầu tiên/tháng (trong 12 tháng đầu) -> $0.
    - Amazon S3 & CloudWatch: Nằm trong mức sử dụng cơ bản miễn phí -> $0.

Tổng chi phí hàng tháng với wed mới mở: ~ 0.00 USD.

### 7. Đánh giá rủi ro  
 Ma trận rủi ro & Chiến lược giảm thiểu

*Khởi động lạnh (Cold Starts) của Lambda: 
* Rủi ro: Request đầu tiên có thể mất thêm vài giây để phản hồi.
    - Giảm thiểu: Tối ưu hóa mã nguồn Node.js, chỉ import các thư viện thực sự cần thiết từ AWS SDK v3 để khởi động nhanh hơn.

*Vượt ngân sách ngoài ý muốn: 
* Rủi ro: Lượng truy cập tăng đột biến làm phát sinh chi phí ngoài Free Tier.
    - Giảm thiểu: Thiết lập AWS Billing Alarm để tự động cảnh báo qua Email ngay khi chi phí vượt quá $2.

### 8. Kết quả kỳ vọng  
Một hệ thống đặt phòng khách sạn vận hành mượt mà, giao diện giống thiết kế mẫu (MiNi Traveloka Booking), có khả năng chịu tải tốt (Production-ready). Dự án chứng minh được tính ưu việt của kiến trúc Cloud-Native so với các giải pháp truyền thống.