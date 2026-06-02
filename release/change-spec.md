# Change Spec — Mandate Creation and Activation

> **WORKED EXAMPLE** — This file shows what a completed change spec looks like.
> Read it fully before writing your own. Then copy `templates/change-spec-template.md`.

```yaml
id: RELEASE-TAPT-DDBT-MAND-001
name: Mandate Creation and Activation
branch: feature/mandate-creation-activation
subcapability: SUBCAP-TAPT-DDBT-MAND
owner: Nancy Muorah
status: draft
jira_epic_slice: ADD-[TBC — populate after Jira sync]
```

---

## Problem and Motivation

Merchants using Teamapt's Direct Debit product cannot create or manage mandates without involving the operations team. Every new mandate requires a manual submission, a phone or email request to ops, and a 3-5 business day wait for bank activation. This creates a bottleneck that limits merchant scale and makes Teamapt's direct debit product uncompetitive against alternatives where merchants self-serve.

This release delivers the first phase of self-service mandate management: merchant-initiated mandate creation, real-time status tracking, and merchant-initiated cancellation.

---

## Current Behaviour

- Merchants submit mandate requests via email or phone to the Teamapt operations team
- The ops team manually keys mandate data into the bank submission portal
- Mandate status updates are communicated to merchants by the ops team ad hoc
- Mandate cancellation requires the merchant to contact ops; there is no self-service path

---

## Desired Behaviour

- Merchants can create a mandate via the Monnify API or web dashboard in under 2 minutes
- Mandate status is available in real time via API query or webhook notification
- Merchants can cancel any active or pending mandate without ops team involvement
- The operations team is not in the critical path for standard mandate lifecycle events

---

## Channels

- `WEB` — Monnify merchant dashboard
- `API` — Monnify REST API (merchants using programmatic integration)

---

## Release Impact

| Area | Impact |
|---|---|
| Merchants | Can self-serve mandate creation, tracking, and cancellation |
| Operations team | Removed from the critical path for standard mandates; handles exceptions only |
| Engineering | New mandate creation, status query, and cancellation endpoints |
| Compliance | No change to mandate data requirements or NIBSS submission process |

---

## Changes

### New stories in this release

| Story ID | Name | Jira |
|---|---|---|
| STORY-TAPT-DDBT-MAND-EP00001-00001 | Merchant creates a new mandate | ADD-[TBC] |
| STORY-TAPT-DDBT-MAND-EP00001-00002 | Merchant tracks mandate status | ADD-[TBC] |
| STORY-TAPT-DDBT-MAND-EP00001-00003 | Merchant cancels an active mandate | ADD-[TBC] |

### Modified artifacts

- Added: `subcapabilities/SUBCAP-TAPT-DDBT-MAND.md`
- Added: `epics/EPIC-TAPT-DDBT-MAND-EP00001.md`

---

## Out of scope

- Mandate amendment (amount/frequency changes)
- Customer-initiated cancellation
- Debit instruction submission
- Bulk mandate creation
