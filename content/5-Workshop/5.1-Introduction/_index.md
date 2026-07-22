---
title : "Introduction"
date : 2026-07-01 
weight : 1 
chapter : false
pre : " <b> 5.1. </b> "
---
### Workshop Objectives

**MINI Traveloka Booking** is a comprehensive online travel agency (OTA) application that simulates a platform for booking flights and hotel accommodations. The application is built entirely on **Amazon Web Services (AWS)** using a **cloud-native serverless architecture**.

This workshop provides a step-by-step guide to provisioning a serverless infrastructure, configuring data flows, securing application connectivity with **CORS** and **Origin Access Control (OAC)**, managing user identities and authentication, and implementing web application firewall protection. All components are designed following modern cloud computing best practices.

### Learning Objectives

- Understand and design a cost-effective system based on a **serverless architecture**.
- Build high-performance, auto-scaling **RESTful APIs** using **Amazon API Gateway** and **AWS Lambda (Node.js)**.
- Design and optimize **Amazon DynamoDB** NoSQL tables to achieve single-digit millisecond latency.
- Securely host the **ReactJS** frontend on **Amazon S3** and accelerate global content delivery through the **Amazon CloudFront** CDN.
- Master **Origin Access Control (OAC)** for protecting static resources and configure **CORS** policies to securely control API access.
- Manage user identity, authentication, and authorization using **Amazon Cognito User Pools** and **JSON Web Tokens (JWT)**.
- Protect the application against common web attacks such as **SQL Injection** and **Cross-Site Scripting (XSS)**, while mitigating **Distributed Denial-of-Service (DDoS)** attacks using **AWS WAF**.

### AWS Services Used

| Service | Purpose |
|---------|---------|
| **AWS Lambda** | Provides **serverless computing** to execute backend business logic (Node.js) in response to events, with automatic scaling based on application demand. |
| **Amazon API Gateway** | Manages **RESTful APIs**, routes incoming requests, controls traffic, and connects the frontend application with AWS Lambda functions. |
| **Amazon DynamoDB** | A fully managed **serverless NoSQL database** used to store hotel, cruise, and booking information with high performance and single-digit millisecond latency. |
| **Amazon Cognito** | Provides user identity and authentication services through **User Pools**, securely manages user credentials, and issues **JSON Web Tokens (JWTs)**. |
| **Amazon S3** | A serverless object storage service used to host the static frontend assets of the ReactJS application after the production build. |
| **Amazon CloudFront** | A global **Content Delivery Network (CDN)** that accelerates content delivery, reduces latency, and secures the Amazon S3 origin using **Origin Access Control (OAC)**. |
| **AWS WAF** | A **Web Application Firewall** that protects Amazon CloudFront and Amazon API Gateway against common web vulnerabilities and malicious traffic through Web ACLs. |
| **Amazon Route 53** | A highly available and scalable **DNS service** used to route the project's custom domain name to Amazon CloudFront. |

### Tools & Frameworks

| Tool / Framework | Purpose |
|------------------|---------|
| **ReactJS & Vite** | Used to build a fast and responsive **Single Page Application (SPA)**, providing a modern user interface for the MINI Traveloka Booking website. |
| **Node.js** | JavaScript runtime environment used to execute backend code within AWS Lambda functions. |
| **JWT (JSON Web Token)** | A secure token standard used to authenticate users and maintain authenticated sessions between the frontend and backend. |
| **ReactJS** | JavaScript framework for developing Single Page Applications (SPA) using reusable components. |
| **CORS (Cross-Origin Resource Sharing)** | A browser security mechanism configured in Amazon API Gateway to control which domains are permitted to access the application's APIs. |

### Architecture Overview

| Component | Description |
|-----------|-------------|
| **Networking & Static Storage** | The ReactJS Single Page Application (SPA) is built and hosted as static assets in **Amazon S3**, with public access blocked to ensure secure access. |
| **Content Delivery** | **Amazon CloudFront** distributes the frontend through global edge locations to reduce latency and improve performance, while securely accessing the S3 origin using **Origin Access Control (OAC)**. |
| **Compute & API Layer** | All **RESTful APIs** are exposed through **Amazon API Gateway**, while backend business logic is implemented using **Node.js** functions running on **AWS Lambda**. |
| **Database & Authentication** | Application data is stored in **Amazon DynamoDB**, and user registration, authentication, and identity management are handled by **Amazon Cognito**. |
| **Security** | The system is protected by **AWS WAF** using managed security rule sets (including the **Core Rule Set** and **SQL Injection Protection**) together with strict **CORS** policies configured on Amazon API Gateway. |
![Architecture Diagram](/images/5-Workshop/5.1-Introduction/images/Diagram.png)

# Workshop Roadmap

| Phase | Objective |
|-------|-----------|
| **1. Prerequisites** | Set up AWS and GitHub accounts, and install the required development tools. |
| **2. Frontend Hosting & Content Delivery** | Build the ReactJS application, host the static website on **Amazon S3**, configure **Amazon CloudFront**, and secure the origin using **Origin Access Control (OAC)**. |
| **3. Database & Authentication** | Create **Amazon DynamoDB** NoSQL tables and configure user identity and authentication with **Amazon Cognito**. |
| **4. Serverless Backend Deployment** | Develop and deploy backend business logic using **AWS Lambda**, and expose RESTful APIs through **Amazon API Gateway**. |
| **5. Data Flow & Security** | Configure **CORS** on Amazon API Gateway to enable secure communication with the frontend, and deploy **AWS WAF** to protect the entire application. |
| **6. Resource Cleanup** | Safely remove all AWS resources after completing the workshop to avoid unnecessary charges. |
