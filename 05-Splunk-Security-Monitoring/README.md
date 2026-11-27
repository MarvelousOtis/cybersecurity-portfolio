# Splunk Security Monitoring and Log Analysis

## 1. Project Overview

This project involved using Splunk Cloud to investigate simulated Windows Security events and identify suspicious authentication patterns.

The exercise focused on collecting, searching, filtering, analysing and visualising login activity to understand how a Security Operations Centre (SOC) analyst uses a SIEM platform during security investigations.

## 2. Tools and Technologies

- Splunk Cloud Platform
- Splunk Search Processing Language (SPL)
- Simulated Windows Security Event Logs (CSV)

## 3. Project Objectives

- Identify failed and successful login attempts.
- Identify user accounts and computers with repeated failed logins.
- Examine source IP addresses and login types.
- Recognise suspicious authentication patterns.
- Configure a basic alert for repeated failed login attempts.

## 4. Investigation Methodology

The simulated Windows Security event dataset was uploaded into Splunk Cloud and indexed for analysis.

The following searches and SPL commands were used:

| SPL Command | Purpose |
|---|---|
| `index=main` | Retrieve events from the main index |
| `table` | Display selected event fields |
| `stats` | Count events by user or computer |
| `top` | Identify frequently occurring field values |
| `sort` | Arrange results by count or time |
| `where` | Filter results based on conditions |
| `timechart` | Visualise event activity over time |

Windows Event IDs examined:

- **4624:** Successful logon.
- **4625:** Failed logon.

## 5. Investigation Findings

The dataset contained 18 simulated Windows Security events:

- 12 failed login events (4625).
- 6 successful login events (4624).

Two accounts had five failed login attempts each.

| Account | Computer | Logon Type | Source IP | Failed Attempts |
|---|---|---:|---|---:|
| james.ade | FINANCE-PC-01 | 2 | Not recorded | 5 |
| tunde.bello | SALES-PC-03 | 10 | 203.0.113.77 | 5 |

### Case 1: FINANCE-PC-01

Five failed interactive login attempts against `james.ade` occurred between 08:14:03 and 08:15:08 on 27 November 2026.

A successful login was recorded at 08:16:02. No source IP was recorded in the events.

### Case 2: SALES-PC-03

Five failed remote interactive login attempts against `tunde.bello` occurred between 09:42:11 and 09:42:43. All were associated with `203.0.113.77`.

A successful remote login from the same IP was recorded at 09:43:02.

An earlier successful remote login was also recorded at 09:30:01 from `203.0.113.45`.

This sequence was considered suspicious and prioritised for further investigation.

## 6. Alert Configuration

A scheduled Splunk alert titled **Repeated Failed Login Attempts** was created.

- Search condition: Failed logins grouped by username.
- Threshold: Five or more failed attempts.
- Trigger condition: Number of results greater than zero.
- Action: Add to Triggered Alerts.

The alert demonstrated how repeated authentication failures can be monitored using a defined threshold.

## 7. Recommendations

- Verify suspicious source IP addresses against authorised company networks and devices.
- Contact affected account owners to confirm whether the login attempts were legitimate.
- Examine endpoint activity following suspicious successful logins.
- Monitor repeated authentication failures and investigate unusual remote access patterns.

## 8. Limitations

This exercise used a simulated CSV dataset rather than live organisational security logs.

The IP addresses were reserved documentation addresses, not actual attacker addresses. The dataset did not contain endpoint activity needed to establish what happened after successful authentication.

Therefore, the observed patterns were treated as suspicious indicators requiring further investigation, not confirmed security breaches.

## 9. Key Lessons Learned

This project provided practical experience with:

- Using Splunk Cloud as a SIEM platform.
- Searching and analysing security events using SPL.
- Investigating Windows authentication events.
- Identifying repeated failed login attempts.
- Analysing login timelines and source IP addresses.
- Configuring basic security alerts.
- Applying an evidence-based approach to security investigations.
