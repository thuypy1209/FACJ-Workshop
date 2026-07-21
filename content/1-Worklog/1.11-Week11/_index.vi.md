---
title: "Tuần 11 - Nhật ký công việc"
date: 2026-07-13
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Thực hiện kiểm thử toàn hệ thống theo đầu-cuối, bao quát đủ 11 bước trong sơ đồ kiến trúc: Route 53 → WAF → CloudFront → S3 Frontend, đăng nhập qua Cognito, và luồng đặt tour qua WAF → API Gateway → Cognito → Lambda → S3 Storage/DynamoDB → CloudWatch.
* Rà soát và sửa các lỗi phát hiện trong quá trình kiểm thử từng chức năng.
* Tối ưu hóa hiệu năng, cải thiện độ ổn định của hệ thống và kiểm tra CloudWatch có ghi log/cảnh báo lỗi đúng như bước 10-11 hay không.

### Công việc thực hiện trong tuần:
| Ngày | Công việc                                                                                                             | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| ---- | -------------------------------------------------------------------------------------------------------------------- | ------------ | ---------------- | ------------------------------------------ |
| 1    | - Xây dựng checklist test case cho toàn bộ luồng: phân giải DNS, phân phối web, đăng ký, đăng nhập, xem danh sách tour, đặt tour | 13/07/2026   | 13/07/2026        | -                                           |
| 2    | - Kiểm thử Route 53/WAF/CloudFront (bước 1-3) và luồng xác thực (đăng ký/đăng nhập/token hết hạn, bước 4 và 7)         | 14/07/2026   | 14/07/2026        | -                                           |
| 3    | - Kiểm thử toàn bộ luồng đặt tour đầu-cuối (bước 5-9) và kiểm tra tính nhất quán dữ liệu trong S3 Storage và DynamoDB | 15/07/2026   | 15/07/2026        | -                                           |
| 4    | - Rà soát và sửa các lỗi phát hiện trong quá trình kiểm thử (UI, API, dữ liệu)                                        | 16/07/2026   | 16/07/2026        | -                                           |
| 5    | - Tối ưu thời gian cold-start của Lambda, và kiểm tra CloudWatch ghi log hoạt động, cảnh báo lỗi đúng theo bước 10-11 | 17/07/2026   | 17/07/2026        | -                                           |

### Thành quả tuần 11:

* Hoàn thành kiểm thử toàn hệ thống theo đầu-cuối, bao quát đủ 11 bước trong sơ đồ kiến trúc, từ tầng Edge (Route 53, WAF, CloudFront, S3 Frontend) đến Backend Serverless (API Gateway, Cognito, Lambda, S3 Storage, DynamoDB) và tầng giám sát (CloudWatch).
* Sửa được các lỗi phát hiện trong quá trình kiểm thử, cải thiện độ ổn định tổng thể của hệ thống.
* Thực hiện các tối ưu hóa hiệu năng ban đầu cho các hàm Lambda dựa trên dữ liệu từ CloudWatch.
* Xác nhận CloudWatch ghi log hoạt động và cảnh báo lỗi chính xác, chuẩn bị một hệ thống ổn định sẵn sàng cho báo cáo thực tập và tài liệu kỹ thuật ở tuần 12.
