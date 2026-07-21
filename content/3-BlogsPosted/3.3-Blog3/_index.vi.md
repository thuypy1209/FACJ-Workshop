---
title: "Blog 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---


### Bài viết này đã được gửi và hiện đang chờ phê duyệt.


Việc lưu trữ dữ liệu trên Amazon S3 thực sự rất đơn giản, từ vài file cho đến hàng tỷ object mà không cần lo về khả năng mở rộng. Tuy nhiên, bài toán thực tế của doanh nghiệp đặt ra là làm thế nào để tìm được đúng file cần thiết trong hàng trăm triệu hoặc hàng tỷ object mà không phải quét toàn bộ bucket.

### 1. Bài toán trước đây: Có dữ liệu nhưng rất khó tìm kiếm
* **Thách thức quy mô lớn:** Khi doanh nghiệp lưu trữ hàng trăm triệu hình ảnh, hàng tỷ file log, dữ liệu IoT hay video giám sát, những câu hỏi như *"Có bao nhiêu file lớn hơn 500 MB?"*, *"Object nào chưa được truy cập trong 90 ngày?"*, hay *"Bao nhiêu object dùng Storage Class Standard thay vì Glacier?"* trở nên vô cùng khó trả lời.
* **Giải pháp thủ công trước đây:** Các kỹ sư thường phải viết script dùng API `ListObjectsV2` quét toàn bộ bucket, đồng bộ metadata sang DynamoDB/Elasticsearch, xây dựng Lambda cập nhật theo thời gian thực hoặc tạo các pipeline ETL phức tạp.

### 2. Giá trị giải pháp và Bài học rút ra
* **Giải pháp thông minh từ AWS:** Amazon S3 Metadata giúp giải quyết triệt để bài toán tìm kiếm và quản lý dữ liệu lớn, giảm đáng kể thời gian phát triển hệ thống cũng như chi phí vận hành.
* **Bài học nhận được:** Khi quy mô dữ liệu ngày càng lớn, vấn đề không còn nằm ở việc lưu được bao nhiêu dữ liệu, mà là khai thác dữ liệu đó nhanh đến mức nào. Tính năng này giúp loại bỏ các công việc lặp đi lặp lại của kỹ sư, để họ có thể tập trung tối đa vào việc phân tích dữ liệu và tạo ra nhiều giá trị kinh doanh hơn.

![Hình bài chưa duyệt](/images/3-BlogsPosted/3.3-Blog3/Blog3.png)