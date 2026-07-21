---
title: "Tuần 5 - Nhật ký công việc"
date: 2026-06-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Phát triển các hàm AWS Lambda (Node.js) hiện thực bước 8 trong sơ đồ kiến trúc ("Chạy lệnh xử lý dữ liệu") cho logic nghiệp vụ đặt tour.
* Thực hiện xác minh JWT Token tại tầng Backend để đảm bảo bảo mật, đúng theo bước 7 ("Xác nhận danh tính").
* Xử lý việc lưu ảnh/tài liệu đặt tour vào S3 Storage và dữ liệu tour vào DynamoDB (bước 9), đồng thời chuẩn bị nền tảng ghi log cho bước 10.

### Công việc thực hiện trong tuần:
| Ngày | Công việc                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| ---- | -------------------------------------------------------------------------------------------------------------------------- | ------------ | ---------------- | ------------------------------------------ |
| 1    | - Thiết lập cấu trúc dự án Lambda Node.js, cài đặt AWS SDK và cấu hình biến môi trường                                     | 01/06/2026   | 01/06/2026        | <https://cloudjourney.awsstudygroup.com/>  |
| 2    | - Phát triển hàm Lambda tạo mới và truy xuất dữ liệu Tours/Bookings (Create, Read)                                         | 02/06/2026   | 02/06/2026        | -                                           |
| 3    | - Phát triển hàm Lambda cập nhật và xóa dữ liệu Tours/Bookings (Update, Delete)                                            | 03/06/2026   | 03/06/2026        | -                                           |
| 4    | - Triển khai logic xác minh JWT Token trong các hàm Lambda trước khi xử lý request <br> - Triển khai upload ảnh/tài liệu đặt tour lên S3 Storage | 04/06/2026   | 04/06/2026        | -                                           |
| 5    | - **Thực hành:** kiểm thử từng hàm Lambda riêng lẻ qua test event trên AWS Console <br> - Sửa lỗi phát hiện trong quá trình kiểm thử | 05/06/2026   | 05/06/2026        | -                                           |

### Thành quả tuần 5:

* Hoàn thành các hàm Lambda (Node.js) xử lý logic CRUD cho Tours và Bookings — khớp với bước 8 trong sơ đồ kiến trúc.
* Triển khai thành công việc xác minh JWT Token tại tầng Backend, đảm bảo chỉ request đã xác thực mới được xử lý.
* Triển khai lưu ảnh/tài liệu đặt tour vào S3 Storage và dữ liệu tour vào DynamoDB, khớp với bước 9.
* Kiểm thử độc lập từng hàm Lambda và xác nhận hoạt động đúng với dữ liệu mẫu, chuẩn bị tầng xử lý logic cần thiết để xây dựng các endpoint API Gateway ở tuần 6.
