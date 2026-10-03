# Windows Log Analysis

## Project Overview

This project demonstrates the analysis of Windows Security Event Logs to identify and investigate successful and failed authentication activities using Windows Event Viewer.

The project focuses on Event ID 4624 (successful logon) and Event ID 4625 (failed logon), including analysis of different Windows Logon Types.

## Objective

- Analyze Windows Security Event Logs
- Understand successful and failed authentication events
- Identify relevant Logon Types
- Investigate suspicious authentication activity
- Document findings from a SOC Analyst perspective

## Tools Used

- Windows Event Viewer
- Windows Security Logs

## Event IDs Analyzed

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |

## Logon Types Analyzed

| Logon Type | Description |
|------------|-------------|
| 2 | Interactive Logon |
| 3 | Network Logon |
| 5 | Service Logon |
| 10 | RemoteInteractive / Remote Desktop |
| 11 | CachedInteractive Logon |

## Investigation Findings

### Event ID 4624 - Successful Logon

- Logon Type: 5
- Meaning: Service Logon
- Result: Successful Logon
- Assessment: Generally normal Windows service activity. Unexpected service accounts or unusual service activity should be investigated.

### Event ID 4625 - Failed Logon

- Logon Type: 2
- Meaning: Interactive Logon
- Result: Failed Logon
- Status: 0xC000006D
- Assessment: A failed interactive logon was recorded. A single failure may be normal, but repeated failures within a short period may require investigation for possible password-guessing or brute-force activity.

## SOC Investigation Process

A SOC Analyst can investigate authentication events by:

1. Identifying the Event ID.
2. Checking the Logon Type.
3. Reviewing the account involved.
4. Checking the event timestamp.
5. Reviewing the source information when available.
6. Looking for repeated failed logons.
7. Comparing successful and failed authentication activity.
8. Investigating unusual authentication patterns.

## Detection Ideas

Repeated Event ID 4625 failures within a short period can be monitored for possible password-guessing or brute-force activity.

A useful detection approach is to correlate:

- Multiple 4625 events
- Same account
- Same source address
- Short time interval
- Followed by a successful 4624 event

A single 4625 event should not automatically be treated as malicious.

## MITRE ATT&CK Relevance

Repeated authentication failures may be relevant to:

- **T1110 - Brute Force**

If valid credentials are suspected to have been used during suspicious activity, **T1078 - Valid Accounts** may also be relevant depending on the investigation evidence.

## Evidence

The project includes redacted screenshots of:

- Event ID 4624 — Successful Service Logon
- Event ID 4625 — Failed Interactive Logon

Sensitive system information has been redacted before publishing the screenshots.

## Skills Demonstrated

- Windows Security Log Analysis
- Authentication Monitoring
- Event Investigation
- Logon Type Analysis
- Threat Detection
- Basic Incident Investigation
- Security Event Documentation

## Key Takeaways

This project provided hands-on experience analyzing Windows authentication events and understanding how SOC Analysts use security logs to identify unusual authentication activity.

The analysis also demonstrates the importance of correlating multiple events and investigating patterns rather than treating a single event as malicious.
