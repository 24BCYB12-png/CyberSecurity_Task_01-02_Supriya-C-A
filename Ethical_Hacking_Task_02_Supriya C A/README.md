# Ethical Hacking Task 02 — Network Scanning & Service Enumeration

**Internship:** White Band Associates — Ethical Hacking Programme  
**Task:** 02 | Scanning and Enumeration  
**Submitted by:** Supriya  
**Date:** 27 June 2026  

---

## Overview

This folder contains the complete submission for **Task 02** of the White Band Associates Ethical Hacking Internship. The objective of this task was to gain practical experience with the **Scanning and Enumeration** phase of ethical hacking using **Nmap (Network Mapper)**.

All scans were performed exclusively on the tester's own **Kali Linux virtual machine** (via Oracle VirtualBox) targeting the loopback address `127.0.0.1`. No external or unauthorized systems were scanned at any point.

---

## Folder Structure

```
Ethical_Hacking_Task_02_Supriya/
│
├── README.md                            ← This file
├── Nmap_Scan_Report.pdf                 ← Full professional scan report
├── Research_Notes_Common_Ports.pdf      ← Port research notes (11 ports)
│
└── screenshots/
    ├── 01_nmap_version.png              ← nmap --version output
    ├── 02_nmap_localhost_default.png    ← nmap localhost output
    ├── 03_nmap_sV_localhost.png         ← nmap -sV localhost output
    ├── 04_nmap_O_error.png              ← sudo nmap -0 (typo error)
    ├── 05_nmap_o_no_hosts.png           ← sudo nmap -o (wrong flag)
    └── 06_nmap_A_aggressive.png         ← sudo nmap -A localhost output
```

---

## Environment

| Parameter        | Details                                      |
|------------------|----------------------------------------------|
| OS               | Kali Linux (x86_64-pc-linux-gnu)             |
| Virtualization   | Oracle VirtualBox                            |
| Nmap Version     | 7.98                                         |
| Target           | localhost / 127.0.0.1                        |
| Scan Date        | 27 June 2026 (18:32–18:38 IST)              |

---

## Commands Used

| Command                    | Purpose                                      |
|----------------------------|----------------------------------------------|
| `nmap --version`           | Verify Nmap installation                     |
| `nmap localhost`           | Default TCP scan (top 1000 ports)            |
| `nmap -sV localhost`       | Service version detection                    |
| `sudo nmap -0 localhost`   | ⚠️ Error — digit zero used instead of -O    |
| `sudo nmap -o localhost`   | ⚠️ Wrong flag — treated as output file arg  |
| `sudo nmap -A localhost`   | Aggressive scan (OS + version + scripts)     |

---

## Key Findings

- **Host Status:** Up (latency ~0.000002s)
- **Open Ports:** **None** — all 1000 scanned TCP ports were closed (reset)
- **Services Detected:** None
- **OS Detection:** Inconclusive via loopback — "too many fingerprints match"
- **Network Distance:** 0 hops (confirmed local machine)

> The absence of open ports is the expected result on a minimal Kali Linux VM  
> with no services (SSH, HTTP, etc.) manually started.

---

## Scan Analysis

**Q: Which services are currently running?**  
No services were detected as listening on any of the 1000 scanned TCP ports at the time of the scan.

**Q: Are all open ports necessary?**  
Since no ports are open, there is nothing to review for necessity. This represents a minimal, low-attack-surface configuration.

**Q: Which services could become security risks if misconfigured?**  
If services were enabled, the highest-risk ones would be: Telnet (port 23 — plaintext), SMB (port 445 — ransomware vector), RDP (port 3389 — brute-force target), and FTP (ports 20/21 — plaintext credentials).

**Q: Which port would you disable if not required?**  
Telnet (port 23) — it transmits all data including passwords in plaintext and has been fully superseded by SSH.

---

## Files Description

### `Nmap_Scan_Report.pdf`
A professional, multi-section scan report covering:
- Objective and scope
- All commands executed (with explanations)
- Detailed scan results for each command
- OS detection findings and analysis
- Errors observed (flag typos and incorrect usage)
- Security recommendations
- Conclusion (150–200 words)

### `Research_Notes_Common_Ports.pdf`
Detailed research notes for 11 common network ports:

| Port    | Service   |
|---------|-----------|
| 20/21   | FTP       |
| 22      | SSH       |
| 23      | Telnet    |
| 25      | SMTP      |
| 53      | DNS       |
| 80      | HTTP      |
| 110     | POP3      |
| 143     | IMAP      |
| 443     | HTTPS     |
| 445     | SMB       |
| 3389    | RDP       |

Each entry covers: Protocol, Purpose, and Common Security Risks.

---

## Important Note

> ⚠️ **Ethical Hacking Disclaimer**  
> All scanning activities in this task were performed solely against the tester's own  
> virtual machine in a controlled, isolated environment. No public or third-party systems  
> were scanned. This task is for educational purposes only as part of the White Band  
> Associates Ethical Hacking Internship.

---

## Repository Structure

This task is part of the ongoing internship repository. Each task is maintained in its own separate folder:

```
ethical-hacking-internship/
├── Ethical_Hacking_Task_01_Supriya/
├── Ethical_Hacking_Task_02_Supriya/   ← Current Task
└── ...
```

---

*Submitted as part of White Band Associates Ethical Hacking Internship — Task 02*
