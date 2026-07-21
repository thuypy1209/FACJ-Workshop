---
title : "Backend-Serverless"
date : 2026-07-01
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

#### Overview
## Phase 2 – Building the Serverless Backend Core (AWS Lambda & Amazon API Gateway)

### Objective

Build the core **business logic layer** of the **MINI Traveloka Booking** application using a fully **serverless architecture**. This phase establishes the foundation for an application that can automatically scale in response to sudden increases in traffic—such as during peak travel seasons—while optimizing operational costs through the **pay-as-you-go** pricing model, where charges are incurred only for actual compute time.

### Architecture Overview

The backend is built using three fully managed AWS services:

- **Amazon API Gateway (REST API):**  
  Acts as the single entry point (reverse proxy) for all HTTP requests from the ReactJS frontend. It is responsible for request routing, traffic management (throttling), and will later be integrated with **AWS WAF** to protect the application from common web attacks.

- **AWS Lambda (Node.js):**  
  Executes the application's backend business logic, such as retrieving hotel information, processing bookings, and handling user requests. Lambda functions operate using an **event-driven** execution model and are invoked directly by Amazon API Gateway.

- **Amazon Simple Email Service (Amazon SES):**  
  Integrated with the booking-related Lambda functions to automatically send confirmation emails containing booking details to customers after a successful reservation.

In this phase, you will create and configure **AWS Lambda** functions, set up **Amazon API Gateway** to expose RESTful APIs, and integrate **Amazon SES** for automated email notifications.



