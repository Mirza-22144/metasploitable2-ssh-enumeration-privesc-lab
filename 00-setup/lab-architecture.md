<!-- ========================================================= -->
<!-- 00-setup/lab-architecture.md -->
<!-- ========================================================= -->

# Lab Architecture (Metasploitable 2 Full Attack Surface Lab)

## Purpose
This is a **local, authorized** penetration-testing training environment built to practice:
- host discovery and connectivity validation
- full port/service enumeration and version fingerprinting
- attack surface mapping and prioritization
- vulnerability validation with **sanitized evidence**
- remediation-focused documentation (impact + fixes)

This repository is intended to be **portfolio-safe** and avoids publishing credentials, wordlists, payloads, or sensitive system artifacts.

---

## Scope & Rules of Engagement
**In scope**
- Metasploitable 2 training VM only
- Traffic between attacker VM and target VM within the lab network

**Out of scope**
- Any real-world hosts or networks without explicit written permission
- Publishing exploit steps/payloads, passwords, hashes, or private keys

**Evidence policy**
- Store only **sanitized** logs and screenshots (no creds, hashes, or weaponized commands)

---

## System Overview

### Host Machine
- **Platform:** macOS (Apple Silicon M5)
- **Role:** Runs the virtualized lab environment via UTM

### Virtualization Layer
- **Hypervisor/Emulator:** UTM
- **Goal:** Run an ARM attacker VM and emulate an x86 target VM on Apple Silicon

### Attacker VM
- **Name:** Kali Linux (ARM)
- **Role:** Enumeration, scanning, analysis, and validation tooling

### Target VM
- **Name:** Metasploitable 2 (x86 emulation)
- **Role:** Intentionally vulnerable target for training and documentation

---


### Addressing
- **Target IP (Metasploitable 2):** `192.168.1.119`
- **Attacker IP (Kali):** `<ATTACKER_IP>` (optional to record)

### Connectivity Validation
- ICMP reachability is used to confirm basic network path:
  - `ping 192.168.1.119`

---

## Data & Evidence Handling

### What is safe to publish
- Nmap scan results (ports/services/versions)
- service banners/headers that don’t include secrets
- proof-of-access outputs (sanitized): `whoami`, `hostname`, `uname -a`, minimal interface lines
- permission boundary checks (sanitized): `sudo -l` summary if needed

### What is NOT published
- usernames/passwords (even defaults)
- wordlists
- exploit payloads and copy/paste weaponized steps
- hashes, `/etc/shadow`, private keys, tokens, or session cookies

### Suggested Evidence Storage
- `06-evidence/sanitized-logs/`
- `06-evidence/screenshots/`
- `03-enumeration/<port-service>/evidence/`

---

## Reproducibility Notes (High-Level)
1. Create/import both VMs in UTM:
   - Kali Linux (ARM)
   - Metasploitable 2 (x86 emulation)
2. Place both VMs on the same virtual network
3. Boot both VMs and confirm IP addressing
4. Confirm attacker can reach target (ICMP)
5. Run recon and document outputs in:
   - `01-recon/nmap-commands.md`
   - `01-recon/nmap-results.md`


<!-- ========================================================= -->
<!-- 00-setup/utm-configuration.md -->
<!-- ========================================================= -->

# UTM Configuration

> This file records the key VM settings used in this lab so the environment is reproducible.

## VM List
- Kali Linux (ARM)
- Metasploitable 2 (x86 emulation)

---

## Kali Linux (ARM) Settings
- **CPU:** `<SET_THIS>`
- **RAM:** `<SET_THIS>`
- **Disk:** `<SET_THIS>`
- **Network Mode:** `<Bridged / NAT / Host-only>`
- **Notes:** `<clipboard sharing, guest tools, display settings, etc.>`

---

## Metasploitable 2 (x86) Settings
- **CPU:** `<SET_THIS>`
- **RAM:** `<SET_THIS>`
- **Disk:** `<SET_THIS>`
- **Network Mode:** `<Bridged / NAT / Host-only>`
- **Notes:** `<emulation notes, boot quirks, etc.>`

---




