---
title: "Week 4 Worklog"
date: 2026-05-25
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* Configure the Amazon Cognito User Pool and Identity Pool used for both step 4 ("Sign in / Sign up") and step 7 ("Verify identity") of the architecture diagram.
* Set up the user authentication flow (sign-up, sign-in, confirm account).
* Configure JSON Web Token (JWT) issuance for authenticated users so it can later be verified by Lambda before processing a booking request.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                | Start Date | Completion Date | Reference Material                        |
| --- | -------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------ |
| 1   | - Study Amazon Cognito concepts: User Pool, Identity Pool, App Client                                                              | 05/25/2026 | 05/25/2026      | <https://cloudjourney.awsstudygroup.com/>  |
| 2   | - Create and configure the Cognito User Pool: password policy, required attributes, verification method                          | 05/26/2026 | 05/26/2026      | -                                           |
| 3   | - Create and configure the Cognito Identity Pool, linked to the User Pool                                                          | 05/27/2026 | 05/27/2026      | -                                          |
| 4   | - **Practice:** implement sign-up, confirm account, and sign-in flows via AWS Console / CLI                                        | 05/28/2026 | 05/28/2026      | -                                          |
| 5   | - Configure JWT issuance (ID Token, Access Token, Refresh Token) after successful sign-in <br> - Test the token payload           | 05/29/2026 | 05/29/2026      | -                                          |

### Week 4 Achievements:

* Successfully configured the Cognito User Pool and Identity Pool for the system.
* Built a complete sign-up / confirm account / sign-in flow, matching step 4 of the architecture diagram.
* Understood how Cognito issues JWTs (ID Token, Access Token, Refresh Token) and what each token is used for during the identity-verification step (step 7).

