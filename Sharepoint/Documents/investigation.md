# Incident Investigation

## Incident Summary

Repeated RDP login failures were followed by a successful remote login.
Suspicious scanning and brute-force utilities were later observed on the
SharePoint server.

## Investigation Timeline

![Forensic Timeline](../../images/RDPforensictimeline.png)

| Time | Event | Evidence |
|---|---|---|
| 3.18 pm - 3.43 pm | Failed RDP logins | Event ID 4625 |
| 3.44 pm | Successful RDP login | Event ID 4624, Logon Type 10 |
| 10 June 2026 | Masscan execution | Sysmon Event ID 1 |
| 10 June 2026 | Outbound connection | Sysmon Event ID 3 |

## Authentication Analysis

Explain the failed and successful RDP activity.

![Bruteforce](../../images/bruteforce.png)

The log shows repeated failed login attempts, the logs keep coming on from 3.18 pm until successful login log appear at 3.44 pm
The attacker successfully logged in as Local Sharepoint Administrator with the given password that was included in the rockyou.txt file

## Sharepoint Compormised and Persistense

The attacker is able to change the Local Sharepoint Administrator password, also created a local user account name dn for persistent access.

## Process Analysis

| Process | Finding |
|---|---|
| `masscan.exe` | Used for network scanning |
| `Massscan_GUI.exe` | Parent interface for Masscan |
| `NLBrute.exe` | Brute-force utility |
| `winpcap-4.3.exe` | Packet-capture driver |

## Network Analysis

Explain the external connections and suspicious destinations.

## Evidence Samples

Include short sanitized log examples or screenshots.

## Conclusion

Summarize what likely happened and what the evidence supports.
