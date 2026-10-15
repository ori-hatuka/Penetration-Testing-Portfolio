# 🌐 Web Application Penetration Testing

Three grey-box web application engagements from the ITSafe track. Each has a full report with vulnerability description, proof-of-concept, and remediation.

## 📋 Engagements

### 🚗 Car Rental
A booking application.

| Finding | Summary |
|---------|---------|
| Parameter Tampering | Enumerated user IDs and modified another user's car order |
| JWT Authentication Bypass | Found exposed JWT signing keys via directory brute-forcing and forged an administrator token |
| Cross-Site Request Forgery (CSRF) | State-changing requests without anti-CSRF protection |
| Cross-Site Scripting (XSS) | Injected script executed in the victim's browser |

### 🏦 Hack Me Bank
A banking application.

| Finding | Summary |
|---------|---------|
| SQL Injection | Dumped the database with SQLMap from a captured Burp request |
| Parameter Tampering → Business Logic | A negative-amount transfer bypassed server-side validation |
| Remote Code Execution | An exposed `dev.php` endpoint executed OS commands (base64-encoded) |
| Cross-Site Request Forgery (CSRF) | Forced fund transfers |
| Cross-Site Scripting (XSS) | Script executed via a crafted file upload (malicious filename) |

### 👥 Facebook Revenge
A social-network clone.

| Finding | Summary |
|---------|---------|
| SQL Injection | Dumped the database with SQLMap to recover admin credentials |
| Parameter Tampering | Manipulated request parameters |
| Remote Code Execution | Bypassed file-upload validation (changed extension to `.php` in Burp) and planted a web shell |
| Accessible Admin Panel | Reached the admin console |
| Business Logic Bypass | Abused flawed application logic |
| Information Disclosure | Leaked sensitive data |
| Cross-Site Request Forgery (CSRF) | State-changing requests |

## 🛠️ Tools Used

`Burp Suite` `SQLMap` `DirBuster` `jwt.io`

## 📂 Files in this folder

- 📄 [**Car-Rental-WebApp-Pentest.pdf**](Car-Rental-WebApp-Pentest.pdf)
- 📄 [**Banking-WebApp-Pentest.pdf**](Banking-WebApp-Pentest.pdf) — Hack Me Bank
- 📄 [**Facebook-Clone-WebApp-Pentest.pdf**](Facebook-Clone-WebApp-Pentest.pdf) — Facebook Revenge

---

[← Back to main portfolio](../../README.md)
