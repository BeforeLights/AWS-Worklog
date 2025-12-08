---
title: "Week 4 Worklog"
date: "2025-09-29"
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---



### Week 4 Objectives:
*   Build custom CloudWatch Dashboards to visualize logs and metrics.
*   Implement cost optimization automation using Lambda and EventBridge.
*   Perform heterogeneous database migration (MSSQL to MySQL) using AWS SCT.
*   Finalize team project proposal and estimate resource costs.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   |**Built a CloudWatch dashboard to visualize key metrics and alarms from the AWS CloudWatch workshop.**<br>&emsp;+ Opened the **CloudWatch console**, navigated to **Dashboards**, and created a new **custom dashboard** with a descriptive name.<br>&emsp;+ Added **metric widgets** displaying the custom **error-count metric** generated from **CloudWatch Logs metric filters**, tuning the period and statistic for readability.<br>&emsp;+ Placed **alarm widgets** on the dashboard to show the real-time state of the **log-derived error alarm**, linking logs, metrics, and alarms in one view.<br>&emsp;+ Arranged and resized widgets on the 24-cell grid to highlight critical observability components and saved the dashboard for reuse.  | 29/09/2025 | 29/09/2025 | [AWS CloudWatch Workshop :: AWS Account Setup](https://000008.awsstudygroup.com/)<br><br>[CloudWatch Dashboards :: AWS Account Setup](https://000008.awsstudygroup.com/6-cloud-watch-dashboard/)<br><br>[Using Amazon CloudWatch dashboards - AWS Documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Dashboards.html)<br><br>[Creating a customized CloudWatch dashboard - AWS Documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/create_dashboard.html) |
| 3 | - Completed **Being a researcher (in Information Science and Technology)** in Coursera **(ENW493c)** | 30/09/2025 | 30/09/2025 | |
| 4   |- Completed **Advanced Writing** in Coursera **(ENW493c)**| 01/10/2025 | 01/10/2025 <br>| |
| 5   |**Automated EC2 cost optimization using Lambda functions, tags, and Slack notifications for start/stop control.**<br>&emsp;+ Created a dedicated **VPC**, **subnets**, and **security group** to host a lab **EC2 instance** targeted for automated scheduling.<br>&emsp;+ Launched and tagged an **EC2 instance** with a cost-optimization tag (for example, **environment_auto**) so only specific instances are affected by automation.<br>&emsp;+ Configured a **Slack Incoming Webhook** and channel to receive real-time notifications from **AWS Lambda** about EC2 start/stop actions.<br>&emsp;+ Created an **IAM execution role** for **Lambda** with permissions to describe, start, and stop tagged EC2 instances and write logs.<br>&emsp;+ Implemented two **Lambda functions** (start/stop) that filter EC2 instances by tag, call **StartInstances**/**StopInstances** APIs, and post structured messages to Slack.[10]<br>&emsp;+ Tested the workflow end-to-end by invoking the functions, validating EC2 state changes in the console, and confirming Slack notifications as the basis for a scheduled solution using **EventBridge/CloudWatch Events**.<br>- **Discussed with the team** on what to do with our **project** and how we can implement **Slack**| 02/10/2025 | 02/10/2025 | [Optimize EC2 cost with Lambda - AWS Study Group](https://000022.awsstudygroup.com)<br><br>[Defining Lambda function permissions with an execution role](https://docs.aws.amazon.com/lambda/latest/dg/lambda-intro-execution-role.html)<br><br>[How to Schedule EC2 Instances to Stop/Start Automatically](https://dev.to/aws-builders/how-to-schedule-ec2-instances-to-stopstart-automatically-1bl5)<br><br>[Use AWS Lambda to send Slack notifications for running Amazon EC2 instances](https://nivleshc.wordpress.com/2021/06/27/use-aws-lambda-to-send-slack-notifications-for-running-amazon-ec2-instances) |
| 6   |- Participated in the **AI-Driven Development Life Cycle: Reimagining Software Engineering** event| 03/10/2025 | 04/10/2025 |  | 


### Week 4 Achievements:
*   Designed and deployed a custom CloudWatch Dashboard to monitor application health and error rates.
*   Developed a serverless cost-optimization solution using Lambda to automatically stop/start EC2 instances, integrated with Slack notifications.
*   Successfully migrated a legacy MSSQL database to Amazon MySQL using the AWS Schema Conversion Tool (SCT), resolving compatibility issues.
*   Collaborated with the team to finalize the capstone project proposal and secured admin access for all members.