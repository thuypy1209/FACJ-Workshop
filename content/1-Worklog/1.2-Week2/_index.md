---
title: "Week 2 Worklog"
date: 2026-05-11
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* Draw and document a complete System Architecture Diagram for the online tour booking system.
* Design the Cloud infrastructure in two parts: **Edge Security & Delivery** (Route 53, WAF, CloudFront, S3 Frontend) and **Region - Serverless Architecture** (WAF, API Gateway, Cognito, Lambda, S3 Storage, DynamoDB, CloudWatch).
* Clearly describe the system's processing flow, from the moment a user accesses the website to when a tour-booking request is processed and stored.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                     | Start Date | Completion Date | Reference Material                        |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------ |
| 1   | - Study AWS architecture-diagram conventions and standard AWS Architecture Icons                                                                        | 05/11/2026 | 05/11/2026      | <https://cloudjourney.awsstudygroup.com/>  |
| 2   | - Design the **Edge Security & Delivery** block: Route 53 for DNS resolution, WAF for security checks, CloudFront for content delivery, S3 Frontend for static web hosting | 05/12/2026 | 05/12/2026      | -                                           |
| 3   | - Design the **Region (Serverless Architecture)** block: WAF to filter malicious traffic, API Gateway to receive requests, Cognito to authenticate users | 05/13/2026 | 05/13/2026      | -                                           |
| 4   | - Design the compute layer with Lambda and the data layer with S3 Storage (booking images/documents) and DynamoDB (store/search tour information)      | 05/14/2026 | 05/14/2026      | -                                           |
| 5   | - Design the monitoring flow with CloudWatch (activity logging, system error tracking) <br> - Finalize the diagram with the full 11-step flow and review it with the mentor | 05/15/2026 | 05/15/2026      | -                                           |

### Week 2 Achievements:

* Completed a full system architecture diagram made up of two main blocks: **Edge Security & Delivery** and **Region (Serverless Architecture)**.
* Clearly documented an 11-step processing flow:
  1. The user looks up the website address via Route 53 (DNS).
  2. WAF performs a security check to allow safe access.
  3. CloudFront delivers the web interface from S3 Frontend.
  4. The user signs in / signs up via Cognito.
  5. The user submits a tour-booking request, which passes through WAF to filter malicious traffic.
  6. API Gateway receives and routes the request.
  7. The user's identity is verified via Cognito.
  8. API Gateway invokes Lambda to run the data-processing logic.
  9. Lambda stores booking images/documents in S3 Storage, and saves/searches tour information in DynamoDB.
  10. Lambda records the activity log.
  11. CloudWatch monitors the system and raises alerts on errors.
* Clearly defined the role of each AWS service in the architecture: Route 53 for DNS, WAF for edge security, CloudFront + S3 Frontend for web delivery, API Gateway for the API layer, Cognito for authentication, Lambda for business logic, S3 Storage/DynamoDB for data storage, and CloudWatch for monitoring/logging.
* Got the mentor's feedback and approval to proceed with the detailed database design in Week 3.
![Architecture Diagram](images/Diagram.png)
