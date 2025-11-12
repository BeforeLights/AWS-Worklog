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
| Tue   | - Get started on Module 2 theory: <br>&emsp; + Learnt about VPC (Amazon Virtual Private Cloud)<br>&emsp; + Learnt about Subnets and Routetable, Security Groups<br>&emsp; + Learnt about ENI and EIP<br>&emsp; + Learnt about VPC Peering and Transit Gateway <br>&emsp; + Learnt about Elastic Load Balancing<br>&emsp; + Learnt about EC2<br> - Setup site for workshop report <br> - Installed Hugo <br> - Successfully write worklog using markdown and Hugo | 09/09/2025 | 09/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| Wed   | - Complete Module 2's labs <br> - Lab 3: <br>&emsp; + Learnt about the resources necessary to create and run EC2 instances <br>&emsp; + Successfully configured and run EC2 instances <br>&emsp; + Successfully connect and ping to EC2 instances <br>&emsp; + Created NAT Gateway to allow private EC2 connections <br> - Lab 10: <br>&emsp; + Learnt how to create and use keypair for security <br>&emsp; + Learnt how to configure security group to manage connections <br>&emsp; + Successfully connect and use RDP via EC2 <br>&emsp; + Set up hybrid DNS with Route 53 Resolver (In progress, Cloud Formation template didn't create security group to proceed with the lab) <br> - Lab 19: <br>&emsp; + Successfully created VPC Peering Connection <br> &emsp; + Learnt how to configure Network ACLs <br> &emsp; + Enabled Cross-Peer DNS to resolve private host names <br> - Downloaded and used MobaXTerm to connect to EC2 instances <br> - Downloaded and used Putty to configures keypairs    | 10/09/2025 | 11/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| Thu   | - Lab 20: <br>&emsp; + Successfully created AWS Transit Gateway to allow for connection between VPCs via a common hub <br>&emsp;&emsp; • The Cloud Formation template yaml file isnt up to date, creation failed <br>&emsp;&emsp; • Fixed template file, changed EC2 instance type to t3.micro <br> - Learnt the hard way why you need to clean up resources after a lab, got charged 12$ credits <br> - Verified the cost and budget plans worked as intended, notified over email | 11/09/2025 | 11/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
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
