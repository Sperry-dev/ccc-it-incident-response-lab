# Candy Cookies & Cola IT Incident Response Lab

## Overview

This repository contains simulated enterprise IT incidents
demonstrating troubleshooting, Active Directory concepts,
network diagnostics, and security event analysis.

## Skills Demonstrated

- Active Directory
- PowerShell
- DNS
- TCP/IP
- Incident Response
- Root Cause Analysis
- Security Event Monitoring

## Incident Scenarios

| Ticket | Description |
|----------|----------|
| INC-2026-0147 | Account Lockout |
| INC-2026-0153 | VPN Failure |
| INC-2026-0158 | DNS Resolution Failure |

## Sample Evidence

See screenshots folder for examples of:

- PowerShell investigation
- Security Event ID 4740
- DNS troubleshooting
  # INC-2026-0147

## User Information

Name: Ben Todd

Department: Finance

Location: Dallas HQ

Computer: FIN-PC-023

Username: btodd

---

## Issue

User reports inability to log into workstation.

Error:

"The referenced account is currently locked out."

---

## Investigation

### Network Verification

Command:

ipconfig

Result:

IPv4: 10.10.25.114

Gateway: 10.10.25.1

Status: Passed

### Domain Controller Connectivity

Command:

ping dc01.ccc.local

Result:

10.10.1.10 reachable

Status: Passed
## PowerShell Investigation

<pre>
Command:

Get-ADUser btodd -Properties LockedOut |
Select Name,SamAccountName,LockedOut

Output:

Name      SamAccountName   LockedOut
----      --------------   ---------
Ben Todd  btodd            True
</pre>
## Ticket Information

Ticket Number: INC-2026-0147

Status: Resolved

Priority: Medium

Category: User Access

Assigned Group: Service Desk

Assigned Technician: Sam Perry

Opened:
2026-06-14 08:43 CST

Closed:
2026-06-14 09:01 CST

## Security Event Analysis

Event ID: 4740

Source:
Microsoft-Windows-Security-Auditing

Target User:
btodd

Caller Computer:
FIN-PC-023

Time:
2026-06-14 08:42:17 CST

Finding:

Multiple failed authentication attempts were generated from FIN-PC-023.

Review of Event ID 4740 confirmed the account lockout originated from cached credentials on a mobile device using an outdated password.

No evidence of malicious activity was observed.

## Resolution

Root Cause:

User's mobile device contained an
outdated password.

The device repeatedly attempted
authentication against Active Directory,
triggering the account lockout threshold.

Corrective Action:

- Unlocked account
- Updated credentials on mobile device
- Verified successful login

Outcome:

Issue resolved.
No further incidents observed.
## Escalation Review

Tier 1 Investigation Completed

Findings:
- Network connectivity verified
- DNS functioning normally
- Domain controller reachable
- User account locked

Escalation Required:
No

Resolution handled by Tier 1.
