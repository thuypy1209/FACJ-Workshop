---
title: "Workshop"
date: 2026-07-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---


# Building and Deploying the MINI Traveloka Booking System on AWS (Serverless-First)

#### Overview

This workshop provides a comprehensive guide to designing, deploying, securing, and operating the **MINI Traveloka Booking** system on **Amazon Web Services (AWS)**.

The **MINI Traveloka Booking** project is a full-stack web application that simulates an online travel booking platform, allowing users to book flights, hotel rooms, and cruise services. The application is built using a **cloud-native serverless architecture**, enabling cost optimization, automatic scaling based on real-time traffic, and eliminating the need to manage physical servers or container infrastructure.

Unlike traditional architectures that rely on virtual machines (Amazon EC2) or container-based platforms such as Amazon ECS and Amazon EKS, this workshop adopts a **Serverless-First** approach. The backend is decomposed into independent microservices running on **AWS Lambda**, exposed through **Amazon API Gateway**, and powered by the **Amazon DynamoDB** NoSQL database. The frontend is optimized and deployed as a static web application on **Amazon S3**, delivering high availability and low-latency access.

By the end of this workshop, you will gain hands-on experience in building and deploying a complete serverless application on AWS, from frontend to backend. You will also learn how to implement security best practices and cloud-native development techniques that closely reflect real-world production environments.

#### Content

1. [Project Overview (Introduction)](5.1-Introduction/)
2. [Environment Setup (Prerequisites)](5.2-Prerequiste/)
3. [Frontend Hosting & Content Delivery (Frontend Hosting)](5.3-Frontend-Hosting/)
4. [Building the Serverless Backend Core (Backend Serverless)](5.4-Backend-Serverless/)
5. [Database & Authentication (Database & Auth)](5.5-Database-Auth/)
6. [Resource Cleanup (Cleanup)](5.6-Cleanup/)