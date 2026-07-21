---
title : "frontend-hosting"
date : 2026-07-01 
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

Giai đoạn này tập trung vào việc đưa giao diện người dùng (Frontend ReactJS) của ứng dụng Traveloka Clone lên môi trường điện toán đám mây. Chúng ta sẽ sử dụng các dịch vụ phi máy chủ của AWS để tối ưu hóa tốc độ tải trang, đảm bảo tính sẵn sàng cao và bảo mật tuyệt đối cho tài nguyên tĩnh.

### 1. Điều kiện tiên quyết (Prerequisite)
Trước khi bắt đầu thực hiện giai đoạn này, bạn cần đảm bảo:

- Đã hoàn thành các bước chuẩn bị môi trường ở mục 5.2.
- Máy cục bộ đã cài đặt Node.js và cấu hình thành công AWS CLI liên kết với tài khoản AWS.
- Mã nguồn Frontend (ReactJS) đã hoạt động ổn định dưới Local và sẵn sàng để đóng gói.

### 2. Mô tả kiến trúc (Architecture)
Kiến trúc lớp Frontend được thiết kế theo mô hình Static Website Hosting kết hợp CDN (Content Delivery Network) nhằm loại bỏ hoàn toàn việc quản lý máy chủ Web truyền thống:

- Amazon S3: Thùng chứa (Bucket) lưu trữ toàn bộ các tệp tin tĩnh sau khi biên dịch (.html, .js, .css, hình ảnh). S3 Bucket này được cấu hình ở chế độ riêng tư (Private), chặn hoàn toàn mọi truy cập công khai trực tiếp từ Internet.

- Amazon CloudFront: Mạng lưới phân phối nội dung toàn cầu. CloudFront sẽ lấy dữ liệu từ S3, lưu vào bộ nhớ đệm (Caching) tại các trung tâm dữ liệu biên (Edge Locations) gần người dùng nhất để tăng tốc độ phản hồi trang web.

- Origin Access Control (OAC): Giải pháp bảo mật tiên tiến của AWS, đóng vai trò như một chứng thư xác thực. OAC bắt buộc mọi yêu cầu truy cập tài nguyên tĩnh phải đi qua CloudFront, ngăn chặn hoàn toàn việc người dùng "vượt rào" truy cập trực tiếp vào S3 Bucket gốc.

