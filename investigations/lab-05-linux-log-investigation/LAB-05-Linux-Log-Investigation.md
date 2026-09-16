# LAB 05 — Linux Log Investigation

## Objective

Investigate a controlled Linux authentication event using raw logs and Wazuh.

## Activity

- Test: SSH authentication using a non-existent user
- Username: fakeuser
- Host: soc-agent
- Source: 127.0.0.1

## Detection

- Rule ID: 5710
- Rule description: sshd: Attempt to login using a non-existent user
- Severity/Level: 5
- Agent: ubuntuagent
- Timestamp: Sep 16, 2026 @ 18:42:41.3...

## Investigation

The SSH authentication attempt using the non-existent user `fakeuser` was detected by Wazuh.

Wazuh generated an alert showing that an SSH login attempt was made using a non-existent account.

The source address was `127.0.0.1`, indicating that the activity originated from the local system.

## Conclusion

The controlled authentication event was successfully detected and investigated using Wazuh.

This lab demonstrates basic Linux authentication log investigation and SOC L1 alert analysis.
