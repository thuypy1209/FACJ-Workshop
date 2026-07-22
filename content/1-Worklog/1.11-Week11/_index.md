---
title: "Week 11 Worklog"
date: 2026-07-13
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* Perform full end-to-end testing of the system, covering all 11 steps in the architecture diagram: Route 53 → WAF → CloudFront → S3 Frontend, sign-in via Cognito, and the booking flow through WAF → API Gateway → Cognito → Lambda → S3 Storage/DynamoDB → CloudWatch.
* Review and fix bugs found across the various features.
* Optimize performance, improve the stability of the system, and verify that CloudWatch correctly captures logs and error alerts (steps 10–11).

### Tasks to be carried out this week:
| Day | Task                                                                                                                    | Start Date | Completion Date | Reference Material                        |
| --- | -------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------ |
| 1   | - Build a test-case checklist covering the full flow: DNS resolution, web delivery, sign-up, login, view tour list, booking | 07/13/2026 | 07/13/2026      | -                                           |
| 2   | - Test Route 53/WAF/CloudFront (steps 1–3) and the authentication flow (sign-up/login/expired token, steps 4 and 7)   | 07/14/2026 | 07/14/2026      | <https://docs.aws.amazon.com/AmazonCloudFront>                                           |
| 3   | - Test the tour-booking flow end-to-end (steps 5–9) and verify data consistency in S3 Storage and DynamoDB            | 07/15/2026 | 07/15/2026      | -                                           |
| 4   | - Review and fix bugs found during testing (UI, API, data)                                                             | 07/16/2026 | 07/16/2026      | -                                           |
| 5   | - Optimize Lambda cold-start time, and verify that CloudWatch correctly logs activity and raises alerts on errors (steps 10–11) | 07/17/2026 | 07/17/2026      | -                                           |

### Week 11 Achievements:

* Completed full end-to-end testing across all 11 steps of the architecture diagram, from the Edge layer (Route 53, WAF, CloudFront, S3 Frontend) to the Serverless backend (API Gateway, Cognito, Lambda, S3 Storage, DynamoDB) and monitoring (CloudWatch).
* Fixed the bugs found during testing, improving the overall stability of the system.
* Made initial performance optimizations for the Lambda functions based on CloudWatch data.
* Confirmed that CloudWatch correctly logs activity and error alerts, preparing a stable system ready for the internship report and technical documentation in Week 12.
