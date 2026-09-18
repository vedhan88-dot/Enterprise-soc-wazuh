# Lab 12 — Final SOC L1 Capstone

## Objective

Perform an end-to-end SOC L1 investigation using Wazuh by generating controlled activity, detecting the activity, triaging the alerts, investigating the evidence, correlating events, mapping the activity to MITRE ATT&CK, classifying the finding, and documenting the investigation.

## Environment

- Wazuh Manager: ubuntu
- Wazuh Agent: ubuntuagent
- Agent Host: soc-agent
- Agent IP: 192.168.56.101
- Source IP: 127.0.0.1

## Detection

A controlled SSH authentication test was performed using the non-existent username `fakeuser`.

Wazuh detected the activity using Rule 5710.

- Rule ID: 5710
- Rule Level: 5
- Rule Description: sshd: Attempt to login using a non-existent user
- Username: fakeuser
- Source IP: 127.0.0.1

## Triage

Multiple related events were identified in Wazuh Threat Hunting.

The events were reviewed using the username, agent, source IP, timestamps, rule ID, rule level, and rule description.

A total of 24 matching events were visible during the investigation.

## Investigation

The activity involved repeated failed SSH authentication attempts using the non-existent username `fakeuser`.

The Wazuh event details confirmed:

- Agent: ubuntuagent
- Agent IP: 192.168.56.101
- Source IP: 127.0.0.1
- Username: fakeuser
- Decoder: sshd
- Rule ID: 5710
- Rule Level: 5
- Rule Description: sshd: Attempt to login using a non-existent user
- Event Timestamp: September 18, 2026 @ 19:01:29

## Correlation

The events were correlated using the same monitored endpoint, username, source IP, SSH service, detection rule, and time sequence.

The activity was treated as one related investigation rather than separate unrelated alerts.

## MITRE ATT&CK Mapping

- Tactic: Credential Access
- Technique: T1110.001 — Password Guessing

Wazuh also associates the SSH activity with:

- Tactic: Lateral Movement
- Technique: T1021.004 — SSH

## Classification

True Positive detection — Authorized/Benign Lab Activity.

The activity was deliberately generated inside the controlled Enterprise SOC Home Lab.

## Response Decision

No additional containment was required because the activity was intentionally generated as part of the lab.

## Linux Authentication Evidence

A Linux authentication-log check was attempted on the monitored endpoint. Readable SSH authentication-log evidence was not captured, so no unsupported Linux log evidence is claimed.

## SOC L1 Investigation Summary

The investigation followed an end-to-end SOC L1 workflow:

1. Generate controlled activity
2. Detect the activity in Wazuh
3. Triage the alerts
4. Investigate event details
5. Correlate related events
6. Map the activity to MITRE ATT&CK
7. Classify the detection
8. Document the investigation

## Lessons Learned

A SOC L1 analyst must be able to move from an alert to validated evidence and a documented conclusion.

This capstone demonstrated detection, triage, investigation, correlation, MITRE ATT&CK mapping, classification, and incident documentation using Wazuh.

## Evidence

- Wazuh Threat Hunting event list
- Wazuh Document Details
- Linux authentication-log check attempted; readable evidence was not captured

## Screenshots

1. Wazuh detection events
2. Wazuh event details
