---
title: "Tuần 6 - Nhật ký công việc"
date: 2026-06-08
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* Xây dựng Amazon API Gateway và định nghĩa các endpoint REST cho hệ thống đặt tour, khớp với bước 6 trong sơ đồ kiến trúc.
* Cấu hình bộ quy tắc WAF phía trước API để lọc luồng độc hại trước khi đến API Gateway, đúng theo bước 5 ("Lọc luồng độc hại").
* Bảo mật các endpoint bằng Cognito Authorizer, và cấu hình CORS để Frontend có thể gọi API mà không bị trình duyệt chặn.

### Công việc thực hiện trong tuần:
| Ngày | Công việc                                                                                                                          | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| ---- | ------------------------------------------------------------------------------------------------------------------------------- | ------------ | ---------------- | ------------------------------------------ |
| 1    | - Tìm hiểu các khái niệm REST API trong API Gateway: resource, method, integration, stage                                        | 08/06/2026   | 08/06/2026        | <https://docs.aws.amazon.com/apigateway/>  |
| 2    | - Tạo API Gateway và định nghĩa endpoint cho Tours và Bookings (GET, POST, PUT, DELETE)                                           | 09/06/2026   | 09/06/2026        | -                                           |
| 3    | - Tích hợp từng endpoint với hàm Lambda tương ứng đã tạo ở tuần 5                                                                  | 10/06/2026   | 10/06/2026        | <https://docs.aws.amazon.com/apigateway/>                                           |
| 4    | - Cấu hình WAF Web ACL phía trước API Gateway để lọc luồng độc hại (bước 5), và cấu hình CORS cho các endpoint                    | 11/06/2026   | 11/06/2026        | <https://docs.aws.amazon.com/waf>                                           |
| 5    | - Thiết lập Cognito Authorizer để bảo mật endpoint <br> - **Thực hành:** kiểm thử endpoint bằng Postman với token hợp lệ/không hợp lệ | 12/06/2026   | 12/06/2026        | <https://docs.aws.amazon.com/apigateway/>                                           |

### Thành quả tuần 6:

* Hoàn thành API Gateway với đầy đủ endpoint REST cho Tours và Bookings, khớp với bước 6 trong sơ đồ kiến trúc.
* Cấu hình WAF Web ACL để lọc luồng độc hại trước khi đến API Gateway (bước 5), và cấu hình CORS thành công, cho phép Frontend gọi API mà không gặp lỗi từ trình duyệt.
* Bảo mật toàn bộ endpoint bằng Cognito Authorizer, đảm bảo chỉ token hợp lệ mới truy cập được API (bước 7).
* Kiểm chứng endpoint đầu-cuối bằng Postman, sẵn sàng cho việc tích hợp Frontend bắt đầu từ tuần 7.
