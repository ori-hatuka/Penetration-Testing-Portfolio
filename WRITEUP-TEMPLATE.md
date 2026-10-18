<!--
  ╔══════════════════════════════════════════════════════════════════╗
  ║  HOW TO USE THIS TEMPLATE                                         ║
  ║  1. Copy this file into the right folder and rename it to the     ║
  ║     machine, e.g. HTB-Writeups/Web-Application/Jerry.md           ║
  ║  2. Fill every section. Delete guidance lines written in italics. ║
  ║  3. Put screenshots in an images/ folder next to the file and     ║
  ║     reference them:  ![alt text](images/01-nmap.png)              ║
  ║  4. PUBLISH ONLY RETIRED machines (or VulnHub / Starting Point).  ║
  ║     Confirm "Retired" on the machine page before committing.      ║
  ╚══════════════════════════════════════════════════════════════════╝
-->

# <MACHINE NAME>

![Platform](https://img.shields.io/badge/Platform-Hack%20The%20Box-9FEF00?style=flat-square)
![OS](https://img.shields.io/badge/OS-Linux-blue?style=flat-square)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-brightgreen?style=flat-square)
![Status](https://img.shields.io/badge/Status-Retired-lightgrey?style=flat-square)

| | |
|---|---|
| **Machine** | `<name>` |
| **Platform** | Hack The Box / VulnHub |
| **OS** | Linux / Windows |
| **Difficulty** | Easy / Medium / Hard |
| **Date** | <YYYY-MM-DD> |
| **Primary vector** | *one line — e.g. "SQL injection → file upload → sudo misconfig"* |

---

## 1. Executive Summary

*Two or three sentences a non-technical reader can follow: how you got in, how you reached root/SYSTEM, and the single root cause. Write this LAST, after the rest is done.*

> Example: The host exposed an outdated web application vulnerable to unauthenticated file upload, which allowed a web shell and a foothold as `www-data`. A `sudo` misconfiguration on a system binary then allowed privilege escalation to `root`. The core issue was missing input validation combined with over-permissive `sudo` rules.

---

## 2. Reconnaissance

### Port & service scan

```bash
nmap -sC -sV -oA nmap/<name> <IP>
```

*Paste the trimmed, relevant output — not 500 lines. Keep the open ports and versions that mattered.*

```
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH ...
80/tcp   open  http    Apache ...
```

### Enumeration

*What you found and how: directory brute-forcing (gobuster/dirb), the CMS/app version, exposed shares, default pages, interesting endpoints. One short paragraph + the commands.*

```bash
gobuster dir -u http://<IP> -w /usr/share/wordlists/dirb/common.txt
```

---

## 3. Initial Foothold

**Vulnerability:** *name it precisely — e.g. "Unauthenticated arbitrary file upload (CVE-XXXX-XXXX)" or "SQL injection on the `id` parameter".*

**Exploitation steps:**

1. *Step by step, reproducible. A reader should be able to repeat it.*
2. *Include the actual request / payload / command.*

```http
POST /upload.php HTTP/1.1
...
```

**Result:** shell as `<user>`.

```bash
id
# uid=33(www-data) gid=33(www-data)
```

*Screenshot of the shell:* `![foothold](images/02-foothold.png)`

---

## 4. Privilege Escalation

**Finding:** *what let you escalate — e.g. "passwordless `sudo` on `/usr/bin/vim`", "SUID binary", "cron job writable by the user", "GPP cpassword".*

**How you found it:**

```bash
sudo -l
# or: linpeas.sh / winPEAS.exe output — the relevant lines only
```

**Exploitation:**

1. *The exact escalation path.*
2. *The command / technique (GTFOBins link if relevant).*

**Result:** `root` / `SYSTEM`.

```bash
id
# uid=0(root) gid=0(root)
```

---

## 5. Findings & Remediation

*This table is what separates a professional report from a walkthrough. Every vulnerability you used becomes a finding with a severity and a fix. This is the section recruiters read.*

| # | Finding | Severity | Remediation |
|---|---------|----------|-------------|
| 1 | *Unauthenticated file upload allows web shell* | High | *Enforce server-side type/extension allow-listing; store uploads outside the web root; disable script execution in the upload directory.* |
| 2 | *Passwordless `sudo` on `<binary>` enables root* | Critical | *Remove the `sudo` entry or restrict it; follow least-privilege; audit `/etc/sudoers`.* |

**Severity guide:** Critical = direct root/SYSTEM or full data loss · High = foothold / sensitive data · Medium = meaningful weakness needing a chain · Low = hardening / info leak.

---

## 6. Tools Used

`Nmap` · `Gobuster` · `Burp Suite` · `<others actually used>`

---

## 7. Lessons Learned

*2–4 bullets, honest and specific. What was new, what you'd do faster next time, which technique you want to drill. This shows a recruiter you reflect, not just copy walkthroughs.*

- *...*
- *...*

---

> ℹ️ Published after the machine retired, in line with Hack The Box's policy on retired content.
