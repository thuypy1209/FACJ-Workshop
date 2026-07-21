---
title: "Workshop"
date: 2026-07-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---




# Xây dựng và Triển khai Hệ thống Đặt vé & Phòng khách sạn MINI Traveloka Booking trên AWS (Serverless First)

#### Tổng quan

Workshop này hướng dẫn toàn bộ quy trình xây dựng, triển khai, bảo mật và vận hành hệ thống Traveloka Clone (Traveloka-Serverless) trên nền tảng điện toán đám mây Amazon Web Services (AWS).

Dự án Traveloka-Serverless là một ứng dụng Full-stack mô phỏng nền tảng đặt vé máy bay, phòng khách sạn và dịch vụ du thuyền. Hệ thống được thiết kế theo kiến trúc Cloud-Native Serverless (Kiến trúc phi máy chủ), giúp tối ưu hóa chi phí vận hành, tự động mở rộng quy mô (Auto-scaling) theo lượng truy cập thực tế và loại bỏ hoàn toàn gánh nặng quản lý máy chủ vật lý hay Container.

Khác với cách xây dựng hệ thống truyền thống sử dụng máy chủ ảo (EC2) hoặc Docker Container (ECS/EKS), workshop này tập trung vào tư duy Serverless First. Toàn bộ logic Backend sẽ được phân rã thành các vi dịch vụ (Microservices) chạy trên AWS Lambda, giao tiếp thông qua Amazon API Gateway và lưu trữ dữ liệu trên cơ sở dữ liệu NoSQL Amazon DynamoDB. Frontend của ứng dụng được tối ưu hóa.

Sau khi hoàn thành workshop, bạn sẽ làm chủ kỹ năng triển khai một hệ thống Serverless hoàn chỉnh từ Frontend đến Backend trên AWS, tích hợp các tiêu chuẩn bảo mật nghiêm ngặt sát với môi trường Production.

#### Nội dung

1. [Tổng quan dự án (Introduction)](5.1-Introduction/)
2. [Chuẩn bị môi trường (Prerequisite)](5.2-Prerequiste/)
3. [Lưu trữ và Tăng tốc Frontend (Frontend Hosting)](5.3-Frontend-Hosting/)
4. [Xây dựng Core Backend Serverless (Backend Serverless)](5.4-Backend-Serverless/)
5. [Cơ sở dữ liệu & Xác thực (Database & Auth)](5.5-Database-Auth/)
6. [Dọn dẹp tài nguyên (Clean up)](5.6-Cleanup/)
