---
title : "apigw-rest-integration"
date : 2026-07-01
weight : 2
chapter : false
pre : " <b> 5.4.2 </b> "
---

#### Building a REST API with Amazon API Gateway

### Objective

Create a secure **REST API endpoint** that routes HTTP requests from the ReactJS frontend to the AWS Lambda backend.

### Implementation Steps

### Step 1: Create a REST API

1. Navigate to the **Amazon API Gateway** service, scroll to the **REST API** section (do **not** choose **HTTP API**), and click **Build**.

2. Select **New API**, enter **Traveloka-Core-API** as the API name, keep the **Endpoint Type** set to **Regional**, and then click **Create API**.

![Create REST API](/images/5-Workshop/5.4-Backend-Serverless/5.4.2-apigw-rest-integration/create-rest-api.png)

---

### Step 2: Create a Resource and Method

1. From the **Actions** menu (or click **Create resource**), create a new resource named **bookings**.

2. Select the newly created **/bookings** resource, click **Create Method**, choose **POST**, and confirm the creation.

![Create Resource and POST Method](/images/5-Workshop/5.4-Backend-Serverless/5.4.2-apigw-rest-integration/create-resource-method.png)

---

### Step 3: Configure Lambda Proxy Integration

1. On the **POST Method** configuration page, select **Lambda Function** as the **Integration type**.

2. Enable the **Use Lambda Proxy integration** option.

3. In the **Lambda Function** field, select **Traveloka-Booking-Handler**, then click **Save**. When prompted, click **OK** to allow Amazon API Gateway to invoke the Lambda function.

![Configure Lambda Proxy Integration](/images/5-Workshop/5.4-Backend-Serverless/5.4.2-apigw-rest-integration/lambda-proxy-integration.png)

---

### Step 4: Deploy the API

1. Select the **/bookings** resource, click **Enable CORS**, enable the **POST** and **OPTIONS** methods, and then click **Save**.

2. Click **Deploy API** at the top of the page.

3. Choose **[New Stage]** as the deployment stage, enter **prod** as the **Stage name**, and click **Deploy**.

4. Copy the generated **Invoke URL** and update your frontend application's **`.env`** file with this endpoint so the ReactJS application can communicate with the backend API.

![Deploy API Gateway](/images/5-Workshop/5.4-Backend-Serverless/5.4.2-apigw-rest-integration/deploy-api.png)