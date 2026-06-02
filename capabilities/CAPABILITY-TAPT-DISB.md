# Capability: Disbursement Processing

```yaml
id: CAPABILITY-TAPT-DISB
name: Disbursement Processing
platform: TAPT
status: active
owner: Head of Platform (Idris Aliyu — acting, pre-platformisation)

personas:
  - business-owner
  - finance-team
  - developer

channels:
  - WEB
  - INTERNAL_SYSTEM
  - API

dependencies:
  - CAPABILITY-TAPT-TRXN  # Transaction Processing Suite
  - NIP (Nigeria Inter-Bank Settlement System)
  - Monnify payment gateway

description: |
  Disbursement Processing covers the initiation, routing, tracking, and reconciliation of
  outbound payments from business owners and platforms to individuals or other businesses.
  This includes single disbursements, bulk disbursements, disbursement status tracking,
  failure handling, and reconciliation reporting — primarily through the Monnify platform.

success_metrics:
  - Single disbursement success rate >= 95%
  - Bulk disbursement processing time <= 2 hours for batches up to 10,000 records
  - Failed disbursement retry resolution rate >= 80% within 24 hours
  - Reconciliation report availability within 1 hour of settlement
```

---

## Subcapabilities under this capability

| Subcapability | Owner | Status |
|---|---|---|
| *(To be created by Ezinne Ogoke)* | Ezinne Ogoke | Pending |

---

## Notes

This capability is owned by the Monnify Disbursement squad. Ezinne Ogoke (APM) is responsible for subcapabilities and epics under this capability.
