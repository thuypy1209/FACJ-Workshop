---
title : "Database-Auth"
date : 2026-07-01
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

##  Phase 3 – Database & Authentication (Amazon DynamoDB & Amazon Cognito)

### Objective

Establish a high-performance **data layer** and a secure **identity management system** for the application. This phase separates data persistence and user authentication from the backend business logic, enabling a **stateless serverless architecture** in which AWS Lambda functions remain lightweight and scalable.

### Architecture Overview

- **Amazon DynamoDB (NoSQL Database):**  
  Amazon DynamoDB is used to store application data, including hotel information, flight details, and booking records. Using **On-Demand Capacity Mode**, the database can automatically scale to handle thousands of concurrent requests while maintaining low latency and eliminating database bottlenecks.

- **Amazon Cognito (User Pools):**  
  Amazon Cognito manages the complete user lifecycle, including **user registration**, **sign-in**, **password recovery**, and **authentication**. After a user successfully signs in through the ReactJS frontend, Cognito issues **JSON Web Tokens (JWTs)**. These tokens are included in subsequent requests to **Amazon API Gateway**, where they are used to authenticate and authorize access to protected backend APIs.


