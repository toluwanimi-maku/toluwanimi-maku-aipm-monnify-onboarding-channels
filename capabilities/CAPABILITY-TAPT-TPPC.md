# Capability: Third Party Processing

```yaml
id: CAPABILITY-TAPT-TPPC
name: Third Party Processing
platform: TAPT
status: active
owner: Head of Platform (Idris Aliyu — acting, pre-platformisation)

personas:
  - partner-institution
  - merchant
  - operations-team
  - developer

channels:
  - API
  - INTERNAL_SYSTEM

dependencies:
  - CAPABILITY-TAPT-TRXN  # Transaction Processing Suite
  - Card schemes (Visa, Mastercard, Verve)
  - NIBSS
  - Partner institution APIs

description: |
  Third Party Processing (TPP) covers Teamapt's role as an acquirer and processor for
  partner institutions and merchants who route card and payment transactions through the
  Aptpay processing infrastructure. This includes merchant onboarding, transaction
  authorisation and routing, chargeback management, settlement, and performance reporting
  for all third-party processed volumes.

success_metrics:
  - Transaction authorisation rate >= 94%
  - Partner onboarding cycle time <= 5 business days
  - Chargeback rate < 0.5% of processed volume
  - Settlement accuracy 100%
  - API uptime >= 99.9%
```

---

## Subcapabilities under this capability

| Subcapability | Owner | Status |
|---|---|---|
| *(To be created by Ruth Adetunji)* | Ruth Adetunji | Pending |

---

## Notes

This capability is owned by the Aptpay TPP squad. Ruth Adetunji (APM) is responsible for subcapabilities and epics under this capability.
