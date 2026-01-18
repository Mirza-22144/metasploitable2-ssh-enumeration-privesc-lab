<!-- 00-setup/lab-architecture.md -->

# Lab Architecture 

## Purpose
This lab is a **local, authorized** penetration-testing training environment built to practice:
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
- **Typical tools:** Nmap, Metasploit Framework, netcat, curl, smbclient, rpc tools (as needed)

### Target VM
- **Name:** Metasploitable 2 (x86 emulation)
- **Role:** Intentionally vulnerable target for training and documentation

---

## Network Design

### Topology

