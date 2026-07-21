---
title: "Tuần 3 - Nhật ký công việc"
date: 2026-05-18
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Thiết kế cơ sở dữ liệu NoSQL bằng Amazon DynamoDB cho hệ thống đặt tour trực tuyến.
* Xác định cấu trúc bảng, partition key, sort key và các access pattern cho Users, Tours và Bookings.
* Khởi tạo dữ liệu mẫu và thiết lập các truy vấn cơ bản, đúng theo luồng dữ liệu trong sơ đồ kiến trúc (bước 9: "Lưu/tìm kiếm thông tin tour").

### Công việc thực hiện trong tuần:
| Ngày | Công việc                                                                                                                     | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| ---- | ------------------------------------------------------------------------------------------------------------------------------ | ------------ | ---------------- | ------------------------------------------ |
| 1    | - Tìm hiểu kiến thức nền tảng về DynamoDB: partition key, sort key, Global Secondary Index (GSI)                               | 18/05/2026   | 18/05/2026        | <https://cloudjourney.awsstudygroup.com/>  |
| 2    | - Thiết kế cấu trúc bảng cho Users, Tours, Bookings dựa trên các access pattern của hệ thống                                    | 19/05/2026   | 19/05/2026        | -                                           |
| 3    | - Tạo các bảng DynamoDB và cấu hình primary key / GSI cho từng bảng                                                            | 20/05/2026   | 20/05/2026        | -                                           |
| 4    | - Khởi tạo dữ liệu mẫu cho Users, Tours, Bookings <br> - **Thực hành:** thêm, sửa, xóa dữ liệu qua AWS Console                 | 21/05/2026   | 21/05/2026        | -                                           |
| 5    | - **Thực hành:** thiết lập các truy vấn cơ bản (Query/Scan) để tìm kiếm thông tin tour theo các access pattern <br> - Review cùng mentor | 22/05/2026   | 22/05/2026        | -                                           |

### Thành quả tuần 3:

* Hoàn thành thiết kế cơ sở dữ liệu NoSQL với DynamoDB cho các bảng Users, Tours, Bookings.
* Hiểu được cách chọn partition key / sort key hiệu quả dựa trên access pattern của hệ thống.
* Khởi tạo thành công dữ liệu mẫu và kiểm chứng bằng các thao tác Query/Scan cơ bản.
* Xây dựng nền tảng dữ liệu vững chắc, khớp với bước 9 trong sơ đồ kiến trúc ("lưu/tìm kiếm thông tin tour"), sẵn sàng bước sang thiết lập luồng xác thực với Cognito ở tuần 4.
