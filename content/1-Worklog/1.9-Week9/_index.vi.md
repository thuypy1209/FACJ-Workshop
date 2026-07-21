---
title: "Tuần 9 - Nhật ký công việc"
date: 2026-06-29
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Phát triển chức năng hiển thị danh sách tour và gửi yêu cầu đặt tour, khớp với bước 5 ("Gửi yêu cầu đặt tour") và bước 6 ("Lọc luồng độc hại") trong sơ đồ kiến trúc.
* Sử dụng fetch/Axios để gọi dữ liệu từ API Gateway.
* Xử lý trạng thái loading/lỗi/rỗng và hiển thị dữ liệu lên giao diện.

### Công việc thực hiện trong tuần:
| Ngày | Công việc                                                                                                            | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| ---- | ----------------------------------------------------------------------------------------------------------------- | ------------ | ---------------- | ------------------------------------------ |
| 1    | - Xây dựng giao diện trang danh sách tour: bố cục card hiển thị thông tin tour                                      | 29/06/2026   | 29/06/2026        | -                                           |
| 2    | - Gọi endpoint GET /tours từ API Gateway để lấy dữ liệu danh sách tour                                              | 30/06/2026   | 30/06/2026        | -                                           |
| 3    | - Xử lý trạng thái loading, trạng thái lỗi và trạng thái danh sách rỗng trên giao diện                              | 01/07/2026   | 01/07/2026        | -                                           |
| 4    | - Xây dựng form "Đặt tour" và gửi yêu cầu đặt tour (POST /bookings) thông qua Axios instance đã đính kèm JWT        | 02/07/2026   | 02/07/2026        | -                                           |
| 5    | - **Thực hành:** bổ sung tính năng lọc/tìm kiếm cơ bản cho danh sách tour <br> - Kiểm thử luồng gửi yêu cầu đặt tour với nhiều dữ liệu mẫu | 03/07/2026   | 03/07/2026        | -                                           |

### Thành quả tuần 9:

* Hoàn thành chức năng hiển thị danh sách tour trên Frontend, kết nối đầu-cuối với API Gateway.
* Xử lý tốt các trạng thái loading, lỗi và dữ liệu rỗng để cải thiện trải nghiệm người dùng.
* Xây dựng thành công form gửi yêu cầu đặt tour và xác nhận luồng đi đúng qua WAF rồi đến API Gateway, khớp với bước 5-6 trong sơ đồ kiến trúc.
* Bổ sung khả năng tìm kiếm/lọc cơ bản, sẵn sàng chuyển sang hoàn thiện UI/UX ở tuần 10.
