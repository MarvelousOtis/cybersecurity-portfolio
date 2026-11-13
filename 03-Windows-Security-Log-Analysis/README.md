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
