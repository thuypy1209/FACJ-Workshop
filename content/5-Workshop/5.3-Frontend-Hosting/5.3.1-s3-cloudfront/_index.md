---
title : "s3-cloudfront"
date : 2026-07-01 
weight : 1
chapter : false
pre : " <b> 5.3.1 </b> "
---

### Objective: Create an Amazon S3 Bucket and Configure an Amazon CloudFront Distribution

#### Step 1: Create an Amazon S3 Bucket

Navigate to the **Amazon S3** service and select **Create bucket**. Enter a unique bucket name (for example, `traveloka-clone-frontend`) and keep the default setting **Block all public access** enabled.

![Create an Amazon S3 bucket](/images/5-Workshop/5.3-frontend-hosting/5.3.1-s3-cloudfront/s3.png)

#### Step 2: Upload the Frontend Build Files

Upload the entire **`dist`** folder (generated after building the ReactJS application) to the Amazon S3 bucket.

![Upload frontend build files](/images/5-Workshop/5.3-frontend-hosting/5.3.1-s3-cloudfront/upload.png)

#### Step 3: Create an Amazon CloudFront Distribution

Navigate to **Amazon CloudFront** and select **Create distribution**. Complete the configuration by following the steps shown below.

**Step 1**

![CloudFront configuration - Step 1](/images/5-Workshop/5.3-frontend-hosting/5.3.1-s3-cloudfront/setup1.png)

**Step 2**

![CloudFront configuration - Step 2](/images/5-Workshop/5.3-frontend-hosting/5.3.1-s3-cloudfront/setup2.png)

**Step 3**

![CloudFront configuration - Step 3](/images/5-Workshop/5.3-frontend-hosting/5.3.1-s3-cloudfront/setup3.png)

**Step 4**

![CloudFront configuration - Step 4](/images/5-Workshop/5.3-frontend-hosting/5.3.1-s3-cloudfront/setup4.png)

#### Step 4: Select the Origin

In the **Origin domain** section, select the Amazon S3 bucket that was created in Step 1.

#### Step 5: Configure Origin Access Control (OAC)

Under **Origin access**, choose **Origin access control settings (recommended)** and click **Create control setting** to create a new **Origin Access Control (OAC)**. This ensures that the S3 bucket can only be accessed securely through Amazon CloudFront.

#### Step 6: Create the Distribution

Click **Create distribution** to deploy the CloudFront distribution.

After the distribution has been created, Amazon CloudFront will generate a **Bucket Policy**. Copy the generated policy and paste it into **Permissions → Bucket Policy** of the corresponding Amazon S3 bucket. This grants CloudFront permission to securely access the bucket while keeping the bucket private.

![CloudFront distribution domain name](/images/5-Workshop/5.3-frontend-hosting/5.3.1-s3-cloudfront/Distribution.png)