---
title : "Backend-Serverless"
date : 2026-07-01 
weight : 4 
chapter : false
pre : " <b> 5.4. </b> "
---

### Giai đoạn 2 – Xây dựng Core Backend Serverless (Lambda & API Gateway)

**Mục tiêu:**
Xây dựng tầng xử lý nghiệp vụ (Business Logic) cốt lõi của ứng dụng Traveloka-Serverless hoàn toàn theo mô hình Phi máy chủ (Serverless). Giai đoạn này thiết lập nền tảng để hệ thống có thể tự động mở rộng (Auto-scaling) ngay lập tức khi lưu lượng truy cập tăng đột biến trong các mùa cao điểm du lịch, đồng thời tối ưu hóa chi phí theo nguyên tắc "Pay-as-you-go" (chỉ trả tiền cho thời gian tính toán thực tế).

**Mô tả kiến trúc:**
Tầng Backend được thiết kế dựa trên sự kết hợp của ba dịch vụ quản lý hoàn toàn (Managed Services) từ AWS:
*   **Amazon API Gateway (REST API):** Đóng vai trò là "cửa ngõ" (Reverse Proxy) duy nhất tiếp nhận toàn bộ các HTTP request từ Frontend ReactJS. Dịch vụ này chịu trách nhiệm định tuyến (routing), quản lý lưu lượng (throttling), và sẽ được tích hợp AWS WAF ở các giai đoạn sau để bảo vệ hệ thống khỏi các cuộc tấn công.
*   **AWS Lambda (Node.js):** Đóng vai trò là các Worker thực thi logic nghiệp vụ (tìm kiếm chuyến bay, tạo booking phòng khách sạn). Lambda hoạt động theo cơ chế Event-driven, được kích hoạt trực tiếp từ API Gateway.
*   **Amazon SES (Simple Email Service):** Dịch vụ được tích hợp trực tiếp vào hàm Lambda xử lý Booking để tự động phát hành email xác nhận chứa thông tin vé/phòng đến khách hàng ngay khi giao dịch thành công.

Trong phần này, chúng ta sẽ lần lượt thiết lập AWS Lambda, cấu hình API Gateway và tích hợp dịch vụ gửi email SES.


