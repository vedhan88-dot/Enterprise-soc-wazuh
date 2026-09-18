# Lab 10 — Active Response

## Objective

Configure and test Wazuh Active Response in the controlled Enterprise SOC Home Lab.

## Environment

- Wazuh Manager: ubuntu
- Wazuh Agent: ubuntuagent
- Agent Host: soc-agent
- Agent IP: 192.168.56.101
- Test Source: 127.0.0.1
- Wazuh Version: 4.14.7

## Trigger

- Wazuh Rule ID: 5710
- Rule Description: sshd: Attempt to login using a non-existent user
- Rule Level: 5
- Test Username: fakeuser
- Source: 127.0.0.1

## Active Response Configuration

The Wazuh Manager was configured with the following Active Response parameters:

- Command: firewall-drop
- Location: local
- Trigger Rule: 5710
- Timeout: 30 seconds
- Disabled: no

The Wazuh Manager configuration was tested successfully without a configuration error, and the Wazuh Manager service was confirmed to be active and running.

## Detection Evidence

A controlled SSH authentication attempt using the non-existent username `fakeuser` generated Wazuh Rule 5710 events.

The Wazuh Threat Hunting results showed:

- Matching events: 16
- Agent: ubuntuagent
- Rule ID: 5710
- Rule Level: 5
- Rule Description: sshd: Attempt to login using a non-existent user

## Active Response Verification

The Active Response configuration was loaded by the Wazuh Manager and the `wazuh-execd` process was running.

The available Agent Active Response log did not contain a `firewall-drop` execution entry for this test. Therefore, successful execution of the `firewall-drop` command is not claimed as verified in this lab evidence.

## Classification

True Positive detection — Authorized/Benign Lab Activity.

The activity was deliberately generated inside the controlled Enterprise SOC Home Lab.

## Safety

The test was performed only on the user's own Enterprise SOC Home Lab virtual machines.

The configured response timeout was 30 seconds.

## SOC L1 Interpretation

The investigation demonstrated the connection between a Wazuh detection rule and an Active Response configuration.

The trigger was Rule 5710, which detects an attempt to log in using a non-existent user. The configured response was `firewall-drop` with a local execution location and a 30-second timeout.

The detection itself was successfully observed in Wazuh. The Active Response configuration was also loaded and the response daemon was running, while direct `firewall-drop` execution was not captured in the available Agent log.

## Lessons Learned

Active Response connects security detection with automated response.

A SOC analyst should verify the trigger rule, response command, execution location, timeout, and actual response evidence before claiming that automated containment occurred.

## Screenshots

1. Active Response configuration and Wazuh Manager status
2. Wazuh Rule 5710 detection evidence
