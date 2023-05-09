# Azure-SOC-Honeynet-Project (Live Traffic)

![Cloud Honeynet / SOC](https://i.imgur.com/S6whvfs.png)

## Introduction
This project will consist of creating my very own honeynet on Microsoft Azure that will entice attackers, log and monitor malicious traffic generated from these attacks, perform incident response, and implement hardening controls to secure the environment. 

## Objectives
The main objective of this project is to create a honeynet that will allow me to analyze live cyberattacks, conduct incident response and investigate event alerts, and study attackers to understand their intentions, tactics, techniques, and procedures. The second objective is to transform the unsecure environment into a secure environment by re-configuring the firewall, NGS, implementing Azure Private Links, and administering regulatory compliance, NIST 800-53, and Microsoft Defender for Cloud recommendations.


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
In this phase, I created a Windows virtual machine. Afterward, I intentionally configured the firewall and NGS to allow all traffic from all ports. Additionally, I disabled everything in Microsoft Defender Firewall. This created a vulnerable internet-facing environment that will attract attackers.

![Firewallrule](https://i.imgur.com/QNfVI72.jpg)

## Phase II - Simulated Attacks & Logging and Monitoring
In this phase, simulated attacks were executed using Powershell to manually trigger events. These simulated attacks consist of Brute Force Attempts, Malware(EICAR Test File), AAD Brute Force Success, Privilege Escalation, and Windows Brute Force Success. Afterward, I utilized KQL queries to filter data from different logs to analyze these triggered events and alerts from actual attackers.

SignInLogs for invalid username or password event alerts

![Firewallrule](https://i.imgur.com/9qKPvnG.jpg)

![Firewallrule](https://i.imgur.com/9A449Il.jpg)

SecuityEvent logs display brute force attacks against Windows virtual machines 

![Firewallrule](https://i.imgur.com/CyT6QZq.jpg)

![Firewallrule](https://i.imgur.com/y8sQDD1.jpg)

Syslog display failed password against Linux virtual machine

![Firewallrule](https://i.imgur.com/IsEDYY7.jpg)

## Phase III - Analysis & Incident Assessment and Response
In this phase of the project, I assessed several incidents that were generated during the 24 hours of running the insecure environment. For each incident, I analyzed information about the entities that were responsible for these attacks, such as IP address, the tactics, and techniques they used, the type of attack they performed, and the timeline of each attack, and I investigated further into the entity IP address to inspect any related alerts determine whether the incident was a true positive or a false positive.

![Firewallrule](https://i.imgur.com/MEIisRs.jpg)

![Firewallrule](https://i.imgur.com/m8J3GEt.jpg)

## Phase IV - Remediation & Regulatory Compliance Implementation

After I finished analyzing these incidents, I took action to secure this environment. Security controls I implemented consisted of disabling public access to the virtual machines and blob storage account, I created private endpoints for the storage account and virtual machine, an additional network security group was created to protect the subnet, and a NSG rule was generated for these virtual machines to only allow traffic from my own IP address source, and private links were enabled to keep key vault safe. These security protocols were implemented following the NIST 800-53 regulatory compliance standards.

An NSG contains a set of security rules that allow or deny inbound or outbound network traffic based on protocol, source IP address, destination IP address, and port number. This strengthens network traffic control, enhances the protection of resources, and prevents authorized access to resources.
A private endpoint is a network interface that enforces security by allowing services to be accessed through a private connection. This ensures access to these resources is only within this private virtual network and prevents traffic from being exposed to the public internet.


## Phase V - Results & Metrics Comparison
Results and metrics of both insecure and secure environments were measured and recorded to determine the effectiveness of implemented security controls.  

## Before Attack World Maps 

This attack world map displays attacks to the MSSQL Server


![Firewallrule](https://i.imgur.com/cOUAHuU.jpg)


This attack world map depicts the number of attacks targetted to the Linux virtual machine


![Firewallrule](https://i.imgur.com/WZXK54D.jpg)

This attack world map accentuates how many attacks the Windows virtual machine encountered
![Firewallrule](https://i.imgur.com/YNxOFvV.jpg)


This attack world world represents the large influx of malicious traffic resulted from insecure environment 

![Firewallrule](https://i.imgur.com/rQITjvQ.jpg)

## Reflection
 have learned so much while doing this project. This project has really reinforced the importance of security. It is crucial to have correct security controls and configurations to protect in place your resources. As the before and after metrics highlight the drastic difference between an insecure and a secure environment, firewall rules, private endpoints, and not allowing public internet access need to be implemented to prevent disastrous consequences caused by attacks and unauthorized access to valuable resources.

## Conclusion
In this project, I created a honeynet using Microsoft Azure. Afterward, I performed logging and monitoring for any attacks against these virtual machines. Additionally, I analyzed these incidents in further detail to understand tactics, techniques, and procedures being executed by attacks. Lastly, I hardened the environment by enforcing security controls following the regulatory compliance NIST 800-53.
