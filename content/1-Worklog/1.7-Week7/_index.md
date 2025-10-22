---
title: "Week 7 Worklog"
date: "2025-10-20"
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---
### Week 7 Objectives:


### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   |- Busy with outside work <br>- Online team meeting to assign tasks. | 20/10/2025 | 20/10/2025 ||
| 3   |**Provisioned and configured an Amazon FSx for Windows File Server lab environment with multiple file systems and SMB shares for later testing.**<br>&emsp;+ Set up the **FSx lab environment via AWS CloudFormation**, creating the required VPC, subnets, security groups, and Windows management instances for the workshop.<br>&emsp;+ Created both **SSD and HDD Multi-AZ FSx for Windows file systems**, selecting appropriate storage sizes, throughput capacities, private subnets, and AWS Managed Microsoft AD integration.<br>&emsp;+ Used the Windows management instance to configure **new SMB file shares on the FSx volumes**, assigning application/data folders and permissive lab share permissions for later scenarios.<br>&emsp;+ Verified basic connectivity from the Windows instance to the **FSx DNS names and shares**, ensuring the environment was ready for performance and data-management exercises. | 21/10/2025 | 21/10/2025 |[Amazon FSx for Windows File Server - AWS Study Group](https://000025.awsstudygroup.com)<br><br>[Getting started with Amazon FSx for Windows File Server](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/getting-started.html)<br><br>[Accessing data using file shares - Amazon FSx for Windows File Server](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/using-file-shares.html)|
| 4   |**Implemented performance testing, monitoring, and advanced data protection features on Amazon FSx for Windows File Server.**<br>&emsp;+ Ran **DiskSpd-based performance tests** from a Windows instance against the mapped FSx drive to measure read/write throughput under load.<br>&emsp;+ Monitored **FSx CloudWatch metrics** (throughput, IOPS, latency, connections) from the FSx console to correlate observed performance with the configured capacity.<br>&emsp;+ Enabled **data deduplication** on the FSx file system via the remote PowerShell FSx CLI, created a daily optimization schedule, and validated dedup status and savings statistics.<br>&emsp;+ Turned on **shadow copies** for the FSx volume, increased the storage limit, created an on-demand snapshot, and confirmed that file “Previous Versions” could be restored from Windows Explorer.<br>&emsp;+ Practiced **admin control over user sessions and open files** using Shared Folders and FSx PowerShell cmdlets, including force-closing an active test file to interrupt client I/O.| 22/10/2025 | 22/10/2025 |[FSx for Windows File Server performance](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/performance.html)<br><br>[Protecting your data with shadow copies](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/shadow-copies-fsxW.html)<br><br>[Administering FSx for Windows file systems](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/administering-file-systems.html)|
| 5   || 23/10/2025 | 23/10/2025 ||
| 6   || 24/10/2025 | 24/10/2025 ||


### Week 7 Achievements:
