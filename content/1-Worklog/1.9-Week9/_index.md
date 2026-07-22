---
title: "Week 9 Worklog"
date: 2026-06-29
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Develop the feature to display the list of tours and to submit a tour-booking request, matching step 5 ("Send tour booking request") and step 6 ("Filter malicious traffic") of the architecture diagram.
* Use `fetch`/Axios calls to retrieve data from API Gateway.
* Handle loading/error/empty states and render the data on the UI.

### Tasks to be carried out this week:
| Day | Task                                                                                                                     | Start Date | Completion Date | Reference Material                        |
| --- | ---------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------ |
| 1   | - Build the Tour List page UI: card layout to display tour information                                                 | 06/29/2026 | 06/29/2026      | -                                           |
| 2   | - Call the GET /tours endpoint from API Gateway to retrieve the tour list data                                         | 06/30/2026 | 06/30/2026      | -                                           |
| 3   | - Handle loading state, error state, and empty-list state on the UI                                                     | 07/01/2026 | 07/01/2026      | -                                           |
| 4   | - Build the "Book this tour" form and submit the booking request (POST /bookings) through the JWT-authenticated Axios instance | 07/02/2026 | 07/02/2026      | -                                           |
| 5   | - **Practice:** add basic filtering/search for the tour list <br> - Test the booking-request flow with various sample data | 07/03/2026 | 07/03/2026      | -                                           |

### Week 9 Achievements:

* Completed the feature to display the tour list on the Frontend, connected end-to-end with API Gateway.
* Built the tour-booking request form and confirmed it flows correctly through WAF and API Gateway.
* Added basic search/filter capability, ready to move on to UI/UX polishing in Week 10.
