# Windows Authentication Monitoring & Suspicious Login Detection Using Splunk

## Project Overview
This project demonstrates a Security Operations Center (SOC) monitoring and investigation workflow using Splunk Enterprise. It focuses on analyzing Windows authentication events, identifying suspicious login patterns, investigating potential Password Spraying activity, and creating detection alerts.

## Objectives
- Monitor Windows authentication events.
- Analyze failed and successful login attempts.
- Identify suspicious source IP addresses.
- Investigate potential Password Spraying activity.
- Monitor account lockout events.
- Develop detection searches and alerts using Splunk.

## Tools & Technologies
- Splunk Enterprise
- Search Processing Language (SPL)
- Windows Security Event Logs
- CSV Dataset

## Lab Environment
The project uses a simulated Windows authentication dataset containing:
- Event ID 4624: Successful Logon.
- Event ID 4625: Failed Logon.
- Event ID 4740: Account Lockout.

## Investigation & Detection
The investigation included:
1. Importing authentication logs into Splunk.
2. Analyzing failed and successful login attempts.
3. Investigating source IP addresses and targeted accounts.
4. Correlating failed login attempts with subsequent successful logins.
5. Identifying account lockout events.
6. Creating SPL-based detection logic and a scheduled alert.
7. Building a security monitoring dashboard.

## Key Findings
- 48 authentication events analyzed.
- 15 failed login attempts.
- 31 successful login events.
- 5 targeted user accounts.
- 2 account lockout events.
- 1 successful login from the same source IP associated with the failed attempts.

The observed activity is consistent with a potential Password Spraying pattern.

## Detection Logic
A Splunk detection search was configured to identify source IP addresses generating:
- At least 10 failed login attempts.
- Attempts targeting at least 5 distinct user accounts.

The thresholds were selected for this training dataset and require tuning for real-world environments.

## Disclaimer
This project was developed for educational and portfolio purposes using synthetic authentication data. The findings do not represent a confirmed real-world security incident.
