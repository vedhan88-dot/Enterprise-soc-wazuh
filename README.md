# 🛡️ Enterprise Soc Home Lab

## Overview

This project is an enterprise-style Security Operations Center (SOC) home lab built with Wazuh.

The purpose of this project is to develop practical SOC L1 skills through hands-on security monitoring, alert triage, investigation, detection engineering, incident response, and security documentation.

> This is a personal learning lab designed to simulate enterprise SOC workflows.

---

## 🏗️ Architecture

The current lab consists of:

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard
- Ubuntu Linux endpoint
- Wazuh Agent
- SOC Analyst

### Architecture Flow

```text
Linux Endpoint
      ↓
Wazuh Agent
      ↓
Wazuh Manager
      ↓
Wazuh Indexer
      ↓
Wazuh Dashboard
      ↓
SOC L1 Analyst
