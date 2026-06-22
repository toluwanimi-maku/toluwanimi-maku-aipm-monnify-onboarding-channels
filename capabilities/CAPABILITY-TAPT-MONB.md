# Capability: Monnify Merchant Onboarding

> **Practice capability for Toluwanimi Maku — Stage 2 assignment**
> Write your subcapability under this capability. Choose the slice of the onboarding
> journey that is most relevant to what your squad is currently working on.

```yaml
id: CAPABILITY-TAPT-MONB
name: Monnify Merchant Onboarding
platform: TAPT
status: active
owner: Head of Platform (Idris Aliyu — acting, pre-platformisation)

personas:
  - merchant
  - business-owner
  - operations-team

channels:
  - WEB
  - MOBILE_APP
  - INTERNAL_SYSTEM

dependencies:
  - CAPABILITY-TAPT-MCOB  # Monnify Channels and Onboarding (parent)
  - KYC / identity verification providers (e.g. Smile ID, Prembly)
  - CAC registry (business registration verification)
  - Monnify payment gateway

description: |
  Monnify Merchant Onboarding covers the end-to-end journey for a new business
  registering on the Monnify platform — from initial sign-up through KYC/KYB
  document collection, compliance review, and account activation. A merchant is
  considered fully onboarded when they have a verified, active Monnify account
  and can initiate their first transaction.

success_metrics:
  - Onboarding completion rate >= 80% (started to fully activated)
  - Time to account activation <= 48 hours for standard KYB cases
  - KYC/KYB document submission completion rate >= 90%
  - Onboarding drop-off rate < 20% at each funnel stage
  - Compliance review SLA: standard cases reviewed within 24 hours
```

---

## Subcapabilities under this capability

| Subcapability | Owner | Status |
|---|---|---|
| *(To be created by Toluwanimi Maku — Stage 2 assignment)* | Toluwanimi Maku | Pending |

---

## Suggested subcapability slices for Stage 2

Pick ONE of these to write your subcapability:

- **Business registration and document collection** — the flow where a merchant submits their CAC documents, directors' IDs, and utility bill for KYB verification
- **KYC identity verification** — the step where the business owner's BVN and ID are verified against identity providers
- **Account activation and dashboard access** — what happens after compliance approval: account creation, login credentials, and first dashboard experience
