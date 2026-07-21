---
title: "Week 3 Worklog"
date: 2026-05-18
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Design the NoSQL database using Amazon DynamoDB for the online tour booking system.
* Define the table structure, partition keys, sort keys and access patterns for Users, Tours and Bookings.
* Seed sample data and set up basic queries to retrieve data, in line with the data flow shown in the architecture diagram (step 9: "Save/search tour information").

### Tasks to be carried out this week:
| Day | Task                                                                                                                       | Start Date | Completion Date | Reference Material                        |
| --- | ----------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------ |
| 1   | - Study DynamoDB fundamentals: partition key, sort key, Global Secondary Index (GSI)                                     | 05/18/2026 | 05/18/2026      | <https://cloudjourney.awsstudygroup.com/>  |
| 2   | - Design the table structure for Users, Tours, and Bookings, based on the system's access patterns                       | 05/19/2026 | 05/19/2026      | -                                           |
| 3   | - Create the DynamoDB tables and configure the primary key / GSI for each table                                          | 05/20/2026 | 05/20/2026      | -                                           |
| 4   | - Seed sample data for Users, Tours and Bookings <br> - **Practice:** insert, update and delete items via AWS Console     | 05/21/2026 | 05/21/2026      | -                                           |
| 5   | - **Practice:** set up basic queries (Query/Scan) to search tour information by different access patterns <br> - Review with mentor | 05/22/2026 | 05/22/2026      | -                                           |

### Week 3 Achievements:

* Completed the NoSQL database design with DynamoDB for the Users, Tours, and Bookings tables.
* Understood how to choose an effective partition key / sort key based on the system's access patterns.
* Successfully seeded sample data and validated it with basic Query/Scan operations.
* Built a solid data foundation that matches step 9 of the architecture diagram ("save/search tour information"), ready to move on to the authentication flow with Cognito in Week 4.
