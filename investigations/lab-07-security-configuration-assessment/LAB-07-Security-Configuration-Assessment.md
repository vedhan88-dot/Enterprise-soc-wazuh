# LAB 07 — Security Configuration Assessment (SCA)

## Objective

Use Wazuh SCA to assess the Ubuntu agent's security configuration, review failed controls, and document the finding like a SOC L1 analyst.

## Environment

- Wazuh Manager/Dashboard: ubuntu
- Wazuh Agent: ubuntuagent
- Host: soc-agent

## SCA Assessment

- Agent: ubuntuagent
- Policy: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.
- Overall Score: 45%
- Passed Controls: 122
- Failed Controls: 148
- Not Applicable: 9
- Total Checks: 279
- End Scan: September 16, 2026 @ 18:35:24.000

## Failed Control Investigated

- Control ID: 35509
- Result: Failed
- Title: Ensure unused filesystems kernel modules are not available.
- Target: Command: modprobe -n -v afs

## Finding

The SCA assessment identified that unused filesystem kernel modules were available on the Ubuntu system. The failed control indicates that unnecessary filesystem kernel modules can increase the attack surface of the system.

## Wazuh Recommendation

Wazuh recommends reviewing the filesystem kernel modules and, where appropriate, disabling or removing unnecessary modules according to the remediation guidance provided by the SCA policy.

## Investigation Summary

The Ubuntu agent was assessed using the CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0. The assessment produced a score of 45%, with 148 failed controls, 122 passed controls, and 9 controls marked not applicable.

One failed control (ID 35509) was selected for investigation. The control checks whether unused filesystem kernel modules are available.

## Classification

Configuration Finding — not automatically a confirmed security incident.

## Lessons Learned

SCA helps a SOC analyst identify security configuration weaknesses, review failed controls, understand the associated risk, and document recommended remediation.
