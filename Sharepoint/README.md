# SharePoint Honeypot Security Monitoring and Incident Investigation

This project documents the deployment and monitoring of a Windows
Server 2016 SharePoint honeypot in a controlled lab environment.

Windows Event Logs, Sysmon, IIS logs, and network telemetry were
forwarded to Splunk for security monitoring. The investigation identified
RDP brute-force activity, suspicious tool execution, successful remote
access, and outbound network connections.

## Objectives

- Deploy a realistic SharePoint honeypot.
- Centralize Windows, Sysmon, IIS, and network logs in Splunk.
- Detect suspicious authentication and process activity.
- Investigate incidents using an incident-response workflow.
- Develop reusable Splunk detection queries.

## Lab Architecture

| Component | Purpose |
|---|---|
| Windows Server 2016 | SharePoint honeypot |
| SharePoint 2016 | Exposed application |
| Sysmon | Process and network telemetry |
| Splunk Universal Forwarder | Log forwarding |
| Splunk | Log analysis and detection |
| Active Directory | Authentication environment |

![Lab Architecture](Honeypot/images/Honeypotarchitecture.png)

## Data Sources

- Windows Security Event Logs
- Sysmon Operational Logs
- IIS Access Logs
- SharePoint application logs
- Splunk indexes
- Network connection telemetry

