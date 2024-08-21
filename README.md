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


# Suspicious Authentication Alerts

# Overview

Investigate alerts regarding suspicious authentication activities, such as failed login attempts or login from unusual locations.

# Steps:

## 1 Receive Alert:

<ul>
  <li>Review suspicious authentication alerts in Azure Sentinel.</li>
  <li>Check details like IP address, login time, and location.</li>
</ul>

## 2 Initial Verification:

<ul>
  <li> Contact the user to verify if they recognize the activity.</li>
  <li> If unreachable, proceed with caution.</li>
</ul>


## 3 Containment:

<ul>
  <li> Lock the account via Azure AD if the activity is deemed suspicious.</li>
  <li> Terminate any active sessions using Microsoft Defender XDR.</li>
</ul>

## 4 Investigation:

<ul>
  <li>Trace the IP and look for patterns in Azure Sentinel.</li>
  <li>Check for similar activities across the network.</li>
</ul>

## 5 Remediation:

<ul>
  <li>Require a password reset via DUO.</li>
  <li>Re-enable the account only after confirming the user’s identity.</li>
</ul>

## 6 Documentation:

<ul>
  <li>Record details of the incident, actions taken, and final resolution.</li>
  
</ul>


## 7 Escalation:

<ul>
  <li> Escalate to SOC managert if the suspicious activity is part of a larger pattern..</li>
</ul>


# Response Timeframe:
High-severity alerts must be responded to within 30 minutes.


<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>


# Phishing

# Overview

Handle phishing incidents reported by users or detected by automated systems.

# Steps:

## 1 Receive Phishing Report:

<ul>
  <li>Acknowledge reports from users or alerts from Proofpoint (Trap and Clear) or Microsoft Defender XDR.</li>
 
</ul>

## 2 Initial Assessment:

<ul>
  <li> Review the reported email for phishing indicators (e.g., suspicious links, sender address).</li>
  
</ul>


## 3 Containment:

<ul>
  <li> Block the sender domain across the network.</li>
  <li> Isolate affected users’ mailboxes.</li>
</ul>

## 4 Investigation:

<ul>
  <li>Trace any clicks on the phishing link using Azure Sentinel logs.</li>
  <li>Identify if any credentials were compromised.</li>
</ul>

## 5 Remediation:

<ul>
  <li>Require password resets for affected users.</li>
  <li>Delete phishing emails from all mailboxes.</li>
</ul>

## 6 Documentation:

<ul>
  <li>Record details of the phishing attack, impacted users, and remediation steps.</li>
  
</ul>


## 7 Escalation:

<ul>
  <li> Escalate if the phishing attack involves multiple users or is part of a larger campaign.</li>
</ul>

## 8 User Education:

<ul>
  <li> From proofpoint or any other source provide additional phishing awareness training to the affected users.</li>
</ul>


# Response Timeframe:
High-severity alerts must be responded to within 15 minutes.


<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>




# Malware

# Overview

Respond to malware detections to prevent the spread of malicious software across the network.

# Steps:

## 1 Receive Malware Alert:

<ul>
  <li>Malware alerts are generated by Microsoft Defender XDR and Azure Sentinel.</li>
 
</ul>

## 2 Initial Containment:

<ul>
  <li> Isolate the infected device from the network.</li>
  <li> Block the file hash or IP associated with the malware.</li> 
</ul>


## 3 Investigation:

<ul>
  <li>Identify the malware type and its entry point.</li>
  <li>Analyze logs in Azure Sentinel for further signs of compromise.</li>
</ul>

## 4 Remediation:

<ul>
  <li>Run a full malware scan on the infected device.</li>
  <li>Remove any malicious files and ensure the system is clean.</li>
</ul>

## 5 Documentation:

<ul>
  <li>Document the malware type, how it was detected, and remediation actions taken.</li>
</ul>


## 6 Escalation:

<ul>
  <li> Escalate if the malware has spread to multiple devices or is part of a targeted attack..</li>
</ul>



# Response Timeframe:
High-severity alerts must be responded to within 10 minutes.


<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>


# Insider Threats

# Overview

Detect and respond to threats originating from within the organization, such as malicious actions by employees.

# Steps:

## 1 Receive  Alert:

<ul>
  <li>Insider threat alerts may come from Digital Guardian, Azure Sentinel, or employee reports.</li>
 
</ul>

## 2 Initial Assessment:

<ul>
  <li> Analyze the nature of the activity (e.g., unauthorized data access, suspicious behavior).</li>
</ul>

## 3 Containment:

<ul>
  <li> Limit the individual’s access to sensitive resources.</li>
  <li> Monitor their activity closely using Azure Sentinel.</li>
</ul>


## 4 Investigation:

<ul>
  <li> Via their Manager conduct interviews if necessary..</li>
  <li> Analyze logs in Azure Sentinel for further signs of compromise.</li>
</ul>

## 5 Remediation:

<ul>
  <li>Revoke access to critical systems.</li>
  <li>Implement corrective actions based on findings (e.g., legal action, re-training).</li>
</ul>

## 6 Documentation:

<ul>
  <li>Record all investigative steps, evidence gathered, and the outcome.</li>
</ul>


## 7 Escalation:

<ul>
  <li> Escalate to SOC manager HR or legal teams if the threat is confirmed.</li>
</ul>


# Response Timeframe:
High-severity alerts must be responded to within 1 hour.


<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>





















