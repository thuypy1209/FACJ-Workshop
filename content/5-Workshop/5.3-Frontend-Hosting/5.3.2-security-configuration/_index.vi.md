---
title : "security-configuration"
date : 2026-07-01 
weight : 2
chapter : false
pre : " <b> 5.3.2 </b> "
---

### Mục tiêu: Xác thực web đã hoạt động và được phân phối đúng cách qua CDN.

Các bước thực hiện:

bước 1
Truy cập vào trang quản lý CloudFront, sao chép Distribution domain name (VD: d123456789.cloudfront.net).
![CloudFront](/images/5-Workshop/5.3.2-security-configuration/CloudFront.png)

bước 2
Dán URL này vào trình duyệt để kiểm tra giao diện Traveloka-booking.
![URL](/images/5-Workshop/5.3.2-security-configuration/URL.png)

bước 3
Kiểm tra bộ nhớ đệm: Thử F5 lại trang web. Nếu CloudFront hoạt động tốt, tốc độ tải các file static sẽ nhanh hơn so với truy cập trực tiếp S3.

bước 4 
Kiểm tra bảo mật: Thử truy cập trực tiếp vào URL của file S3 (đã bị Block Public Access), trình duyệt sẽ trả về lỗi Access Denied - điều này khẳng định cấu hình OAC đã thành công.

### Tại sao phải cấu hình như vậy?
CloudFront hoạt động như một lớp đệm nội dung (CDN), nó giúp cache (lưu đệm) giao diện web tại các vị trí gần người dùng hơn, làm giảm độ trễ (latency) khi tải trang Traveloka booking.
