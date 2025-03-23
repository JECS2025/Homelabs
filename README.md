# Homelab Project Overview

Welcome to my homelab documentation repo. This project showcases my ability to design, deploy, and manage enterprise-grade IT infrastructure in a virtual lab environment.

---

## 🛠️ Purpose
- Simulate real-world IT environments.
- Gain hands-on experience with Active Directory, Group Policy, Networking, Logging, and Security.
- Build a foundation for blue team operations, detection, and response.

---

## 📃 Current Lab Stack
| Component                | Description                                         |
|-------------------------|-----------------------------------------------------|
| **DC01**                | Domain Controller, DNS, DHCP, NAT                  |
| **FS01**                | File Server with shared storage                   |
| **WS01**                | Windows 11 Client for policy/logging validation   |
| **Router/NAT**          | Configured via DC01's RRAS role                   |

---

## 📋 Documentation Structure
| Phase                  | Documentation                                      |
|-----------------------|-----------------------------------------------------|
| **Phase 1**           | AD Setup & Basic Config                            |
| → [DC01 Config](./DC01_Config.md)     | Domain Controller Setup                        |
| → [FS01 Config](./FS01_Config.md)     | File Server Setup                              |
| → [WS01 Config](./WS01_Config.md)     | Workstation Domain Join & Testing             |
| → [Router Config](./Router_Config.md) | NAT & Routing Setup via RRAS                  |
| → [Group Policy](./GroupPolicy.md)    | Baseline GPOs for Security                    |
| → [Logging Setup](./Security_Logging.md)| WEF + Sysmon for log collection               |

---

## 📚 Skills Demonstrated
- Active Directory management
- Network segmentation and NAT
- Group Policy hardening
- Centralized logging (WEF + Sysmon)
- PowerShell command usage and validation

---

## 📂 Contact / More
- GitHub: [github.com/JECS2025](https://github.com/JECS2025)
- LinkedIn: [linkedin.com/in/jordan-abbott-197377346](https://www.linkedin.com/in/jordan-abbott-197377346/)

