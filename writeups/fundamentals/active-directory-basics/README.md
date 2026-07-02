# Active Directory Basics

## 📖 Overview
Active Directory (AD) is the backbone of most corporate enterprise networks. This writeup covers the foundational concepts learned in the **Active Directory Basics** TryHackMe room. Understanding AD is critical for both Red Teaming (Lateral Movement, Privilege Escalation) and Blue Teaming (Monitoring, Securing).

---

## 🏗️ 1. What is Active Directory?
*Provide a high-level explanation of what AD is and why organizations use it (Centralized management, identity, and access).*

---

## 🌳 2. Domains, Trees, and Forests
*Explain the logical structure of Active Directory.*

- **Domain:** The core logical structure.
- **Tree:** A collection of domains that share a contiguous namespace.
- **Forest:** The highest level of organization; a collection of one or more trees.

---

## 👥 3. Users, Groups, & OUs (Organizational Units)
*Discuss how objects are categorized in AD.*

- **Users/Computers:** The base objects.
- **Groups (Security vs Distribution):** How permissions are assigned efficiently.
- **OUs:** How administrators organize objects to apply policies.

---

## 📜 4. Group Policy Objects (GPO)
*Explain what GPOs are and how they enforce security policies across the network.*
*Example: Disabling USB drives, enforcing password complexity.*

---

## 🎯 Conclusion & Security Implications
*Why is AD a high-value target for attackers? Mention concepts like Kerberoasting, AS-REP Roasting, or BloodHound enumeration that you plan to learn next.*
