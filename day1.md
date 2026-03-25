# Room: Logs & Monitoring

## What I Learned
SOC Team Roles: The SOC personnel team includes a Senior SOC Analyst, SOC Engineer, and Incident Responder.
SIEM Monitoring: Analyze the SIEM dashboard to identify suspicious or malicious IP addresses.
Incident Response Workflow: Pass the malicious IP through IP Hunter, escalate to the Senior Analyst, and block it in the firewall.

## Key Concepts
- Malicious IP: The source of suspicious or harmful activity on the network.
- Escalation: Forwarding an alert to someone more experienced (senior analyst) when needed.

## Example Log / Screenshot
- 
## Suspicious Patterns Observed
- A successful SSH login from a malicious ip
-Several logins attempt from the same malicious ip

## My Explanation
The repeated login attempts from the same IP indicate a possible brute-force attack trying to guess credentials.
The fact that one login succeeded from a known malicious IP is highly suspicious and suggests that the account may have been compromised.
Immediate action, such as blocking the IP, reviewing the affected account activity, and escalating to a senior analyst, is required to prevent further unauthorized access.

## Tools Used
- TryHackMe Lab

## Difficulty
- Easy 
