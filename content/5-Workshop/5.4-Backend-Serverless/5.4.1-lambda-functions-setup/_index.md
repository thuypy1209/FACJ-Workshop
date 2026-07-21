---
title : "lambda-functions-setup"
date : 2026-07-01
weight : 1
chapter : false
pre : " <b> 5.4.1 </b> "
---

#### Configure IAM Permissions and Create an AWS Lambda Function

### Objective

Create a **serverless compute environment** to execute the Node.js backend application and configure the required IAM permissions so that the Lambda function can securely interact with **Amazon DynamoDB** and **Amazon SES**.

### Implementation Steps

### Step 1: Create an IAM Role for the Backend

Before creating the Lambda function, an IAM role must be configured to grant the required permissions.

1. Sign in to the **AWS Management Console**, search for **IAM**, navigate to **Roles**, and choose **Create role**.

2. Select **AWS service** as the **Trusted entity type** and **Lambda** as the **Use case**, then click **Next**.

![Select trusted entity](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/setup5.4.1.png)

3. On the **Add permissions** page, attach the following managed policies:

- `AWSLambdaBasicExecutionRole`
- `AmazonDynamoDBFullAccess`
- `AmazonSESFullAccess`

![Add permissions](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/Add5.4.1.png)

4. Click **Next**, enter **Traveloka-Backend-Execution-Role** as the **Role name**, and then click **Create role**.

![Create IAM Role for Backend Lambda](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/create-iam-role.png)

![Create IAM Role for Backend Lambda](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/create-iam-role1.png)


---

### Step 2: Create an AWS Lambda Function

1. Open the **AWS Lambda** service and choose **Create function**.

![Create Lambda Function](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/create-function.png)

2. Select **Author from scratch** and configure the following settings:

- **Function name:** `Traveloka-Booking-Handler`
- **Runtime:** **Node.js 24.x**
- **Architecture:** **arm64**

3. Expand **Change default execution role**, select **Use an existing role**, choose **Traveloka-Backend-Execution-Role** created in Step 1, and then click **Create function**.

![Create AWS Lambda Function](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/create-lambda-function.png)

4. After the Lambda function has been created, navigate to the **Code** tab, open the **Code source** editor, and paste the provided backend source code into the editor.

![Deploy Lambda Source Code](/images/5-Workshop/5.4-Backend-Serverless/5.4.1-lambda-functions-setup/deploy-lambda-code.png)


