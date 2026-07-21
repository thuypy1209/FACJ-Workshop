---
title : "s3-cloudfront-setup"
date : 2026-07-01
weight : 3
chapter : false
pre : " <b> 5.3.1 </b> "
---

### Mục tiêu: Tạo S3 Bucket và thiết lập CloudFront Distribution.

1 Truy cập dịch vụ S3 > Create bucket. Nhập tên bucket (VD: traveloka-clone-frontend) và giữ nguyên mặc định là Block all public access.

![tạo S3](/images/5-workshop/5.3.1-s3-cloudfront-setup/s3.png)

2 Upload toàn bộ thư mục dist (đã build từ source code React) lên Bucket.

![upload file ](/images/5-workshop/5.3.1-s3-cloudfront-setup/upload.png)

3 Truy cập dịch vụ CloudFront > Create distribution, thực hiện qua từng bước .
bước 1
![setup1 ](/images/5-workshop/5.3.1-s3-cloudfront-setup/setup1.png)
bước 2
![setup2 ](/images/5-workshop/5.3.1-s3-cloudfront-setup/setup2.png)
bước 3
![setup3 ](/images/5-workshop/5.3.1-s3-cloudfront-setup/setup3.png)
bước 4
![setup4 ](/images/5-workshop/5.3.1-s3-cloudfront-setup/setup4.png)


4 Tại phần Origin domain, chọn S3 bucket vừa tạo.

5 Tại phần Origin access, chọn Origin access control settings (recommended) và nhấn Create control setting để tạo OAC.

6 Nhấn Create distribution. Sau khi tạo xong, CloudFront sẽ cung cấp một đoạn Policy, hãy copy và dán vào phần Permissions > Bucket policy của S3 bucket để cấp quyền cho CloudFront truy cập.

 ![Distribution domain name ](/images/5-Workshop/5.3.1-s3-cloudfront-setup/Distribution.png)

