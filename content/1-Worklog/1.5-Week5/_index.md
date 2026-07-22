---
title: "Week 5 Worklog"
date: 2026-06-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Develop AWS Lambda functions (Node.js) that implement step 8 of the architecture diagram ("Run data-processing logic") for the tour-booking business logic.
* Implement JWT Token verification at the Backend layer to ensure security, in line with step 7 ("Verify identity").
* Handle saving booking images/documents to S3 Storage and tour data to DynamoDB (step 9), and prepare the logging groundwork for step 10.

### Tasks to be carried out this week:
| Day | Task                                                                                                                          | Start Date | Completion Date | Reference Material                        |
| --- | ---------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------ |
| 1   | - Set up the Node.js Lambda project structure, install the AWS SDK, and configure environment variables                      | 06/01/2026 | 06/01/2026      | <https://docs.aws.amazon.com/lambda/>  |
| 2   | - Develop Lambda functions to create and retrieve Tours/Bookings data (Create, Read)                                          | 06/02/2026 | 06/02/2026      | -                                           |
| 3   | - Develop Lambda functions to update and delete Tours/Bookings data (Update, Delete)                                         | 06/03/2026 | 06/03/2026      | -                                           |
| 4   | - Implement JWT Token verification logic in the Lambda functions before processing requests <br> - Implement uploading booking images/documents to S3 Storage | 06/04/2026 | 06/04/2026      | <https://docs.aws.amazon.com/lambda/>                                           |
| 5   | - **Practice:** test each Lambda function individually via the AWS Console test event <br> - Fix bugs found during testing   | 06/05/2026 | 06/05/2026      | -                                           |

### Week 5 Achievements:

* Completed the Lambda functions (Node.js) handling the CRUD logic for Tours and Bookings — matching step 8 of the architecture diagram.
* Successfully implemented JWT Token verification at the Backend layer, ensuring only authenticated requests are processed.
* Implemented saving booking images/documents to S3 Storage and tour records to DynamoDB, matching step 9.
* Independently tested each Lambda function and confirmed it worked correctly with sample data, preparing the compute layer needed to build API Gateway endpoints in Week 6.
