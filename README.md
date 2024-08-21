# SOPs

These are the main Standard Operating Procedures (SOPs) that I have used as a Security Operations Center (SOC) analyst using Azure Sentinel (Azure SIEM), Microsoft Defender (XDR), DUO (MFA), and Digital Guardian (DLP). I have I have generalised them to suit most SOC environments. In any case SOPs should be reviewed quarterly and immediate updates if new security tools are implemented or new threats are identified. Access Control should be observed ie restrict access to incident details involving sensitive data or HR issues to relevant personnel only. 

# Incident Triage and Response

### Employee Offboarding
### DLP Alert Response
### Suspicious Authentication Alerts
### Phishing
### Malware
### Insider Threats

<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>

# Employee Offboarding

# Overview

In the case of an Immediate Termination of Empoyment. Ensure the secure offboarding of employees by disabling access to corporate resources and monitoring for any suspicious activities post-offboarding.

# Steps:

## 1 Receive Offboarding Request:

<ul>
  <li>Initiate upon notification from HR or IT.</li>
  <li>Validate the request through the employee database ie Workday SAGE or Oracle.</li>
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


# Response Timeframe:
Immediate action required within 1 hour of receiving the offboarding request.


<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>



# DLP Alert Response

# Overview

Respond to alerts triggered by Digital Guardian related to data loss prevention (DLP) to protect sensitive corporate data.

# Steps:

## 1 Receive Alert:

<ul>
  <li>Alerts are generated via Digital Guardian and forwarded to Azure Sentinel.</li>
  <li>In DG or Sentinel review alert details, including the type of data and user involved.</li>
</ul>

## 2 Initial Assessment:

<ul>
  <li> Verify if the data is classified as sensitive.</li>
  <li> Cross-reference with existing policies.</li>
</ul>


## 3 Containment:

<ul>
  <li> Block any ongoing data exfiltration.</li>
  <li>Isolate the device if necessary using Microsoft Defender XDR.</li>
</ul>

## 4 Investigation:

<ul>
  <li>Identify the root cause, whether it’s malicious or accidental.</li>
  <li>Via users manager, interview the user involved if necessary.</li>
</ul>

## 5 Remediation:

<ul>
  <li>Delete or secure exposed data.</li>
  <li>Re-train the user on data handling policies if accidental.</li>
</ul>

## 6 Documentation:

<ul>
  <li>Record details of the incident, actions taken, and final resolution.</li>
  <li>Update DLP policies if necessary to prevent future incidents.</li>
</ul>


## 7 Escalation:

<ul>
  <li>Escalate to the DLP team if the incident involves large volumes of sensitive data or repeated violations.</li>
</ul>


# Response Timeframe:
High-severity alerts must be responded to within 15 minutes.


<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>








