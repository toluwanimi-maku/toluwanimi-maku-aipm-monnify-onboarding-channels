# Subcapability: Mandate Management

> **WORKED EXAMPLE** — This file shows what a completed subcapability looks like.
> Read it fully before writing your own. Then copy `templates/subcapability-template.md`.

```yaml
id: SUBCAP-TAPT-DDBT-MAND
name: Mandate Management
capability: CAPABILITY-TAPT-DDBT
platform: TAPT
status: active
owner: Nancy Muorah

personas:
  - merchant
  - business-owner

channels:
  - WEB
  - API

problem: |
  Merchants who need to collect recurring payments from customers cannot initiate or manage
  direct debit mandates without calling the Teamapt operations team, creating a manual
  bottleneck that delays mandate activation by 3-5 business days and prevents merchants
  from scaling their recurring revenue operations independently.

description: |
  Mandate Management covers the full lifecycle of a direct debit mandate between a merchant
  and their customer — from initial mandate creation and customer authorisation, through
  active mandate status tracking, amendment, suspension, and cancellation.

  A mandate is the customer's authorised instruction to their bank to allow the merchant to
  collect payments from their account on a recurring basis. This subcapability ensures
  merchants can initiate, track, and manage mandates entirely through the Monnify platform
  without operations team involvement for standard cases.

success_metrics:
  - Merchant-initiated mandate creation: available via API and web dashboard
  - Mandate activation (bank approval) rate >= 85% within 24 hours
  - Mandate status visible to merchant in real time (no polling lag > 60 seconds)
  - Self-service mandate amendment (amount, frequency): available without ops team
  - Mandate cancellation: available to merchant and customer within same session
```

---

## Epics under this subcapability

| Epic | Name | Status |
|---|---|---|
| EPIC-TAPT-DDBT-MAND-EP00001 | Mandate Creation and Activation | Active |
| *(Add more as they are created)* | | |
