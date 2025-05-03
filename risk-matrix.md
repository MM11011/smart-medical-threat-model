# 📊 Risk Matrix and Mitigation Plan

This risk matrix uses a simplified **OWASP Risk Rating** method to evaluate the threats identified in this project. Each threat is scored by:

- **Likelihood**: How probable the threat is (Low / Medium / High)
- **Impact**: What the effect would be if exploited (Low / Medium / High)
- **Risk Level**: Combined severity (Low / Medium / High / Critical)

---

## 🔒 Risk Matrix

| ID | Threat | Component | Likelihood | Impact | Risk Level | Mitigation |
|----|--------|-----------|------------|--------|------------|------------|
| R-1 | Firmware Tampering via Debug Port | Device | Medium | High | **High** | Disable debug ports, sign firmware |
| R-2 | BLE Spoofing Attack | Device | High | Medium | **High** | Authenticated BLE pairing |
| R-3 | App Reverse Engineering | Mobile App | High | Medium | **High** | Obfuscation, secure secrets |
| R-4 | Token Hijacking | Mobile App | Medium | High | **High** | Short-lived tokens, device binding |
| R-5 | Cloud Role Misuse | Cloud API | Medium | High | **High** | RBAC, access reviews |
| R-6 | Log Tampering | Cloud API | Low | High | **Medium** | Centralized SIEM, immutable logging |
| R-7 | DoS via API Flooding | Mobile App → Cloud | Medium | Medium | **Medium** | Rate limiting, API gateway protections |
| R-8 | Insecure Local Storage | Mobile App | Medium | Medium | **Medium** | Secure storage APIs (Keychain, Keystore) |
| R-9 | Insider Data Browsing | Cloud Dashboard | High | Medium | **High** | Fine-grained access control, alerting |
| R-10 | Phishing Admin Access | Cloud | High | Critical | **Critical** | MFA, login anomaly detection |

---

## 🚦 Risk Levels Explained

| Level | Description |
|-------|-------------|
| **Critical** | Must fix immediately; real-world exploitation likely and devastating |
| **High**     | Major concern; should be prioritized in next dev/security cycle |
| **Medium**   | Address with mitigations during regular release cycles |
| **Low**      | Acceptable with documentation, or handled by layered controls |

---

## 🎯 Mitigation Summary

- **Device Hardening**: Remove debug ports, enforce secure firmware verification
- **Mobile App Security**: Avoid hardcoded secrets, obfuscate binaries, enforce TLS
- **Cloud Controls**: Enforce least privilege, configure audit logging, monitor access patterns
- **Detection & Response**: Enable anomaly detection, alerts, and centralized logging

---

## 📌 Notes

- This matrix is qualitative but realistic, based on attacker capability and system exposure.
- It can be extended using the full OWASP [Risk Rating Methodology](https://owasp.org/www-community/OWASP_Risk_Rating_Methodology) or quantitative models like FAIR.

