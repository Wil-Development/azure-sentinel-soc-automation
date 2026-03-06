# Azure Sentinel SOC Automation

## Overview

This project demonstrates how to build a Microsoft Sentinel automation playbook that enriches security incidents with additional investigation data.

The playbook automatically queries multiple Azure log sources and posts a structured investigation summary into the incident timeline to assist SOC analysts during triage.

---

## Project Goal

Security analysts often need to manually gather context during investigations. This project automates that process by retrieving relevant security telemetry when an incident is triggered.

The playbook enriches incidents using:

- Azure Activity Logs
- Security Alerts
- Azure Diagnostics

The results are automatically posted to the incident activity log.

---

## Playbook Workflow

1. Microsoft Sentinel Incident Trigger
2. Retrieve Incident Details
3. Query Azure Activity Logs
4. Validate Results
5. Query Security Alerts
6. Validate Results
7. Query Azure Diagnostics
8. Generate HTML investigation tables
9. Post investigation summary into incident activity

---

## Example Incident Enrichment Output

The playbook automatically posts an investigation summary directly into the Sentinel incident activity timeline.

![Incident Enrichment Output][screenshots/sentinel-incident-enrichment-output1.png]

---

## Technologies Used

Microsoft Sentinel  
Azure Logic Apps  
Kusto Query Language (KQL)  
Azure Log Analytics  

---

## Key Skills Demonstrated

SOC automation  
Security investigation with KQL  
Microsoft Sentinel playbook development  
Cloud security monitoring  
Incident enrichment automation  
Security telemetry analysis  

---

## Challenges Encountered

During development several issues were identified and resolved:

Logic App validation errors due to incorrect dynamic content references.

Incorrect KQL fields in SecurityAlert queries.

Missing log data due to diagnostic logging configuration.

These issues were resolved by validating schema fields in Log Analytics and implementing conditional automation logic.

---

## Lessons Learned

Security automation workflows require validation logic to ensure reliable execution.

KQL schemas differ across log tables and should always be verified.

Automation can significantly reduce manual investigation effort for SOC analysts.

---

## Future Improvements

IP reputation enrichment using threat intelligence sources.

Automatic tagging of incidents.

SOC notification integration with Microsoft Teams.

User risk enrichment using identity logs.

---

## Repository Structure

```
azure-sentinel-soc-automation
│
├─ screenshots
├─ queries
├─ architecture
└─ README.md
```
## Architecture

The following diagram shows the incident enrichment workflow implemented using Microsoft Sentinel and Azure Logic Apps.

[![Architecture](architecture/sentinel-playbook-architecture.png)](https://github.com/Wil-Development/azure-sentinel-soc-automation/blob/main/architecture/sentinel-playbook-architecture.png.png)
