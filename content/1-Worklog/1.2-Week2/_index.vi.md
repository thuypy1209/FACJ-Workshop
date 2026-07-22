---
title: "Tuần 2 - Nhật ký công việc"
date: 2026-05-11
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* Vẽ và soạn thảo sơ đồ kiến trúc hệ thống (System Architecture Diagram) hoàn chỉnh cho hệ thống đặt tour trực tuyến.
* Thiết kế kiến trúc hạ tầng Cloud gồm hai phần: **Edge Security & Delivery** (Route 53, WAF, CloudFront, S3 Frontend) và **Region - Serverless Architecture** (WAF, API Gateway, Cognito, Lambda, S3 Storage, DynamoDB, CloudWatch).
* Mô tả rõ luồng xử lý của hệ thống, từ lúc người dùng truy cập web cho đến khi yêu cầu đặt tour được xử lý và lưu trữ.

### Công việc thực hiện trong tuần:
| Ngày | Công việc                                                                                                                                                     | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | ---------------- | ------------------------------------------ |
| 1    | - Tìm hiểu quy ước và các biểu tượng chuẩn (AWS Architecture Icons) khi vẽ sơ đồ kiến trúc AWS                                                                | 11/05/2026   | 11/05/2026        | <<https://aws.amazon.com/vi/architecture/icons/>  |
| 2    | - Thiết kế khối **Edge Security & Delivery**: Route 53 phân giải tên miền, WAF kiểm tra bảo mật, CloudFront phân phối nội dung, S3 Frontend lưu trữ giao diện web tĩnh | 12/05/2026   | 12/05/2026        | <https://docs.aws.amazon.com/cloudfront/>                                           |
| 3    | - Thiết kế khối **Region (Serverless Architecture)**: WAF lọc luồng độc hại, API Gateway tiếp nhận request, Cognito xác thực người dùng                       | 13/05/2026   | 13/05/2026        | <https://docs.aws.amazon.com/apigateway/>                                           |
| 4    | - Thiết kế tầng xử lý logic với Lambda và tầng dữ liệu gồm S3 Storage (lưu ảnh/tài liệu đặt tour) và DynamoDB (lưu/tìm kiếm thông tin tour)                    | 14/05/2026   | 14/05/2026        | <https://docs.aws.amazon.com/lambda/>                                           |
| 5    | - Thiết kế luồng giám sát với CloudWatch (ghi log hoạt động, theo dõi lỗi hệ thống) <br> - Vẽ hoàn chỉnh sơ đồ với đầy đủ 11 bước luồng xử lý và review cùng mentor | 15/05/2026   | 15/05/2026        | <https://docs.aws.amazon.com/cloudwatch/>                                           |

### Thành quả tuần 2:

* Hoàn thành sơ đồ kiến trúc hệ thống đầy đủ, gồm 2 khối chính: **Edge Security & Delivery** và **Region (Serverless Architecture)**.
* Mô tả rõ luồng xử lý gồm 11 bước, cụ thể:
  1. User tìm địa chỉ web qua Route 53 (DNS)
  2. WAF kiểm tra bảo mật để cho phép truy cập an toàn
  3. CloudFront tải giao diện web từ S3 Frontend
  4. User đăng nhập / đăng ký qua Cognito
  5. User gửi yêu cầu đặt tour, đi qua WAF để lọc luồng độc hại
  6. API Gateway tiếp nhận và định tuyến request
  7. Xác nhận danh tính người dùng qua Cognito
  8. API Gateway gọi Lambda để chạy logic xử lý dữ liệu
  9. Lambda lưu ảnh/tài liệu đặt tour vào S3 Storage, và lưu/tìm kiếm thông tin tour trong DynamoDB
  10. Lambda ghi lại nhật ký hoạt động
  11. CloudWatch theo dõi và cảnh báo lỗi hệ thống
* Xác định rõ vai trò của từng dịch vụ AWS trong kiến trúc: Route 53 cho DNS, WAF cho bảo mật biên, CloudFront + S3 Frontend cho phân phối giao diện web, API Gateway cho tầng API, Cognito cho xác thực, Lambda cho xử lý logic, S3 Storage/DynamoDB cho lưu trữ dữ liệu, và CloudWatch cho giám sát/logging.
* Nhận được góp ý và sự đồng thuận từ mentor để tiến hành thiết kế chi tiết cơ sở dữ liệu ở tuần 3.
![Sơ đồ kiến trúc](images/Diagram.png)
