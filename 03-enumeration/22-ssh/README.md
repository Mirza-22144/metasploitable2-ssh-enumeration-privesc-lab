# metasploitable2-ssh-enumeration-privesc-lab
Hands-on Metasploitable 2 pentesting lab: host discovery, full port/service enumeration, SSH authentication testing, post-exploitation validation, and privilege escalation in an isolated environment.
## Metasploitable 2 Lab: Service Enumeration → SSH Access → Privilege Escalation (Local, Authorized)

This repository documents a **hands-on penetration testing lab** performed in a **controlled, isolated environment** using **Kali Linux (ARM)** and **Metasploitable 2 (x86 emulation)** on an Apple Silicon Mac (M5). The goal is to build practical skills in **reconnaissance, enumeration, authentication testing, and post-exploitation validation**—and to practice writing clear, repeatable security notes.

> **Ethics & Scope**
> - This work was completed **only** against **Metasploitable 2**, an intentionally vulnerable training VM.
> - Do **not** reuse these techniques or tooling on systems you do not own or explicitly have permission to test.

---

### Lab Environment

- **Host:** macOS on Apple Silicon (M5)
- **Virtualization:** UTM
- **Attacker VM:** Kali Linux (ARM edition)
- **Target VM:** Metasploitable 2 (x86 via emulation)
- **Network:** Same LAN segment / isolated lab network for VM-to-VM connectivity

---

### What I Did (High-Level)

1. **Confirmed connectivity** between attacker and target (ICMP reachability).
2. **Enumerated services** by scanning the target for open TCP ports and identifying running service versions.
3. **Focused on SSH (port 22)** after discovery, based on service exposure and feasibility.
4. **Performed authentication testing** against SSH using a community wordlist (lab-only) to validate weak credential risk.
5. **Validated access** by confirming session context (user identity, hostname, OS details, network interface).
6. **Checked privilege boundaries** and verified whether the authenticated user could elevate privileges (misconfiguration / excessive sudo permissions).
7. **Documented results** and captured evidence outputs for reporting and learning.

---

### Key Results (Summary)

- The target exposed **multiple network services** typical of an intentionally vulnerable system.
- SSH authentication testing demonstrated the risk of **weak/default credentials** in real environments.
- Post-access checks confirmed:
  - Successful interactive access as a valid user
  - Host/OS identification
  - Privilege escalation was possible due to permissive privilege configuration (lab scenario)

---

### Skills Demonstrated

- Network reachability validation
- Full service enumeration + version identification
- Attack surface prioritization (choosing a target service)
- Authentication testing methodology (controlled)
- Evidence-based post-exploitation verification
- Basic privilege escalation validation (permission review)

---

### Tools Used

- **Nmap** (service discovery / version detection)
- **Metasploit Framework** (authentication testing module + session interaction)
- Standard Linux commands for host verification (identity, OS, networking, privilege checks)

---

### Repository Contents (Suggested Structure)

- `notes/` — step-by-step lab notes and observations
- `evidence/` — sanitized command output screenshots/logs (no sensitive data)
- `wordlists/` — **do not** upload real credential lists used against live systems; keep lab-only lists private
- `report.md` — short write-up: objective, method, findings, takeaways

---

### Takeaways

This lab reinforced how quickly exposure + weak credentials can lead to unauthorized access, and why basic controls matter:
- strong credential policies
- disabling default accounts
- limiting SSH exposure
- least-privilege sudo configuration
- continuous service inventory and patching


---

This project is for **educational security training** and **portfolio demonstration** only. Any misuse is the responsibility of the user. Please test **only** in environments where you have explicit permission.

### Disclaimer

This project is for **educational security training** and **portfolio demonstration** only. Any misuse is the responsibility of the user. Please test **only** in environments where you have explicit permission.
