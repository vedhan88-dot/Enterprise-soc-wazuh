# Lab 08 — MITRE ATT&CK Mapping

## 1. Investigation Summary

- Source: Lab 03 — SSH Brute-Force Investigation
- Agent: ubuntuagent
- Agent IP: 192.168.56.101
- Activity: Repeated SSH authentication attempts
- Username observed: fakeuser

## 2. Evidence

- Wazuh Rule ID: 5710
- Rule Description: sshd: Attempt to login using a non-existent user
- Rule Level: 5
- Rule Fired Times: 3
- Decoder: sshd
- Source Information: 127.0.0.1
- Location: journald
- Original SSH Log Timestamp: September 17, 2026 @ 19:54:32
- Wazuh Event Timestamp: September 18, 2026 @ 01:25:13.859

## 3. MITRE ATT&CK Mapping

### Primary Mapping

- Tactic: Credential Access
- Technique: T1110.001 — Password Guessing

### Additional Wazuh Mapping

- Tactic: Lateral Movement
- Technique: T1021.004 — SSH

Wazuh associated the event with both T1110.001 — Password Guessing and T1021.004 — SSH.

## 4. Reason for Mapping

The event shows repeated SSH authentication attempts using the non-existent username "fakeuser" in the controlled Enterprise SOC Home Lab environment.

The observed authentication behavior maps to MITRE ATT&CK T1110.001 — Password Guessing.

Wazuh also associates the event with T1021.004 — SSH because SSH was the remote service involved in the authentication activity.

## 5. Classification

True Positive — Authorized/Benign Lab Activity

## 6. Analyst Note

The activity was intentionally generated as part of the Enterprise SOC Home Lab.

The investigation demonstrates the SOC workflow of reviewing security evidence, validating the observed behavior, mapping the behavior to MITRE ATT&CK, and documenting the finding.

## 7. MITRE ATT&CK Summary

| Field | Value |
|---|---|
| Primary Tactic | Credential Access |
| Primary Technique | T1110.001 — Password Guessing |
| Additional Tactic | Lateral Movement |
| Additional Technique | T1021.004 — SSH |
| Wazuh Rule | 5710 |
| Severity Level | 5 |
| Agent | ubuntuagent |
| Source | 127.0.0.1 |
