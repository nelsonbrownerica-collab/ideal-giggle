# Project 02 — Windows Security Event Investigation

**Status:** Starter guide — not yet completed  
**Track:** SOC Analyst / Endpoint Monitoring  
**Environment:** Your own Windows test machine or a provided training dataset. Never access another person's device or logs without authorization.

## Objective
Practice reviewing Windows Security events, filtering relevant records, and creating an evidence-based authentication timeline.

## Event IDs to learn
- **4624** — successful logon.
- **4625** — failed logon.
- **4634** — logoff.
- **4648** — logon attempted using explicit credentials.
- **4672** — special privileges assigned to a new logon.
- **4720** — user account created.
- **4726** — user account deleted.
- **4732** — member added to a security-enabled local group.

An event ID is a clue, not a verdict. Interpret it with the account, logon type, host, timestamp, source details, and surrounding events.

## Lab procedure
1. Use a Windows VM or your own device. Create a restore point or snapshot if using a VM.
2. Open Event Viewer → Windows Logs → Security.
3. Filter for the event IDs above. If the log is empty or auditing is not enabled, use a trusted sample EVTX dataset from a training provider rather than changing security policy without understanding the impact.
4. For each selected event, record event ID, timestamp and timezone, account, computer, logon type, source address if present, and relevant process fields.
5. Compare a failed logon with a successful logon. Explain the context and uncertainty.
6. Export only sanitized lab events; remove usernames, device names, public IPs, and other identifying details before publishing.

## PowerShell read-only examples
Show recent failed logon events:
```powershell
Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4625} -MaxEvents 20 |
  Select-Object TimeCreated, Id, ProviderName, Message
```

Show recent successful logons:
```powershell
Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4624} -MaxEvents 20 |
  Select-Object TimeCreated, Id, ProviderName, Message
```

These commands read local event logs. Access may require an elevated PowerShell session. Do not clear logs or alter audit settings for this exercise.

## Analysis prompts
- Is the event expected for the account and device?
- What does the logon type mean in this specific context?
- Are there repeated failures, unusual timing, or a new source?
- Is there corroborating evidence such as endpoint, VPN, or identity-provider logs?
- What would you escalate, and what further evidence is needed?

## Deliverables
- Sanitized screenshots or exported sample events.
- A table of selected event IDs and their meaning.
- A short timeline with timezone stated.
- A triage note containing observed facts, assessment, confidence, limitations, and next steps.

## Completion standard
Only mark complete after personally examining events and creating the evidence. Do not imply that a lab event represents an actual breach.
