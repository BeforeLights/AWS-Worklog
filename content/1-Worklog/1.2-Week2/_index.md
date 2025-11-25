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
| 2   | - Finished restricting an **IAM** from creating **EC2** from another region. (**Restricting Service Usage by AWS Region**) <br> - Learnt how to **analyze compute requirements** and chose an appropriate **instance family** for it. <br> - Launched instances within the **same and different families** to test the **IAM EC2 Policy** <br> -   | 08/11/2025 | 08/11/2025      | [Amazon EC2 instance types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html) <br><br> [Introduction to Amazon EC2](https://000004.awsstudygroup.com/) <br><br> [Amazon EC2 instance types](https://aws.amazon.com/ec2/instance-types/?nc1=h_ls)
| 3   |- Lab 4 <br> - Lab 6: RDS Database <br> -Succesfully used Linux via EC2 instance to: <br>&emsp; + Install and use MySQL database <br>&emsp; + Install and run a web apllication, can be connected to from browers <br> - Created Load Balancer and Target Groups <br> -Paessler Webstress tool has been discontinued, cannot test using the given tool  <br> - Successfully install Siege on EC2 instance to load test: <br>&emsp; + Ran loadtest, simulated 50 users at the same time for 10 minutes <br>&emsp; + The EC2 instance is terminated and load balanced 10 times in succession <br>&emsp; + Seige automatically stopped after 5 minutes due to too much packet loss <br>&emsp; + The reason might be due to the EC2 instance and RDS Database were created using the only available free tier options, and could not handle the increased traffics    <br> - Succesfully hosted database using RDS                                         | 08/12/2025 | 08/12/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | <br> Module 4 3, module 4 4 <br> - Help teammate with Lab 5<br> - Instruction of lab 5 is missing some steps: 5.5.3: The given script didnt connect the RDS database to MySQL, 5.5.5: The instruction is missing the step: cd to the application folder <> | 08/13/2025 | 08/13/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Joined the AWS Cloud Day 2025 HCM Event: Gen AI and Data track <br>&emsp; | 08/14/2025 | 08/15/2025      | [Vietnam Cloud Day Agenda](https://pages.awscloud.com/vietnam-cloud-day-hcmc-connect-edition.html?trk=a3b21210-a497-4502-8073-982920d98210&sc_channel=em#agenda) |
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
