# Room: SOC L1 Alert Triage

## What I Learned
An alert is basically how a SOC team knows something might be wrong without going through millions of logs. Instead of checking everything manually, the system highlights suspicious activity.

I also learned the full flow of how this works:
Event → Log → SIEM → Alert → Triage → Response

As an L1 analyst, my job is to look at alerts and decide if they are actually a threat or just normal activity. I don’t fix everything, I decide what needs attention and escalate if necessary.

---

## Key Concepts
- Alert: A notification of something suspicious
- Event: Any action like login, download, or process running
- SIEM: System that collects and analyzes logs
- Alert Triage: Reviewing and deciding if an alert is real or not
- True Positive: Real attack
- False Positive: Looks suspicious but is actually normal
- Severity: How serious the alert is

---

## Example Scenario
- Large data transfer to *.zoom.us (looked like data exfiltration)
- File downloaded: cats2025.mp4.exe (fake video but actually malware)
- GitHub access by a developer

---

## Suspicious Patterns Observed
- Large data going to an external domain
- Double extension files (.mp4.exe)
- Downloads from unknown or sketchy websites
- Multiple alerts that need to be prioritized

---

## My Explanation
At first, the large data transfer looked like data theft, but it turned out to be normal Zoom usage, so that was a false positive.

The file cats2025.mp4.exe is clearly malicious because attackers use double extensions to trick users. That one is a true positive and should be taken seriously.

The GitHub alert was normal because developers use it all the time.

This showed me that I can’t just trust the alert name — I have to look at the context before deciding.

---

## Alert Triage Process
1. Assign the alert to myself
2. Set it to In Progress
3. Look at details (IP, user, file, activity)
4. Investigate what happened
5. Decide if it’s real or not
6. Write my reasoning
7. Close the alert

---

## Tools Used
- TryHackMe SIEM dashboard

---

## Difficulty
- Easy

---

## Key Takeaway
Not every alert is an attack. My job is to slow down, look at the details, and figure out what’s actually going on before making a decision.
