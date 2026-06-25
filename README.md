# Microsoft Sentinel Security Monitoring Lab

## Project Overview

This project demonstrates the deployment and configuration of Microsoft Sentinel for collecting, monitoring, and analyzing Windows Event Logs from a Windows 11 endpoint. The lab includes Azure Arc onboarding, Azure Monitor Agent deployment, Data Collection Rule configuration, log ingestion, KQL-based analysis, and analytics rule design.

## Technologies Used

- Microsoft Sentinel
- Azure Arc
- Azure Monitor Agent (AMA)
- Azure Monitor
- Log Analytics Workspace
- Kusto Query Language (KQL)
- Windows Event Logs

## Architecture

Windows 11 Laptop
→ Azure Arc
→ Azure Monitor Agent (AMA)
→ Data Collection Rule (DCR)
→ Log Analytics Workspace
→ Microsoft Sentinel
→ KQL Analysis & Threat Detection

## Implementation Steps

### 1. Azure Resource Setup

- Created Resource Group (SOC-Lab)
- Created Log Analytics Workspace (SOC-Workspace)
- Enabled Microsoft Sentinel

### 2. Endpoint Onboarding

- Connected Windows 11 laptop using Azure Arc
- Successfully onboarded endpoint to Azure
- Verified Azure Arc machine connectivity

### 3. Agent Deployment

- Installed Azure Monitor Agent (AMA)
- Verified successful extension deployment
- Connected endpoint to monitoring infrastructure

### 4. Data Collection Configuration

Created Data Collection Endpoint (DCE)

- SOC-DCE

Created Data Collection Rule (DCR)

- windows-security-logs

Configured collection of:

- Security Audit Success Events
- Security Audit Failure Events
- System Error Events
- System Warning Events

### 5. Log Ingestion

Successfully collected Windows Event Logs into Microsoft Sentinel through Azure Monitor Agent and Data Collection Rules.

### 6. KQL Queries and Log Analysis

#### View Security Events

• Event | where EventLog == "Security" | take 20

• Event | summarize Count=count() by Source | sort by Count desc

• Event | summarize Count=count() by EventLevelName

• Event | summarize Count=count() by Source | sortby Count desc

• Event | summarize Count=count() by EventID | sort by Count desc

• Event | where EventID == 4672 | take 20

• Event | where EventID == 4624 | take 20

• Event | where EventID == 4625 | take 20
