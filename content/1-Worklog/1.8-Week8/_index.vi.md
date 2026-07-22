---
title: "Tuần 8 - Nhật ký công việc"
date: 2026-06-22
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Phát triển chức năng đăng nhập/đăng ký trên ReactJS, kết nối với API xác thực Cognito — khớp với bước 4 trong sơ đồ kiến trúc.
* Lưu trữ JWT Token an toàn sau khi đăng nhập thành công.
* Đính kèm JWT Token vào Request Header cho các lần gọi API cần xác thực tiếp theo (dùng để xác nhận danh tính ở bước 7).

### Công việc thực hiện trong tuần:
| Ngày | Công việc                                                                                                              | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| ---- | ----------------------------------------------------------------------------------------------------------------------- | ------------ | ---------------- | ------------------------------------------ |
| 1    | - Xây dựng giao diện trang Đăng nhập / Đăng ký: form email/mật khẩu và validate dữ liệu                                 | 22/06/2026   | 22/06/2026        | <https://docs.amplify.aws/javascript/build-a-backend/auth/>                                           |
| 2    | - Kết nối form đăng nhập/đăng ký với API xác thực Cognito thông qua API Gateway                                         | 23/06/2026   | 23/06/2026        | -                                           |
| 3    | - Lưu trữ JWT Token (Access Token, Refresh Token) sau khi đăng nhập thành công                                          | 24/06/2026   | 24/06/2026        | -                                           |
| 4    | - Cấu hình Axios interceptor để tự động đính kèm JWT Token vào Authorization Header của mỗi request                    | 25/06/2026   | 25/06/2026        | <https://axios.rest/pages/advanced/interceptors>                                           |
| 5    | - **Thực hành:** kiểm thử toàn bộ luồng đăng nhập, xử lý lỗi đăng nhập và trường hợp token hết hạn                      | 26/06/2026   | 26/06/2026        | -                                           |

### Thành quả tuần 8:

* Hoàn thành chức năng đăng nhập/đăng ký trên Frontend, kết nối đầu-cuối với Cognito.
* Lưu trữ và quản lý JWT Token thành công sau khi đăng nhập.
* Cấu hình Axios interceptor để tự động đính kèm token vào mọi request API, hỗ trợ bước xác nhận danh tính  khi gửi yêu cầu đặt tour.
* Xử lý các trường hợp lỗi cơ bản (sai mật khẩu, token hết hạn), chuẩn bị xây dựng tính năng hiển thị dữ liệu tour.
