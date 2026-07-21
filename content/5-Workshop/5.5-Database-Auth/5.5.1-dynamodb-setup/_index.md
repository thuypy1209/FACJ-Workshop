---
title : "dynamodb-setup"
date : 2026-07-01
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

#### Creating a NoSQL Database with Amazon DynamoDB

### Objective

Create **serverless NoSQL database tables** to store and retrieve booking data with **single-digit millisecond latency**.

### Implementation Steps

### Step 1: Create a DynamoDB Table

1. Sign in to the **AWS Management Console**, search for **Amazon DynamoDB**, navigate to **Tables**, and choose **Create table**.

2. Configure the table with the following settings:

- **Table name:** `Traveloka-Bookings`
- **Partition key:** `bookingId`
- **Data type:** **String**

The **Partition Key** uniquely identifies each booking record and serves as the primary key for efficient data retrieval.

![Create DynamoDB Table](/images/5-Workshop/5.5-Database-Auth/5.5.1-dynamodb-setup/create-dynamodb-table1.png)

![Create DynamoDB Table](/images/5-Workshop/5.5-Database-Auth/5.5.1-dynamodb-setup/create-dynamodb-table.png)

---

### Step 2: Configure Capacity Settings

1. Under **Table settings**, select **Customize settings** instead of **Default settings**.

2. Scroll to the **Read/Write Capacity Settings** section and choose **On-demand** as the capacity mode.

3. Scroll to the bottom of the page and click **Create table**.

4. Repeat the same process to create additional tables required by the application, such as:

- `Traveloka-Flights`
- `Traveloka-Hotels`

![Configure On-Demand Capacity Mode](/images/5-Workshop/5.5-Database-Auth/5.5.1-dynamodb-setup/dynamodb-capacity-settings.png)