## GDPR Compliance Mapping

The architecture follows **privacy-by-design and privacy-by-default** principles in alignment with GDPR.

| GDPR Article / Principle | Implementation Control | Evidence |
|------------------------|------------------------|---------|
| **Art. 5 – Data minimization** | No personal data stored; tokenized payment flow | Lambda processes amount only, no PII (Phase 3) |
| **Art. 25 – Data protection by design** | Security embedded at every architectural layer | Defense-in-depth approach (All phases) |
| **Art. 32 – Security of processing** | Encryption, integrity, and availability controls | TLS, WAF, rate limiting, backups (Phases 2, 5, 7) |
| **Art. 33 – Breach notification readiness** | Incident response workflow with alerting | CloudWatch alarms + SNS notifications (Phase 10) |
| **Art. 35 – DPIA** | Threat modeling conducted pre-deployment | STRIDE-Light threat model (Phase 2) |

---
# GDPR Controls

## Data Minimization
- No PII stored

## Privacy by Design
- Edge filtering of malicious traffic
- Encrypted communications

## Breach Preparedness
- Logging
- Alerting
- Incident response workflow
