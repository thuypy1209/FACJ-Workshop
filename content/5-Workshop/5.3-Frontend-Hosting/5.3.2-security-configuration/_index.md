---
title : "oac-security-configuration"
date : 2026-07-01 
weight : 2
chapter : false
pre : " <b> 5.3.2 </b> "
---

### Objective: Verify That the Website Is Accessible Through Amazon CloudFront

Follow the steps below to ensure that the frontend has been deployed successfully and is being served through the CloudFront CDN.

#### Step 1

Open the **Amazon CloudFront** console and copy the **Distribution domain name** (for example, `d123456789.cloudfront.net`).

![Amazon CloudFront Distribution](/images/5-Workshop/5.3-frontend-hosting/5.3.2-security-configuration/CloudFront.png)

#### Step 2

Paste the distribution URL into your web browser and verify that the **MINI Traveloka Booking** website loads successfully.

![Access the CloudFront URL](/images/5-Workshop/5.3-frontend-hosting/5.3.2-security-configuration/URL.png)

#### Step 3

Verify content caching by refreshing the page several times (for example, by pressing **F5**). If Amazon CloudFront is configured correctly, the static assets should load faster than if they were accessed directly from Amazon S3.

#### Step 4

Verify the security configuration by attempting to access an object directly through its Amazon S3 URL. Since **Block Public Access** is enabled and **Origin Access Control (OAC)** is configured, the browser should return an **Access Denied** error. This confirms that the S3 bucket is protected and can only be accessed through Amazon CloudFront.

### Why Is This Configuration Important?

Amazon CloudFront acts as a **Content Delivery Network (CDN)** by caching static website assets at edge locations around the world. This significantly reduces latency, improves page load performance, and provides a better user experience for visitors accessing the **MINI Traveloka Booking** application.

Using **Origin Access Control (OAC)** also enhances security by preventing users from bypassing CloudFront and accessing the Amazon S3 bucket directly. As a result, all requests for static content are securely routed through CloudFront while the S3 bucket remains private.













