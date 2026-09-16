# LAB 05 — Linux Log Investigation

## Objective

Investigate a controlled Linux authentication event using raw logs and Wazuh.

## Activity

- Test: SSH authentication using a non-existent user
- Username: fakeuser
- Host: soc-agent
- Source: 127.0.0.1

## Detection

- Rule ID: [5710]
- Rule description: [sshd: Attempt to login using non-existing user]
- Severity/Level: [5]
- Agent: ubuntuagent
- Timestamp: [sep 16, 2026 @ 18:42:41.3..]

## Investigation

Reviewed the raw Linux authentication log and correlated it with the corresponding Wazuh event.

## Classification

True Positive detection — Authorized/Benign Lab Activity.

## Response

No Active Response performed.

## Lessons Learned

Raw Linux logs provide evidence; Wazuh centralizes and analyzes security-relevant events.
