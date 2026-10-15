# 🏗️ Infrastructure Penetration Testing

Infrastructure engagement covering 10 machines across Linux and Windows, from initial foothold to root/SYSTEM. Documented in a single full report.

## 🐧 Linux Machines

| Machine | Platform | Initial Foothold | Privilege Escalation |
|---------|----------|------------------|----------------------|
| Kioptrix3 | VulnHub | Web enumeration + credential brute-force (Hydra) | Misconfigured `sudo ht` on a sensitive file |
| pWnOS v2.0 | VulnHub | Vulnerable blog CMS (Metasploit) | Credentials in `mysqli_connect.php` → SSH as root |
| SkyTower | VulnHub | SQL injection on the login page → SSH via `proxychains` | Passwordless `sudo` for a second user |
| beep | Hack The Box | Elastix LFI (public exploit) leaked credentials | Reused credentials → direct root SSH login |
| Sunday | Hack The Box | `finger` service enumeration | User allowed to run a script as root |

## 🪟 Windows Machines

| Machine | Platform | Initial Foothold | Privilege Escalation |
|---------|----------|------------------|----------------------|
| Blue | Hack The Box | EternalBlue — SMBv1 RCE (MS17-010) | Included in the initial exploit |
| Optimum | Hack The Box | Rejetto HTTP File Server RCE | Kernel exploit (MS16-032) |
| Devel | Hack The Box | Anonymous FTP + ASPX web shell upload | Kernel exploit (MS13-053) |
| Grandpa | Hack The Box | IIS 6.0 WebDAV exploitation | Kernel exploit (MS14-070) |
| Granny | Hack The Box | IIS 6.0 WebDAV exploitation | Kernel exploit (MS15-051) |

## 🛠️ Techniques Demonstrated

- Network reconnaissance and service enumeration (Nmap)
- Exploitation of public CVEs (EternalBlue, MS-series kernel exploits)
- Web service exploitation (IIS, WebDAV, outdated web apps)
- SQL injection for initial access
- Linux privilege escalation via misconfigured `sudo` and exposed credentials
- Proxying SSH through the target with `proxychains`

## 📂 Files in this folder

- 📄 **ITSafe-Infrastructure-Report.pdf** — full report covering all 10 machines

---

[← Back to main portfolio](../../README.md)
