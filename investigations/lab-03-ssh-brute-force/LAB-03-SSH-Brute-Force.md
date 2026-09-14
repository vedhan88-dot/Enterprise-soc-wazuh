# LAB 03 — SSH Brute-Force Investigation

## Objective

Investigate repeated failed SSH authentication attempts against the Linux endpoint and validate Wazuh detection and alerting.

## Lab Environment

- Endpoint: Ubuntu Linux
- Wazuh Agent: ubunt uagent
- Test source: 127.0.0.1
- Test username: fakeuser
- Service: SSH
- Detection platform: Wazuh

## Attack Simulation

Repeated SSH login attempts were generated against the local Ubuntu endpoint using a non-existent user account.

Example test:

```bash
ssh fakeuser@127.0.0.1
