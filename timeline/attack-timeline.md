# ShadowGate Attack Timeline

## Overview

This timeline summarizes the reconstructed attack sequence from the **Operation Data Fortress** senior cybersecurity capstone. The scenario involved a simulated attack against the fictional organization Global Synergy Solutions (GSS).

The timeline focuses on the progression of the incident rather than exact timestamps.

## Reconstructed Attack Sequence

| Stage | Attack Activity | Evidence / Analysis |
|---|---|---|
| 1. Initial Access | A targeted spear-phishing email reached a GSS employee and resulted in malicious payload execution on a workstation. | Email/phishing scenario evidence and endpoint activity |
| 2. User Execution | The malicious attachment or payload was executed, establishing the initial endpoint compromise. | Windows endpoint and process telemetry |
| 3. Persistence | The attacker established persistence on the compromised workstation, including scheduled-task activity. | Endpoint artifacts, registry/activity review, EDR-related evidence |
| 4. Credential Access | Credentials associated with the compromised environment were obtained and later reused by the attacker. | Authentication and identity-related evidence |
| 5. Lateral Movement | Compromised credentials and attacker tooling were used to expand access beyond the initially affected system. | Authentication, endpoint, and network evidence |
| 6. Cloud Access | Stolen credentials were used to access cloud resources and identities in AWS and Microsoft Azure. | AWS CloudTrail and Azure identity/activity logs |
| 7. Privilege Expansion | The attacker abused valid accounts and cloud identity permissions to expand access and perform unauthorized administrative activity. | IAM/RBAC and cloud audit evidence |
| 8. Command and Control | Network activity indicated communications associated with attacker command-and-control behavior. | Network/SIEM traffic analysis |
| 9. Data Access / Exfiltration Risk | Unauthorized access placed sensitive organizational information at risk and included attempted data exfiltration. | Correlated cloud, identity, network, and incident evidence |
| 10. Containment & Response | Affected endpoints and accounts were isolated, credentials and sessions were addressed, and relevant forensic evidence was preserved before eradication. | Incident-response and forensic procedures |

## MITRE ATT&CK Mapping

The simulated incident included activity associated with several MITRE ATT&CK techniques:

- **T1566** — Phishing
- **T1204.002** — User Execution: Malicious File
- **T1110.003** — Brute Force: Password Spraying
- **T1078** — Valid Accounts
- **T1071.001** — Application Layer Protocol: Web Protocols
- **T1053.005** — Scheduled Task/Job: Scheduled Task
- **T1570** — Lateral Tool Transfer
- **T1114** — Email Collection

## Investigative Takeaway

The investigation demonstrated the importance of correlating multiple evidence sources. Endpoint artifacts helped establish the initial compromise and persistence activity, while network, authentication, AWS, and Azure evidence helped reconstruct the attacker's movement into cloud resources.

Rather than relying on a single alert or log source, the investigation used cross-source correlation to build a defensible sequence of attacker activity.

---

**Portfolio Note:** This timeline is a sanitized summary of a simulated academic cybersecurity investigation. Global Synergy Solutions and the ShadowGate incident are fictional and were created for instructional purposes.
