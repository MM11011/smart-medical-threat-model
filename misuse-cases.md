# 🚨 Misuse & Abuse Cases

This section outlines realistic attack or abuse scenarios affecting the smart medical device ecosystem. These scenarios are based on STRIDE threats and mapped MITRE ATT&CK techniques, and are written from the attacker's point of view.

---

## 🧑‍💻 Case 1: Firmware Injection via Debug Port

> "I found an old insulin pump model still exposing its debug pins (JTAG). I used a test jig to connect and flash my own firmware, which bypassed all safety checks. I could send false readings or even disable the device’s alerts."

**Threats Covered**: Tampering, Elevation of Privilege  
**Mitigation**: Physically disable or fuse debug ports in production builds

---

## 📱 Case 2: Mobile App Reverse Engineering

> "I downloaded the Android APK from a third-party site, decompiled it, and found hardcoded API credentials and some base64-encoded keys. I used these to interact directly with the cloud API and pull real patient data."

**Threats Covered**: Information Disclosure, Spoofing  
**Mitigation**: Obfuscate mobile code, store secrets securely, avoid hardcoded values

---

## ☁️ Case 3: Overprivileged Cloud Account

> "A temporary contractor account had full admin access to the cloud dashboard. I used it to reconfigure device telemetry thresholds, disable alert emails, and exfiltrate logs — and nobody noticed for days."

**Threats Covered**: Elevation of Privilege, Repudiation  
**Mitigation**: Role-based access control (RBAC), access reviews, activity logging

---

## 🛜 Case 4: BLE Spoofing Attack

> "I built a BLE spoofing rig to imitate the medical device’s MAC address. The patient’s app connected to my device, and I fed it fake vitals. It even synced that data to the cloud."

**Threats Covered**: Spoofing, Information Disclosure  
**Mitigation**: Device pairing, BLE encryption, strong authentication tokens

---

## 🧟 Case 5: API Flood via Compromised App

> "I jailbroke a phone, tampered with the app, and used it to hammer the cloud API with fake vitals 24/7. Eventually, their backend buckled — no alerts, no monitoring."

**Threats Covered**: Denial of Service  
**Mitigation**: Device-level rate limiting, cloud-side throttling, anomaly detection

---

## 🧑‍⚕️ Case 6: Insider Abuse

> "As a hospital technician, I had dashboard access. I browsed patient data outside my job scope — just curiosity. There were no alerts or audit logs, so I kept going."

**Threats Covered**: Information Disclosure, Repudiation  
**Mitigation**: Enforce access control by patient assignment; audit access logs with alerts

---

## 🔐 Summary

These scenarios highlight the importance of:
- Secure software/hardware development
- Identity and access management (IAM)
- Logging and detection of both external and internal misuse

Each case informs the **risk matrix** and helps prioritize **realistic** mitigations.
