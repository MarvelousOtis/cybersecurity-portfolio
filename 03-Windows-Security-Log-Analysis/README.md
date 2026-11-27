# Windows Security Log Analysis

## 1. Project Overview

This project involved examining Windows Security logs to identify and investigate failed login attempts on a Windows 10 computer.

The exercise simulated a basic task performed by a Security Operations Centre (SOC) analyst: reviewing authentication records, identifying unusual activity, and documenting findings.

## 2. Tools Used

- Windows 10
- Windows Event Viewer
- PowerShell

## 3. Investigation Process

I used Windows Event Viewer to examine the Security log and focused on two event IDs:

- **Event ID 4625:** Failed logon attempt.
- **Event ID 4624:** Successful logon.

I reviewed the failure reason, logon type, timestamps, workstation information and available process details.

## 4. Findings

Three failed login events were identified on 13 November 2026.

| Time | Event ID | Logon Type |
|---|---:|---:|
| 5:20:28 PM | 4625 | 2 |
| 5:27:44 PM | 4625 | 2 |
| 5:46:53 PM | 4625 | 2 |

Additional observations:

- The failure reason was recorded as **Unknown username or bad password**.
- All three attempts targeted the same local Windows account.
- Logon Type 2 represents an interactive logon attempt.
- The workstation name matched the computer being investigated.
- The source network address field was blank.
- The latest failed event contained a Chrome process path in its process information.
- A successful interactive logon for the same account was also found earlier that day, at 1:43:48 PM.

## 5. Analysis

The three failed login events occurred within approximately 26 minutes.

Although repeated failed logins can indicate suspicious activity, the available records do not establish that these attempts were malicious.

The Chrome process information is worth noting, but it does not prove that Chrome initiated the failed login attempts.

There was also no source IP address available to help identify a remote source.

## 6. Conclusion

The investigation identified three failed interactive login attempts against the same Windows account.

However, the available evidence was insufficient to determine the cause or classify the activity as a confirmed security incident.

This exercise provided practical experience in reviewing Windows authentication logs, distinguishing successful and failed logons, interpreting logon types, and documenting findings without making unsupported assumptions.

## 7. Skills Practised

- Windows Event Viewer navigation
- Windows Security log analysis
- Identifying failed and successful logon events
- Understanding Windows Event IDs 4624 and 4625
- Interpreting logon types
- Basic PowerShell log filtering
- Security investigation and documentation

## 8. Screenshots

### Failed Login Event (Event ID 4625)

![Failed Login Event](failed-login-event.png)

### Successful Interactive Login Events (Event ID 4624)

![Successful Login Events](successful-login-events.png)

---

## Case Study 2: Windows Authentication Monitoring (25–27 November 2026)

### Objective
Investigate repeated Windows authentication failures, examine associated event details, and determine whether the activity indicates suspicious behaviour.

### Tools Used
- Windows Event Viewer
- Windows PowerShell
- Windows Security Logs

### Investigation Process
- Examined Event ID 4625 to identify failed authentication attempts.
- Reviewed Event ID 4624 to compare successful logon activity.
- Investigated Logon Types and authentication status codes.
- Examined associated processes, account identifiers, and source IP information.
- Used PowerShell to filter and compare recent security events.

### Key Findings

**Failed Authentication Events (4625)**

The 20 most recent failed logon events examined shared the following characteristics:

| Field | Finding |
|---|---|
| Event ID | 4625 |
| Logon Type | 2 (Interactive) |
| Status | 0xc000006e |
| Associated Process | chrome.exe |
| Source IP | Not recorded |
| Target SID | S-1-0-0 (Null SID) |

All 20 events shared the same observed characteristics.

**Successful Authentication Events (4624)**

- The 10 most recent successful events initially examined were Logon Type 5 (Service).
- Two additional successful Logon Type 2 events were identified on 27 November 2026 at approximately 9:52 AM.
- These two events were consistent with the user's reported computer activity.

### Analysis

The repeated failed authentication events indicated a consistent pattern of interactive authentication failures.

The status code `0xc000006e` represents `STATUS_ACCOUNT_RESTRICTION`. However, the specific restriction responsible could not be determined.

Although `chrome.exe` was associated with the events, this did not establish that browser activity caused them.

The Null SID and absence of a recorded source IP also limited the ability to identify the attempted account and origin of the activity.

### Recommendations
1. Strengthen local account security with appropriate sign-in protection.
2. Continue monitoring repeated failed authentication events.
3. Investigate associated processes if the activity persists.
4. Review local account and authentication policies.
5. Maintain appropriate Windows Security log retention.

### Conclusion

The investigation provided practical experience in Windows authentication monitoring, event filtering, identifying repeated patterns, and interpreting security event details.

The available evidence was insufficient to confirm malicious activity or establish the source of the failed authentication attempts.

**Investigation outcome:** Inconclusive; further monitoring and investigation would be required.

**Note:** This was a personal hands-on learning exercise conducted on a Windows 10 system.
