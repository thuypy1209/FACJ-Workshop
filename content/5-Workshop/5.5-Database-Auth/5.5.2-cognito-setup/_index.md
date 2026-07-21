---
title : "cognito-setup"
date : 2026-07-01
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

#### Configuring User Authentication with Amazon Cognito

### Objective

Set up a secure **authentication system** using **Amazon Cognito** without managing user passwords manually. Amazon Cognito provides built-in user authentication, account management, and automatic issuance of **JSON Web Tokens (JWTs)**.

### Implementation Steps

### Step 1: Create a Cognito User Pool

1. Open the **Amazon Cognito** service and select **Create user pool**.

2. Under **Configure sign-in experience**:

- Select **Email** as the sign-in option so users authenticate with their email addresses instead of usernames.
- Click **Next**.

![Create User Pool](/images/5-Workshop/5.5-Database-Auth/5.5.2-cognito-setup/cognito-signin-experience1.png)

![Configure Sign-in Experience](/images/5-Workshop/5.5-Database-Auth/5.5.2-cognito-setup/cognito-signin-experience2.png)

---

### Step 2: Configure Security and Sign-up Settings

1. Under **Configure security requirements**:

- Keep the default **Password Policy** recommended by AWS.
- Choose **No MFA** to simplify testing, or select **Optional MFA** if additional security is required.

2. Under **Configure sign-up experience**:

- Select the required user attributes that must be provided during registration (for example, `name` and `phone_number`).
- Click **Next**.

![Configure User Attributes](/images/5-Workshop/5.5-Database-Auth/5.5.2-cognito-setup/cognito-signup-attributes.png)

---

### Step 3: Configure the Application (App Client)

1. Under **Integrate your app**, configure the following settings:

- **User pool name:** `Traveloka-Users`
- **App client type:** **Public client**
- **App client name:** `Traveloka-React-Frontend`

> **Important:** Do **not** enable **Generate client secret**.  
> Because the ReactJS application is a **Single Page Application (SPA)** running in the browser, embedding a client secret in frontend code would expose sensitive credentials and create a security risk.

2. Click **Next**, review all configuration settings, and then select **Create user pool**.

![Create Cognito App Client](/images/5-Workshop/5.5-Database-Auth/5.5.2-cognito-setup/cognito-app-client.png)