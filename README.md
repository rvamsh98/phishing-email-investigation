# phishing-email-investigation
# Office 365 Credential Harvesting Phishing Investigation

## Overview

This project documents the investigation of a phishing email campaign targeting Office 365 users.

The phishing email used an account termination theme to create urgency and redirected users to a Google Form designed to harvest credentials.

## Skills Demonstrated

- Phishing Email Analysis
- Email Header Analysis
- URL Investigation
- IOC Identification
- Threat Intelligence
- MITRE ATT&CK Mapping
- Incident Reporting

## Threat Summary

| Category | Details |
|-----------|-----------|
| Subject | CONFIRM TERMINATION |
| Severity | High |
| Threat Type | Credential Harvesting |
| Platform | Microsoft Office 365 |
| Delivery Method | Email |

## Investigation Process

1. Examined phishing email content
2. Identified social engineering indicators
3. Extracted and expanded embedded URLs
4. Investigated destination infrastructure
5. Analyzed phishing landing page
6. Collected Indicators of Compromise (IOCs)
7. Mapped findings to MITRE ATT&CK

## Key Findings

- Office 365 verification lure
- Credential harvesting attempt
- Google Forms abuse
- Urgency-based social engineering
- Potential compromised internal account

## MITRE ATT&CK

- T1566 – Phishing

## Indicators of Compromise

### Email

- Subject: CONFIRM TERMINATION

### Domains

- forms[.]gle
- docs[.]google[.]com

## Report

See the complete investigation report:

[Phishing Email Case Study](Phising%20Email%20Case%20Study.pdf)

## Author

Vamshi Ramavath

Cybersecurity Analyst | SOC Analyst Candidate
