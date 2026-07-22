---
title: "Week 8 Worklog"
date: 2026-06-22
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Develop the login/register feature on the ReactJS Frontend, connected to the Cognito authentication API — matching step 4 of the architecture diagram.
* Store the JWT Token securely after a successful login.
* Attach the JWT Token to the Request Header for subsequent authenticated API calls (used for identity verification in step 7).

### Tasks to be carried out this week:
| Day | Task                                                                                                                  | Start Date | Completion Date | Reference Material                        |
| --- | ---------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------ |
| 1   | - Build the Login / Register page UI: email/password form and validation                                             | 06/22/2026 | 06/22/2026      | -                                           |
| 2   | - Connect the login/register form to the Cognito authentication API via API Gateway                                  | 06/23/2026 | 06/23/2026      | <https://docs.amplify.aws/javascript/build-a-backend/auth/>                                           |
| 3   | - Store the JWT Token (Access Token, Refresh Token) after a successful login                                          | 06/24/2026 | 06/24/2026      | -                                           |
| 4   | - Configure the Axios interceptor to automatically attach the JWT Token to the Authorization Header of every request | 06/25/2026 | 06/25/2026      | <https://axios.rest/pages/advanced/interceptors>                                           |
| 5   | - **Practice:** test the full login flow, handle login errors and expired token cases                                | 06/26/2026 | 06/26/2026      | -                                           |

### Week 8 Achievements:

* Completed the login/register feature on the Frontend, connected end-to-end with Cognito.
* Successfully stored and managed the JWT Token after login.
* Configured the Axios interceptor to automatically attach the token to every API request, supporting the identity-verification step  when a booking request is submitted.
* Handled basic error cases (wrong password, expired token), preparing to build tour-booking data-display features .
