---
title: "Week 9 Worklog"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---
### Week 9 Objectives:

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Completed **Quản trị dữ liệu và an toàn thông tin** MOOC in Coursera **(KS57 Program)** | 03/11/2025 | 03/11/2025 ||
| 3   | **Used AWS Glue and Amazon Athena to explore AWS Cost & Usage Reports and understand where cloud spending comes from.**<br>&emsp;+ Ran **simple Athena queries** on the Glue-created CUR tables to view example rows, check billing periods, and get familiar with the structure of the cost data.<br>&emsp;+ Summarized **costs by account and service** in Athena to see which accounts and AWS services are responsible for the highest spend, then focused on key **Amazon EC2 on-demand usage** lines for more detail.<br>&emsp;+ Checked **cost allocation tags** (such as a cost-center tag) in the CUR data to compare how much spend is correctly tagged to teams versus how much is still untagged.<br>&emsp;+ Compared **discounted usage (Savings Plans/Reserved Instances)** with estimated on-demand prices in Athena queries to see how much savings the discounts provide for specific EC2 usage types.<br>&emsp;+ Used the query results to build a clearer picture of **who is spending, on which services, and how efficiently**, as preparation for future cost optimization work. | 04/11/2025 | 04/11/2025      | [Cost and performance analysis with AWS Glue and Amazon Athena](https://000040.awsstudygroup.com/)<br><br>[Querying Cost and Usage Reports using Amazon Athena](https://docs.aws.amazon.com/cur/latest/userguide/cur-query-athena.html)<br><br>[AWS Cost and Usage Reports overview](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)<br><br>[Creating tables for CUR data using AWS Glue and Athena](https://docs.aws.amazon.com/athena/latest/ug/creating-tables.html)<br><br>[Organizing and tracking costs with AWS cost allocation tags](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html)<br><br>[Amazon Athena pricing](https://aws.amazon.com/athena/pricing/) |
| 4   |**Set up Grafana to monitor my EC2 instance using CloudWatch and built a simple live dashboard.**<br>&emsp;+ Connected **Grafana** to **Amazon CloudWatch** as a data source so it can read EC2 metrics from my AWS account.<br>&emsp;+ Tested the data source and confirmed Grafana could successfully query CloudWatch metrics for my instance.<br>&emsp;+ Created a **Grafana dashboard** with panels showing key **EC2 metrics** like CPU usage over time.<br>&emsp;+ Saved the dashboard and used the **refresh and share** options so it can be reused to watch instance health in real time.| 05/11/2025 | 05/11/2025 |[Getting started with Grafana basic](https://000029.awsstudygroup.com/)<br><br>[Using Amazon CloudWatch metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/working_with_metrics.html)<br><br>[Grafana CloudWatch data source configuration](https://grafana.com/docs/grafana/latest/datasources/aws-cloudwatch/)<br><br>[Build your first Grafana dashboard](https://grafana.com/docs/grafana/latest/fundamentals/getting-started/first-dashboards/)| 
| 5   || 06/11/2025 | 06/11/2025      ||
| 6   || 07/11/2025 | 07/11/2025 | |


### Week 9 Achievements:
