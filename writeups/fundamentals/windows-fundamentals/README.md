# Windows Command Line & PowerShell Basics

## 📖 Overview
This writeup combines concepts from the **Windows CLI Basics**, **Windows Command Line**, and **Windows PowerShell** modules on TryHackMe. It acts as a reference guide for interacting with Windows environments without a GUI.

---

## 💻 1. Windows CLI Basics (CMD)
*Discuss your experience using the traditional Windows Command Prompt.*

**Common Commands:**
- `dir` / `cd`: Navigation
- `type`: Reading files (equivalent to cat)
- `findstr`: Searching text
- `net user` / `net localgroup`: User management enumeration

---

## ⚡ 2. Windows PowerShell
*Explain why PowerShell is significantly more powerful than CMD and how it utilizes objects instead of text.*

**Key Concepts:**
- **Cmdlets:** Explain what they are (Verb-Noun syntax).
- **Execution Policy:** How to check or bypass execution policies (`Set-ExecutionPolicy Bypass`).
- **Piping:** How piping objects works in PowerShell vs text in Linux.

---

## 🛠️ 3. Essential Cmdlets for Security
*List the cmdlets you found most useful during the labs for enumeration or administration.*

- `Get-Help`: Finding documentation.
- `Get-Command`: Searching for cmdlets.
- `Get-Process` / `Get-Service`: Enumerating running tasks.
- `Invoke-WebRequest`: Downloading files (equivalent to wget/curl).

---

## 🎯 Conclusion
*Summarize your thoughts on navigating Windows from the command line and how PowerShell is utilized in both administration and exploitation (e.g., PowerShell Empire/BloodHound).*
