# Security & Logging Setup

Owner: JECS2025

---

## 📂 Contents
1. [Windows Event Forwarding (WEF) Setup](#1-windows-event-forwarding-wef-setup)
2. [Sysmon Deployment](#2-sysmon-deployment)
3. [Validate Logging Functionality](#3-validate-logging-functionality)

---

## 1. Windows Event Forwarding (WEF) Setup

Implement **centralized event collection** by configuring **Windows Event Forwarding**. This enables DC01 to act as a log collector, receiving logs from domain-joined clients.

### 🚀 Configure Event Collector on DC01
1. Open **Event Viewer** on **DC01**.
2. Navigate to **Subscriptions** → Right-click → **Create Subscription**.
3. Choose **Source-Initiated Subscription**.
4. Select **machines forwarding events** (e.g., WS01, FS01).
5. Ensure **DC01** is configured to collect forwarded logs.

### 🌎 Configure WS01 and FS01 as Sources
Run the following command on each machine:
```powershell
wecutil qc
```
*This command configures the client to allow event forwarding to DC01.*

---

## 2. Sysmon Deployment

Install **Sysinternals Sysmon** for enhanced process and network logging.

### 🔧 Steps:
1. Download **Sysmon** from Microsoft Sysinternals.
2. Use a **standard configuration file**, such as:
   - [SwiftOnSecurity Sysmon Config](https://github.com/SwiftOnSecurity/sysmon-config)
3. Deploy Sysmon on **DC01, FS01, WS01** using the command:
```powershell
sysmon.exe -accepteula -i sysmonconfig.xml
```
*This enables detailed logging of system events and activity for security monitoring.*

---

## 3. Validate Logging Functionality

### 🔍 Verify Event Forwarding
On **DC01**, open **Event Viewer** → Navigate to **Forwarded Events**:
- Confirm logs from **WS01** and **FS01** are being received.
- Look for security-related events such as logon attempts, file access, etc.

### 📊 Verify Sysmon Activity
Run the following command on any machine with Sysmon installed:
```powershell
Get-WinEvent -LogName "Microsoft-Windows-Sysmon/Operational" | Select-Object -First 5
```
*Confirms Sysmon is actively logging events per configuration.*

---

This setup ensures **centralized log management**, **detailed endpoint telemetry**, and forms a foundation for **incident detection and response** within your homelab. (Which'll become more apparent in future homelabs)
