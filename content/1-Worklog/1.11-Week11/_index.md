---
title: "Week 11 Worklog"
date: "2025-09-09"
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   |Attended the AWS Cloud Mastery Series #2 – DevOps on AWS| 17/11/2025 | 17/11/2025 ||
| 3   | **Consolidated the Telegram and SES Lambdas into one unified Alert Dispatch function with structured code, integrated a friend's Slack implementation, and validated everything with GuardDuty.**<br>&emsp;+ Merged the **separate Telegram and SES Lambda functions** into a single **Alert Dispatch Lambda** with clean, modular code structure and dedicated helper functions for each channel.<br>&emsp;+ Integrated **Slack webhook delivery** from my friend's code—now all three channels (Telegram, SES, Slack) are handled by one function with shared parsing logic.<br>&emsp;+ Structured the **Lambda code properly** with clear separation: SNS parsing → alert enrichment → channel-specific formatters (Slack blocks, Telegram messages, SES HTML) → error handling.<br>&emsp;+ Set up **environment variables** to centrally manage all credentials (Slack webhook URLs, Telegram bot token/chat ID/thread ID, SES sender address)—way cleaner than hardcoding.<br>&emsp;+ Tested the **complete multi-channel pipeline** with GuardDuty sample findings—verified alerts arrive correctly formatted in Slack, Telegram, and email simultaneously, and everything works reliably.| 18/11/2025 | 18/11/2025 ||
| 4   |**Structured the AWS Incident Response System project in Jira by defining core epics, assigning ownership across multiple teams, and establishing the foundation for incident handling workflows.**<br>&emsp;+ Created **5 key epics** in Jira to map the incident response workflow: Threat Detection, Alerting, Response Workflow, Data Pipeline, and Dashboard components.<br>&emsp;+ Assigned **epic ownership to individual team members** so each area has a clear lead responsible for its scope and delivery.<br>&emsp;+ Organized **team structure and responsibilities** by aligning each epic with the appropriate skill set (threat detection, alerting infrastructure, workflow orchestration, data ingestion, dashboarding).<br>&emsp;+ Configured **epic-to-task rolldown** in Jira so that sub-tasks and issues are tied to their parent epics, enabling team visibility and burndown tracking across the incident response system.| 19/11/2025 | 19/11/2025 ||
| 5   |Went back **Bùi Thị Xuân** High school for Teacher's Day.| 20/11/2025 | 20/11/2025 ||
| 6   || 21/11/2025 | 21/11/2025 ||


### Week 11 Achievements: