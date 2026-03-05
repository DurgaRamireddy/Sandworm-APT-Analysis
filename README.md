# Sandworm-APT-Analysis

## Overview
This project analyzes the cyber operations conducted by the Russian state-sponsored threat group Sandworm Team, which is linked to GRU Unit 74455. The analysis focuses on the group's cyberattacks against Ukraine’s power grid in 2015, 2016, and 2022, which represent the first confirmed cyber operations that caused real-world power outages. These incidents demonstrate how Advanced Persistent Threats (APTs) can target critical infrastructure and create physical consequences through cyber means.

This report examines the attack methodology, malware used, infrastructure weaknesses exploited, and defensive lessons for organizations operating Industrial Control Systems (ICS).

## Key Events Analyzed

**2015 Ukraine Power Grid Attack**
On December 23, 2015, attackers compromised three energy distribution companies and remotely shut down electrical substations, leaving over 230,000 people without power.

## Attack Characteristics
- Initial access through spear-phishing
- Deployment of BlackEnergy
- Credential harvesting and lateral movement
- Remote manipulation of SCADA systems
- Use of KillDisk to wipe operator workstations
- Telephone DDoS attack to disrupt outage reporting

## 2016 Ukraine Power Grid Attack
In December 2016, attackers launched another power disruption using a more advanced ICS-focused malware.

**Malware Used**
- Industroyer (also known as CrashOverride)
**Capabilities**
- Direct communication with industrial protocols:
    - IEC 101
    - IEC 104
    - OPC DA
- Automated command execution against substation equipment
- Built-in wiper module to hinder recovery
This attack demonstrated automated ICS manipulation, increasing the scale and efficiency of cyber operations against infrastructure.

## 2022 Power Grid Attack
In October 2022, during the Russia-Ukraine war, Sandworm conducted another cyberattack against a Ukrainian power facility while missile strikes targeted infrastructure.
**Key Techniques**
- Compromise of SCADA hypervisor
- Deployment of malicious ISO containing MicroSCADA control binary
- Circuit breaker manipulation
- Deployment of CaddyWiper on IT infrastructure
This operation showed a shift toward living-off-the-land techniques, where attackers used legitimate system tools instead of custom malware.

## Attack Lifecycle

Typical Sandworm attack chain observed across incidents:
**1. Initial Access**
- Spear-phishing emails
- Exploitation of vulnerabilities
**2. Persistence**
- Scheduled tasks
- Credential harvesting
- Backdoors 
**3. Lateral Movement**
- Remote administration tools
- Domain credential abuse 
**ICS Manipulation**
- SCADA command execution
- Circuit breaker shutdown 
**5. Impact**
- Power outages
- Destruction of recovery systems
- Operational disruption

## Key Vulnerabilities Exploited
The attacks succeeded due to several systemic weaknesses:
- Poor segmentation between IT and OT networks
- Legacy ICS protocols without authentication
- Limited monitoring of industrial control traffic
- Insufficient incident response capabilities
- Lack of visibility into lateral movement\
Protocols such as Modbus and DNP3 lack built-in encryption and authentication, making them easier to manipulate.

## Defensive Lessons for Organizations
**1. Network Segmentation**
Strict separation between IT and OT networks reduces the risk of malware reaching industrial systems.
**2. Continuous Monitoring**
Organizations should deploy:
- SIEM platforms
- EDR solutions
- ICS protocol monitoring tools
Monitoring traffic involving protocols such as IEC 104 can reveal early reconnaissance or manipulation attempts.
**3. Infrastructure Hardening**
- Patch vulnerable systems
- Disable unused ports and services
- Update firmware in ICS devices 
**4. Incident Response Planning**
Critical infrastructure organizations should maintain:
- ICS-specific response playbooks
- Backup operational procedures
- Cyber incident simulation exercises
**5. Threat Intelligence Integration**
Participation in threat intelligence sharing communities (such as ISACs) helps organizations detect emerging attack patterns faster.  

## Strategic Impact
Sandworm’s campaigns changed how the cybersecurity community views cyber warfare. These incidents demonstrated that cyberattacks can move beyond data theft and cause direct physical disruption to national infrastructure. The attacks forced governments and critical infrastructure operators worldwide to reconsider the security of industrial control systems.

## Skills Demonstrated
This project demonstrates:
- Threat actor analysis
- Critical infrastructure security analysis
- Industrial Control System (ICS) threat modeling
- APT campaign analysis
- Cyber warfare case study research

## References
- MITRE ATT&CK – Ukraine Electric Power Attack Campaigns
- WIRED – Analysis of Sandworm operations
- Recorded Future – Threat intelligence reporting
- Reuters – Coverage of cyber warfare investigations
