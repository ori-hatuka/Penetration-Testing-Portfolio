# 🌐 Web Application Pentesting

Comprehensive Web Application penetration testing engagements covering OWASP Top 10 and beyond. This section includes three separate web application pentest projects.

## 📋 Projects Covered

| Project | Type | Key Techniques |
|---------|------|----------------|
| Car Rental App | Booking platform | SQLi, XSS, Broken Access Control |
| Facebook Clone | Social network | Authentication flaws, IDOR, CSRF |
| Hack Me Bank | Banking application | Business logic, Authentication, Session |

## 🎯 Vulnerabilities Covered

### Injection Attacks
- **SQL Injection** — Error-based, Boolean-based, Time-based, UNION-based
- **Command Injection** — OS command execution
- **HTML Injection** — Content manipulation
- **CSS Injection** — Style manipulation

### Cross-Site Scripting (XSS)
- **Reflected XSS** — Via URL parameters
- **Stored XSS** — Persistent payloads
- **DOM-based XSS** — Client-side execution

### Access Control & Authentication
- **Broken Access Control** — IDOR, missing authorization
- **Broken Authentication** — Weak login mechanisms
- **Session Fixation** — Session hijacking
- **JWT Attacks** — Token manipulation, algorithm confusion

### Cross-Site & Server-Side Request Forgery
- **CSRF** — Cross-Site Request Forgery
- **SSRF** — Server-Side Request Forgery
- **CORS Misconfigurations** — Origin validation bypass

### File & Path Attacks
- **LFI** — Local File Inclusion
- **RFI** — Remote File Inclusion
- **Path Traversal** — Directory traversal attacks

### Other Web Vulnerabilities
- **Open Redirect** — URL redirection abuse
- **Insecure Deserialization** — Object injection
- **OAuth2 Vulnerabilities** — Implementation flaws

## 📂 Files in this folder

- 📄 **Car-Rental-WebApp-Pentest.pdf** — Pentest report for car rental booking application
- 📄 **Facebook-Clone-WebApp-Pentest.pdf** — Pentest report for social network clone
- 📄 **Banking-WebApp-Pentest.pdf** — Pentest report for banking application

## 🛠️ Tools Used

`Burp Suite` `OWASP ZAP` `SQLmap` `Nikto` `Gobuster` `Wfuzz` `Chrome DevTools`

---

[← Back to main portfolio](../../README.md)
