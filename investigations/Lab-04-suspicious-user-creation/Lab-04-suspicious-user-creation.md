# Suspicious User Creation Investigation

## Objective

Detect and investigate local Linux account creation.

## Affected Host

soc-agent / ubuntuagent

## Created Account

soc-test

## Evidence

- Linux account/authentication log
- Wazuh account-creation event
- Wazuh event details

## Investigation

A new local Linux account named `soc-test` was intentionally created on the lab endpoint.

The Linux system recorded the account creation activity, and Wazuh collected and detected the corresponding event.

## Finding

A new local account was created and the activity was detected by Wazuh.

## Classification

**True Positive detection — Authorized/Benign Lab Activity**

The account creation was intentionally performed as part of this security lab.

## Response

The temporary `soc-test` account was removed after the investigation.

No containment was required.

## Lessons Learned

Unexpected account creation can be an indicator of persistence or additional access.

SOC analysts should investigate the identity, timing, authorization, and surrounding telemetry before classifying the activity as malicious.
