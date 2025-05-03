# 🎯 MITRE ATT&CK Mapping

This document maps threats identified via STRIDE to real-world adversary techniques from the MITRE ATT&CK framework. The analysis draws from three matrices:

- **Mobile** (for smartphone threats)
- **Enterprise (Cloud)** (for backend/cloud APIs)
- **ICS/IoT / Custom ATT&CK Techniques** (for embedded devices)

---

## 🔷 Device Threats → ATT&CK Mapping

| STRIDE Threat | MITRE Technique | Description | Matrix |
|---------------|------------------|-------------|--------|
| Device Spoofing | [T1557.001 – Adversary-in-the-Middle: Bluetooth](https://attack.mitre.org/techniques/T1557/001/) | Intercept or spoof BLE communication | Mobile |
| Firmware Tampering | [T1542.001 – Pre-OS Boot: System Firmware](https://attack.mitre.org/techniques/T1542/001/) | Modify firmware to execute malicious code | Enterprise |
| Debug Interface Exploitation | [T1200 – Hardware Additions](https://attack.mitre.org/techniques/T1200/) | Use exposed JTAG or SWD to bypass device controls | ICS / Embedded |
| Signal Jamming | N/A (outside MITRE's current scope) | RF/EM interference disrupting communication | --- |

---

## 📱 Mobile App Threats → ATT&CK Mapping

| STRIDE Threat | MITRE Technique | Description | Matrix |
|---------------|------------------|-------------|--------|
| Session Hijacking | [T1528 – Steal Application Access Token](https://attack.mitre.org/techniques/T1528/) | Harvest tokens from mobile app | Mobile |
| App Reverse Engineering | [T1611 – Device Unlocking](https://attack.mitre.org/techniques/T1611/) | Modify app or unlock device to inspect code | Mobile |
| Insecure Storage | [T1407 – Access Sensitive Data in Storage](https://attack.mitre.org/techniques/T1407/) | Harvest sensitive data on mobile devices | Mobile |
| API Flooding | [T1499 – Endpoint Denial of Service](https://attack.mitre.org/techniques/T1499/) | Overload API to degrade availability | Enterprise |

---

## ☁️ Cloud API Threats → ATT&CK Mapping

| STRIDE Threat | MITRE Technique | Description | Matrix |
|---------------|------------------|-------------|--------|
| Phishing Admin Credentials | [T1566.001 – Spearphishing: Link](https://attack.mitre.org/techniques/T1566/001/) | Trick users into giving up login access | Enterprise |
| Log Tampering | [T1070.001 – Indicator Removal: Clear Windows Event Logs](https://attack.mitre.org/techniques/T1070/001/) | Erase evidence from logs | Enterprise |
| Open Cloud Misconfig | [T1530 – Data from Cloud Storage](https://attack.mitre.org/techniques/T1530/) | Access sensitive data via exposed S3 buckets, APIs | Enterprise |
| DoS via Junk Telemetry | [T1499 – Endpoint DoS](https://attack.mitre.org/techniques/T1499/) | Saturate backend API with garbage data | Enterprise |
| Role Misassignment | [T1078 – Valid Accounts](https://attack.mitre.org/techniques/T1078/) | Exploit valid account with excessive privileges | Enterprise |

---

## ✅ Notes

- Not all threats map cleanly to MITRE (e.g., RF jamming).
- You can build a custom [ATT&CK Navigator layer](https://mitre-attack.github.io/attack-navigator/) with selected techniques for visual presentation.
- Multiple STRIDE threats may map to the same ATT&CK technique — that's expected.

---

## 📎 Related Resources

- [MITRE ATT&CK Mobile Matrix](https://attack.mitre.org/matrices/mobile/)
- [MITRE ATT&CK for Enterprise](https://attack.mitre.org/matrices/enterprise/)
- [MITRE ATT&CK Navigator Tool](https://attack.mitre.org/resources/navigator/)
