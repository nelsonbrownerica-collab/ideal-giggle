# Project 01 — SIEM Alert Triage with Splunk

**Status:** Starter guide — not yet completed  
**Track:** SOC Analyst / Security Monitoring  
**Environment:** Splunk Free or a permitted training environment; use only synthetic or public training data.

## Objective
Demonstrate a repeatable alert-triage workflow: understand an alert, search relevant events, build a short timeline, assess evidence, and recommend a next action.

## What to do
1. Install Splunk in a local lab or use a legitimate training environment. Do not ingest company, customer, or personal logs.
2. Import a small synthetic authentication dataset. Create a CSV with fields: `_time,user,src_ip,dest,action,status`.
3. Use these sample rows (all fictional):
   ```csv
   _time,user,src_ip,dest,action,status
   2026-01-12T08:01:00Z,alex,198.51.100.24,VPN,login,failure
   2026-01-12T08:02:00Z,alex,198.51.100.24,VPN,login,failure
   2026-01-12T08:03:00Z,alex,198.51.100.24,VPN,login,failure
   2026-01-12T08:05:00Z,alex,198.51.100.24,VPN,login,success
   2026-01-12T08:08:00Z,alex,203.0.113.45,VPN,login,success
   2026-01-12T08:14:00Z,jordan,192.0.2.19,VPN,login,failure
   ```
   The IP ranges above are reserved for documentation and examples; they are not real attacker infrastructure.
4. Confirm the timestamp field is parsed correctly and note the timezone.
5. Run searches and explain what each result does—and does not—prove.

## Example SPL searches
Count failed logins by user and source:
```spl
index=main action=login status=failure
| stats count as failures by user src_ip
| sort - failures
```

Build an event timeline for one account:
```spl
index=main user="alex"
| sort 0 _time
| table _time user src_ip dest action status
```

Find accounts with multiple failures:
```spl
index=main action=login status=failure
| stats count as failures by user
| where failures >= 3
```

## Investigation questions
- Which account has repeated failures?
- What changes after the failures?
- Are the source addresses the same or different?
- What additional telemetry would you request before calling this a compromise?
- What containment or escalation step would be proportionate?

## Deliverables to add when you complete the lab
- Screenshot of the imported data and each search result (hide local usernames or sensitive paths).
- SPL queries in a text file.
- A one-page triage report: alert summary, scope, timeline, evidence, assessment, limitations, recommended next step.
- A short note on false positives and why failed logins alone do not prove account compromise.

## Completion standard
Do not label this complete until you have run the searches yourself and saved your own evidence. Do not claim a real incident was investigated; this is a synthetic-data exercise.
