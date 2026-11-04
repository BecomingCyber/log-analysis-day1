# 🔍 Day 2: Log Analysis Basics - Windows Security Logs

![Windows Security](https://img.shields.io/badge/Windows-Security-blue)
![Log Analysis](https://img.shields.io/badge/Log-Analysis-green)
![SOC Skills](https://img.shields.io/badge/SOC-Skills-purple)
![Day 2 Complete](https://img.shields.io/badge/Day%202-Complete-brightgreen?style=for-the-badge&logo=checkmarx&logoColor=white)

---

This lab focuses on analyzing Windows Security Logs to detect critical security events such as:
- Successful Logins (Event ID 4624)
- Failed Logins (Event ID 4625)
- Account Lockouts (Event ID 4740)

## 📂 Folder Contents
| File/Folder | Description |
|:------------|:------------|
| `README.md` | This file (overview of the lab) |
| `images/` | Screenshots of captured security events |
| `lab/windows-setup.md` | Setup instructions for recreating the lab |
| `lab/observations.md` | Observations and reflections on the lab |

## 🛠️ Skills Practiced
- Windows Security Log Analysis
- Event Viewer Filtering
- Threat Detection: Failed Logins and Account Lockouts
- SOC Analyst Investigation Techniques

---
✅ **Lab Completed Successfully**

---

## 🔎 Investigation Evidence

The following screenshots document Windows Security events examined during this controlled authentication lab.

| Event ID | Evidence | Investigation Finding |
|---|---|---|
| 4625 | [Failed Logon Screenshot](images/Event%20ID%204625%20%28Failed%20Logon%29.png) | Failed network logon involving `haxuser1`, with an incorrect-password substatus. |
| 4624 | [Successful Logon Screenshot](images/4624%20Successful%20Login.png) | Successful workstation unlock (Logon Type 7) using the Negotiate authentication package. |
| 4740 | [Account Lockout Screenshot](images/Event%20ID%204740%20%28002%29.png) | Account lockout recorded for `haxuser1`. |

### Investigation Documentation

- [Review My Investigation Findings and Observations](lab/observations.md)
- [Review the Windows Lab Setup](lab/windows-setup.md)

### Key Takeaway

This lab helped me practice examining Windows authentication events, interpreting event details, and documenting findings based on available evidence.

The events were generated during a controlled lab. Although failed authentication attempts and account lockouts can indicate suspicious activity, you need additional context before concluding that an actual attack occurred.
