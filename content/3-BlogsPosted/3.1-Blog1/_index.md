---
title: "Blog 1"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---


### Key Takeaways
* **Concept:** A session policy is an inline IAM policy that can be specified when creating or updating a Pod Identity association.
* **Effective permissions:** The resulting permissions are the intersection of the IAM role's permissions and the session policy. Therefore, a session policy can only restrict permissions—it cannot grant additional access.
* **Prevent over-permissioning:** Helps avoid granting excessive permissions when multiple workloads reuse the same IAM role but require different access levels.
* **Supported scenarios:** Works with both same-account and cross-account environments (through IAM role chaining).
* **Optimize IAM quotas:** Significantly reduces the number of IAM roles that need to be managed, helping large Kubernetes clusters stay within IAM service quotas.
* **Easy configuration:** Can be configured through the AWS Management Console, AWS CLI, or AWS SDK when creating an association between a Kubernetes ServiceAccount and an IAM role.

This feature is especially useful when multiple applications share the same IAM role but require different permission boundaries. For example, one pod may only need read access to a specific Amazon S3 bucket, while another pod may only require permission to invoke a limited set of AWS APIs.

![Mini Traveloka Booking Architecture Diagram](/images/3-BlogsPosted/Diagram.png)

> **References:**
> * Architecture diagram tutorial video: [Watch here](https://www.youtube.com/watch?v=l8isyDe-GwY)
> * Original article on AWS Study Group Vietnam: [View the original post](https://www.facebook.com/photo?fbid=2705511749850703&set=gm.2215708592527434&idorvanity=660548818043427&locale=vi_VN)