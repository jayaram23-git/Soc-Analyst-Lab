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
