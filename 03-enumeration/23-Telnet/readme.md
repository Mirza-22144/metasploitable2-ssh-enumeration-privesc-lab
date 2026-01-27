# 23/tcp — Telnet Enumeration (Cleartext Credential Risk) 🛰️

> **Scope:** Authorized local lab only (Metasploitable 2)  
> **Target:** `192.168.1.122`  
> **Service:** Telnet (`23/tcp`)  
> **Detected Service/Version:** `Linux telnetd` (via Nmap)

---

## Overview
This folder documents the **enumeration phase** for **Port 23 (Telnet)** on the target VM. The goal of this stage is to:
- confirm the Telnet service is reachable,
- identify any banner / login behavior,
- validate the protocol-level risk of **cleartext transmission** using packet analysis,
- and store **sanitized evidence** suitable for a public GitHub portfolio.

> This repo does **not** include weaponized exploit steps, payloads, or credential lists.

---

## Why I Didn’t Stop at the Banner
During initial interaction, the Telnet banner provided an **overly direct entry point** (default credentials presented immediately). While this is a valid misconfiguration, it’s also **unrealistic in most real environments**, where services rarely advertise credentials so openly.

To demonstrate a more technical and realistic risk, I moved beyond the banner and performed **packet sniffing** to prove Telnet’s core weakness: **credentials and session data can be intercepted in cleartext** by anyone with visibility on the network path.

---

## Key Findings (High Level)
- Telnet is running and accessible on **23/tcp**.
- The service banner discloses **default credentials** (high-risk misconfiguration).
- Packet analysis confirms Telnet traffic (including authentication strings) can be observed in **cleartext** by a network observer.

---

## Method Summary
1. **Service confirmation** with Nmap (port open + service fingerprint).
2. **Banner interaction** via Telnet client to observe login prompt/banner behavior.
3. **Protocol analysis** using Wireshark to verify whether login/session data is encrypted (it is not).

---

## Evidence
- `03-enumeration/23-Telnet/images`
- **Enumeration write-up:** `23-telnet-enumeration.md`
- **Raw banner output (sanitized):** `evidence/telnet-banner.txt`
- **Session capture (sanitized):** `../../06-evidence/commands-output/telnet-session-capture.txt`
- **Wireshark proof screenshot:** `../../06-evidence/screenshots/telnet-wireshark-cleartext.png`

---

## How This Maps to a Finding
This enumeration supports **Finding F-003** (Telnet cleartext transmission / insecure remote access).  
Remediation steps are documented in:
- `../../05-remediation/23-telnet-remediation.md`

---

## Notes on Safe Redaction (Public Repo)
Do **not** upload:
- passwords/credentials (even defaults)
- packet capture files (`.pcap`) containing real cleartext logins
- hashes, `/etc/shadow`, keys, tokens, or exploit payloads

Use screenshots and sanitized text outputs instead.
