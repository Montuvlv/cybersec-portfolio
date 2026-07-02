# Linux Fundamentals – TryHackMe

**Category:** Systems / Fundamentals
**Rooms covered:** Linux CLI Basics, Linux Fundamentals Part 1-3, Linux Shells
**Difficulty:** Easy
**Skills demonstrated:** Terminal navigation, SSH, file permissions, process management, shell scripting basics

## Objective
This set of rooms builds core Linux command-line competency — the baseline skill
required before any privilege escalation, enumeration, or exploitation work.
Covers navigating the filesystem, connecting to remote machines over SSH,
managing users/permissions, and understanding shell types.

## Environment
- Target: THM-provided Linux VM (browser terminal / SSH via VPN)
- Attacking machine: Kali Linux / local terminal

## Methodology

### 1. Filesystem navigation & file operations
```bash
pwd
ls -la
cd /var/www
find / -name "*.conf" 2>/dev/null
```
Practiced navigating the Linux directory tree, listing hidden files, and
using `find` to locate configuration files — a habit that carries directly
into recon on real engagements.

### 2. Connecting via SSH
```bash
ssh username@10.10.x.x -p 22
```
Logged into the target machine using SSH, the primary remote-access method
used throughout TryHackMe and in real-world Linux administration.

### 3. File permissions & ownership
```bash
ls -l file.txt
chmod 755 script.sh
chown user:group file.txt
```
Learned the rwx permission model (owner/group/other) and how misconfigured
permissions (e.g. world-writable scripts run by root) become a privilege
escalation vector later on.

### 4. Process & service management
```bash
ps aux
top
systemctl status ssh
```
Reviewed running processes and services — relevant for both enumeration
(what's running on a box) and later privesc work (what's running as root).

### 5. Shell types
Compared `bash`, `sh`, and `zsh` behavior, and how shell selection affects
scripting compatibility — relevant when writing exploit/reverse-shell
payloads that need to match the target's available shell.

## Key findings / takeaways
- File permission misconfigurations are one of the most common real-world
  privesc paths — this is the foundation for the Linux PrivEsc room
- SSH key-based auth vs password auth has direct implications for both
  attackers (credential access) and defenders (hardening)

## What I learned
- Comfort with the CLI is non-negotiable — GUI tools don't exist on most
  target/server environments
- Permission and ownership models (`chmod`/`chown`) are foundational to
  understanding privilege escalation later in the pentest path
- `find`, `grep`, and piping (`|`) are the three tools I'll use constantly
  during recon

## Flags
Redacted per TryHackMe's terms of service. Completion verifiable via my
[TryHackMe profile](https://tryhackme.com/p/montuvalvi074).
