# Room: SOC L1 Alert Triage & Reporting

## What I Learned
- SOC L1 analysts handle **alert triage**: review, prioritize, escalate, and report alerts.
- Not all alerts are threats—some are **false positives**.
- Prioritization rules:
  - Severity: Critical > High > Medium > Low
  - Age: Older alerts first if severity is the same
- Alerts are classified as:
  - **True Positive** = real threat
  - **False Positive** = benign activity
- Critical alerts should be **escalated to L2** for deeper analysis.

---

## Key Concepts
- **Alert Triage:** Analyzing alerts to decide what’s important.
- **Alert Escalation:** Sending a suspicious alert to L2.
- **Alert Reporting:** Writing down alert details, what happened, when, and why.
- **False Positive:** Looks bad but isn’t.
- **True Positive:** Legit threat.
- **Severity:** Urgency of the alert (Critical, High, Medium, Low).
- **IoCs:** Indicators of compromise, like malicious IPs, file hashes, or suspicious commands.
- **Common Alerts:** Phishing, malware, webshells, suspicious file activity, abnormal logins.

---

## Example Alerts / Scenarios
- **Data Exfiltration Alert**  
  - Source IP: `192.168.45.66`  
  - Destination: `*.zoom.us`  
  - Data Sent: 5.8 GB  
  - Verdict: False Positive (legit Zoom traffic)

- **Double-Extension File**  
  - File: `cats2025.mp4.exe`  
  - Source: `freecatvideoshd.monster`  
  - Verdict: True Positive (malware disguised as video)

- **Leaked Document**  
  - User: `m.boslan@tryhackme.thm`

- **Suspicious Email / Phishing**  
  - Sender: `support@microsoft.com`  
  - Recipient: `e.huffman@tryhackme.thm`  
  - Date: 27 Mar 2025, 19:25  
  - DKIM & SPF failed  
  - Flag: `THM{nice_attempt_faking_microsoft_support}`

- **Webshell via Old Exchange**  
  - Host: `DMZ-MSEXCHANGE-2013`  
  - OS: Windows Server 2012 R2  
  - Commands: `w3wp.exe`, `revshell.exe`, `powershell.exe`  
  - Date: 27 Mar 2025, 19:56  
  - Flag: `THM{looks_like_webshell_via_old_exchange}`

---

## Suspicious Patterns I Saw
- Commands trying to pull **AD user info**
- Emails failing SPF/DKIM checks
- Files with **double extensions** (`.mp4.exe`)
- Large or unusual data transfers to external domains

---

## My Thoughts
- Phishing email: **True Positive**, escalated to L2 (`E.Fleming`)
- Webshell commands: **True Positive**, needed immediate attention
- GitHub and doc alerts: **False Positives**, normal user activity
- Context is everything—don’t assume every alert is bad

---

## Tools I Used
- TryHackMe SOC L1 Dashboard

---

## Difficulty
- Easy

---

## Key Takeaway
- **Not every alert is a threat. Context matters.**
- A good SOC analyst:
  - Investigates before acting
  - Knows what normal behavior looks like
  - Uses severity, time, and context to prioritize
  - Escalates real threats properly
