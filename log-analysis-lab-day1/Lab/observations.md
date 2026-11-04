# 🔍 Day 1: Observations and Learnings

## What Did I Observe?

- The PowerShell command `Get-LocalUser | Select-Object Name, Enabled` was recorded under Event ID 4104.
- Windows PowerShell Operational logging provided visibility into the command that was executed.
- The event record contained the script block text, which could be examined as part of an investigation.

## What Did I Learn?

- PowerShell Script Block Logging can help investigators examine commands and scripts executed on a Windows system.
- Commands that enumerate local user accounts can be relevant during investigations of potential reconnaissance or unauthorized activity.
- A command appearing in a security log does not automatically mean malicious activity occurred. Additional context is needed.
- Event logs provide evidence that can support security monitoring, incident response, and digital forensic investigations.

## Investigation Findings

**Observed activity:** Enumeration of local Windows user accounts.

**Command:** `Get-LocalUser | Select-Object Name, Enabled`

**Event ID:** 4104

**Log source:** Microsoft-Windows-PowerShell/Operational

**Evidence:** Screenshot saved in `Images/Log Analysis.png`.

**Assessment:** The event demonstrates that PowerShell Script Block Logging captured the account enumeration command. The command can serve legitimate administrative purposes, and the available evidence does not establish malicious intent.

## Key Takeaway

This lab helped me practice locating and interpreting PowerShell activity in Windows Event Viewer. It also reinforced the importance of examining evidence and context before determining whether an observed action represents a security threat.
