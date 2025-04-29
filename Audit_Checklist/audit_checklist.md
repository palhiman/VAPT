Here's a **detailed audit checklist** for **Windows 11** and **Ubuntu 22.04+ systems**, based on **ISMS (ISO/IEC 27001/27002)** and **CIS (Center for Internet Security)** benchmarks. The checklist includes **checkpoints, control references**, and **recommendations** for each item to support a thorough technical audit in alignment with information security management principles.

---

## ✅ WINDOWS 11 AUDIT CHECKLIST (ISMS + CIS)

| **#** | **Checkpoint** | **Control Ref. (ISMS/CIS)** | **Recommendation** |
|-------|----------------|------------------------------|---------------------|
| 1 | OS Version & Patch Level | A.12.6.1 / CIS 1.1 | Ensure Windows 11 is fully updated. Enable automatic updates. |
| 2 | User Account Control (UAC) | A.9.2.3 / CIS 1.2 | Set UAC to 'Always Notify'. Prevent silent privilege escalations. |
| 3 | Local Account Password Policies | A.9.4.3 / CIS 1.3 | Enforce complex passwords, 14+ characters, history retention & lockout policies. |
| 4 | Administrator Account Renaming & Status | A.9.2.1 / CIS 1.4 | Rename default admin accounts and disable if not in use. |
| 5 | Audit Policy Configuration | A.12.4.1 / CIS 9 | Enable detailed auditing (success & failure) for logon, policy changes, and privilege use. |
| 6 | Windows Firewall State | A.13.1.1 / CIS 5 | Ensure Windows Defender Firewall is enabled for all profiles. Restrict inbound rules. |
| 7 | Antivirus/Antimalware Configuration | A.12.2.1 / CIS 8 | Ensure Microsoft Defender or a third-party AV is active, real-time protection on. |
| 8 | BitLocker Drive Encryption | A.10.1.1 / CIS 18 | Enable BitLocker for all drives including removable media. TPM + PIN preferred. |
| 9 | SMB Protocol Hardening | A.13.1.1 / CIS 2.3 | Disable SMBv1. Enforce SMB signing and restrict anonymous access. |
| 10 | Remote Desktop Settings | A.9.1.2 / CIS 2.2 | Disable RDP if not needed. If required, restrict access by IP and enforce NLA. |
| 11 | Application Control | A.12.6.2 / CIS 3.5 | Use AppLocker or Windows Defender Application Control (WDAC) to control software execution. |
| 12 | AutoRun and AutoPlay | A.12.2.1 / CIS 2.5 | Disable AutoRun for all drives to prevent USB-based threats. |
| 13 | Logging and Monitoring | A.12.4.1 / CIS 9 | Forward logs to central SIEM. Monitor for anomalies and failed login attempts. |
| 14 | PowerShell Logging | A.12.4.1 / CIS 16.4 | Enable transcription and module logging. Restrict usage to authorized admins. |
| 15 | Group Policy Hardening | A.9.2 / CIS 1, 17 | Review and enforce hardening policies via GPO (e.g., disable guest account, enforce lockout). |

---

## ✅ UBUNTU 22.04+ AUDIT CHECKLIST (ISMS + CIS)

| **#** | **Checkpoint** | **Control Ref. (ISMS/CIS)** | **Recommendation** |
|-------|----------------|------------------------------|---------------------|
| 1 | OS Version & Updates | A.12.6.1 / CIS 1.1 | Ensure system is up-to-date. Enable unattended-upgrades for security patches. |
| 2 | User Accounts Review | A.9.2.3 / CIS 6.2 | List all users. Disable unused accounts. Check for UID 0 (root) duplicates. |
| 3 | Password Policies | A.9.4.3 / CIS 6.3 | Use `libpam-pwquality` or `pam_cracklib`. Set min length, complexity, retry limit. |
| 4 | SSH Configuration | A.13.1.1 / CIS 5.2 | Disable root login, enforce key-based auth, set idle timeout, limit users/groups. |
| 5 | UFW / Firewall Rules | A.13.1.1 / CIS 3.5 | Enable and configure UFW. Deny by default, allow only required services. |
| 6 | File Permissions | A.9.4.1 / CIS 1.4 | Audit `/etc`, `/home`, `/var/log` for excessive permissions or world-writable files. |
| 7 | Auditd & Logging | A.12.4.1 / CIS 4.1 | Ensure `auditd` is enabled and logs critical actions (e.g., sudo, su, file changes). |
| 8 | Secure Boot & Disk Encryption | A.10.1.1 / CIS 1.1.2 | Use full-disk encryption (e.g., LUKS). Check for secure boot configuration. |
| 9 | Root Account Control | A.9.2.3 / CIS 6.1 | Disable direct root login via SSH. Use `sudo` for administrative access. |
| 10 | AppArmor Status | A.12.6.2 / CIS 1.7 | Ensure AppArmor is active and profiles are in enforce mode for sensitive apps. |
| 11 | Cron Job Permissions | A.12.1.2 / CIS 5.1 | Restrict access to `cron` via `/etc/cron.allow`, audit existing jobs. |
| 12 | Sudo Configuration | A.9.2.3 / CIS 5.3 | Use minimal privilege principles. Avoid `NOPASSWD`. Use `sudo -l` to verify roles. |
| 13 | World-Writable & No-Owner Files | A.9.4.1 / CIS 6.1.10 | Find and eliminate world-writable or orphaned files. Use `find / -perm -002`. |
| 14 | Network Configuration | A.13.1.1 / CIS 3 | Disable IPv6 if not needed. Disable unused network interfaces and services. |
| 15 | Container or VM Hardening (if applicable) | A.12.6.1 / CIS Docker/VM Baselines | Ensure isolation, restrict container privileges, avoid running as root, enable AppArmor/SELinux profiles. |

---

## 📌 General Audit Actions (Cross-Platform)

- **Maintain an Asset Inventory** – Know which devices are Windows or Linux.
- **Perform Vulnerability Scanning** – Use tools like OpenVAS, Nessus, or Lynis (Linux).
- **Centralized Logging** – Use tools like ELK Stack or Splunk to aggregate and analyze logs.
- **Role-Based Access Control (RBAC)** – Ensure that least privilege is enforced across both platforms.
- **Security Awareness & Access Reviews** – Regularly review user access and provide training.

---

