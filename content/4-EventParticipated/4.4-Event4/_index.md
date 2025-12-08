---
title: "Event 4"
date: "2025-11-29"
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# Summary Report: “AWS Cloud Mastery Series #3: AWS Well-Architected – Security Pillar Workshop”

## Event Overview

The third session of the AWS Cloud Mastery Series focused on the **AWS Well-Architected Framework**, specifically the **Security Pillar**. This workshop provided attendees with a deep dive into the five key areas of cloud security: Identity and Access Management (IAM), Detection and Continuous Monitoring, Infrastructure Protection, Data Protection, and Incident Response. The event also introduced the AWS Cloud Club initiative, which aims to foster cloud computing skills and build a strong community of cloud professionals.

---

## Event Objectives

The workshop aimed to achieve the following objectives:
- Introduce the AWS Cloud Club initiative and its benefits for students and professionals.
- Provide a detailed understanding of the **five pillars of cloud security**:
  1. Identity and Access Management (IAM)
  2. Detection and Continuous Monitoring
  3. Infrastructure Protection
  4. Data Protection
  5. Incident Response
- Share best practices for implementing security measures on AWS.
- Highlight real-world use cases and advanced security solutions.

---

## Speakers

The event featured a diverse panel of AWS Cloud Club Captains, AWS Community Builders, and industry professionals, including:
- **Le Vu Xuan An** – AWS Cloud Club Captain, HCMUTE
- **Tran Duc Anh** – AWS Cloud Club Captain, SGU
- **Tran Doan Cong Ly** – AWS Cloud Club Captain, PTIT
- **Danh Hoang Hieu Nghi** – AWS Cloud Club Captain, HUFLIT
- **Huynh Hoang Long** – AWS Community Builder
- **Dinh Le Hoang Anh** – AWS Community Builder
- **Van Hoang Kha** – Cloud Security Engineer, AWS Community Builder
- **Mendel Grabski (Long)** – Ex-Head of Security & DevOps, Cloud Security Solution Architect
- **Tinh Truong** – Platform Engineer, TymeX, AWS Community Builder

---

## Key Highlights

### **1. AWS Cloud Club Initiative**

The event began with an introduction to the AWS Cloud Club, a program designed to:
- Help students and professionals explore and grow their cloud computing skills.
- Develop technical leadership and mentorship opportunities.
- Build meaningful connections within the global AWS community.

**Benefits of Joining AWS Cloud Club:**
- Hands-on AWS experiences through workshops and projects.
- Mentorship from AWS professionals.
- Long-term career support and networking opportunities.

Participating AWS Cloud Clubs:
- HCMUTE
- SGU
- PTIT
- HUFLIT

---

### **2. Identity & Access Management (IAM)**

IAM is a foundational AWS service for managing secure access to AWS resources. The session covered:
- **Core Concepts:**
  - Users, Groups, Roles, and Policies.
  - Authentication and Authorization.
- **Best Practices:**
  - Apply the **Principle of Least Privilege**.
  - Delete root access keys after account creation.
  - Avoid using wildcards (`*`) in policies.
  - Use AWS Single Sign-On (SSO) for centralized access management.

**Advanced IAM Features:**
- **Service Control Policies (SCPs):** Organization-wide policies that define the maximum permissions available to accounts.
- **Permission Boundaries:** Limit the maximum permissions a user or role can have.
- **Multi-Factor Authentication (MFA):**
  - **TOTP (Time-based One-Time Password):** Requires manual entry of a 6-digit code.
  - **FIDO2 (Fast Identity Online):** Uses biometric scans or hardware tokens for authentication.

**Credential Rotation with AWS Secrets Manager:**
- Automates the rotation of credentials using a 4-step process: Create, Set, Test, and Finish Secret.
- Integrates with EventBridge for scheduling and automation.

---

### **3. Detection & Continuous Monitoring**

This session emphasized the importance of real-time visibility and proactive threat detection:
- **Multi-Layer Security Visibility:**
  - **Management Events:** API calls and console actions.
  - **Data Events:** S3 object access and Lambda executions.
  - **Network Activity Events:** VPC Flow Logs for network-level monitoring.
- **Event-Driven Architecture with EventBridge:**
  - Real-time event processing for automated alerting and response.
  - Integration with Lambda, SNS, and SQS for security workflows.
- **Detection-as-Code:**
  - Use CloudTrail Lake queries for advanced threat hunting.
  - Version-controlled detection rules managed in code repositories.

---

### **4. GuardDuty – Intelligent Threat Detection**

GuardDuty provides continuous threat detection using three key data sources:
| **Data Source**       | **What It Monitors**                  | **Example**                                   |
|-----------------------|---------------------------------------|-----------------------------------------------|
| **CloudTrail Events** | IAM actions, permission changes      | Disabling logging to cover tracks.           |
| **VPC Flow Logs**     | Network traffic                      | EC2 sending data to a botnet C2 server.      |
| **DNS Logs**          | DNS queries                         | Malware querying cryptomining domains.       |

**Advanced Protection Plans:**
- **S3 Protection:** Detects abnormal access patterns and scans for malware.
- **EKS Protection:** Monitors Kubernetes audit logs for unauthorized access.
- **Malware Protection:** Scans EBS volumes for compromised instances.
- **RDS Protection:** Detects brute-force attacks on databases.
- **Lambda Protection:** Monitors network traffic from Lambda functions.

---

### **5. Infrastructure Protection**

The session covered key network security controls:
- **Security Groups (SG):** Stateful firewalls at the instance level.
- **Network ACLs (NACLs):** Stateless firewalls at the subnet level.
- **AWS Network Firewall:** Provides intrusion prevention and egress filtering.

---

### **6. Data Protection & Governance**

The session highlighted AWS services for securing data:
- **Encryption with KMS:** Protects data using customer-managed keys.
- **AWS Secrets Manager:** Automates credential rotation.
- **Certificate Management with ACM:** Provides free public certificates with automatic renewal.

---

### **7. Incident Response**

The final session focused on preparing for and responding to security incidents:
- **Best Practices:**
  - Use temporary credentials.
  - Avoid exposing S3 buckets directly.
  - Manage infrastructure through IaC.
- **Incident Response Process:**
  1. Preparation
  2. Detection & Analysis
  3. Containment
  4. Eradication & Recovery
  5. Post-Incident Review

---

## Event Experience

This workshop was highly relevant to our project on **Automated Incident Response and Forensics**. Key takeaways included:
- **GuardDuty Latency:** Findings take up to 5 minutes due to the large dataset analysis. Third-party tools like Open Clarity can provide near real-time findings.
- **Support from Experts:** Mendel Grabski offered valuable insights and expressed interest in supporting our project.

---

## Event Photos

- ![Group Picture With Speakers](/images/4-EventParticipated/4.4-Event4/PicturewithSpeakers.jpg)
  _Group photo with Mendel Grabski and Van Hoang Kha._