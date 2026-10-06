# Week 9 – SOC Introduction & Snort IDS

## Cyber Security Internship | DG Interns Hub

### Project Overview

Week 9 focuses on understanding Security Operations Center (SOC) concepts and building a basic network monitoring environment using Ubuntu Server and Snort IDS.

The practical work connects SOC theory with a controlled detection exercise by installing Snort, creating custom ICMP and HTTP detection rules, generating authorized traffic, and validating Snort alerts.

---

## Objectives

- Understand what a Security Operations Center (SOC) is.
- Understand L1, L2, and L3 SOC analyst responsibilities.
- Differentiate between SIEM, IDS, and IPS.
- Create an Ubuntu Server virtual environment.
- Perform basic system, hostname, and network configuration.
- Install and verify Snort IDS.
- Understand the structure of Snort rules.
- Create custom ICMP and HTTP detection rules.
- Generate controlled traffic.
- Validate Snort alerts.
- Document practical evidence and results.

---

## Lab Environment

| Component | Purpose |
|---|---|
| Ubuntu Server | Snort monitoring sensor |
| Snort IDS | Network traffic detection |
| Test Machine | Generates authorized test traffic |
| Virtual Network | Provides communication between systems |
| Custom Rules | Detect ICMP and HTTP traffic |
| Terminal | Configuration and alert validation |

---

## SOC Workflow

```text
Monitor → Detect → Triage → Investigate → Respond/Escalate → Document → Improve
