# Capability: Collections and Payments

```yaml
id: CAPABILITY-TAPT-COLL
name: Collections and Payments
platform: TAPT
status: active
owner: Head of Platform (Idris Aliyu — acting, pre-platformisation)

personas:
  - merchant
  - developer
  - business-owner
  - end-customer

channels:
  - MOBILE_APP
  - WEB
  - USSD
  - API

dependencies:
  - CAPABILITY-TAPT-TRXN  # Transaction Processing Suite
  - Card schemes (Visa, Mastercard, Verve)
  - NIP
  - Monnify payment gateway

description: |
  Collections and Payments covers all inbound payment flows through the Monnify platform —
  enabling merchants and businesses to collect payments from their customers via cards,
  bank transfers, USSD, and other channels. Includes payment link creation, checkout
  integration, collection tracking, partial payments, refunds, and settlement reporting.

success_metrics:
  - Payment success rate >= 92% across all channels
  - Card payment authorisation rate >= 88%
  - Bank transfer confirmation time <= 5 minutes (NIP)
  - Settlement to merchant within T+1 business day
  - Refund processing time <= 3 business days
```

---

## Subcapabilities under this capability

| Subcapability | Owner | Status |
|---|---|---|
| *(To be created by David Redemi)* | David Redemi | Pending |

---

## Notes

This capability is owned by the Monnify Collections squad. David Redemi (APM) is responsible for subcapabilities and epics under this capability.
