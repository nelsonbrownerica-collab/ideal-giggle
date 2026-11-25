# SOC Level 1 Investigation

**Track:** Security Operations  
**Status:** Not started — starter guide only  
**Estimated time:** 2–4 hours  
**Difficulty:** Beginner–intermediate

## Objective

Work a fictional alert from intake through validation, evidence collection, escalation decision, and closure note.

## Safety and scope

> Use a fictional alert packet. Do not interact with real endpoints.

- Stop if the environment differs from the stated scope.
- Use read-only analysis unless a step explicitly calls for a change in a disposable local lab.
- Record scope, exclusions, tool versions, and sample provenance.

## Prerequisites

A browser, text editor, notes folder, and the safe sample or environment described above. Create an evidence folder for this project. A heavy VM is not required unless you deliberately choose an authorized local training environment.

## Safe lab setup

- Use synthetic, benign, local, or explicitly authorized training material only.
- Do not scan, exploit, access, or disrupt systems outside written scope. Do not execute malware.
- Keep original sample files unchanged. Work from copies and sanitize evidence.
- Never commit credentials, tokens, keys, personal data, or employer/client information.
- Prefer lightweight sample files and browser documentation over heavy VMs when possible.

## Step-by-step workflow

1. **Define scope:** Write the objective, in-scope material, exclusions, and the question to answer.
2. **Prepare evidence:** Record dataset provenance, date/time (UTC), tool/version, and sample hash where relevant.
3. **Establish baseline:** Note expected behavior, fields, assets, identities, and known limitations.
4. **Perform the lab:** Follow the project-specific steps below. Record each question, action, result, and interpretation.
5. **Validate:** Consider at least one benign explanation; cross-check the key observation; separate fact from assumption.
6. **Report:** Summarize evidence, findings, confidence/severity, recommendations, and limitations.
7. **Review:** Sanitize screenshots and confirm that every claim is supported by your own work.

## Project-specific exercise

1. Record alert ID, severity, detection time, user, and host. 2. Validate the alert in sample logs. 3. Scope adjacent activity. 4. Build timeline and indicator list. 5. Decide close, monitor, or escalate with rationale. 6. Draft handoff note.

## Example questions

1. What evidence directly answers the investigation question?
2. What alternative benign explanation did you consider?
3. Which conclusion is fact, which is interpretation, and what remains unknown?
4. What is the impact and confidence of each finding?
5. What would you do next, and how would you verify it?

## Evidence checklist

- [ ] Scope, objective, and safety boundary recorded.
- [ ] Sample provenance and date/time recorded.
- [ ] Tool names and versions recorded.
- [ ] Screenshots of your own steps saved and sanitized.
- [ ] Queries, commands, code, or configuration excerpts saved as text.
- [ ] Important outputs captured with context and timestamps.
- [ ] Findings supported by evidence; facts separated from assumptions.
- [ ] Recommendations and validation steps documented.
- [ ] Limitations and false-positive considerations included.
- [ ] Final report reviewed for accuracy and privacy.

## Final report structure

1. Executive summary
2. Scope, environment, and exclusions
3. Method and tools actually used
4. Evidence and observations (reference evidence filenames)
5. Findings, impact, confidence, and severity rationale
6. Recommendations and validation plan
7. Limitations and lessons learned

## Completion gate

This guide is **not** proof of completion. Keep status **Not started** or **In progress** until you personally perform the lab. Mark it **Completed** only after your screenshots, outputs, report, limitations, and recommendations are saved and reviewed. Do not invent results or claim tools you did not use.
