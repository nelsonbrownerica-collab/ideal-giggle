# Project 03 — Phishing Email Analysis

**Status:** Starter guide — not yet completed  
**Track:** SOC Analyst / Email Security  
**Environment:** A fictional training email below. Do not send it, click links, open attachments, or use real credentials.

## Objective
Practice a safe first-pass email investigation: inspect sender details and headers, identify suspicious indicators, explain uncertainty, and recommend a safe response.

## Fictional training message
```text
From: Payroll Support <payroll-alert@example.invalid>
To: employee@example.invalid
Subject: Urgent: payroll account review required
Date: Mon, 12 Jan 2026 09:14:00 +0000
Message-ID: <training-001@example.invalid>

Your payroll profile requires review today. Use the link below to confirm your account:
hxxps://payroll-review.example.invalid/login

Attachment: Payroll_Adjustment_Review.txt
```
All domains use the reserved `.invalid` suffix and are non-operational placeholders.

## Analysis workflow
1. Preserve the message as an attachment or raw text in your isolated training folder.
2. Inspect From, Reply-To, Return-Path, Message-ID, Received chain, Authentication-Results, SPF, DKIM, and DMARC fields when available.
3. Compare the visible sender with the actual sending domain and reply destination.
4. Defang URLs (for example, change `https://` to `hxxps://`) and do not visit them.
5. Do not open unknown attachments. Record filename, extension, and any provided hash; analyze only in an approved sandbox if the lab explicitly requires it.
6. Decide whether evidence supports phishing, suspicious, or inconclusive. Avoid relying on spelling or urgency alone.

## Questions to answer
- Does the sender domain align with the claimed organization?
- Is Reply-To different from From?
- Do SPF, DKIM, and DMARC pass, fail, or remain unknown?
- What is the destination domain of the defanged link?
- What evidence would increase or decrease confidence?
- What should the user and security team do next?

## Deliverables
- Sanitized message text and headers (fictional or approved sample only).
- Indicator table: type, observed value, why it matters, confidence.
- Verdict with evidence and limitations.
- User guidance and SOC escalation recommendation.

## Completion standard
A screenshot of this starter message is not proof of a completed analysis. Mark complete only after analyzing a real training sample or this complete fictional case and documenting the findings. Never publish live malicious URLs, personal data, or actual employee email.
