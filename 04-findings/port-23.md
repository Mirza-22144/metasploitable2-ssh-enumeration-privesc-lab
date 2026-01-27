# Finding Template (Fill As You Go)

> Copy this file for each issue and rename it like:  
> `F-001-short-title.md` (example: `F-001-ssh-weak-auth.md`)

---

## Finding ID
- **ID:** `F-XXX`
- **Title:** `<short, clear title>`
- **Date:** `<YYYY-MM-DD>`
- **Status:** `Draft / Validated / Completed`

---

## Summary (1–3 sentences)
Describe the issue in plain English:
- `<what is exposed/misconfigured/vulnerable?>`
- `<why it matters?>`

---

## Scope
- **Target:** `192.168.1.119`
- **Service / Port:** `<e.g., 22/tcp SSH>`
- **Component / Software:** `<e.g., OpenSSH 4.7p1>`
- **Environment:** `Authorized local lab (Metasploitable 2)`

---

## Evidence (Sanitized)
Link to your enumeration notes and include only safe outputs.

### Enumeration Notes
- `../03-enumeration/<port-service>/README.md`

### Evidence Files
- `../03-enumeration/<port-service>/evidence/<file1>.txt`
- `../03-enumeration/<port-service>/evidence/<file2>.txt`

### Proof (Short Snippet)
Paste a *small* redacted snippet (no creds/hashes/payloads):
```text
<sanitized output here>

