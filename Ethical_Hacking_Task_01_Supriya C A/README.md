# Ethical Hacking Task 01 — Information Gathering & Reconnaissance

**White Band Associates | Cybersecurity Internship Programme**
**Submitted by:** Supriya C A
**Date:** 27 June 2026

---

## Overview

This repository contains the deliverables for **Task 01** of the White Band Associates Ethical Hacking Internship. The task covers the first phase of the ethical hacking methodology — **Passive Reconnaissance** — performed on a publicly accessible target website using only legal, non-intrusive, open-source tools.

> **Target:** Amazon (`https://www.amazon.com`)
> **Reason for Selection:** Amazon is a globally recognised, publicly accessible e-commerce platform that provides sufficient publicly available information to perform passive reconnaissance using ethical methods.

---

## Objectives

- Understand and apply passive reconnaissance techniques
- Perform WHOIS lookups to gather domain registration information
- Enumerate DNS records (A, MX, NS, TXT)
- Identify website technologies and infrastructure
- Analyse HTTP security headers
- Examine `robots.txt` and `sitemap.xml` for reconnaissance insights

---

## Repository Structure

```
Ethical_Hacking_Task_01_Supriya_CA/
│
├── README.md                               # This file
├── Ethical_Hacking_Task_01_Supriya_CA.docx # Full reconnaissance report (Word)
│
└── Screenshots/
    ├── WHOIS/
    │   ├── Screenshot_2026-06-27_144052.png   # WHOIS — Contact Information
    │   ├── Screenshot_2026-06-27_144105.png   # WHOIS — Registrar, Dates & Nameservers
    │   └── Screenshot_2026-06-27_144119.png   # WHOIS — Domain Status Flags
    │
    ├── DNS/
    │   ├── Screenshot_2026-06-27_144315.png   # DNS A Record
    │   ├── Screenshot_2026-06-27_144421.png   # DNS MX Record
    │   ├── Screenshot_2026-06-27_144455.png   # DNS NS Record
    │   ├── Screenshot_2026-06-27_144609.png   # DNS TXT Record (Page 1)
    │   └── Screenshot_2026-06-27_144621.png   # DNS TXT Record (Page 2)
    │
    ├── Technology/
    │   └── Screenshot_2026-06-27_144849.png   # Wappalyzer Technology Lookup
    │
    ├── Security_Headers/
    │   ├── Screenshot_2026-06-27_145526.png   # Security Headers — Grade A Summary
    │   ├── Screenshot_2026-06-27_145539.png   # Security Headers — Missing & Raw Headers (1)
    │   ├── Screenshot_2026-06-27_145553.png   # Security Headers — Raw Headers (2)
    │   └── Screenshot_2026-06-27_145621.png   # Security Headers — Additional Info
    │
    └── Robots_Sitemap/
        ├── Screenshot_2026-06-27_145741.png   # robots.txt
        └── Screenshot_2026-06-27_145825.png   # sitemap.xml (error response)
```

---

## Key Findings Summary

### WHOIS Lookup
| Field | Value |
|---|---|
| Registrar | MarkMonitor Inc. |
| Registration Date | November 1, 1994 |
| Expiry Date | October 31, 2026 |
| Nameservers | AWS Route 53 (4 servers across .com / .net / .org / .co.uk) |
| Domain Status | 6× Prohibited flags (client + server level) |

### DNS Enumeration
| Record | Value |
|---|---|
| A Record | 98.87.170.74 / 98.82.161.185 / 98.87.170.71 |
| MX Record | 5: amazon-smtp.amazon.com |
| NS Record | ns-264.awsdns-33.com, ns-521.awsdns-01.net, ns-1447.awsdns-52.org, ns-1707.awsdns-21.co.uk |
| TXT Record | Zoom, Google, Apple, Canva, Stripe, Docker, Facebook, Uber, Brevo verifications (and more) |

### HTTP Security Headers — Grade: A
| Header | Present |
|---|---|
| Content-Security-Policy | ✅ Yes |
| X-Frame-Options | ✅ Yes (SAMEORIGIN) |
| X-Content-Type-Options | ✅ Yes (nosniff) |
| Strict-Transport-Security | ✅ Yes (max-age=47474747; includeSubDomains; preload) |
| Referrer-Policy | ❌ No |
| Permissions-Policy | ❌ No |

### robots.txt & sitemap.xml
- **robots.txt** — Present and accessible. Reveals numerous disallowed paths including authentication (`/gp/sign-in`), cart (`/gp/cart`), AWS (`/gp/aws/ssop`), customer review, media upload, and wishlist endpoints.
- **sitemap.xml** — Not accessible at the standard path (`/sitemap.xml`). Amazon returns a custom error page, indicating deliberate restriction of site structure information.

---

## Tools Used

| Tool | Purpose | URL |
|---|---|---|
| who.is | WHOIS Lookup | https://who.is/whois/amazon.com |
| dnschecker.org | DNS Record Enumeration | https://dnschecker.org |
| Wappalyzer | Website Technology Identification | https://www.wappalyzer.com/lookup/ |
| securityheaders.com | HTTP Security Header Analysis | https://securityheaders.com |

---

## Important Note

> All activities performed in this task are **strictly passive** and use only **publicly available information**. No direct interaction was initiated with the target's systems. No unauthorised access was attempted. This task is submitted solely for **educational purposes** as part of the White Band Associates Cybersecurity Internship Programme.

---

## Topics Studied

- Ethical Hacking Methodology
- Penetration Testing Phases
- Passive vs Active Reconnaissance
- WHOIS & Domain Registration
- DNS Basics (A, MX, NS, TXT records)
- HTTP Security Headers
- robots.txt & sitemap.xml Analysis
- Footprinting Techniques

---

*White Band Associates — Cybersecurity Internship Programme*
