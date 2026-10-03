# Windows Log Analysis

## Objective

Analyze Windows Security Event Logs to identify successful and failed logon activities and understand how a SOC Analyst can investigate suspicious authentication events.

## Tools Used

- Windows Event Viewer
- Windows Security Logs

## Event IDs Analyzed

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |

## Logon Types

| Logon Type | Description |
|------------|-------------|
| 2 | Interactive Logon |
| 3 | Network Logon |
| 10 | RemoteInteractive / Remote Desktop |
| 11 | CachedInteractive Logon |

## SOC Analyst Investigation

A SOC Analyst can review Windows Security Logs to identify:

- Repeated failed login attempts
- Successful logins after multiple failures
- Suspicious remote logins
- Unusual login times
- Unexpected source IP addresses
- Possible brute-force activity

## Skills Demonstrated

- Windows Log Analysis
- Security Event Monitoring
- Authentication Analysis
- Threat Detection
- Basic Incident Investigation
## Investigation Findings

### Event ID 4624 - Successful Logon

- Logon Type: 5
- Meaning: Service Logon
- Result: Successful Logon
- Assessment: Generally normal Windows service activity. An unexpected service account should be investigated.

### Event ID 4625 - Failed Logon

- Logon Type: 2
- Meaning: Interactive Logon
- Result: Failed Logon
- Status: 0xC000006D
- Assessment: A failed interactive logon was recorded. A single failure may be normal, but repeated failures should be investigated for possible password-guessing or brute-force activity.

## SOC Analyst Investigation Approach

1. Identify the Event ID.
2. Check the Logon Type.
3. Review the account involved.
4. Check the time of the event.
5. Look for repeated failed logons.
6. Investigate unusual or suspicious authentication activity.
