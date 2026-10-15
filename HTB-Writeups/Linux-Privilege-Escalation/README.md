# 🐧 Linux Privilege Escalation

Five Linux machines taken from initial foothold to root, documented in a single full report.

## 📋 Machines Covered

| Machine | Platform | Initial Foothold | Privilege Escalation |
|---------|----------|------------------|----------------------|
| Spectra | Hack The Box | Web enumeration exposed credentials | `sudo initctl` → edited an Upstart job to get root |
| Shocker | Hack The Box | Shellshock via `cgi-bin` (CVE-2014-6271) | `sudo perl` (GTFOBins) |
| Mirai | Hack The Box | Default credentials | `sudo su`; recovered the deleted root flag from a USB drive with `strings` |
| Bank | Hack The Box | Exposed `/balance-transfer` path | SUID file found with `LinEnum` |
| Lame | Hack The Box | Outdated Samba (public CVE) | Included in the initial exploit |

## 🛠️ Techniques Demonstrated

- Linux enumeration (manual + `LinEnum`)
- Shellshock exploitation
- `sudo` misconfigurations (GTFOBins, `initctl`)
- SUID binary abuse
- Credential and sensitive-file discovery
- Default-credential access

## 📂 Files in this folder

- 📄 **ITSafe-Linux-PrivEsc-Report.pdf** — full report covering all 5 machines

---

[← Back to main portfolio](../../README.md)
