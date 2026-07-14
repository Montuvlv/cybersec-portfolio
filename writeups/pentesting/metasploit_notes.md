# Metasploit Notes: Scanning, Vulnerability Checks, Exploitation, and Msfvenom

Beginner-friendly notes from studying Metasploit, covering the full workflow rather than just exploitation: scanning, service enumeration, vulnerability checks, exploitation concepts, and payload generation with Msfvenom.

> These notes are for learning purposes only and must only be applied in controlled, authorized environments.

## Scanning with Metasploit

Before exploiting anything, the target needs to be understood. Metasploit includes scanning modules that identify open ports, services, versions, protocols, and sometimes weak configurations. Port scanning is usually the first step, since open ports indicate which services may be running.

Key scan options:

| Option | Purpose |
|---|---|
| `RHOSTS` | Target or target network |
| `PORTS` | Port range to scan |
| `THREADS` | Number of threads used during the scan |
| `CONCURRENCY` | Number of targets scanned at the same time |

Scanning helps build a picture of the environment before taking any deeper action.

### Lab commands

```
nmap -sS YOUR_MACHINE_IP
# result: 5

use scanner/discovery/udp_sweep
set RHOSTS YOUR_MACHINE_IP
run
# result: ACME IT SUPPORT

use scanner/http/http_version
set RHOSTS YOUR_MACHINE_IP
set RPORT 8000
run
# result: webfs/1.21

use scanner/smb/smb_login
set RHOSTS YOUR_MACHINE_IP
set SMBUser penny
set PASS_FILE /usr/share/wordlists/MetasploitRoom/MetasploitWordlist.txt
run
# result: [credential found]
```

### Organizing findings

During a test, a lot of information accumulates: hosts, ports, services, versions, credentials, vulnerabilities, notes. The Metasploit database helps keep this organized. Security testing isn't just running tools — it's collecting evidence, understanding context, and making better decisions.

Services worth paying attention to:

- **HTTP** — may host web applications
- **FTP** — may allow anonymous access or expose files
- **SMB** — history of serious vulnerabilities and misconfigurations
- **SSH** — weak credentials create risk
- **RDP** — exposed remote desktop access can be dangerous if poorly protected

Exposed services aren't automatically vulnerable, but they guide the next phase of analysis.

## Vulnerability Scanning

After identifying services, the next step is checking whether any are vulnerable or misconfigured. Metasploit includes modules for checking weak logins, open relay configurations, exposed services, and known vulnerabilities.

One example studied: the **SMTP open relay check** — an open relay can let an email server be abused for sending unauthorized messages.

```
use scanner/smtp/smtp_relay
info
# result: [relay info returned]
```

## Exploitation

Exploitation is the phase where a vulnerability is used to achieve a specific, defined result in an authorized test — gaining access, executing code, reading files, or validating that a vulnerability is actually exploitable.

This is also the phase requiring the most responsibility. In a real environment, exploitation should only happen with clear authorization, defined scope, and proper documentation.

Key lesson: exploitation isn't just "running a command" — it's about understanding risk, validating impact, and proving a weakness can actually affect the system.

```
cd C:\Users\Jon\Documents
dir
type flag.tsx
# result: [flag value — redacted]

cd C:\Users\Jon
background
sessions
use post/multi/manage/shell_to_meterpreter
run
sessions -i 2
getuid
# result: [user SID]
```

## Msfvenom and Post-Exploitation

Meterpreter is one of the most well-known Metasploit payloads — an interactive session used during authorized testing to collect information, interact with the system, and perform post-exploitation activities.

Post-exploitation covers what happens after access is obtained: checking the current user, understanding privileges, collecting system information, reviewing files, identifying credential exposure. Understanding this from a defensive angle helps build better detections for suspicious behavior, privilege escalation attempts, credential dumping, unusual processes, and unauthorized access.

Notes from this section:

- Meterpreter session used in a controlled lab
- User context verification — important for understanding access level
- Credential exposure identified as a major security risk

**Msfvenom** generates payloads in different formats for different operating systems and architectures (Windows, Linux, Android, etc.). Common output formats include executables, ELF files, DLLs, and PHP files. A payload defines what runs on the target after successful execution.

Notes from this section:

- Payload generation tool: Msfvenom
- Payload format studied: ELF
- Target context: Linux-based controlled lab
- Hash dumping studied from a defensive awareness perspective

## Why This Matters for Cybersecurity

This isn't only useful for offensive security — Blue Team professionals benefit from understanding these concepts too:

- Knowing how scanning works helps defenders detect reconnaissance
- Knowing how weak credentials are tested helps defenders improve authentication security
- Knowing how payloads behave helps defenders improve endpoint monitoring
- Knowing what post-exploitation looks like helps SOC analysts investigate suspicious activity more effectively

This is why tools like Metasploit are valuable to both Red Team and Blue Team professionals.

## What I Learned

- Exploitation is only one part of a larger process
- Scanning and enumeration come before exploitation
- Open ports help identify possible attack surfaces
- Service versions can reveal outdated or vulnerable software
- Weak credentials create serious security risks
- The Metasploit database helps organize findings
- Vulnerability scanning helps validate possible weaknesses
- Meterpreter is used during post-exploitation in authorized environments
- Msfvenom generates payloads in different formats
- Tools are powerful, but methodology matters more — scope, authorization, evidence, impact, and documentation are what make a security professional responsible

## Defensive Takeaways

- Monitor exposed services
- Eliminate weak passwords
- Regularly review SMB, SSH, RDP, FTP, and HTTP services
- Patch and harden systems
- Monitor for scanning behavior
- Treat credential exposure seriously
- Maintain endpoint and network logs for investigation

## Final Thoughts

Studying Metasploit exploitation clarified the full security testing workflow: it starts with scanning, moves through understanding services and checking vulnerabilities, and ends with validating impact and understanding how defenders can detect this kind of activity. Ethical hacking must always be done with permission, responsibility, and a clear learning purpose.
