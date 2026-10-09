# 🛡️ Blue Team Cyber Incident Investigation | Trojan Mirage

**SOC Investigation • Malware Analysis • Network Traffic Analysis • SIEM • Incident Response**

A hands-on Blue Team security investigation of a simulated endpoint compromise involving a malicious Microsoft Word document, suspicious network connections, malicious executables, and a Remote Access Trojan (RAT).

The investigation focused on reconstructing the attack chain, identifying indicators of compromise (IOCs), analyzing endpoint and network activity, and determining appropriate containment and remediation actions.

---

## 🔎 Project Overview

A user reported unusual behavior on their workstation, including:

- Full-screen browser activity
- Repeated infection notifications
- Files reported as infected
- Modified desktop wallpaper
- Suspicious system behavior

The objective was to determine **what happened, how the compromise occurred, what systems or files were affected, and what actions should be taken to contain the threat.**

![Trojan Incident](Trojan%20image.png)

---

## 🎯 Investigation Objectives

The investigation focused on answering several core incident-response questions:

1. What triggered the suspicious activity?
2. What was the initial attack vector?
3. Which files and processes were involved?
4. Did the workstation communicate with suspicious external infrastructure?
5. Was there evidence of additional network compromise?
6. What indicators of compromise could be identified?
7. What containment and remediation actions were required?

---

## 🧰 Security Tools

| Tool | Investigation Use |
|---|---|
| **Splunk** | Log analysis, event correlation, and timeline investigation |
| **Security Onion** | Network security monitoring and traffic investigation |
| **Palo Alto Networks** | Firewall and network traffic analysis |
| **Windows Endpoint Data** | File, process, download, and system activity investigation |
| **Network Topology** | Identification of affected hosts and network relationships |

---

## 🔗 Attack Chain

The investigation connected activity across the endpoint, network, and security logs.

```text
Spear-Phishing Email
        │
        ▼
Malicious Word Document
        │
        ▼
Macro-Related Activity
        │
        ▼
Malicious File Execution
        │
        ▼
Reverse TCP / External Communication
        │
        ▼
Remote Access Trojan (RAT)
        │
        ▼
Endpoint Manipulation
        │
        ├── Full-screen warning messages
        ├── Desktop wallpaper modification
        └── Malicious process activity
```

This provided a working timeline for correlating events across multiple security data sources.

---

# 🔬 Investigation

## 1. Initial Endpoint Analysis

The investigation began by reviewing the affected workstation and examining the reported infection behavior.

![Infected Files](files.png)

![Warning Message](warning%20message.png)

Recent downloads and system changes were examined to identify activity surrounding the incident.

The investigation identified activity associated with an email and downloaded Word document. Timestamps and related events were then cross-referenced to establish the sequence of activity.

![Message Investigation](message.png)

---

## 2. Network Analysis

The network topology was reviewed to understand the workstation's connections and identify communications requiring further investigation.

![Network Topology](network%20topology.png)

This helped connect endpoint activity with network-level evidence and identify external IP addresses associated with the incident.

---

## 3. SIEM Investigation with Splunk

Splunk was used to investigate event data and correlate activity surrounding the suspected compromise.

The analysis focused on:

- Suspicious process activity
- Network connections
- File activity
- Event timestamps
- Relationships between endpoint and network events

![Splunk Investigation](splunk.png)

![Splunk Event Analysis](Splunk%202.png)

---

## 4. Network Security Monitoring with Security Onion

Security Onion was used to investigate network activity associated with the compromised workstation.

The analysis helped correlate network traffic with events identified during the endpoint and Splunk investigation.

![Security Onion Investigation](Security%20onion.png)

![Security Onion Network Analysis](Security%20onion2.png)

---

## 5. Firewall Investigation

Palo Alto Networks firewall data was reviewed to analyze communications associated with the affected workstation and suspicious external IP addresses.

![Palo Alto Network Investigation](palo%20alto%20network.png)

![Palo Alto Firewall Analysis](palo%20alto%202.png)

Firewall evidence was compared with findings from Splunk and Security Onion to build a broader picture of the incident.

---

# 🦠 Malware Analysis

The investigation identified activity associated with a Word document containing macro-related functionality capable of triggering additional malicious activity.

Analysis connected the document with:

- Reverse TCP communication
- Downloaded executable files
- Suspicious process execution
- A malicious executable masquerading as a Splunk forwarder
- Additional spawned processes
- Remote Access Trojan behavior

![Malware Finding](information%20-%20finding.png)

Rather than relying on a single alert, evidence from multiple sources was correlated to understand the relationship between the document, malicious processes, and network activity.

---

# 🚨 Key Findings

The investigation identified several important security findings:

- A malicious Word document was associated with the initial compromise.
- The activity originated from a targeted phishing scenario.
- Macro-related activity contributed to the malicious execution chain.
- Suspicious executable files were identified on the affected system.
- Reverse TCP communication was associated with the malicious activity.
- A Remote Access Trojan was disguised as a Splunk-related executable.
- Two suspicious external IP addresses were identified.
- Firewall logs were reviewed for evidence of additional movement or compromise.
- The available evidence did not identify further internal compromise.

---

# 🛡️ Incident Response and Remediation

Based on the investigation, the response actions included:

### Containment
- Block identified malicious external IP addresses.
- Remove malicious files from the affected workstation.
- Remove the malicious Word document and RAT-associated files.

### Investigation
- Correlate endpoint, SIEM, network-monitoring, and firewall evidence.
- Document the incident timeline.
- Review suspicious executable activity.
- Investigate network activity for evidence of additional compromise.

### Prevention
- Reinforce phishing and untrusted-download awareness.
- Review lessons learned from the incident.
- Evaluate security controls and policies that could reduce similar risks.

---

# 🧠 Skills Demonstrated

### Security Operations
- Security incident investigation
- Incident response
- Alert triage
- Event correlation
- Timeline reconstruction
- Indicator of compromise identification

### SIEM & Log Analysis
- Splunk
- Log investigation
- Event analysis
- Cross-source correlation

### Network Security
- Network traffic analysis
- Security Onion
- Firewall log analysis
- Palo Alto Networks
- IP investigation
- Reverse TCP analysis

### Endpoint & Malware Investigation
- Malicious document analysis
- Suspicious process investigation
- Remote Access Trojan investigation
- Malicious executable identification
- Attack-chain reconstruction

### Threat Investigation
- Phishing investigation
- IOC analysis
- Network and endpoint correlation
- Containment and remediation planning

---

# 📊 Investigation Summary

| Category | Finding |
|---|---|
| **Attack Vector** | Targeted phishing / malicious Word document |
| **Endpoint** | User workstation |
| **Malware Behavior** | Remote Access Trojan activity |
| **Network Activity** | Reverse TCP / suspicious external communication |
| **SIEM** | Splunk |
| **Network Monitoring** | Security Onion |
| **Firewall Analysis** | Palo Alto Networks |
| **Primary Evidence** | Endpoint, process, log, and network activity |
| **Response** | IOC blocking, malicious-file removal, documentation, prevention recommendations |

---

# 💡 What I Learned

This project strengthened my ability to approach a security incident from a Blue Team perspective rather than treating individual security alerts independently.

The most valuable part of the investigation was correlating multiple sources of evidence:

**endpoint activity → process execution → SIEM events → network traffic → firewall data**

This helped me practice building an incident timeline, identifying IOCs, tracing an attack chain, validating the scope of suspicious activity, and developing appropriate containment and remediation recommendations.

---

## 🏆 Certificate

Certificate earned after completing the investigation:

![Certificate](certificate%20earned%20.png)

---

## 🔐 Cybersecurity Focus

This project demonstrates hands-on experience relevant to:

`SOC Analyst` • `Security Operations` • `Cybersecurity Analyst` • `Incident Response` • `Blue Team` • `SIEM` • `Network Security` • `Threat Detection`

---

> **Note:** This repository documents a simulated cybersecurity training environment. The systems, malware activity, and incident investigation shown here were performed for authorized educational and defensive-security purposes.
