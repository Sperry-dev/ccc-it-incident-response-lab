# ccc-it-incident-response-lab

IT support and incident response portfolio demonstrating troubleshooting, Active Directory concepts, networking fundamentals, and root cause analysis.

## Skills Demonstrated

- Active Directory
- PowerShell
- DNS
- TCP/IP
- Incident Response
- Security Event Analysis
- Root Cause Analysis

## Incident Reports

### Account Lockout Investigation

**Ticket:** INC-2026-0147  
**Category:** User Access  
**Tools Used:** Active Directory, PowerShell, Event Viewer, DNS, TCP/IP

**Summary:**
A Finance department user was unable to log in due to an Active Directory account lockout. Investigation confirmed the account was locked after repeated authentication attempts from a mobile device containing outdated credentials. The account was unlocked, credentials were updated, and normal access was restored.

**Key Actions Performed:**
- Verified network connectivity
- Verified domain controller accessibility
- Confirmed account lockout using PowerShell
- Reviewed Security Event ID 4740
- Identified root cause
- Restored user access

**Report Location:**
`incidents/INC-2026-0147-Ben-Todd-Account-Lockout.md`

---

Additional incident investigations will be added as the portfolio grows.
