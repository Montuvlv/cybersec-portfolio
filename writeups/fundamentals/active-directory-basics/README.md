# Active Directory Basics – TryHackMe

**Category:** Windows / Enterprise Environments
**Difficulty:** Easy
**Skills demonstrated:** AD structure, domain concepts, user/group management, GPOs

## Objective
Introduces the core concepts and components of Active Directory (AD) — the
identity and access management system used by the vast majority of
enterprise Windows networks. This is foundational knowledge before
attempting any AD attack path (Kerberoasting, AS-REP Roasting, lateral
movement, etc.) in later rooms like Attacktive Directory.

## Environment
- Target: THM-provided Windows Server VM configured as a Domain Controller
- Access: RDP / browser-based

## Methodology

### 1. AD structure & terminology
Explored the core hierarchy:
- **Forest** → top-level container
- **Domain** → logical grouping of objects (users, computers, groups)
- **Organizational Units (OUs)** → containers used to organize objects and
  apply policy
- **Domain Controller (DC)** → server running AD Domain Services, holds the
  database of all domain objects

### 2. Objects in AD
```powershell
Get-ADUser -Filter *
Get-ADGroup -Filter *
Get-ADComputer -Filter *
```
Reviewed how users, groups, and computers are represented as objects in AD,
each with attributes (SID, distinguished name, group membership) that
matter during enumeration in a real attack.

### 3. Group Policy Objects (GPOs)
Explored how GPOs push configuration (password policies, software
restrictions, login scripts) to users/computers within an OU — and how
misconfigured GPOs are a common privilege escalation / lateral movement
vector in real AD environments.

### 4. Authentication basics
Covered how AD authentication relies on **Kerberos** by default (with NTLM
as a fallback), which is the foundation for understanding later attacks
like Kerberoasting and Pass-the-Hash.

## Key findings / takeaways
- AD's hierarchical trust model (forest → domain → OU) means a single
  misconfiguration at a high level (e.g. a permissive GPO) can cascade
  across thousands of objects
- Kerberos-based authentication is the reason AD attacks look very
  different from standalone Windows machine attacks

## What I learned
- AD enumeration (`Get-AD*` cmdlets, or tools like BloodHound in later
  rooms) is the first step in any AD-focused engagement — you can't attack
  what you haven't mapped
- Understanding the forest/domain/OU hierarchy is essential before
  Kerberoasting or AS-REP Roasting make sense conceptually
- This room is prerequisite knowledge for Attacktive Directory and any
  further AD attack-path rooms

## Flags
Redacted per TryHackMe's terms of service. Completion verifiable via my
[TryHackMe profile](https://tryhackme.com/p/montuvalvi074).
