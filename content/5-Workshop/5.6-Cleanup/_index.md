---
title : "Clean up"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---
## Resource Cleanup

### Objective

Remove all AWS resources created during the deployment of the **MINI Traveloka Booking** application to prevent unnecessary charges from being incurred on your AWS account.

### Cleanup Steps

### Step 1: Delete the Frontend and Amazon S3 Bucket

1. Open the **Amazon S3** service and locate the frontend bucket (for example, `traveloka-clone-frontend`).

2. Select the bucket and click **Empty** to remove all static files stored inside it.

3. After the bucket is empty, click **Delete** to permanently remove the Amazon S3 bucket.

![Delete Amazon S3 Bucket](/images/5-Workshop/5.6-Cleanup/delete-s3.png)

---

### Step 2: Delete the Amazon CloudFront Distribution

1. Open the **Amazon CloudFront** service and select the distribution associated with the project.

2. First, choose **Disable** and wait until the distribution status changes to **Disabled**.

3. Once the distribution has been disabled, click **Delete** to permanently remove it.

![Delete Amazon CloudFront Distribution](/images/5-Workshop/5.6-Cleanup/delete-cloudfront.png)

---

### Step 3: Remove the Serverless Backend (Amazon API Gateway & AWS Lambda)

1. Open **Amazon API Gateway**, select the **Traveloka-Core-API**, open the **Actions** menu, and choose **Delete API**.

2. Open **AWS Lambda**, select the **Traveloka-Booking-Handler** function, open the **Actions** menu, and choose **Delete**.

![Delete Amazon API Gateway](/images/5-Workshop/5.6-Cleanup/delete-API.png)

![Delete AWS Lambda Function](/images/5-Workshop/5.6-Cleanup/delete-Lambda.png)

---

### Step 4: Delete the Database and Authentication Resources (Amazon DynamoDB & Amazon Cognito)

1. Open **Amazon DynamoDB**, navigate to **Tables**, select the **Traveloka-Bookings** table, and click **Delete table**.

2. Open **Amazon Cognito**, navigate to **User pools**, select the **Traveloka-Users** user pool, and click **Delete user pool**.

![Delete Amazon DynamoDB Table and Amazon Cognito User Pool](/images/5-Workshop/5.6-Cleanup/delete-db-auth.png)