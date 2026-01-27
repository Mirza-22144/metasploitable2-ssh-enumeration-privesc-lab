# Finding Template: F-003-telnet-cleartext

---

## Finding ID
- **ID:** F-003
- **Title:** Exposure of Sensitive Credentials via Unencrypted Telnet 🔓
- **Date:** 2026-01-27
- **Status:** Validated

---

## Summary 
Describe the issue in plain English:
- The target system utilizes the **Telnet protocol** for remote management, which lacks any form of encryption. 
- This allows an attacker to perform a **Man-in-the-Middle (MITM)** attack to intercept administrative credentials and session data in cleartext. 🕵️‍♂️

---

## Scope
- **Target:** 192.168.1.122
- **Service / Port:** 23/tcp Telnet
- **Component / Software:** Linux telnetd
- **Environment:** Authorized local lab (Metasploitable 2)

---

## Evidence (Sanitized)
Link to your enumeration notes and include only safe outputs.

### Enumeration Notes
- `../03-enumeration/23-telnet/README.md`

### Evidence Files
- `../06-evidence/commands-output/telnet-banner.txt`
- `../06-evidence/commands-output/telnet-session-capture.txt`
- `../06-evidence/screenshots/telnet-wireshark-cleartext.png`

### Proof (Short Snippet)
```text
[REDACTED] login: msfadmin
Password: [REDACTED]
Last login: Mon Jan 26 22:59:06 EST 2026 on tty1
msfadmin@metasploitable:~$ whoami
msfadmin
msfadmin@metasploitable:~$ ls
vulnerable
