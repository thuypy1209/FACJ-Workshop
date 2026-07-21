---
title: "Tuần 4 - Nhật ký công việc"
date: 2026-05-25
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Cấu hình Amazon Cognito User Pool và Identity Pool, phục vụ cho cả bước 4 ("Đăng nhập / Đăng ký") và bước 7 ("Xác nhận danh tính") trong sơ đồ kiến trúc.
* Thiết lập luồng xác thực người dùng (đăng ký, đăng nhập, xác nhận tài khoản).
* Cấu hình cấp phát JSON Web Token (JWT) cho người dùng đã xác thực, để sau này Lambda có thể xác minh trước khi xử lý yêu cầu đặt tour.

### Công việc thực hiện trong tuần:
| Ngày | Công việc                                                                                                                       | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| ---- | ---------------------------------------------------------------------------------------------------------------------------- | ------------ | ---------------- | ------------------------------------------ |
| 1    | - Tìm hiểu các khái niệm của Amazon Cognito: User Pool, Identity Pool, App Client                                              | 25/05/2026   | 25/05/2026        | <https://cloudjourney.awsstudygroup.com/>  |
| 2    | - Tạo và cấu hình Cognito User Pool: chính sách mật khẩu, thuộc tính bắt buộc, phương thức xác minh                            | 26/05/2026   | 26/05/2026        | -                                           |
| 3    | - Tạo và cấu hình Cognito Identity Pool, liên kết với User Pool                                                                | 27/05/2026   | 27/05/2026        | -                                           |
| 4    | - **Thực hành:** triển khai luồng đăng ký, xác nhận tài khoản và đăng nhập qua AWS Console / CLI                              | 28/05/2026   | 28/05/2026        | -                                           |
| 5    | - Cấu hình cấp phát JWT (ID Token, Access Token, Refresh Token) sau khi đăng nhập thành công <br> - Kiểm tra nội dung token    | 29/05/2026   | 29/05/2026        | -                                           |

### Thành quả tuần 4:

* Cấu hình thành công Cognito User Pool và Identity Pool cho hệ thống.
* Xây dựng hoàn chỉnh luồng đăng ký / xác nhận tài khoản / đăng nhập, khớp với bước 4 trong sơ đồ kiến trúc.
* Hiểu được cách Cognito cấp phát JWT (ID Token, Access Token, Refresh Token) và mục đích sử dụng của từng loại token trong bước xác nhận danh tính (bước 7).
* Chuẩn bị nền tảng xác thực cần thiết để tích hợp với backend ở tuần 5.
