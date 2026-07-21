---
title : "apigw-rest-integration"
date : 2026-07-01
weight : 2
chapter : false
pre : " <b> 5.4.2 </b> "
---

#### Xây dựng REST API với Amazon API Gateway

**Mục tiêu:** 
Xây dựng điểm neo (Endpoint) định tuyến các HTTP Request từ Frontend ReactJS vào hàm Lambda một cách an toàn.

**Các bước thực hành:**

**Bước 1: Khởi tạo REST API**
1. Điều hướng tới dịch vụ **API Gateway**, cuộn đến mục **REST API** (không chọn HTTP API) và nhấn **Build**.
2. Chọn **New API**, nhập API name là `Traveloka-Core-API`. Endpoint Type để mặc định là **Regional**. Nhấn **Create API**.

![Khởi tạo REST API](/images/5-Workshop/5.4-Backend-Serverless/5.4.2-apigw-rest-integration/create-rest-api.png)


**Bước 2: Tạo Resource và Method**
1. Từ menu **Actions** (hoặc nút **Create resource**), tạo một tài nguyên mới, nhập Resource Name là `bookings`.
2. Chọn Resource `/bookings` vừa tạo, nhấn **Create Method**, chọn loại là **POST** và xác nhận.

![Tạo Resource và Method POST](/images/5-Workshop/5.4-Backend-Serverless/5.4.2-apigw-rest-integration/create-resource-method.png)

**Bước 3: Cấu hình Lambda Proxy Integration**
1. Tại màn hình thiết lập của Method **POST**, chọn Integration type là **Lambda Function**.
2. Đánh dấu tick vào ô **Use Lambda Proxy integration**.
3. Tại ô Lambda Function, chọn hàm `Traveloka-Booking-Handler` đã tạo ở phần trước và nhấn **Save**. Nhấn **OK** khi hộp thoại yêu cầu cấp quyền hiện ra.

![Tích hợp Lambda Proxy](/images/5-Workshop/5.4-Backend-Serverless/5.4.2-apigw-rest-integration/lambda-proxy-integration.png)


**Bước 4: Deploy API**
1. Chọn Resource `/bookings`, nhấn **Enable CORS** (chọn POST và OPTIONS) rồi nhấn **Save**.
2. Nhấn nút **Deploy API** ở góc trên màn hình.
3. Chọn Deployment stage là **[New Stage]**, nhập tên Stage là `prod` và nhấn **Deploy**.
4. Sao chép **Invoke URL** được cung cấp để cập nhật vào file `.env` của Frontend.

![Deploy API Gateway](/images/5-Workshop/5.4-Backend-Serverless/5.4.2-apigw-rest-integration/deploy-api.png)