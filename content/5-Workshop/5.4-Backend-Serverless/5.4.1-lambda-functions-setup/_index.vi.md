---
title : "lambda-functions-setup"
date : 2026-07-01
weight : 1
chapter : false
pre : " <b> 5.4.1 </b> "
---

#### Thiết lập Quyền truy cập và Khởi tạo AWS Lambda

**Mục tiêu:** 
Tạo môi trường tính toán phi máy chủ để chạy mã nguồn Backend Node.js và cấp các quyền bảo mật cần thiết để Lambda có thể giao tiếp với DynamoDB và SES.

**Các bước thực hành:**

**Bước 1: Thiết lập IAM Role cho Backend**
Trước khi tạo mã nguồn, chúng ta cần cấp quyền cho dịch vụ bằng IAM Role.

1. Truy cập vào **AWS Management Console**, tìm kiếm dịch vụ **IAM** và chọn **Roles** -> **Create role**.
2. Chọn Trusted entity type là **AWS service** và Use case là **Lambda**. Nhấn **Next**.
![Select trusted entity](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/setup5.4.1.png)
3. Tại trang Add permissions, tìm và đánh dấu chọn các policy sau: `AWSLambdaBasicExecutionRole`, `AmazonDynamoDBFullAccess`, `AmazonSESFullAccess`.
![Add permissions ](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/Add5.4.1.png)

4. Nhấn **Next**, đặt tên Role name là `Traveloka-Backend-Execution-Role` và nhấn **Create role**.

![Tạo IAM Role cho Backend Lambda](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/create-iam-role.png)
![Tạo IAM Role cho Backend Lambda1](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/create-iam-role1.png)


**Bước 2: Khởi tạo hàm AWS Lambda**
1. Truy cập dịch vụ **AWS Lambda**, chọn **Create function**.
![Khởi tạo Create function ](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/create-function.png)
2. Chọn tùy chọn **Author from scratch** và thiết lập:
   * **Function name:** `Traveloka-Booking-Handler`
   * **Runtime:** Node.js 24.x
   * **Architecture:** arm64
3. Mở rộng phần **Change default execution role**, chọn *Use an existing role* và trỏ đến role `Traveloka-Backend-Execution-Role` đã tạo ở Bước 1. Nhấn **Create function**.

![Khởi tạo AWS Lambda](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/create-lambda-function.png)

4. Tại giao diện Code source, chọn **** dán đoạn mã chương trình vào 

![deploy source code Lambda](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/deploy-lambda-code.png)






