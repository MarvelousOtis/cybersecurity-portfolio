# Phishing Analysis and Security Awareness

## 1. Project Overview

This project focuses on understanding phishing attacks, identifying suspicious emails, analysing potentially malicious links and attachments, and learning how organisations can protect themselves.

## 2. What is Phishing?

Phishing is a social engineering attack in which attackers impersonate trusted individuals or organisations to trick people into revealing sensitive information, clicking malicious links or downloading harmful attachments.

## 3. Phishing Indicators Identified

During practical email analysis exercises, I identified several common warning signs:

- Urgent language designed to pressure recipients into acting quickly.
- Suspicious sender email addresses or unfamiliar domains.
- Generic greetings such as "Dear Customer".
- Unexpected attachments, especially macro-enabled documents.
- Links that may lead to fraudulent websites.
- Requests for sensitive information or unusual financial transactions.

## 4. Related Cybersecurity Concepts

**Email Spoofing:** Forging email sender information to make a message appear to come from a trusted source.

**Business Email Compromise (BEC):** A form of cybercrime involving impersonation or compromised business email accounts to deceive organisations into transferring money or sharing sensitive information.

**Social Engineering:** Manipulating people into taking actions that could compromise their security.

## 5. Introduction to VirusTotal

VirusTotal is an online security analysis platform used to examine URLs, domains, IP addresses and files.

During this exercise, I submitted the test URL `https://example.com`.

### Observations

- Security vendor detection: 0/93.
- Community score: -346.
- Page title: Example Domain.
- Trackers: Not Found.

### Lessons Learned

- VirusTotal compares submitted indicators against multiple security detection engines.
- A detection result does not automatically prove that a URL is malicious.
- Zero detections do not guarantee that a URL is safe.
- Community scores should be treated as supporting information, not a definitive security verdict.
- Security analysts should consider multiple sources of evidence before reaching a conclusion.

## 6. Security Recommendations

- Avoid clicking suspicious links or opening unexpected attachments.
- Verify unusual requests through trusted communication channels.
- Report suspicious emails to the appropriate security team.
- Never enable macros in unexpected or unverified documents.
- Use security analysis tools to support investigations.

## 7. Skills Practised

- Identifying phishing indicators.
- Recognising email spoofing and social engineering.
- Understanding Business Email Compromise.
- Basic URL reputation analysis using VirusTotal.
- Interpreting security vendor detection results.
- Making evidence-based security assessments.

**Project Status:** In Progress

### Network Requests and External Links

During the VirusTotal investigation of `https://example.com`, I examined the Network Requests / HTTPs Transactions section.

**Observations:**
- Two network requests were listed.
- Both requests returned HTTP status code 200.
- Neither URL received a malicious detection from the 93 security vendors.
- One external outbound link pointed to IANA's example-domain information page.

**Analysis:**

The results showed that the website made or was associated with multiple network requests and referenced an external website. These findings were not suspicious on their own.

During phishing investigations, unexpected redirects or external links may require further examination, especially when the destination domain differs from the organisation the email claims to represent.

**Key Learning:**

A redirect or external link is not automatically malicious. Analysts should examine the destination and consider it alongside other evidence before making a decision.
