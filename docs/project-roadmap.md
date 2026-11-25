# Cybersecurity portfolio project roadmap

This roadmap is a learning plan. Items below are not completed projects until the lab is performed, evidence is saved, and a report is written.

## Guided project files\n\n- [01 — Splunk SIEM alert triage](../projects/01-splunk-soc-triage/README.md)\n- [02 — Windows security event investigation](../projects/02-windows-event-investigation/README.md)\n- [03 — Phishing email analysis](../projects/03-phishing-email-analysis/README.md)\n- [04 — AWS CloudTrail investigation](../projects/04-aws-cloudtrail-investigation/README.md)\n- [05 — Vulnerability assessment and remediation](../projects/05-vulnerability-assessment/README.md)\n\n## Priority 1 — SOC Analyst foundations

1. **Windows security event investigation**
   - Use a safe sample dataset or isolated lab.
   - Identify selected authentication and account-management events.
   - Record event IDs, timestamps, query/filter logic, and investigation limitations.
2. **SIEM alert triage**
   - In a training environment, ingest sample logs into Splunk or another SIEM.
   - Build a search, explain the alert condition, triage a sample event, and document false-positive considerations.
3. **Phishing analysis**
   - Use a safe training email sample.
   - Inspect sender details, headers, URLs, and attachments without opening unsafe content.
   - Write a verdict supported by observable indicators.

## Priority 2 — Investigation and network skills

4. **Wireshark packet analysis**
   - Use a public training capture.
   - Identify protocols and suspicious-looking patterns, then distinguish evidence from speculation.
5. **Incident timeline and report**
   - Build a timeline from supplied lab evidence.
   - Document scope, facts, impact assessment, response options, and lessons learned.

## Priority 3 — Cloud security

6. **AWS CloudTrail investigation**
   - Use an authorized sandbox or sample CloudTrail records.
   - Review identity and API activity and document an investigation.
7. **AWS IAM least-privilege review**
   - Inspect a deliberately vulnerable lab policy.
   - Explain excessive permissions and propose a least-privilege alternative.

## Priority 4 — Vulnerability management

8. **Vulnerability assessment and remediation**
   - Scan only an authorized lab target.
   - Record scope, tool/version, findings, severity method, prioritization rationale, and remediation verification.

## Definition of done

A project is ready to publish when it includes:
- A clear objective and authorized scope
- Tools actually used
- Reproducible methodology
- Sanitized evidence
- Findings tied to evidence
- Limitations and recommendations
- A short explanation of what was learned
- No secrets, personal information, or unsupported claims
