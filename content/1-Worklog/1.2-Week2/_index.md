---
title: "Week 2 Worklog"
date: "2025-09-15"
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---


### Week 2 Objectives:

* Complete Module 3 & 4
* Help team members get up to speed
* Discuss workshop ideas
* Do first optional research: AWS Well Architected Framework
* Check out AWS Advanced Networking - Specialty Study Guide
* Check out AWS Microsoft Workload
* Check out AWS Skill Builder

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Finished restricting an **IAM** from creating **EC2** from another region. (**Restricting Service Usage by AWS Region**) <br> - Learnt how to **analyze compute requirements** and chose an appropriate **instance family** for it. <br> - Launched instances within the **same and different families** to test the **IAM EC2 Policy** <br> - Learnt how to **restrict** certain **EBS volumes** and the general information about **EBS volume types** <br> - Tested the policy by launching an **EC2** with an **EBS volume type** that isn't permitted. <br> - Learnt how to **limit access to resources** by only **allowing access to certain IPs** <br> - Learnt how to limit permission to **delete resources by time period** | 08/11/2025 | 08/11/2025      | [Amazon EC2 instance types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html) <br><br> [Introduction to Amazon EC2](https://000004.awsstudygroup.com/) <br><br> [Amazon EC2 instance types](https://aws.amazon.com/ec2/instance-types/?nc1=h_ls) <br><br> [IAM policy testing with the IAM policy simulator](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html) <br><br> [IAM Policy Simulator](https://policysim.aws.amazon.com/home/index.jsp?#)
| 3   |- Created an **EC2** and **SSH'ed into it** using **MobaXterm** and created an **S3 bucket** <br> - Upload files using an **accesskey/secretaccesskey**: <br>&emsp; + Generated an **IAM user with an access key** <br>&emsp; + **Uploaded files** to the **S3 bucket** <br> - Upload files with **eligible roles** on **EC2**: <br>&emsp; + Created a **role** for the **EC2** <br>&emsp; + **Uploaded files** to the **S3 bucket** via **EC2 role**.| 08/12/2025 | 08/12/2025      | [Granting authorization for an application to access AWS services with an IAM role.](https://000048.awsstudygroup.com/)
| 4   | <br> - Looked into **Cloud 9** IDE, on what it is about (Can't use it because I don't have access to it.)![Cloud9](/images/cloud9.png) - Information about **S3**: <br>&emsp; + Know the difference between **S3 Bucket** and **S3 Object** <br>&emsp; + Know about the **storage classes** and others. <br> - **Create an S3 bucket** and **host a static website**: <br>&emsp; + Created an **S3 bucket** and **uploaded the data** <br>&emsp; + Enabled **Static website hosting** and unchecked **Block all public access** <br>&emsp; + Changed the **bucket permission settings** and made **objects public using ACL** <br>&emsp; + Successfully accessed the **static website** | 08/13/2025 | 08/13/2025 | [How to migrate from AWS Cloud9 to AWS IDE Toolkits or AWS CloudShell](https://aws.amazon.com/blogs/devops/how-to-migrate-from-aws-cloud9-to-aws-ide-toolkits-or-aws-cloudshell/) <br><br> [Get started with AWS Cloud 9](https://000049.awsstudygroup.com/) <br><br> [Starting with Amazon S3](https://000057.awsstudygroup.com/) |
| 5   | - Accelerate Static Websites with **Cloudfront**: <br>&emsp; + **Blocked** all **public access** <br>&emsp; + Created and configured a **Cloudfront distribution** (The new UI doesn't let you choose the **Default root object** and **Price class** on creating, to change this, select your **distribution**, click on the **General** tab, find **Settings** and click **Edit**, then you can see the missing options there.) <br>&emsp; + **Successfully** accessed the **website** <br>&emsp; + **Checked** the **loading time** by inspecting the website, the flow would be: <br> **Inspect -> Network -> Refresh page** <br> You can see the time at the far right of the **Cloudfront document** (for me it's 29ms), when you click on the **Cloudfront document**, you can see which PoP the website is being returned from ![PoP location](/images/pop_location.png) It's **HKG1-P2** (Hong Kong) for me <br> - Bucket Versioning: <br>&emsp; + Read and enabled **Bucket Versioning** <br>&emsp; + Tested it by **editing** the **index.html** file and uploading it onto the **S3 bucket** and checking **Cloudfront** <br> - Moving objects from an S3 to another: <br>&emsp; + Created a new **S3 Bucket** <br>&emsp; + Calculated the **size** of the **entire bucket** to compare **after moving** <br>&emsp; + **Successfully moved** the bucket <br>&emsp; + Calculated the **size** to make sure we didn't lose any data <br> Out of curiosity, I tried changing the **Origin domain** of the **Cloudfront distribution**, added a **Bucket policy** in permissions and enabled **Static website hosting** on the new **S3 Bucket** and it works wonder! <br> - Successfully replicated **objects** inside of a **S3 Bucket** to another **region**. | 08/14/2025 | 08/14/2025 | [Starting with Amazon S3](https://000057.awsstudygroup.com/) <br><br> [Restrict access to an Amazon S3 origin](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html) <br><br> [AWS Global Infrastructure](https://aws.amazon.com/about-aws/global-infrastructure/#:~:text=The%20AWS%20Cloud%20in%20North,two%20Regional%20Edge%20Cache%20locations.) <br><br> - Expenses: <br><br>&emsp; + [Amazon S3 Price](https://aws.amazon.com/s3/pricing/) <br><br>&emsp; +	[Amazon CloudFront Pricing](https://aws.amazon.com/cloudfront/pricing/)	<br><br>&emsp; + [Amazon Price](https://aws.amazon.com/pricing/)	 |
| 6   | - Retry Lab 10: <br>&emsp; + Fix given template: Region changed to ap-southeast-1, instance changed to t3.micro <br>&emsp; + Successfully configured endpoints and rules in Route 53 for hybrid DNS <br>&emsp; + Succesfully deployed Microsoft AD<br> - Lab 8:<br>&emsp; + Viewed metrics and graph using Cloudwatch on selected EC2 Instances <br>&emsp; + Learnt the basics on monitoring logs <br>&emsp; + 8.4.2: cannot be done: Cant find the resource s3://workshop-template-bucket/logger.py . <br>&emsp; + Configured Cloudwatch Alarm and Dashboard  <br> - Lab 14: Installing Ubuntu <br> - Reformatted worklog <br> - Wrote about Cloud Day 2025 experiences <br><br> - Additional research on AWS Well Architected Framework: <br>&emsp; + Documents a set of foundational questions that enable you to understand how a specific architecture aligns with cloud best practices <br>&emsp; **+ Purpose:** <br>&emsp;&emsp; • A cloud service for reviewing and measuring your workloads against AWS best practices to build more secure, resilient, high-performing, and cost-effective systems.<br>&emsp;&emsp; • Core Function: Identifies High Risk Issues (HRIs) and Medium Risk Issues (MRIs) in your architecture and provides an improvement plan to mitigate them. <br>&emsp; **+ Usage:** <br>&emsp;&emsp; • Step 1: Define a Workload: Specify the name, environment, owner, and regions for the application or system you are reviewing.<br>&emsp;&emsp; • Step 2: Document the State: Answer questions based on the pillars of the AWS Well-Architected Framework (Security, Reliability, etc.) and save a "milestone" to capture your progress.<br>&emsp;&emsp; • Step 3: Review the Improvement Plan: The tool generates a prioritized list of risks (HRIs and MRIs) based on your answers.<br>&emsp;&emsp; • Step 4: Make Improvements & Measure: Update your architecture based on the plan, then update your answers in the tool to track the reduction in risks over time <br>&emsp; **+ Key Features:** <br>&emsp;&emsp; • Workloads: The central component representing your application; can be viewed, edited, shared, and deleted. <br>&emsp;&emsp; • Lenses: Provide focused questions for specific technologies (e.g., Serverless Lens) or industries. You can also create Custom Lenses for internal standards. <br>&emsp;&emsp; • Review Templates & Profiles: Help standardize reviews by pre-filling common answers (Templates) and prioritizing questions based on business goals (Profiles). <br>&emsp;&emsp; • Jira Integration: Allows you to sync improvement items directly from the Well-Architected Tool into your Jira projects as epics, tasks, and sub-tasks for streamlined tracking. <br>&emsp; **+ Security:** <br>&emsp;&emsp; • Shared Responsibility Model: AWS secures the cloud infrastructure, while you are responsible for securing your workloads in the cloud. <br>&emsp;&emsp; • IAM Integration: Access is controlled through AWS IAM, with pre-built policies for full access and read-only access. <br>&emsp;&emsp; • Data Protection: Recommends using IAM users (not root), enabling MFA, and avoiding placing sensitive data in free-form text fields. <br>&emsp;&emsp; • Monitoring & Auditing: Integrates with AWS CloudTrail to log all API activity and with Amazon EventBridge to trigger automated notifications.  | 08/15/2025 | 08/15/2025      | [Vietnam Cloud Day Experience](4-EventParticipated/4.1-Event1/) [AWS Well Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/userguide/intro.html) |


### Week 2 Achievements:

* Understood what AWS is and mastered the basic service groups: 
  * Compute
  * Storage
  * Networking 
  * Database
  * ...

* Successfully created and configured an AWS Free Tier account.

* Became familiar with the AWS Management Console and learned how to find, access, and use services via the web interface.

* Installed and configured AWS CLI on the computer, including:
  * Access Key
  * Secret Key
  * Default Region
  * ...

* Used AWS CLI to perform basic operations such as:

  * Check account & configuration information
  * Retrieve the list of regions
  * View EC2 service
  * Create and manage key pairs
  * Check information about running services
  * ...

* Acquired the ability to connect between the web interface and CLI to manage AWS resources in parallel.
* ...
