---
title : "frontend-hosting"
date : 2026-07-01
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

This phase focuses on deploying the **ReactJS frontend** of the **MINI Traveloka Booking** application to the AWS cloud. We will leverage AWS serverless services to optimize website performance, ensure high availability, and provide strong security for static resources.

### 1. Prerequisites

Before starting this phase, ensure that the following requirements have been completed:

- The environment setup described in **Section 5.2** has been completed.
- **Node.js** is installed on the local machine, and the **AWS CLI** has been configured successfully with your AWS account.
- The ReactJS frontend application runs correctly in the local development environment and is ready for production deployment.

### 2. Architecture Overview

The frontend architecture follows a **Static Website Hosting** model combined with a **Content Delivery Network (CDN)**, eliminating the need to manage traditional web servers.

- **Amazon S3:** An S3 bucket is used to store all static assets generated during the build process, including HTML, JavaScript, CSS, and image files. The bucket is configured as **private**, preventing any direct public access from the Internet.

- **Amazon CloudFront:** A global **Content Delivery Network (CDN)** that retrieves content from the Amazon S3 bucket and caches it at geographically distributed **Edge Locations**. This significantly reduces latency and improves page load performance for users worldwide.

- **Origin Access Control (OAC):** An advanced AWS security mechanism that ensures all requests for static content are routed through Amazon CloudFront. By preventing direct access to the Amazon S3 bucket, OAC provides an additional layer of protection for the application's static resources.