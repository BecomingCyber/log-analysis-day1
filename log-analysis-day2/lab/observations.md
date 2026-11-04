# 🧠 Day 2 Observations - Log Analysis Basics: Windows Security Logs

## 🔍 What Did I Observe?

### Failed Login (Event ID 4625):

I simulated a failed login attempt by using an invalid password for the haxuser1 account.
The Security Log captured this attempt under Event ID 4625.

Details included:

- Username: `haxuser1`

- Failure Reason: Bad username or password

- Logon Type: 3 (network logon)

### Successful Logon (Event ID 4624)

I reviewed Windows Security Event ID 4624, which records a successful logon.

The captured event included:

- **Event ID:** 4624
- **Logon Type:** 7 (Workstation Unlock)
- **Authentication Package:** Negotiate
- **Workstation:** DESKTOP-O13BV2L

**Investigation Finding:**

The event indicates that an existing Windows session was unlocked. Although Event ID 4624 records successful authentication activity, the Logon Type provides important context about the action performed.

**What I Learned:**

A successful logon event does not always represent a new interactive sign-in. Examining the Logon Type and authentication details helps distinguish different types of account activity and prevents incorrect conclusions during an investigation.

### Account Lockout (Event ID 4740):

After multiple failed login attempts with the wrong password, the `haxuser1` account was locked.
Event Viewer recorded this event under Event ID 4740.

Details included:

- Locked Account: `haxuser1`

- Caller Computer Name: My machine’s hostname

## 🧠 What Did I Learn?

Windows Security Logs are a powerful tool for detecting unauthorized access attempts and tracking user activity.

You can quickly identify failed login attempts by filtering for Event ID 4625.

Successful logins provide important details like logon type and authentication method.

Account lockouts can signal possible brute-force attacks or password guessing attempts, especially if they happen frequently.

Filtering specific Event IDs saves time and helps SOC Analysts find critical security events faster.

Real-world SOC teams monitor these Event IDs actively to detect intrusions and potential insider threats.

## 🛡️ Importance for a SOC Analyst:

SOC Analysts must constantly monitor Windows Security Logs for suspicious patterns such as:

- Multiple failed logins from different accounts or IP addresses

- Unexpected account lockouts

- Privilege escalations after successful logins

Early detection can help prevent security breaches and respond to threats before damage occurs.

## 🔎 Investigation Assessment

### Findings

During this controlled lab, I examined three Windows Security Event IDs associated with authentication activity:

- **Event ID 4625:** Recorded a failed network logon attempt involving the `haxuser1` account.
- **Event ID 4624:** Recorded a successful interactive logon using NTLM authentication.
- **Event ID 4740:** Recorded the lockout of the `haxuser1` account following multiple failed password attempts.

### Security Interpretation

Repeated authentication failures followed by an account lockout can indicate password guessing or brute-force activity. However, these events were generated during a controlled simulation and do not independently establish malicious intent.

### Additional Evidence Needed

In a real investigation, I would examine:

- Event timestamps to establish the sequence and frequency of authentication attempts.
- Source IP addresses and workstation information, when available.
- Account activity before and after the lockout.
- Whether the authentication attempts were expected or authorized.

### Key Takeaway

This lab reinforced the importance of investigating authentication events in context. Identifying an Event ID is only the beginning. Understanding the sequence of events, reviewing supporting evidence, and distinguishing suspicious behavior from confirmed malicious activity are essential investigative skills.
