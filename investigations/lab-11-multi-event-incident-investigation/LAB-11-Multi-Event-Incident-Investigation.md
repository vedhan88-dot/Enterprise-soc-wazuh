# Lab 11 — Multi-Event Incident Investigation

## Objective

Investigate multiple related Wazuh events as one activity sequence, build a timeline, correlate the evidence, classify the activity, and document the investigation.

## Affected Host

- Agent: ubuntuagent
- Agent IP: 192.168.56.101

## Activity

- Service: SSH
- Username: fakeuser
- Source IP: 127.0.0.1
- Wazuh Rule ID: 5710
- Rule Level: 5
- Rule Description: sshd: Attempt to login using a non-existent user

## Evidence Sources

- Wazuh Threat Hunting events
- Wazuh event/document details
- Linux authentication log check attempted; readable endpoint log evidence was not captured

## Timeline

- September 18, 2026 @ 20:31:02 — Failed SSH authentication / fakeuser
- September 18, 2026 @ 20:31:04 — Failed SSH authentication / fakeuser
- September 18, 2026 @ 22:24:15 — Failed SSH authentication / fakeuser

## Correlation

The events were correlated using the same agent, username, source IP, SSH activity, rule context, and timestamps.

The events were associated with the same monitored endpoint, the same non-existent username, the same source IP, and the same SSH authentication behavior.

## Investigation Finding

Repeated failed SSH authentication activity involving the non-existent username `fakeuser` was observed on the monitored Linux endpoint.

Wazuh identified the activity using Rule 5710.

## Classification

True Positive detection — Authorized/Benign Lab Activity.

The activity was deliberately generated inside the controlled Enterprise SOC Home Lab.

## Response

No additional containment was required because the activity was deliberately generated inside the controlled Enterprise SOC Home Lab.

## Lessons Learned

Multi-event investigations provide more context than reviewing alerts individually.

Correlating timestamps, host, account, source, and rule information helps a SOC analyst understand whether events are part of the same activity sequence.

## Screenshots

1. Wazuh related event list
2. Wazuh event/document details
