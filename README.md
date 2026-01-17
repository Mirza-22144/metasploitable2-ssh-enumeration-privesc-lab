# Metasploitable 2: Full Attack Surface Lab (Authorized, Local)

This repository documents an **end-to-end penetration testing lab** against **Metasploitable 2** in a **controlled, isolated environment** using **Kali Linux (ARM)** and **Metasploitable 2 (x86 emulation)** on an Apple Silicon Mac (M5) via **UTM**.

The focus of this repo is to build practical skills in:
- **Host discovery & connectivity validation**
- **Full port/service enumeration + version fingerprinting**
- **Attack surface mapping and risk-based prioritization**
- **Vulnerability validation (lab-only) with sanitized evidence**
- **Post-exploitation verification (proof of access)**
- **Remediation-focused documentation (how to fix/mitigate)**

> ✅ **Ethics & Scope**
> - This work was performed **only** against **Metasploitable 2**, an intentionally vulnerable training VM.
> - Do **not** apply these techniques to systems you do not own or do not have explicit permission to test.
> - This repo is written to be **portfolio-safe**: no passwords, payloads, wordlists, or sensitive artifacts are published.

---

## Lab Environment

- **Host:** macOS (Apple Silicon M5)
- **Virtualization:** UTM
- **Attacker VM:** Kali Linux (ARM)
- **Target VM:** Metasploitable 2 (x86 emulation)
- **Target IP:** `192.168.1.119`

---

## Methodology (High Level)

1. Confirm target reachability and basic network assumptions
2. Perform full TCP scanning and service version detection
3. Build an attack-surface inventory (ports, services, versions)
4. Prioritize services by risk and exposure
5. Validate vulnerabilities in a lab-only setting and capture **sanitized** evidence
6. Document findings like a real pentest report: **impact + remediation**

---

## Recon & Enumeration (Evidence)

### Connectivity Check
- ICMP reachability confirmed from Kali to target (`ping 192.168.1.119`)

### Port Scan + Service Version Detection
Command used:
```bash
nmap -sV -p- 192.168.1.119



.
├── 00-setup/                # UTM + network topology + lab build notes
├── 01-recon/                 # discovery + Nmap commands/results
├── 02-attack-surface/        # service inventory table (ports/services/versions)
├── 03-enumeration/           # per-service notes (one folder per port/service)
├── 04-findings/              # report-style writeups (risk/impact/remediation)
├── 05-remediation/           # mitigations + hardening checklist
├── 06-evidence/              # sanitized logs/screenshots/outputs
└── report/                   # executive summary + final report





## Open Services Identified (Snapshot)

| Port | Protocol | Service | Version / Notes |
|------|----------|---------|-----------------|
| 21 | TCP | FTP | vsftpd 2.3.4 |
| 22 | TCP | SSH | OpenSSH 4.7p1 Debian 8ubuntu1 |
| 23 | TCP | Telnet | Linux telnetd |
| 25 | TCP | SMTP | Postfix smtpd |
| 53 | TCP | DNS | ISC BIND 9.4.2 |
| 80 | TCP | HTTP | Apache 2.2.8 (Ubuntu) DAV/2 |
| 111 | TCP | RPC | rpcbind v2 |
| 139 | TCP | SMB | Samba smbd 3.X–4.X (WORKGROUP) |
| 445 | TCP | SMB | Samba smbd 3.X–4.X (WORKGROUP) |
| 512 | TCP | rexec | netkit-rsh rexecd |
| 513 | TCP | rlogin | remote login service |
| 514 | TCP | tcpwrapped | service wrapped/filtered |
| 1099 | TCP | Java RMI | GNU Classpath grmiregistry |
| 1524 | TCP | bindshell | Metasploitable root shell (training backdoor) |
| 2049 | TCP | NFS | NFS v2–v4 (RPC #100003) |
| 2121 | TCP | FTP | ProFTPD 1.3.1 |
| 3306 | TCP | MySQL | MySQL 5.0.51a-3ubuntu5 |
| 3632 | TCP | distccd | distccd v1 (GNU 4.2.4) |
| 5432 | TCP | PostgreSQL | PostgreSQL 8.3.0–8.3.7 |
| 5900 | TCP | VNC | VNC protocol 3.3 |
| 6000 | TCP | X11 | access denied |
| 6667 | TCP | IRC | UnrealIRCd |
| 6697 | TCP | IRC (TLS) | UnrealIRCd |
| 8009 | TCP | AJP13 | Apache Jserv Protocol v1.3 |
| 8180 | TCP | HTTP (Tomcat) | Apache Tomcat/Coyote JSP engine 1.1 |
| 8787 | TCP | DRb | Ruby DRb RMI (Ruby 1.8) |
| 36071 | TCP | nlockmgr | NFS lock manager (RPC #100021) |
| 40826 | TCP | Java RMI | GNU Classpath grmiregistry |
| 48842 | TCP | status | RPC status (RPC #100024) |
| 60877 | TCP | mountd | RPC mountd (RPC #100005) |
