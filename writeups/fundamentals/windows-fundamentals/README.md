# Windows Fundamentals – TryHackMe

**Category:** Systems / Fundamentals
**Rooms covered:** Windows CLI Basics, Windows Command Line, Windows PowerShell, Windows Fundamentals 1-3
**Difficulty:** Easy
**Skills demonstrated:** CMD navigation, PowerShell scripting basics, Windows Registry, UAC, system configuration

## Objective
Builds core competency navigating and administering Windows systems from the
command line — essential for both offensive work (Windows is the most common
enterprise target) and defensive work (most SOC alerts originate from Windows
endpoints).

## Environment
- Target: THM-provided Windows VM (RDP / browser-based access)
- Tools used: Command Prompt (cmd.exe), PowerShell

## Methodology

### 1. CMD navigation & file operations
```cmd
dir
cd C:\Users\
tree /f
type file.txt
```
Practiced core CMD navigation and file inspection commands — the Windows
equivalent of `ls`/`cat`/`find` on Linux.

### 2. PowerShell basics
```powershell
Get-Process
Get-Service
Get-ChildItem -Recurse -Include *.txt
Get-LocalUser
```
Used PowerShell cmdlets to enumerate running processes, services, and local
users. PowerShell's object-oriented output (vs plain text in CMD) makes it
far more powerful for scripting and automation — and it's the same tool
attackers abuse for living-off-the-land techniques.

### 3. System configuration & UAC
Explored Control Panel, System Configuration (`msconfig`), and User Account
Control (UAC) settings — understanding how UAC prompts function is relevant
both for legitimate admin work and for recognizing privilege-escalation
attempts as a defender.

### 4. Windows Registry
```cmd
regedit
```
Navigated the Registry structure (HKEY_LOCAL_MACHINE, HKEY_CURRENT_USER) —
a common location for persistence mechanisms and configuration artifacts
that both attackers and forensic analysts interact with.

### 5. NTFS & file permissions
Reviewed how NTFS permissions differ from Linux's rwx model — Windows uses
ACLs (Access Control Lists) with more granular permission types
(Read, Write, Modify, Full Control).

## Key findings / takeaways
- PowerShell's scripting depth is significantly greater than CMD — most
  real-world Windows administration (and a lot of red-team tooling) happens
  in PowerShell, not CMD
- The Registry is a high-value location during both persistence
  (offensive) and incident investigation (defensive)

## What I learned
- Windows CLI tooling is split across two ecosystems (legacy CMD vs modern
  PowerShell) and knowing both is necessary — CMD still shows up in legacy
  environments and scripts
- Understanding NTFS ACLs matters for spotting misconfigured permissions
  during a Windows privesc assessment
- PowerShell's `Get-` cmdlet pattern makes system enumeration much faster
  once you know the naming convention

## Flags
Redacted per TryHackMe's terms of service. Completion verifiable via my
[TryHackMe profile](https://tryhackme.com/p/montuvalvi074).
