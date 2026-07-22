---
title: "Week 6 Worklog"
date: 2026-06-08
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Build Amazon API Gateway and define the REST endpoints for the tour-booking system, matching step 6 of the architecture diagram.
* Configure a WAF rule set in front of the API to filter malicious traffic before it reaches API Gateway, matching step 5 ("Filter malicious traffic").
* Secure the endpoints using a Cognito Authorizer, and configure CORS so the Frontend can call the API without being blocked by the browser.

### Tasks to be carried out this week:
| Day | Task                                                                                                                            | Start Date | Completion Date | Reference Material                        |
| --- | -------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------ |
| 1   | - Study REST API concepts in API Gateway: resource, method, integration, stage                                                   | 06/08/2026 | 06/08/2026      | <https://docs.aws.amazon.com/apigateway/>  |
| 2   | - Create the API Gateway and define endpoints for Tours and Bookings (GET, POST, PUT, DELETE)                                    | 06/09/2026 | 06/09/2026      | -                                           |
| 3   | - Integrate each endpoint with the corresponding Lambda function created in Week 5                                               | 06/10/2026 | 06/10/2026      | <https://docs.aws.amazon.com/apigateway/>                                           |
| 4   | - Configure a WAF Web ACL in front of API Gateway to filter malicious traffic (step 5), and configure CORS for the endpoints     | 06/11/2026 | 06/11/2026      | <https://docs.aws.amazon.com/waf>                                           |
| 5   | - Set up a Cognito Authorizer to secure the endpoints <br> - **Practice:** test the endpoints with Postman using a valid/invalid token | 06/12/2026 | 06/12/2026      | <https://docs.aws.amazon.com/apigateway/>                                           |

### Week 6 Achievements:

* Completed the API Gateway with full REST endpoints for Tours and Bookings, matching step 6 of the architecture diagram.
* Configured a WAF Web ACL to filter malicious traffic before it reaches API Gateway (step 5), and successfully configured CORS so the Frontend can call the API without browser errors.
* Secured all endpoints with a Cognito Authorizer, ensuring only valid tokens can access the API (step 7).
* Verified the endpoints end-to-end with Postman, ready for Frontend integration starting Week 7.
