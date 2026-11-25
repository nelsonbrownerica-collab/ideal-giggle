# Project 04 — AWS CloudTrail Investigation

**Status:** Starter guide — not yet completed  
**Track:** Cloud Security / Detection & Response  
**Environment:** AWS Free Tier or an authorized sandbox; sample events are synthetic. Avoid creating billable resources unnecessarily.

## Objective
Learn how to read CloudTrail management events, identify identity and API context, and write a cautious investigation note.

## Safe setup
1. If using AWS, enable or use an existing CloudTrail trail in an account you own or are explicitly authorized to use.
2. Prefer a sandbox account with no production data. Enable MFA and never share access keys.
3. Do not create public S3 buckets, weaken IAM policies, or run destructive API calls.
4. Alternatively, use the synthetic JSON examples below and clearly label them as sample data.

## Synthetic CloudTrail-style examples
```json
[
  {
    "eventVersion": "1.08",
    "eventTime": "2026-01-12T09:00:00Z",
    "eventSource": "signin.amazonaws.com",
    "eventName": "ConsoleLogin",
    "awsRegion": "us-east-1",
    "sourceIPAddress": "198.51.100.24",
    "userAgent": "Mozilla/5.0 (Training Example)",
    "userIdentity": {"type": "IAMUser", "userName": "training-user"},
    "responseElements": {"ConsoleLogin": "Failure"}
  },
  {
    "eventVersion": "1.08",
    "eventTime": "2026-01-12T09:03:00Z",
    "eventSource": "signin.amazonaws.com",
    "eventName": "ConsoleLogin",
    "awsRegion": "us-east-1",
    "sourceIPAddress": "198.51.100.24",
    "userAgent": "Mozilla/5.0 (Training Example)",
    "userIdentity": {"type": "IAMUser", "userName": "training-user"},
    "responseElements": {"ConsoleLogin": "Success"}
  },
  {
    "eventVersion": "1.08",
    "eventTime": "2026-01-12T09:10:00Z",
    "eventSource": "iam.amazonaws.com",
    "eventName": "CreateAccessKey",
    "awsRegion": "us-east-1",
    "sourceIPAddress": "198.51.100.24",
    "userIdentity": {"type": "IAMUser", "userName": "training-user"}
  }
]
```
The IP address is documentation-only reserved example space. These events are fabricated for learning and are not authentic AWS logs.

## Investigation steps
1. Parse the event time and state that CloudTrail timestamps are UTC.
2. Identify event source, event name, identity type/name, source IP, region, user agent, and result.
3. Build a timeline and ask whether the access-key creation was expected and authorized.
4. Identify what corroborating records would be needed (IAM change history, MFA context, ticket/change record, related API calls).
5. Recommend proportionate follow-up: verify with the account owner, review the key's use and permissions, and follow the organization's approved incident process if unauthorized activity is confirmed.

## Useful fields
`eventTime`, `eventSource`, `eventName`, `awsRegion`, `sourceIPAddress`, `userAgent`, `userIdentity`, `requestParameters`, `responseElements`, and `errorCode`.

## Deliverables
- Sanitized sample JSON or screenshots from your own sandbox.
- Timeline table in UTC.
- Explanation of the event sequence and confidence level.
- Recommendations and limitations.
- If using AWS, note the services used and any costs incurred.

## Completion standard
Do not claim a live AWS incident or production investigation. Clearly identify synthetic data as synthetic. Never publish AWS account IDs, credentials, access keys, or sensitive resource names.
