# Scenario Overview

## Organization

**Name:** NorthWave Logistics  
**Industry:** Regional logistics and distribution  
**Size:** Approximately 80 employees  

NorthWave Logistics is a fictional organization created exclusively for this educational cybersecurity laboratory.

---

## Operational Context

The simulated organization operates from Monday to Saturday between **06:00 and 22:00**.

Expected administrative activity generally occurs between **08:00 and 18:00**.

Automated backup operations are expected to run at approximately **02:00**.

Automated activity may occur outside normal operating hours. However, interactive access during those periods is less common and may require additional contextual investigation.

---

## Monitored Server

**Logical hostname:** `nw-log-prod-01`

**Role:** Production log centralization and remote administration.

The server is considered operationally important because it centralizes internal application logs and supports remote administrative access.

A potential compromise could affect log visibility, log integrity, remote administration, and potentially access to other systems.

---

## Relevant Accounts

| Account | Role | Expected Activity |
|---|---|---|
| `admin-sys` | Primary system administrator | SSH access, sudo usage, and scheduled maintenance |
| `svc-backup` | Service account | Automated backup operations |
| `monitor` | Monitoring service | Local connections and system checks |
| `analyst` | Operations analyst | Occasional access and log queries |

The presence of an account in a security event does not automatically indicate malicious activity. Events must be interpreted within their operational context.

---

## Relevant Services

The scenario may include the following services and data sources:

- SSH
- Cron
- Rsyslog
- Internal application logs
- Auditd

Components will be implemented progressively according to the requirements of the investigation.

---

## Laboratory Architecture

This project is built as a **self-contained single-host laboratory**.

The same Linux system represents the logical monitored host and also runs Splunk Enterprise.

This differs from a production environment, where log sources and SIEM infrastructure would normally be physically or logically separated.

This limitation is intentionally documented to maintain transparency about the laboratory architecture.

---

## Expected Normal Activity

The simulated environment may include:

- Administrative SSH access during expected working hours
- Scheduled maintenance activity
- Automated backup operations at approximately 02:00
- Monitoring-related system checks
- Occasional legitimate remote access
- Authentication errors caused by users or services

This operational context will be used during the investigation to distinguish between expected, anomalous, and potentially malicious activity.
