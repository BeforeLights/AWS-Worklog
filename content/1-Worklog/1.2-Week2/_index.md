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
| 2   | - Finished restricting an **IAM** from creating **EC2** from another region. (**Restricting Service Usage by AWS Region**) <br> - Learnt how to **analyze compute requirements** and chose an appropriate **instance family** for it. <br> - Launched instances within the **same and different families** to test the **IAM EC2 Policy** <br> - Learnt how to **restrict** certain **EBS volumes** and the general information about **EBS volume types** <br> - Tested the policy by launching an **EC2** with an **EBS volume type** that isn't permitted. <br> - Learnt how to **limit access to resources** by only **allowing access to certain IPs** <br> - Learnt how to limit permission to **delete resources by time period** | 15/09/2025 | 15/09/2025      | [Amazon EC2 instance types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html) <br><br> [Introduction to Amazon EC2](https://000004.awsstudygroup.com/) <br><br> [Amazon EC2 instance types](https://aws.amazon.com/ec2/instance-types/?nc1=h_ls) <br><br> [IAM policy testing with the IAM policy simulator](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html) <br><br> [IAM Policy Simulator](https://policysim.aws.amazon.com/home/index.jsp?#)
| 3   |- Created an **EC2** and **SSH'ed into it** using **MobaXterm** and created an **S3 bucket** <br> - Upload files using an **accesskey/secretaccesskey**: <br>&emsp; + Generated an **IAM user with an access key** <br>&emsp; + **Uploaded files** to the **S3 bucket** <br> - Upload files with **eligible roles** on **EC2**: <br>&emsp; + Created a **role** for the **EC2** <br>&emsp; + **Uploaded files** to the **S3 bucket** via **EC2 role**.| 16/09/2025 | 16/09/2025      | [Granting authorization for an application to access AWS services with an IAM role.](https://000048.awsstudygroup.com/)
| 4   | <br> - Looked into **Cloud 9** IDE, on what it is about (Can't use it because I don't have access to it.)![Cloud9](/images/cloud9.png) - Information about **S3**: <br>&emsp; + Know the difference between **S3 Bucket** and **S3 Object** <br>&emsp; + Know about the **storage classes** and others. <br> - **Create an S3 bucket** and **host a static website**: <br>&emsp; + Created an **S3 bucket** and **uploaded the data** <br>&emsp; + Enabled **Static website hosting** and unchecked **Block all public access** <br>&emsp; + Changed the **bucket permission settings** and made **objects public using ACL** <br>&emsp; + Successfully accessed the **static website** | 17/09/2025 | 17/09/2025 | [How to migrate from AWS Cloud9 to AWS IDE Toolkits or AWS CloudShell](https://aws.amazon.com/blogs/devops/how-to-migrate-from-aws-cloud9-to-aws-ide-toolkits-or-aws-cloudshell/) <br><br> [Get started with AWS Cloud 9](https://000049.awsstudygroup.com/) <br><br> [Starting with Amazon S3](https://000057.awsstudygroup.com/) |
| 5   | - Accelerate Static Websites with **Cloudfront**: <br>&emsp; + **Blocked** all **public access** <br>&emsp; + Created and configured a **Cloudfront distribution** (The new UI doesn't let you choose the **Default root object** and **Price class** on creating, to change this, select your **distribution**, click on the **General** tab, find **Settings** and click **Edit**, then you can see the missing options there.) <br>&emsp; + **Successfully** accessed the **website** <br>&emsp; + **Checked** the **loading time** by inspecting the website, the flow would be: <br> **Inspect -> Network -> Refresh page** <br> You can see the time at the far right of the **Cloudfront document** (for me it's 29ms), when you click on the **Cloudfront document**, you can see which PoP the website is being returned from ![PoP location](/images/pop_location.png) It's **HKG1-P2** (Hong Kong) for me <br> - Bucket Versioning: <br>&emsp; + Read and enabled **Bucket Versioning** <br>&emsp; + Tested it by **editing** the **index.html** file and uploading it onto the **S3 bucket** and checking **Cloudfront** <br> - Moving objects from an S3 to another: <br>&emsp; + Created a new **S3 Bucket** <br>&emsp; + Calculated the **size** of the **entire bucket** to compare **after moving** <br>&emsp; + **Successfully moved** the bucket <br>&emsp; + Calculated the **size** to make sure we didn't lose any data <br> Out of curiosity, I tried changing the **Origin domain** of the **Cloudfront distribution**, added a **Bucket policy** in permissions and enabled **Static website hosting** on the new **S3 Bucket** and it works wonder! <br> - Successfully replicated **objects** inside of a **S3 Bucket** to another **region**. <br> [**Notes and Best Practices**](https://000057.awsstudygroup.com/12-notes/)  | 18/09/2025 | 18/09/2025 | [Starting with Amazon S3](https://000057.awsstudygroup.com/) <br><br> [Restrict access to an Amazon S3 origin](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html) <br><br> [AWS Global Infrastructure](https://aws.amazon.com/about-aws/global-infrastructure/#:~:text=The%20AWS%20Cloud%20in%20North,two%20Regional%20Edge%20Cache%20locations.) <br><br> - Expenses: <br><br>&emsp; + [Amazon S3 Price](https://aws.amazon.com/s3/pricing/) <br><br>&emsp; +	[Amazon CloudFront Pricing](https://aws.amazon.com/cloudfront/pricing/)	<br><br>&emsp; + [Amazon Price](https://aws.amazon.com/pricing/)	|
| 6   | - **Completed deploying a Node.js application connected to Amazon RDS MySQL on EC2.** <br>&emsp;+ Installed **Node.js**, **npm**, and **nvm** on **Amazon Linux** and troubleshot missing modules (such as `has-proto`). <br>&emsp;+ Installed the **MariaDB command-line client** on the EC2 instance to connect to the **RDS MySQL** database more easily and debug connection/schema issues from the terminal. <br>&emsp;+ Configured the **.env** file with **DB_HOST**, **DB_NAME**, **DB_USER**, **DB_PASS** pointing correctly to the **RDS endpoint** and actual database. <br>&emsp;+ Adjusted **Security Groups** for **EC2** and **RDS** to only allow **MySQL** access from the **EC2 security group**, fixing `ECONNREFUSED` and **Unknown database** errors. <br>&emsp;+ Tested the application on port **5000** and confirmed successful **read/write** operations to **RDS** <br> - **Practiced backup and restore with Amazon RDS.** <br>&emsp;+ Created a **manual snapshot** and reviewed **automatic backup** behavior and retention. <br>&emsp;+ Performed a **restore from snapshot** to create a new **DB instance** and understood the **recovery flow** in case of incidents. | 19/09/2025 | 19/09/2025      |  [Amazon Relational Database Service (Amazon RDS)](https://000005.awsstudygroup.com/) <br><br> [Controlling access with security groups](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.RDSSecurityGroups.html) <br><br> [Setting up public or private access in Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/gettingstartedguide/security-public-private.html) <br><br> [Working with a DB instance in a VPC](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.WorkingWithRDSInstanceinaVPC.html) <br><br> [Installing the MySQL command-line client](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/mysql-install-cli.html) <br><br> [Creating and connecting to a MySQL DB instance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_GettingStarted.CreatingConnecting.MySQL.html)|


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
