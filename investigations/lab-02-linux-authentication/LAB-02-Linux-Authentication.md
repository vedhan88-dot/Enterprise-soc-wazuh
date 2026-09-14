# LAB 02 — Linux Authentication Monitoring & Investigation

## Objective
Detect and investigate repeated failed SSH authentication attempts on a Linux endpoint using Wazuh.

## Lab Environment
- SIEM: Wazuh
- Endpoint: soc-agent
- Operating System: Ubuntu Linux
- Test Account: fakeuser
- Source IP: 127.0.0.1

## Activity Generated
I generated multiple controlled failed SSH login attempts against my own Linux endpoint using the nonexistent account `fakeuser`.

## Evidence
Linux authentication logs recorded the failed login attempts, and Wazuh detected the authentication activity.

## Investigation
- Endpoint: soc-agent
- Username: fakeuser
- Source IP: 127.0.0.1
- Event: Failed SSH authentication
- Timestamp: [Sep 14, 2026 @ 19:04:04.8...]
- Rule/Alert: [Rule/Alert: sshd: Attempt to login using a non-existent user (Rule ID: 5710)]
- Severity: [Level 5]

## Timeline
1. Failed SSH login attempt generated.
2. Additional failed login attempts generated.
3. Linux authentication logs recorded the failures.
4. Wazuh collected and detected the activity.
5. SOC L1 investigation performed.

## Classification
**True Positive detection — Authorized/Benign Lab Activity**

The detection is a True Positive because the failed authentication activity actually occurred. It was authorized because I intentionally generated the activity as part of this lab.

## Response
No containment required because this was a controlled lab test.

## Lessons Learned
Authentication logs and SIEM alerts provide useful evidence for identifying repeated login failures.

## Evidence Screenshots
Screenshots demonstrate:
1. Linux authentication evidence
2. Wazuh authentication alert
3. Wazuh event details
