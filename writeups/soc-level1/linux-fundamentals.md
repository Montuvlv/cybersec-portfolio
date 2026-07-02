# Linux Fundamentals (CLI, Permissions, & Shells)

## 📖 Overview
This writeup consolidates my learnings from the **Linux CLI Basics**, **Linux Fundamentals (Parts 1-3)**, and **Linux Shells** modules on TryHackMe. It serves as a core reference for navigating and interacting with Linux systems, which is essential for any cybersecurity role.

---

## 🔐 1. SSH Login & Remote Access
*Briefly explain how you used SSH to connect to the target machines in the labs.*

**Example Command:**
```bash
ssh user@<target-ip>
```
*Add your notes on SSH keys, the known_hosts file, etc.*

---

## 🛠️ 2. Common Utilities & Navigation
*Document the essential commands you learned for navigating the system.*

- `ls` / `cd` / `pwd`: Basic navigation.
- `cat` / `less` / `head` / `tail`: Reading files.
- `grep` / `find`: Searching for files or strings.
- `wget` / `curl`: Downloading files.

*Add practical examples of how you used these in the THM rooms.*

---

## 🛡️ 3. File Permissions
*Explain the Linux permission structure (User, Group, Other) and how to read/change them.*

- **Understanding Permissions:** e.g., `rwxr-xr--`
- **Chmod:** How to change permissions (e.g., `chmod +x script.sh` or `chmod 755 script.sh`).
- **Chown:** How to change ownership.

---

## 🐚 4. Linux Shells
*Discuss the difference between shells (e.g., Bash, Zsh) and any reverse/bind shells you explored in the modules.*

- **Reverse Shells:** *Your notes here*
- **Bind Shells:** *Your notes here*
- **Netcat (nc):** *How you used nc to catch a shell.*

---

## 🎯 Conclusion
*Summarize what you took away from these modules and how it applies to real-world penetration testing or SOC analysis.*
