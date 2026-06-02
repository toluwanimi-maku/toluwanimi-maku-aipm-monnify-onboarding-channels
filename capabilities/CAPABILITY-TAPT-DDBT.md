# Capability: Direct Debit Operations

```yaml
id: CAPABILITY-TAPT-DDBT
name: Direct Debit Operations
platform: TAPT
status: active
owner: Head of Platform (Idris Aliyu — acting, pre-platformisation)

personas:
  - merchant
  - business-owner
  - operations-team

channels:
  - MOBILE_APP
  - WEB
  - INTERNAL_SYSTEM

dependencies:
  - CAPABILITY-TAPT-TRXN  # Transaction Processing Suite
  - NIP (Nigeria Inter-Bank Settlement System)
  - CBN Direct Debit framework

description: |
  Direct Debit Operations covers the end-to-end lifecycle of recurring payment collections
  via the CBN-regulated direct debit scheme. This includes mandate creation, mandate management,
  debit instruction processing, failure handling, and reporting for merchants and business owners
  collecting recurring payments from their customers.

success_metrics:
  - Mandate approval rate >= 85% within 24 hours of submission
  - Debit success rate >= 90% on first attempt
  - Mandate-to-first-debit cycle time <= 3 business days
  - Failed debit retry resolution rate >= 70% within the same billing cycle
```

---

## Subcapabilities under this capability

| Subcapability | Owner | Status |
|---|---|---|
| SUBCAP-TAPT-DDBT-MAND — Mandate Management | Nancy Muorah | Active |
| *(Add more as they are created)* | | |

---

## Notes

This capability is owned by the Teamapt Direct Debit squad. Nancy Muorah (APM) is responsible for subcapabilities and epics under this capability.

Pre-platformisation note: `TAPT` is a temporary platform code. This capability ID will be reassigned when Teamapt migrates to the Moniepoint GitHub org.
