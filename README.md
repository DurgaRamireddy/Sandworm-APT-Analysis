# Sandworm APT - Threat Intelligence Analysis

A structured cyber threat intelligence report analyzing the Sandworm APT group's campaigns against Ukraine's power grid (2015, 2016, 2022) reconstructing multi-stage attack sequences, mapping adversary TTPs to MITRE ATT&CK, and extracting defensive lessons for critical infrastructure security.

📄 [Full Analysis Report (PDF)](Sandworm_APT_Analysis_Paper.pdf)

---

## Threat Actor Profile

| Attribute | Details |
|---|---|
| Group | Sandworm Team |
| Sponsor | Russian GRU Unit 74455 |
| Target Sector | Critical Infrastructure (Energy / ICS / OT) |
| Notable Malware | BlackEnergy, Industroyer (CrashOverride), CaddyWiper |
| First Confirmed Impact | December 2015 — Ukraine power outages |

---

## Attack Timeline

| Year | Event | Impact |
|---|---|---|
| 2015 | BlackEnergy + SCADA manipulation | 230,000+ customers lost power |
| 2016 | Industroyer automates substation attacks | First malware built for ICS disruption |
| 2022 | LotL techniques + CaddyWiper during active conflict | Power facility disrupted alongside missile strikes |

---

## Attack Lifecycle & MITRE ATT&CK Mapping

### 2015 Attack Chain

| Stage | Technique | MITRE ID |
|---|---|---|
| Initial Access | Spear-phishing with malicious attachment | T1566.001 |
| Execution | BlackEnergy malware deployment | T1204.002 |
| Credential Access | Credential harvesting | T1003 |
| Lateral Movement | Remote administration tools | T1021 |
| Impact | Remote SCADA manipulation, KillDisk wiper | T1489, T1485 |
| Defense Evasion | Telephone DDoS to disrupt outage reporting | T1498 |

### 2016 Attack Chain - Industroyer

Industroyer (CrashOverride) was the first malware purpose-built to speak native ICS protocols — eliminating the need for manual operator interaction.

| Capability | Detail |
|---|---|
| ICS Protocols Targeted | IEC 101, IEC 104, OPC DA |
| Function | Automated circuit breaker commands |
| Persistence Module | Scheduled tasks, backdoors |
| Wiper Module | Hindered recovery post-attack |

| Stage | MITRE ID |
|---|---|
| ICS Protocol Abuse | T0855 |
| Automated Attack Sequencing | T0858 |
| Inhibit Response Function | T0838 |

### 2022 Attack Chain - Living off the Land

| Stage | Technique | MITRE ID |
|---|---|
| Initial Access | SCADA hypervisor compromise | T1190 |
| Execution | Malicious ISO with MicroSCADA binary | T1204 |
| Impact | Circuit breaker manipulation | T0855 |
| Defense Evasion | CaddyWiper on IT infrastructure | T1485 |

**Key shift:** 2022 demonstrated a move away from custom malware toward living-off-the-land (LotL) techniques — using legitimate system tools to blend in with normal operations and evade detection.

---

## Key Vulnerabilities Exploited

| Weakness | Description |
|---|---|
| IT/OT Flat Networks | No segmentation between corporate and operational systems |
| Unauthenticated ICS Protocols | Modbus, DNP3 lack built-in encryption or authentication |
| Limited OT Visibility | No monitoring of industrial control traffic |
| Weak Incident Response | No ICS-specific playbooks or backup procedures |
| Credential Exposure | Domain credentials reused across IT and OT environments |

---

## Defensive Recommendations

**1. Network Segmentation**
Strict IT/OT separation is the single most impactful control. Once Sandworm breached corporate networks, flat architecture allowed direct reach to SCADA systems.

**2. ICS Protocol Monitoring**
Deploy monitoring for IEC 104, Modbus, and DNP3 traffic. Anomalous command sequences against substation equipment are detectable with the right visibility tools (e.g., Claroty, Dragos, Security Onion).

**3. SIEM & EDR Coverage**
Extend SIEM ingestion to OT network logs. EDR on engineering workstations can surface lateral movement before ICS systems are reached.

**4. Threat Intelligence Sharing**
Participation in ISACs (E-ISAC for energy sector) accelerates detection of emerging Sandworm TTPs before they reach your environment.

**5. ICS Incident Response Playbooks**
Maintain backup manual procedures for substation operations — the 2015 attack succeeded partly because operators had no fallback when SCADA was taken offline.

---

## Key Takeaway

The most consistent enabler across all three attacks was **poor IT/OT segmentation**. Once Sandworm gained a foothold in corporate networks, the path to operational systems was largely unobstructed. Traditional IT security failures cascaded directly into physical infrastructure disruption which is a pattern that remains relevant for any organization running industrial control systems today.

---

## Skills Demonstrated

`Threat Intelligence` `APT Analysis` `ICS/OT Security` `MITRE ATT&CK Mapping` `Critical Infrastructure Security` `Cyber Warfare Research` `Attack Reconstruction` `Defensive Recommendations`

---

## Research Sources

- MITRE ATT&CK - Ukraine Electric Power Attack Campaigns
- CISA Advisory AA22-076A - Destructive Malware Targeting Ukrainian Organizations
- Recorded Future - Sandworm Threat Intelligence Reporting
- WIRED - Analysis of Sandworm Operations

---

> This analysis was conducted using publicly available threat intelligence. Developed as part of academic coursework and expanded for cybersecurity portfolio demonstration.

**Author:** Durga Sai Sri Ramireddy | MS Cybersecurity, University of Houston  
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0072b1?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/durga-ramireddy)
[![GitHub](https://img.shields.io/badge/-GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/DurgaRamireddy)
