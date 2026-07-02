# Nmap Cheat Sheet

## Basic Scans
- `nmap <target>`: Scan top 1000 TCP ports.
- `nmap -p- <target>`: Scan all 65535 TCP ports.
- `nmap -p 1-1000 <target>`: Scan ports 1 to 1000.
- `nmap -p 22,80,443 <target>`: Scan specific ports.

## Discovery & Detection
- `nmap -sV <target>`: Determine service/version info on open ports.
- `nmap -O <target>`: Enable OS detection.
- `nmap -A <target>`: Aggressive scan (OS detection, version detection, script scanning, and traceroute).

## Scripting Engine (NSE)
- `nmap -sC <target>`: Run default, safe scripts.
- `nmap --script vuln <target>`: Run scripts in the "vuln" category to check for known vulnerabilities.

## Output Formats
- `nmap -oN nmap_normal.txt <target>`: Output in normal format.
- `nmap -oG nmap_grep.txt <target>`: Output in grepable format.
- `nmap -oA nmap_all <target>`: Output in all major formats (normal, grepable, XML).

## Stealth & Evasion
- `nmap -sS <target>`: TCP SYN Scan (Stealth scan, requires root).
- `nmap -Pn <target>`: Treat all hosts as online (skip ping discovery).
