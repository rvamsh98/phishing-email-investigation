# phishing-email-investigation
# Office 365 Credential Harvesting Phishing Investigation

## Executive Summary

This project documents the investigation of a phishing email campaign targeting Microsoft Office 365 users. The phishing email used an account termination theme to create urgency and trick recipients into verifying their accounts.

Investigation revealed that the embedded hyperlink redirected users to a Google Forms page impersonating an IT Help Desk portal. The form requested Office 365 credentials and additional personal information, indicating a credential harvesting and information gathering campaign.

The incident was later confirmed as malicious by the University of New Haven Information Technology Department, which removed the email from affected mailboxes and initiated remediation actions.

---

## Incident Overview

| Category | Details |
|-----------|-----------|
| Subject | CONFIRM TERMINATION |
| Threat Type | Credential Harvesting |
| Severity | High |
| Delivery Method | Email |
| Target Platform | Microsoft Office 365 |
| Date Observed | June 3, 2026 |

---

## Investigation Objectives

- Analyze the phishing email
- Review email authentication indicators
- Investigate embedded URLs
- Analyze the destination landing page
- Identify Indicators of Compromise (IOCs)
- Determine attacker objectives
- Map activity to MITRE ATT&CK
- Document findings and remediation recommendations

---

## Investigation Methodology

### 1. Email Analysis

The phishing email claimed that the recipient's Office 365 account required verification to avoid account termination.

Observed phishing indicators included:

- Fear and urgency-based language
- Threat of account closure
- Request for account verification
- Generic messaging
- Suspicious hyperlink

---

### 2. Email Header Analysis

Authentication review identified missing email security controls:

**Authentication Results**

- DKIM: None
- DMARC: None

**Exchange Headers**

- X-MS-Exchange-Organization-AuthAs: Internal
- X-MS-Exchange-CrossTenant-AuthAs: Internal

These indicators suggested the message may have originated from an authenticated internal Microsoft 365 account, potentially indicating account compromise.

---

### 3. URL Analysis

#### Embedded URL

```text
hxxps://forms[.]gle/16PMRGhmVbrD12ZR9
```

#### Expanded URL

```text
hxxps://docs[.]google[.]com/forms/d/e/1FAIpQLSfNdIi6Wv_cJIpOYnTE27dZ7PZsm7sI8pE516FA4_8FDeLENw/viewform
```

### URLScan Findings

- Hosted on Google infrastructure
- Valid TLS certificate
- Legitimate domain reputation
- No infrastructure-based indicators of compromise

Despite the legitimate hosting platform, further analysis showed the destination was being abused for credential collection.

---

### 4. Landing Page Analysis

The destination page was titled:

```text
IT HELP DESK
```

The form requested users to authenticate before accessing the form contents.

#### Credential Collection Fields

- Office365 School Email
- Password (PWD)

#### Additional Data Collection

- Name
- Phone Number
- Previous University/College Attended
- Previous University Email Address

A significant finding was the mismatch between the email's Office 365 verification claim and the Google Forms destination.

This is a common phishing technique used to steal credentials while leveraging trusted cloud platforms.

---

## Indicators of Compromise (IOCs)

### Email Indicators

| Indicator Type | Value |
|----------------|--------|
| Subject | CONFIRM TERMINATION |
| Sender Email | e@unh.newhaven.edu |
| Display Name | Medina, Eziyon D |

### URL Indicators

```text
hxxps://forms[.]gle/16PMRGhmVbrD12ZR9
```

```text
hxxps://docs[.]google[.]com/forms/d/e/1FAIpQLSfNdIi6Wv_cJIpOYnTE27dZ7PZsm7sI8pE516FA4_8FDeLENw/viewform
```

### Domain Indicators

```text
forms[.]gle
docs[.]google[.]com
```

### Credential Collection Indicators

- Office365 School Email
- Password (PWD)

---

## Social Engineering Techniques Observed

- Account termination threat
- Urgency-based messaging
- Office 365 verification lure
- IT support impersonation
- Trust abuse through Google Forms
- Credential harvesting

---

## MITRE ATT&CK Mapping

### Credential Access

| Technique ID | Technique |
|-------------|-----------|
| T1566 | Phishing |

### Possible Adversary Objectives

- Credential Harvesting
- Information Gathering
- Account Compromise

---

## Key Findings

- The phishing email leveraged fear and urgency to influence user behavior.
- The attacker abused Google Forms to collect credentials.
- The phishing lure impersonated an IT Help Desk service.
- Users were asked to provide Office 365 usernames and passwords.
- Additional personal information was collected.
- The campaign was confirmed malicious through organizational remediation actions.

---

## Remediation Actions

1. Remove phishing emails from affected mailboxes.
2. Reset passwords for affected users.
3. Revoke active user sessions.
4. Investigate the sender account for compromise.
5. Review authentication logs for suspicious activity.
6. Block or monitor identified phishing URLs.
7. Conduct user awareness training.

---

## Lessons Learned

- Trusted domains do not guarantee trusted content.
- Google Forms can be abused for phishing campaigns.
- Credential harvesting attacks frequently leverage legitimate cloud services.
- Internal accounts may be abused if compromised.
- URL expansion and landing page analysis are critical during phishing investigations.

---

## Tools Used

- Microsoft Outlook
- URLScan.io
- Google Forms Analysis
- Microsoft 365 Email Header Review
- MITRE ATT&CK Framework

---

## Skills Demonstrated

- Phishing Email Analysis
- Email Header Analysis
- Threat Hunting
- URL Investigation
- IOC Extraction
- Threat Intelligence Analysis
- Incident Response
- Security Documentation
- MITRE ATT&CK Mapping

---

## Report

Full Investigation Report:

[Phishing Email Case Study](Phising%20Email%20Case%20Study.pdf)

---

## Author

Vamshi Ramavath

Cybersecurity Analyst | SOC Analyst Candidate


Vamshi Ramavath

Cybersecurity Analyst | SOC Analyst Candidate
