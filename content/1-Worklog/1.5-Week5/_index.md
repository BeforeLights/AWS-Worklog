---
title: "Week 5 Worklog"
date: "2025-10-06"
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   |**Completed end-to-end setup of a hybrid DNS environment using Route 53 Resolver with AWS Managed Microsoft AD and RD Gateway.**<br>&emsp;+ Launched the provided **CloudFormation** template to create a custom **VPC**, public/private subnets across two **Availability Zones**, **Internet Gateway**, and **NAT Gateways** for outbound access from private subnets.<br>&emsp;+ Configured a **Remote Desktop Gateway (RDGW) EC2 instance** in the public subnet, adjusted **security groups** for controlled **RDP/ICMP** access, and verified remote connectivity from the local workstation.<br>&emsp;+ Deployed **AWS Managed Microsoft AD**, joined RDGW to the managed domain, and confirmed domain authentication from the RD session host. <br>&emsp;+ Created **Route 53 Resolver outbound endpoints** in private subnets and forwarding rules so VPC workloads can resolve on-premises-style domain names via the managed AD DNS servers. <br>&emsp;+ Created **Route 53 Resolver inbound endpoints** and rules to allow external or on-premises DNS forwarders to resolve private AWS hostnames in the VPC, completing the hybrid DNS flow. <br>&emsp;+ Tested DNS name resolution from the RDGW instance to ensure queries for both **AWS private records and on-premises-style domains** were correctly routed through the configured Resolver endpoints and AD DNS. | 06/10/2025 | 06/10/2025      | [AWS Managed Microsoft AD - AWS Directory Service](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/directory_microsoft_ad.html)<br><br>[What is Route 53 VPC Resolver?](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resolver.html)<br><br>[NAT Gateways - Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html) |
| 3   |  | 07/10/2025 | 07/10/2025      | |
| 4   |  | 08/10/2025 | 08/10/2025      | |
| 5   |  | 09/10/2025 | 09/10/2025      | |
| 6   |  | 10/10/2025 | 10/10/2025      | |


### Week 5 Achievements:

* Proposal Development: Successfully created and updated the team's workshop architecture diagram, learning the best practices for diagramming AWS architecture.
