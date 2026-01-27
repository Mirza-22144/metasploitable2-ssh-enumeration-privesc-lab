# Remediation Report: Port 23 (Telnet) 🛠️

---

## 1. Vulnerability Summary
- **Finding ID:** F-003
- **Port/Service:** 23/tcp — Telnet
- **Vulnerability:** Use of Unencrypted Protocol (Cleartext Data Transmission)
- **Risk Level:** High 🔴
- **Impact:** Administrative credentials (`msfadmin:msfadmin`) were intercepted in cleartext via packet sniffing. This can enable full system compromise and lateral movement.

---

## 2. Hardening Strategy 🧱

The primary goal is to eliminate the use of unencrypted remote access and transition to a secure, encrypted standard (**SSH**).

### Step A: Disable the Insecure Service
On Metasploitable 2, Telnet is managed by the `openbsd-inetd` super-server. Disabling this service stops the Telnet daemon from listening for connections.

**Command to stop Telnet service:**
```bash
sudo service openbsd-inetd stop
```

### Step B: Migrate to Secure Alternative (SSH)

Users should be transitioned to SSH (Port 22) for all remote administration. SSH protects credentials and session data using encryption.

Standard SSH connection method:

ssh msfadmin@192.168.1.122


Optional hardening (recommended in real environments):

Disable password authentication and use SSH keys (where feasible)

Restrict SSH to trusted source IPs (firewall allow-list)

Disable root login over SSH


## 3. Verification Checklist ✅

After applying the remediation, perform the following tests to ensure the system is hardened:

 Service Check: Run sudo service openbsd-inetd status to confirm it is stopped.

 Port Scan: From the attacker machine, run:

nmap -p 23 192.168.1.122


The port state should be closed.

 Sniffing Confirmation: Open Wireshark, filter for ssh, and log in via Port 22. Verify that captured application data is encrypted and unreadable.

 Access Test: Confirm successful login via SSH with msfadmin credentials.
