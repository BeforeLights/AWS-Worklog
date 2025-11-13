---
title: "Week 1 Worklog"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Week 1 Objectives:

* Connect with FCJ members and mentors.
* Find out what working in an office is like.
* Install Linux, learn how to properly use Linux.
* Learn the basics of AWS, console and CLI.
* Complete first and second module.


### Tasks to be carried out this week:
| Day |Task| Start Date | Completion Date | Reference Material |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| Mon   | - Reviewed and acknowledged the official internship rules and guidelines. <br> - Created an AWS account based on the materials. (**Viewed account ID**, **Updated account credentials**, **Created an alias**) <br> - Acknowledged the steps required to close my account <br>- Understanding on MFA for accounts (**Chose Virtual MFA for ease of use**) <br>- Understood and created Groups and Users <br>- Read the **Account authentication support** (I didn't need to do this part since everything went well) <br>- Learnt about the basics of the AWS Management Console <br>- Know about the support cases (**types of support cases**, **how to create one well**) <br>- Know about the **types of Budgets**, the **steps** to create them and the **benefits** for each one of them. | 08/09/2025 | 08/09/2025 | [Setting up an AWS account](https://000001.awsstudygroup.com) <br><br> [What is the AWS Management Console?](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/what-is.html) <br><br> [Managing Costs with AWS Budgets](https://000007.awsstudygroup.com/) <br><br> [Getting Help with AWS Support](https://000009.awsstudygroup.com/) <br><br> [AWS Service Quotas](https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html) <br><br> [Compare AWS Support Plans](https://aws.amazon.com/premiumsupport/plans/)
| Tue   | - Installed **Hugo** and started setting up<br> - Learnt the fundamentals about **IAM**<br>&emsp; + Create and manage **IAM Groups** for user organization<br>&emsp; + Apply **IAM Policies** for effective permissions<br>&emsp; + Manage **IAM Users** through groups for streamlined control<br>&emsp; + **IAM Role** for easy permission switching<br> - Getting started on **Amazon VPC** (Virtual Private Cloud)<br>&emsp; + Revise **Subnets**, getting to know about its relationship with **AZ**s and best (Availability Zone) and the best practices <br>&emsp; + Learnt about **Route table** <br>&emsp; + Learnt about **IGW** (Internet Gateway) and **NAT Gateway** <br>&emsp; Learnt about Firewall fundamentals (**Security Group**, **Network ACLs**, **VPC Resource Map**) <br> - Practice after learning the fundamentals <br>&emsp; + Get through  <br>&emsp; Created an **EC2** instance, **NAT Gateway**, used **Reachability Analyzer**, **SSM**, **CloudWatch** | 09/09/2025 | 09/09/2025 | [AWS Identity and Access Management (IAM) Access Control](https://000002.awsstudygroup.com/vi/) <br><br> [Amazon VPC and AWS Site-to-Site VPN Workshop](https://000003.awsstudygroup.com/)
| Wed   | - Finished fixing up bugs for **Hugo** <br> Started with **Site to Site VPN** <br>&emsp; + Created a **VPC** for the **VPN**, created an **EC2** instance <br>&emsp; Created a **Virtual Private Gateway** to connect to the endpoints, created a **Customer Gateway**, Set up **route tables** and **propagation** for the **VPN connection** (**EC2** in this case) <br>&emsp; + Configure the **Customer Gateway** (I chose **Libreswan** not knowing **Strongswan** is recommended and **OpenSwan** is no longer usable.) <br>&emsp; + Spend most of the time on **debugging**. | 10/09/2025 | 11/09/2025 | [Amazon VPC and AWS Site-to-Site VPN Workshop](https://000003.awsstudygroup.com/)
| Thu   | - Finished **debugging** the **configuration** of the **Customer Gateway** (some commands are not working and the ones that work are in **5.2.7**, use **systemd** instead of **service**) <br> - **Finished the Amazon VPC and AWS Site-to-Site VPN Workshop** as a whole <br> - Starting the new Lab (**Introduction to Amazon EC2**) <br>&emsp; + Created a **Linux VPC**, **Windows VPC**, **Security group Linux**, **Security group Windows** <br>&emsp; + Created the **Windows Instance** and connected to it. <br>&emsp; + Created the **Linux Instance** and connected to it. <br>&emsp; + Learnt about the fundamentals of **EC2**, changing **instance type**, creating **snapshots**, etc... <br>&emsp; + Created **custom AMIs** with and without **sysprep**, created instances from the AMIs. <br>&emsp; + For the **How to connect when you lost the keypair** part, I created an IAM Role with **AmazonSSMFullAccess** and updated the EC2 to have that policy, checked SSM but I don't see the instance, spent some time searching and still seeing **Managed: false**, tested the connection, checked the **SSM Agent logs** to see if there are errors (no errors), **restarted** the **SSM service** inside of the AMI and it worked after that, it is still **Managed: false** for some reasons <br>&emsp; + Replace **keypair** via **editing user data** is successful for the **Linux machine** <br>&emsp; + Installed desktop environment for the **Ubuntu AMI** and it booted up successfully  | 11/09/2025 | 11/09/2025 | [Amazon VPC and AWS Site-to-Site VPN Workshop](https://000003.awsstudygroup.com/) <br><br> [Introduction to Amazon EC2](https://000004.awsstudygroup.com/) <br><br> [Create an Amazon EC2 AMI using Windows Sysprep](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ami-create-win-sysprep.html#sysprep-phases) <br><br> [Working with SSM Agent on EC2 instances for Windows Server](https://docs.aws.amazon.com/systems-manager/latest/userguide/ssm-agent-windows.html) <br><br> [AWS Systems Manager Parameter Store](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html) |
| Fri   | - Get started on Module 3 theory <br>&emsp; + Learnt about EBS, Instance store feature and check User and Meta Data <br>&emsp; + Learnt about Amazon Lightsail <br>&emsp; + Learnt about Elastic File System(EFS) and FSx <br>&emsp; + Learnt about MGN <br>&emsp; + Learnt how to use S3 Bucket on AWS <br>- Complete Module 3's labs <br>- Lab 13: Successuly created Backup Plan and Vaults for data in S3 Bucket <br>&emsp; + Successfully setted up notification for Backup events <br>&emsp; + Successfully restored backup <br> - Lab 24: <br>&emsp; + Created storage gateway <br>&emsp; + Succesfully completed file sharing <br> - Lab 57: <br>&emsp; + Successfully hosted static website using S3 Bucket <br>&emsp; + Successfully configured access modifiers <br>&emsp; + Successfully created bucket versions <br>&emsp; + Moved objects between buckets <br>&emsp; + Replicated bucket across regions  | 12/09/2025 | 12/09/2025 | <https://cloudjourney.awsstudygroup.com/> |


### Week 1 Achievements:

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
