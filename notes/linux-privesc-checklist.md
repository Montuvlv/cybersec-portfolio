# Linux Privilege Escalation Cheat Sheet

## Basic Enumeration
Always start by gathering information about the system and current user.

- `whoami`: What user am I?
- `id`: What groups does this user belong to?
- `uname -a`: OS version and kernel info.
- `sudo -l`: What commands can I run as sudo without a password?
- `cat /etc/passwd`: View all users on the system.
- `cat /etc/crontab`: View scheduled cron jobs (look for scripts you can write to).

## SUID/SGID Binaries
Look for executables that have the SUID bit set, which run with the permissions of the file owner (usually root).

- `find / -perm -u=s -type f 2>/dev/null`: Find SUID files.
- **GTFOBins:** Always cross-reference found binaries with [GTFOBins](https://gtfobins.github.io/) to see if they can be abused for privesc.

## World-Writable Files/Directories
- `find / -writable -type d 2>/dev/null`: Find directories where you can write files.
- `find / -writable -type f 2>/dev/null`: Find writable files (sometimes configuration files or scripts).

## Automated Tools
Tools to quickly find potential privilege escalation vectors.
- **LinPEAS:** `wget https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh`
- **LinEnum:** `wget https://raw.githubusercontent.com/rebootuser/LinEnum/master/LinEnum.sh`
