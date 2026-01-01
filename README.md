# Wazuh SOC Lab: Threat Detection & Monitoring

## 🔍 Project Overview
This project focuses on building a home lab to simulate a corporate Security Operations Center (SOC). I deployed **Wazuh** as a SIEM and integrated **Sysmon** on a Windows 10 endpoint to detect advanced threats.

## 🛠️ Tools Used
* **SIEM:** Wazuh (Running on Ubuntu 24.04)
* **Endpoint:** Windows 10 Enterprise
* **Telemetry:** Sysmon (SwiftOnSecurity Config)
* **Virtualization:** VMware Workstation

## ⚡ Key Achievements
1.  **Infrastructure Deployment:** Configured manager-agent communication over a bridged network.
2.  **Log Analysis:** Tuned `ossec.conf` to ingest Sysmon Event IDs (1, 3, 11).
3.  **Threat Simulation:**
    * **Persistence:** Detected User Account Creation (T1136).
    * **Malware:** Detected & Quarantined `mimikatz.exe` payload (Defense in Depth verification).

## 📸 Evidence

### 1. Dashboard Status
*Verifying active agent communication.*
![Agent Status](Screenshot%202026-01-01%20135912.png)

### 2. Attack Execution
*Simulating Persistence (T1136) via PowerShell.*
![PowerShell Attack](Screenshot%202026-01-01%20140026.png)

### 3. SIEM Detection
*Wazuh catching the user creation event.*
![Detection](Screenshot%202026-01-01%20140250.png)

### 4. Defense in Depth (The "Pro" Verification)
*Here, Sysmon captures the file creation (Event ID 11) even before Windows Defender quarantines it.*

**SIEM View (Sysmon Log):**
![Sysmon Log](Screenshot%202026-01-01%20144927.png)

**Endpoint View (Defender Quarantine):**
![Defender](Screenshot%202026-01-01%20144043.png)

---
### 📄 Full Report
For a deep dive into the detection logic and architecture, please read the full [Threat Detection Report.pdf](Threat_Detection_Report.pdf) included in this repository.
