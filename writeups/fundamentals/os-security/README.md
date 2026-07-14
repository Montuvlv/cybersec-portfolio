# Operating System Security & SSH Authentication

**Category:** Fundamentals
**Rooms covered:** Operating System Security
**Difficulty:** Easy
**Skills demonstrated:** SSH key generation, secure authentication, basic OS hardening

## Objective
This writeup documents key takeaways from the Operating System Security room on TryHackMe, with a specific focus on a practical demonstration of secure SSH authentication.

## Environment
- Target: THM-provided VM
- Attacking machine: Local terminal

## Methodology

### 1. Authentication vs. Authorization
*Briefly explain the difference between the two concepts as taught in the room.*
- **Authentication:** Who are you?
- **Authorization:** What are you allowed to do?

### 2. SSH Key-Based Authentication Demo
*Walk through the process of setting up and using SSH keys instead of passwords.*

**Step 1: Generating the Key Pair**
*Show the command you used (e.g., `ssh-keygen -t ed25519`). Explain the public and private keys.*

**Step 2: Transferring the Public Key**
*Explain how to move the public key to the target server (e.g., `ssh-copy-id`).*

**Step 3: Logging In securely**
*Show the command to log in using the private key and explain why this is significantly more secure than password authentication (prevents brute-forcing).*

## Key findings / takeaways
- Hardening OS services like SSH is critical to prevent unauthorized access and brute-force attacks.

## What I learned
- The core difference between authentication and authorization.
- Practical application of SSH key pairs for secure login.

## Flags
Redacted per TryHackMe's terms of service. Completion verifiable via my
[TryHackMe profile](https://tryhackme.com/p/montuvalvi074).
