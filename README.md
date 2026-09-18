# Enterprise SOC Home Lab

A hands-on Security Operations Center (SOC) home lab built with Wazuh to practice security monitoring, detection, investigation, threat hunting, MITRE ATT&CK mapping, vulnerability management, security configuration assessment, and automated response.

## 🎯 Project Goal

The goal of this project is to develop practical SOC Analyst L1 / Blue Team skills by investigating security events in a controlled virtual environment.

## 🛠️ Technologies Used

- Wazuh
- Wazuh SIEM
- Ubuntu Linux
- SSH
- VirtualBox
- Linux system logs
- MITRE ATT&CK
- Vulnerability Detection
- Security Configuration Assessment
- Active Response
- Threat Hunting

## 🖥️ Lab Environment

### Wazuh Manager

- Operating System: Ubuntu
- Role: Wazuh Manager / Dashboard

### Wazuh Agent

- Hostname: soc-agent
- Agent Name: ubuntuagent
- IP Address: 192.168.56.101
- Operating System: Ubuntu Linux

## 🔎 SOC Investigation Workflow

This project follows a basic SOC L1 workflow:

1. Generate security activity
2. Detect the activity
3. Triage the alert
4. Investigate the event
5. Correlate evidence
6. Map activity to MITRE ATT&CK
7. Classify the activity
8. Determine response
9. Document the investigation

## 🧪 Investigations

| Lab | Investigation |
|---|---|
| Lab 01 | File Integrity Monitoring |
| Lab 02 | Linux Authentication |
| Lab 03 | SSH Brute-Force |
| Lab 04 | Suspicious User Creation |
| Lab 05 | Linux Log Investigation |
| Lab 06 | Vulnerability Detection & Remediation |
| Lab 07 | Security Configuration Assessment |
| Lab 08 | MITRE ATT&CK Mapping |
| Lab 09 | Threat Hunting |
| Lab 10 | Active Response |
| Lab 11 | Multi-Event Incident Investigation |
| Lab 12 | Final SOC L1 Capstone |

## 📂 Repository Structure

```text
Enterprise-soc-wazuh/
│
├── README.md
│
├── screenshots/
│
└── investigations/
    ├── lab-01/
    ├── lab-02/
    ├── lab-03/
    ├── lab-04/
    ├── lab-05-linux-log-investigation/
    ├── lab-06-vulnerability-detection-remediation/
    ├── lab-07-security-configuration-assessment/
    ├── lab-08-mitre-attck-mapping/
    ├── lab-09-threat-hunting/
    ├── lab-10-active-response/
    ├── lab-11-multi-event-incident-investigation/
    └── lab-12-final-soc-l1-capstone/
