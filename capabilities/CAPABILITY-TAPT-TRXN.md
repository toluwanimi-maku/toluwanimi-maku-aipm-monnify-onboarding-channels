# Capability: Transaction Processing Suite

```yaml
id: CAPABILITY-TAPT-TRXN
name: Transaction Processing Suite
platform: TAPT
status: active
owner: Head of Platform (Idris Aliyu — acting, pre-platformisation)

personas:
  - merchant
  - agent
  - business-owner
  - operations-team
  - developer

channels:
  - MOBILE_APP
  - WEB
  - POS
  - USSD
  - API
  - INTERNAL_SYSTEM

dependencies:
  - NIBSS
  - CBN payment processing framework
  - Card schemes (Visa, Mastercard, Verve)

description: |
  The Transaction Processing Suite is the core processing layer underpinning all
  Teamapt payment products. It covers transaction initiation, routing, authorisation,
  clearing, settlement, and reconciliation across all channels and payment types.
  Other capabilities depend on TRXN for their underlying processing infrastructure.
  This capability is managed by the Aptpay Transaction Suite squad.

success_metrics:
  - Transaction processing uptime >= 99.95%
  - End-to-end authorisation latency <= 3 seconds (p95)
  - Settlement accuracy 100%
  - Failed transaction retry success rate >= 75%
  - Reconciliation break rate < 0.01%
```

---

## Subcapabilities under this capability

| Subcapability | Owner | Status |
|---|---|---|
| *(To be created by Khadijat Musa)* | Khadijat Musa | Pending |

---

## Notes

This capability is owned by the Aptpay Transaction Suite squad. Khadijat Musa (APM) is responsible for subcapabilities and epics under this capability.

This capability is a shared dependency — DDBT, DISB, COLL, PTSP, and TPPC all depend on it.
