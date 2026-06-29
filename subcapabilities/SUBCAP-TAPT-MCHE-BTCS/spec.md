---
id: SUBCAP-TAPT-MCHE-BTCS
name: Bank Transfer Channel Setup
capability: CAPABILITY-TAPT-MCHE — Monnify Channel Enablement
platform: TAPT — Teamapt
status: active
personas:
  - merchant
channels:
  - WEB
  - API
problem: Merchants approved on Monnify have no self-serve path to activate bank transfer
  collection. Virtual account provisioning, webhook configuration, and go-live
  confirmation all require manual ops involvement, causing delays in order fulfilment,
  reconciliation errors, and poor customer experience.
design_refs:
engineering_refs:
deprecation_reason:
---

## Description

Bank Transfer Channel Setup covers the end-to-end flow by which an approved Monnify
merchant activates NIP-based bank transfer collection. This includes virtual account
provisioning (unique account numbers assigned per merchant or per transaction), webhook
endpoint configuration, sandbox environment testing, and production go-live confirmation.
A merchant is considered channel-enabled when they have completed at least one successful
live NIP transaction routed through their provisioned virtual account.

## Success Metrics

| Metric | Target |
|---|---|
| Channel activation success rate | ≥ 95% post-onboarding approval |
| Time from channel activation request to first live transaction | ≤ 24 hours |
| API key provisioning time | ≤ 5 minutes |

## Scope Boundaries

In scope: NIP virtual account provisioning (per-merchant and per-transaction modes),
webhook endpoint configuration and verification, sandbox testing (test transactions and
webhook simulation), production go-live confirmation, and automated payment matching
with merchant notification on successful transfer.

Out of scope: card payment enablement, USSD channel setup, manual reconciliation
workflows (replaced, not managed, by this subcapability), multi-currency support,
and bulk or batch payment collection.

## Dependencies

- **NIP** — the only hard infrastructure dependency; virtual account routing and
  settlement depend on NIP availability and settlement windows.

## Edge Cases and Failure Modes

- **Provisioning failure** — if virtual account provisioning fails, the merchant receives
  an error and can retry cleanly. Setup cannot be left in a partial or stuck state.
- **Webhook delivery failure** — the system retries a configurable number of attempts;
  if all retries are exhausted, the transfer is flagged as unmatched and escalated to
  the ops queue. (Retry count declared as a config parameter in `team-parameters.md`.)
- **Wrong-amount transfer** — fulfilment is not automatically blocked. Merchants
  configure a tolerance window; transfers within that window are matched and fulfilled,
  outside it are held for merchant review. (Tolerance window declared as a config
  parameter in `team-parameters.md`.)
