---
title: "Event 3"
date: "2025-11-17"
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Summary Report: “AWS Cloud Mastery Series #2 - DevOps on AWS”

### Event Overview

The second session of the AWS Cloud Mastery Series focused on DevOps practices and tools available on AWS. The event aimed to provide attendees with a solid understanding of DevOps principles, Infrastructure as Code (IaC), container services, and monitoring solutions to build scalable, reliable, and maintainable cloud-based systems.

---

### Event Objectives

The primary goals of the event were to:
- Introduce AWS DevOps services, including CI/CD pipelines.
- Explore Infrastructure as Code (IaC) concepts and tools such as AWS CloudFormation, AWS CDK, and Terraform.
- Provide insights into container services on AWS, including Amazon ECS, EKS, and App Runner.
- Highlight the importance of monitoring and observability using AWS services like CloudWatch and AWS X-Ray.

---

### Speakers

The event featured a panel of experienced AWS Community Builders and cloud professionals:
- **Truong Quang Tinh** – Platform Engineer, TymeX
- **Bao Huynh** – AWS Community Builder
- **Nguyen Khanh Phuc Thinh** – AWS Community Builder
- **Tran Dai Vi** – AWS Community Builder
- **Huynh Hoang Long** – AWS Community Builder
- **Pham Hoang Quy** – AWS Community Builder
- **Nghiem Le** – AWS Community Builder
- **Dinh Le Hoang Anh** – Cloud Engineer Trainee, First Cloud AI Journey

---

### Key Highlights

#### **DevOps Mindset**
The session began with an introduction to the DevOps culture and its core principles:
- **Collaboration:** Breaking down silos between development and operations teams.
- **Automation:** Streamlining repetitive tasks to improve efficiency.
- **Continuous Learning:** Encouraging experimentation and learning from failures.
- **Measurement:** Using metrics to track progress and optimize processes.

**Key Roles in DevOps:**
- DevOps Engineer
- Cloud Engineer
- Platform Engineer
- Site Reliability Engineer (SRE)

**Success Metrics:**
- Deployment health and frequency
- System stability and reliability
- Improved agility and customer experience
- Justification of technology investments

**Best Practices:**
| DO                              | DON'T                     |
|---------------------------------|---------------------------|
| Start with fundamentals         | Stay in tutorial hell     |
| Learn by building real projects | Copy-paste blindly        |
| Document everything             | Compare your progress to others |
| Master one thing at a time     | Give up after failures    |
| Soft skills enhancement         |                           |

**- Continuous Integration:** Team members integrate their work frequently, aims for continuous Delivery and Deployment

---

#### **Infrastructure as Code (IaC)**

The event provided an in-depth look into Infrastructure as Code (IaC) and its benefits:
- **Automation:** Reducing manual intervention and potential errors.
- **Scalability:** Easily scaling infrastructure up or down based on demand.
- **Reproducibility:** Ensuring consistent environments from development to production.
- **Collaboration:** Enhancing teamwork between development and operations.

**AWS CloudFormation:**
AWS's native IaC tool, allowing users to define and provision AWS infrastructure using a declarative template format (YAML or JSON).
- **Stack:** A collection of AWS resources managed as a single unit.
- **CloudFormation Template:** A file that describes the infrastructure resources needed for a specific application or service.
- **Drift Detection:** Identifying and correcting differences between the stack's actual configuration and its expected configuration.

**AWS Cloud Development Kit (CDK):**
An open-source software development framework that allows users to define cloud infrastructure using a programming language of their choice.
- **Construct:** The basic building block of AWS CDK, representing a single unit of deployment.

**AWS Amplify:**
A development platform for building secure, scalable mobile and web applications.

**Terraform:**
An open-source IaC tool that enables users to define and provision data center infrastructure using a high-level configuration language.
- **Strengths:** Multi-cloud support, state management, and a large module ecosystem.

**Criteria for Choosing IaC Tools:**
- Project requirements: single cloud vs. multi-cloud
- Team expertise: developer-focused or operations-focused
- Ecosystem and community support

---

#### **Container Services on AWS**

The event covered various container services offered by AWS and how they fit into the DevOps landscape:
- **Docker:** A platform for developing, shipping, and running applications in containers.
- **Amazon ECR (Elastic Container Registry):** A fully managed Docker container registry that makes it easy to store, manage, and deploy Docker container images.
- **Amazon ECS (Elastic Container Service):** A fully managed container orchestration service that supports Docker containers.
- **Amazon EKS (Elastic Kubernetes Service):** A managed service that simplifies running Kubernetes on AWS without needing to install and operate your own Kubernetes control plane or nodes.
- **AWS App Runner:** A service that makes it easy to quickly deploy containerized web applications and APIs.

**Container Orchestration with ECS and EKS:**
- **ECS:** AWS's native container orchestration service, tightly integrated with other AWS services.
- **EKS:** A managed Kubernetes service, providing the flexibility and control of Kubernetes without the operational overhead.

---

#### **Monitoring & Observability**

The final session focused on monitoring and observability solutions available on AWS:
- **Amazon CloudWatch:** A monitoring and observability service that provides data and actionable insights to monitor applications, respond to system-wide performance changes, and optimize resource utilization.
- **AWS X-Ray:** A service that helps developers analyze and debug production, distributed applications, such as those built using a microservices architecture.

**Key Features:**
- **CloudWatch Metrics:** Monitor and collect metrics from AWS resources and applications.
- **CloudWatch Alarms:** Automatically react to changes in your AWS resources.
- **CloudWatch Logs:** Monitor, store, and access log files from Amazon EC2 instances, AWS CloudTrail, and other sources.
- **X-Ray Tracing:** Analyze and debug distributed applications, providing insights into performance bottlenecks and errors.

---

### Event Experience

This event was very important for our project as it tackle our plan of adding IaC using CDK, instead of using ClickOps for maintainability and reproducibility. Also some more insights on CloudWatch helped greatly with our data monitoring feature

The speakers answered our team's question:

- Q: Our project up until now have been purely built with ClickOps, and we are planning to use CDK. Are there any tool that could scan and turn our existing infrastructure into CDK or CloudFormation rather than reproducing the infrastructure from scratch with IaC? 
- A: Unfortunately no, there isn't a tool that can assist with that problem yet, your team is going to have to built the infrastructure from scratch again. If there by any chance that you do found a tool that can assist with please share with us too.

- Q: We noticed that AWS X-Ray used with CloudWatch is similar to CloudTrail in its tracing method, can you explain more on what differentiate them?
- A: X-Ray is used for CloudWatch and used to trail the resources and services that the system interacted with, meanwhile CloudTrail is commonly used to trail the AWS user's actions

- Q: Our project is built around Guard Duty Findings, do you have any experiences on how to reliably trigger Findings for a demo scenarios?
- A: In my experience I know that Guard Duty Findings can be triggered by port scanning activities but i'm sure there are other ways too
- A: Guard Duty can be configured to have a threat list containing custom rules to trigger findings upon activities relating the configured malicious domains or IPs  

This event is also the first time some of the speaker's first time presenting a topic:
- The DevOps and IaC sections was well presented 
- Monitoring & Observability wasn't as great and we can notice the speaker's nervousness but still delivered great values regardless

#### Some event photos
![Group picture during the event taken by speaker Tran Dai Vi](../4.3-Event3/CM2GroupPic.jpg)