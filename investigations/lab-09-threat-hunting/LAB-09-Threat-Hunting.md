# Lab 09 — Threat Hunting

## Objective

Perform a basic SOC L1 threat hunt in Wazuh by searching for repeated failed SSH authentication activity, narrowing the results, investigating a representative event, and documenting the conclusion.

## Hunting Question

Are there repeated failed SSH authentication attempts involving an invalid or non-existent username on the monitored Linux endpoint?

## Environment

- Wazuh Agent: ubuntuagent
- Agent IP: 192.168.56.101
- Test Source: 127.0.0.1
- Host: soc-agent

## Search Performed

- Initial search: fakeuser
- Narrowed search: Rule ID 5710

## Evidence

- Matching events: 4
- Username: fakeuser
- Rule ID: 5710
- Rule Level: 5
- Rule Description: sshd: Attempt to login using a non-existent user
- Time Range: September 17, 2026 @ 18:45:24.133 – September 18, 2026 @ 18:45:24.134
- Representative Wazuh Event Timestamp: September 18, 2026 @ 01:25:13.859
- Source IP: 127.0.0.1
- Decoder: sshd
- Location: journald

## Investigation

Four matching SSH authentication events involving the non-existent username "fakeuser" were identified during the threat hunt.

The events were reviewed for repetition, username, timestamps, source information, agent, and detection context.

The hunt was narrowed using Rule ID 5710, which identifies attempts to log in using a non-existent user.

## MITRE ATT&CK Context

- MITRE Technique: Password Guessing
- MITRE Technique: SSH
- MITRE Tactic: Credential Access
- MITRE Tactic: Lateral Movement

Wazuh associates Rule 5710 with Password Guessing and SSH.

## Timeline

- September 18, 2026 @ 01:25:13.859 — Representative invalid-user SSH authentication event

## SOC L1 Assessment

- Targeted account: fakeuser
- Host generating the events: soc-agent
- Agent: ubuntuagent
- Source IP: 127.0.0.1
- Matching events found: 4
- Detection rule: 5710
- Rule level: 5
- Activity expected in this lab: Yes

## Classification

True Positive detection — Authorized/Benign Lab Activity.

The activity was deliberately generated inside the controlled Enterprise SOC Home Lab.

## Response

No containment or Active Response was required because the activity was deliberately generated inside the controlled Enterprise SOC Home Lab.

## Lessons Learned

Threat hunting starts with a question and uses available telemetry to look for evidence.

A hunt can begin with a broad search such as "fakeuser" and become more specific using fields such as username, rule ID, source IP, agent, and time range.

This investigation demonstrated the SOC L1 workflow of searching telemetry, identifying repeated activity, narrowing the results, investigating a representative event, validating the evidence, classifying the activity, and documenting the finding.
