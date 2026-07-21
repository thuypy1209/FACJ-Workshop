---
title: "Proposal"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---


## Online Hotel Booking Solution Using AWS Serverless Architecture

### 1. Executive Summary
The Serverless Hotel Booking Application is a proof-of-concept project simulating a travel booking platform (MINI Traveloka Booking) built entirely on a 100% AWS Serverless architecture. The system provides a responsive user interface to search and view hotel listings, complete with visual components and promotional banners. By leveraging core AWS services (S3, API Gateway, Lambda, DynamoDB), the project addresses the need for cost optimization and automatic scalability, delivering high performance with a near-zero monthly maintenance budget.

### 2. Problem Statement
### What’s the Problem?
Traditional booking systems rely on renting and maintaining virtual servers (VPS/EC2) that run 24/7. This leads to massive resource waste during off-peak hours. Furthermore, during peak travel seasons, legacy architectures lack flexibility, often resulting in server overloads and downtime.

### The Solution
Implementing an Event-Driven architecture on AWS. The Frontend (ReactJS/Vite) is hosted as static files on Amazon S3. Backend API requests are managed by API Gateway, which triggers Node.js Lambda functions to retrieve data from a NoSQL database (DynamoDB).

### Benefits and Return on Investment
The Pay-as-you-go model combined with the AWS Free Tier completely eliminates fixed server maintenance costs. This solution creates a modern, fast-responding platform, offering an immediate return on investment by cutting infrastructure expenses.

### 3. Solution Architecture
*Core AWS Services Used*

- Amazon S3: Hosts the static source code (HTML, CSS, JS) of the ReactJS Frontend via Static Website Hosting.

- Amazon API Gateway: Acts as the entry point for the RESTful API, handling CORS and request routing.

- AWS Lambda: Executes business logic using Node.js (e.g., the getHotelsList function utilizing AWS SDK v3 to fetch data).

- Amazon DynamoDB: An on-demand NoSQL database storing hotel listings, prices, and location details.

- Amazon CloudWatch & SNS: Monitors system logs and automatically triggers email alerts when API Gateway encounters 5xx errors.
### 4. Technical Implementation
The project is divided into two independent modules for easier management and deployment:

    * Backend (AWS Serverless): Provisioning the Hotels table in DynamoDB. Writing logic functions using  Node.js and AWS SDK v3. Integrating API Gateway with Lambda and setting up monitoring alarms via CloudWatch and SNS.

    * Frontend (ReactJS + Vite): Building a component-based UI (Header, Hero, HotelList). Utilizing CSS Flexbox for responsive layouts. Using the useEffect hook and the fetch API to retrieve data from AWS API Gateway and render it on the screen. Finally, building the project and deploying it to S3.
### 5. Timeline & Milestones
The project was developed and finalized within the internship timeframe:

- Phase 1 (Design & Setup): Architecture analysis, database design on DynamoDB, writing AWS Lambda logic,   and configuring API Gateway.

-Phase 2 (Frontend Development): Constructing the ReactJS layout, applying Flexbox for the navigation bar, and designing the Hero Section.

- Phase 3 (Integration & Testing): Fetching data from the AWS Backend to the Frontend, parsing JSON responses, handling errors, and monitoring logs via CloudWatch.

- Phase 4 (Deployment - Go-Live): Building the application, configuring Static Website Hosting on Amazon S3, and handing over the source code.

### 6. Budget Estimation
The project is designed to operate entirely within the AWS Free Tier limits:

### Infrastructure Costs
- AWS Lambda: 1 million free requests/month -> $0.
- Amazon DynamoDB: 25 GB storage, 25 RCU/WCU free -> $0.
- Amazon API Gateway: Free for the first 1 million API calls/month (for the first 12 months) -> $0.
- Amazon S3 & CloudWatch: Well within the basic free tier usage -> $0.

Total Estimated Monthly Cost: ~ 0.00 USD..

### 7. Risk Assessment
* Lambda Cold Starts:
* Risk: The initial request may take a few extra seconds to respond.
       - Mitigation: Optimizing the Node.js source code by only importing necessary modules from the AWS SDK v3 to accelerate initialization.

* Unexpected Budget Overruns:
* Risk: A sudden traffic spike could generate costs beyond the Free Tier.

       - Mitigation: Setting up an AWS Billing Alarm to automatically send an email alert if costs exceed $2.


### 8. Expected Outcomes
A smoothly operating hotel booking frontend mirroring the reference design (Traveloka), backed by a production-ready cloud database. The project successfully demonstrates the superiority of Cloud-Native architectures over traditional solutions in terms of scalability and cost-efficiency.