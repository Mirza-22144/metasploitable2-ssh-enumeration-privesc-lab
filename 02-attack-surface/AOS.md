# Services Inventory (Attack Surface)

This file is the **single source of truth** for the target’s exposed attack surface.  
It tracks **what is exposed**, **why it matters**, **what I’m doing next**, and links to supporting notes.

> **Target:** `192.168.1.119`  
> **Scope:** Authorized local lab (Metasploitable 2)  
> **Last updated:** `<YYYY-MM-DD>`

---

## Quick Legend
- **Priority:** High / Medium / Low (risk + likelihood)
- **Status:** Not started / Enumerating / Finding drafted / Completed
- **Exposure:** Remote = reachable over network; Local = requires existing access

---

## Inventory Table

| Port | Proto | Service | Version / Notes | Exposure | Priority | Status | Enumeration Notes | Findings |
|------|-------|---------|------------------|----------|----------|--------|-------------------|----------|
| 21 | TCP | FTP | vsftpd 2.3.4 | Remote | High | Not started | `../03-enumeration/21-ftp/README.md` | `../04-findings/F-XXX.md` |
| 22 | TCP | SSH | OpenSSH 4.7p1 Debian 8ubuntu1 | Remote | High | Enumerating | `../03-enumeration/22-ssh/README.md` | `../04-findings/F-XXX.md` |
| 23 | TCP | Telnet | Linux telnetd | Remote | High | Not started | `../03-enumeration/23-telnet/README.md` | `../04-findings/F-XXX.md` |
| 25 | TCP | SMTP | Postfix smtpd | Remote | Medium | Not started | `../03-enumeration/25-smtp/README.md` | `../04-findings/F-XXX.md` |
| 53 | TCP | DNS | ISC BIND 9.4.2 | Remote | Medium | Not started | `../03-enumeration/53-dns/README.md` | `../04-findings/F-XXX.md` |
| 80 | TCP | HTTP | Apache 2.2.8 (Ubuntu) DAV/2 | Remote | High | Not started | `../03-enumeration/80-http/README.md` | `../04-findings/F-XXX.md` |
| 111 | TCP | RPC | rpcbind v2 | Remote | Medium | Not started | `../03-enumeration/111-rpc/README.md` | `../04-findings/F-XXX.md` |
| 139 | TCP | SMB | Samba smbd 3.X–4.X (WORKGROUP) | Remote | High | Not started | `../03-enumeration/139-445-smb/README.md` | `../04-findings/F-XXX.md` |
| 445 | TCP | SMB | Samba smbd 3.X–4.X (WORKGROUP) | Remote | High | Not started | `../03-enumeration/139-445-smb/README.md` | `../04-findings/F-XXX.md` |
| 512 | TCP | rexec | netkit-rsh rexecd | Remote | High | Not started | `../03-enumeration/512-rexec/README.md` | `../04-findings/F-XXX.md` |
| 513 | TCP | rlogin | remote login service | Remote | High | Not started | `../03-enumeration/513-rlogin/README.md` | `../04-findings/F-XXX.md` |
| 514 | TCP | tcpwrapped | wrapped/filtered | Remote | Low | Not started | `../03-enumeration/514-tcpwrapped/README.md` | `../04-findings/F-XXX.md` |
| 1099 | TCP | Java RMI | GNU Classpath grmiregistry | Remote | Medium | Not started | `../03-enumeration/1099-java-rmi/README.md` | `../04-findings/F-XXX.md` |
| 1524 | TCP | bindshell | Metasploitable root shell (training backdoor) | Remote | High | Not started | `../03-enumeration/1524-bindshell/README.md` | `../04-findings/F-XXX.md` |
| 2049 | TCP | NFS | v2–v4 (RPC #100003) | Remote | High | Not started | `../03-enumeration/2049-nfs/README.md` | `../04-findings/F-XXX.md` |
| 2121 | TCP | FTP | ProFTPD 1.3.1 | Remote | Medium | Not started | `../03-enumeration/2121-proftpd/README.md` | `../04-findings/F-XXX.md` |
| 3306 | TCP | MySQL | MySQL 5.0.51a-3ubuntu5 | Remote | Medium | Not started | `../03-enumeration/3306-mysql/README.md` | `../04-findings/F-XXX.md` |
| 3632 | TCP | distccd | distccd v1 (GNU 4.2.4) | Remote | High | Not started | `../03-enumeration/3632-distccd/README.md` | `../04-findings/F-XXX.md` |
| 5432 | TCP | PostgreSQL | PostgreSQL 8.3.0–8.3.7 | Remote | Medium | Not started | `../03-enumeration/5432-postgresql/README.md` | `../04-findings/F-XXX.md` |
| 5900 | TCP | VNC | protocol 3.3 | Remote | Medium | Not started | `../03-enumeration/5900-vnc/README.md` | `../04-findings/F-XXX.md` |
| 6000 | TCP | X11 | access denied | Remote | Low | Not started | `../03-enumeration/6000-x11/README.md` | `../04-findings/F-XXX.md` |
| 6667 | TCP | IRC | UnrealIRCd | Remote | Medium | Not started | `../03-enumeration/6667-irc/README.md` | `../04-findings/F-XXX.md` |
| 6697 | TCP | IRC (TLS) | UnrealIRCd | Remote | Medium | Not started | `../03-enumeration/6697-irc-tls/README.md` | `../04-findings/F-XXX.md` |
| 8009 | TCP | AJP13 | Apache Jserv Protocol v1.3 | Remote | Medium | Not started | `../03-enumeration/8009-ajp13/README.md` | `../04-findings/F-XXX.md` |
| 8180 | TCP | HTTP (Tomcat) | Tomcat/Coyote JSP engine 1.1 | Remote | High | Not started | `../03-enumeration/8180-tomcat/README.md` | `../04-findings/F-XXX.md` |
| 8787 | TCP | DRb | Ruby DRb RMI (Ruby 1.8) | Remote | Medium | Not started | `../03-enumeration/8787-drb/README.md` | `../04-findings/F-XXX.md` |
| 36071 | TCP | nlockmgr | RPC #100021 | Remote | Low | Not started | `../03-enumeration/36071-nlockmgr/README.md` | `../04-findings/F-XXX.md` |
| 40826 | TCP | Java RMI | GNU Classpath grmiregistry | Remote | Low | Not started | `../03-enumeration/40826-java-rmi/README.md` | `../04-findings/F-XXX.md` |
| 48842 | TCP | status | RPC #100024 | Remote | Low | Not started | `../03-enumeration/48842-rpc-status/README.md` | `../04-findings/F-XXX.md` |
| 60877 | TCP | mountd | RPC #100005 | Remote | Low | Not started | `../03-enumeration/60877-mountd/README.md` | `../04-findings/F-XXX.md` |

---

## Current Plan (Next Steps)
1. Finish enumeration for **High priority** services first (SSH, Telnet, FTP, SMB, NFS, Tomcat, distccd, bindshell).
2. Convert confirmed issues into **Findings** (risk + impact + remediation) under `04-findings/`.
3. Keep evidence sanitized and linked from both enumeration notes and findings.

---

## Redaction Rules (Public Repo)
- No credentials, wordlists, payloads, hashes, or `/etc/shadow`
- Evidence should be limited to safe outputs (versions, banners, sanitized proof-of-access)

