# 🪟 Windows Privilege Escalation

Five Windows machines taken from initial foothold to SYSTEM, documented in a single full report. Includes an Active Directory host.

## 📋 Machines Covered

| Machine | Platform | Initial Foothold | Privilege Escalation |
|---------|----------|------------------|----------------------|
| Bounty | Hack The Box | IIS `web.config` upload | Task Scheduler exploit (MS10-092) |
| Active | Hack The Box | GPP credentials in an exposed SMB `Replication` share (`Groups.xml`) | Kerberoasting a service account |
| Nest | Hack The Box | Sensitive files in SMB shares | HQK reporting tool on port 4386 |
| Toolbox | Hack The Box | SQL injection on the web page | Default Boot2Docker credentials |
| Jeeves | Hack The Box | Jenkins Script Console → reverse shell | Token-reflection exploit (MS16-075) |

## 🛠️ Techniques Demonstrated

- SMB enumeration and share abuse
- GPP `cpassword` credential recovery
- Kerberoasting against Active Directory
- Web-to-shell via Jenkins and IIS upload
- Token-reflection / kernel privilege escalation

## 📂 Files in this folder

- 📄 **ITSafe-Windows-PrivEsc-Report.pdf** — full report covering all 5 machines

---

[← Back to main portfolio](../../README.md)
