# SOPs

These are the main Standard Operating Procedures (SOPs) that I have used as a Security Operations Center (SOC) analysts using Azure Sentinel (Azure SIEM), Microsoft Defender (XDR), DUO (MFA), and Digital Guardian (DLP). I have I have generalised them to suit most SOC environments. In any case SOPs should be reviewed quarterly and immediate updates if new security tools are implemented or new threats are identified. Access Control should be observed ie restrict access to incident details involving sensitive data or HR issues to relevant personnel only. 

# Incident Triage and Response

### Employee Offboarding
### DLP Alert Response
### Suspicious Authentication Alerts
### Phishing
### Malware
### Insider Threats


# Employee Offboarding

# Overview

In the case of an Immediate Termination of Empoyment. Ensure the secure offboarding of employees by disabling access to corporate resources and monitoring for any suspicious activities post-offboarding.

# Steps:

## 1 Receive Offboarding Request:

<ul>
  <li>Initiate upon notification from HR or IT.</li>
  <li>Validate the request through the employee database.</li>
</ul>

## 2 Account Deactivation:

### Azure Sentinel:

<ul>
  <li>Navigate to Azure Active Directory (AAD).</li>
  <li>Locate the employee’s account.</li>
  <li>Disable the account and reset passwords.</li>
</ul>

### DUO for MFA:

<ul>
  <li>Remove MFA configurations associated with the user.</li>
</ul>

### Microsoft Defender XDR:

<ul>
  <li>Terminate active sessions on all corporate devices.</li>
</ul>

## 3 Monitor for Post-Deactivation Activity:

<ul>
  <li>Use Azure Sentinel to set up a monitoring rule for any access attempts after deactivation.</li>
  <li>Investigate any anomalies immediately.</li>
</ul>

## 4 Documentation

<ul>
  <li>Record all actions taken in the offboarding process.</li>
  <li>Save logs in the incident management system.</li>
</ul>


## 5 Escalation

<ul>
  <li>If suspicious activity is detected post-offboarding, escalate to SOC Manager.</li>
</ul>







