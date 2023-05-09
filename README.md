# Azure-SOC-Honeynet-Project (Live Traffic)

![Cloud Honeynet / SOC](https://i.imgur.com/S6whvfs.png)

## Introduction
This project will consists of creating my very own honeynet on Microsoft Azure that will entice attackers, log and monitor malicious traffic generated from these attacks, perform incident response, and implement hardening controls to secure the enivronment.  

## Objectives
The main objective of this project is to create a honeynet that will allow me to analyze live cyberattacks, conduct incident response and investigate event alerts, study attackers to understand their intentions, tactics, techniques, and procedures.  The second objective is to transform the unsecure environment into a secure environment by re-configuring the firewall, NGS, implementing Azure Private Links, and administering regulatory compliance, such as, NIST 800-53, PCI DSS. CIS, and Microsoft Defender for Cloud recommendations.  


## Before Hardening

![Before](https://i.imgur.com/VRXMAtr.png)

## After Hardening

![After](https://i.imgur.com/pwJqFZt.png)

## Technologies, Regulations, and Azure Components Employed:

- Virtual Network (VNet)
- Network Security Group (NSG)
- Virtual Machines (2 windows, 1 linux)
- Log Analytics Workspace for performing Kusto Query (KQL) queries to filters data
- Azure Key Vault to securely store secrets 
- Azure Storage Account for storing data 
- Microsoft Sentinel for Security Information and Event Management (SIEM)
- Microsoft Defender for Cloud to monitor resources and ingest logs from virtual machines into Log Analytic Workspace
- Powershell for performing simulated attacks
- Command Line Interface (CLI) to verify connection to virtual machine
- Windows Remote Desktop to remotely connect to virtual machines

## Phase I - Creating The Honeynet 
In this phase, I created a Windows virtual machine.  Afterward, I  intentionally configured the firewall and NGS to allow all traffics from all ports. Additionally, I disabled everything in Microsoft Defender Firewall.  This created the vulnerable internet facing environment that will attract attackers.  

![Firewallrule](https://i.imgur.com/QNfVI72.jpg)

![Firewallrule](https://i.imgur.com/G3LRDMW.jpg)

## Phase II - Simulated Attacks & Logging and Monitoring
In this phase, simulated attacks were executed using Powershell to manually trigger events.  These simulated attacks consist of Brute Force Attempt, Malware(EICAR Test File), AAD Brute Force Success, Privilege Escalation, Windows Brute Force Success.  Afterward, I utilized KQL queries to filter data from different logs to analyze these triggered events performed by me and also alerts from actual attackers.  

SignInLogs for invalid username or password event alerts

![Firewallrule](https://i.imgur.com/9qKPvnG.jpg)

![Firewallrule](https://i.imgur.com/9A449Il.jpg)

SecuityEvent logs display brute force attacks against Windows virtual machines 

![Firewallrule](https://i.imgur.com/CyT6QZq.jpg)

![Firewallrule](https://i.imgur.com/y8sQDD1.jpg)

Syslog display failed password against Linux virtual machine

![Firewallrule](https://i.imgur.com/IsEDYY7.jpg)

## Phase III - Analysis & Incident Assessment and Response

## Phase IV - Remediation & Regulatory Compliance Implementation

## Phase V - Results & Metrics Comparison
![Firewallrule](https://i.imgur.com/cOUAHuU.jpg)
![Firewallrule](https://i.imgur.com/WZXK54D.jpg)
![Firewallrule](https://i.imgur.com/YNxOFvV.jpg)
![Firewallrule](https://i.imgur.com/rQITjvQ.jpg)

## Reflection



## Conclusion
