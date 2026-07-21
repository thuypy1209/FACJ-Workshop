---
title : "ses-email-service-setup"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.4.3 </b> "
---

#### Configuring Amazon SES (Email Notifications)

### Objective

Verify a sender email address with **Amazon Simple Email Service (Amazon SES)** so that the application can automatically send booking confirmation (E-ticket) emails after a successful reservation.

### Implementation Steps

### Step 1: Verify an Email Identity

1. Sign in to the **AWS Management Console**, search for **Amazon SES**, and navigate to **Identities**.

2. Click **Create identity** and select **Email address** as the **Identity type**.

3. Enter the email address that will be used to send notifications (for example, `noreply.traveloka.clone@gmail.com` or your own testing email address), then click **Create identity**.

![Create an email identity in Amazon SES](/images/5-Workshop/5.4-Backend-Serverless/5.4.3-ses-email-service-setup/verify-ses-email1.png)

![Verify an email identity in Amazon SES](/images/5-Workshop/5.4-Backend-Serverless/5.4.3-ses-email-service-setup/verify-ses-email.png)

4. Open the inbox of the specified email address, locate the verification email sent by AWS, and click the verification link to confirm ownership of the email address.

![Verified email identity](/images/5-Workshop/5.4-Backend-Serverless/5.4.3-ses-email-service-setup/ses-verified-success.png)

---

### Step 2: Integrate the AWS SDK for JavaScript v3

After the sender email has been successfully verified, the **Traveloka-Booking-Handler** Lambda function can use the **`@aws-sdk/client-ses`** package to send emails through the **`SendEmailCommand`** API.

This enables the backend application to automatically deliver booking confirmation emails to users immediately after a successful reservation.

![Lambda function integrated with Amazon SES](/images/5-Workshop/5.4-Backend-Serverless/5.4.3-ses-email-service-setup/lambda-ses-code.png)




