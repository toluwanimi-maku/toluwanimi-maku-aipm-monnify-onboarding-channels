---
id: SUBCAP-TAPT-MCOB-KYCV
name: KYC Identity Verification
capability: CAPABILITY-TAPT-MCOB — Monnify Channels and Onboarding
platform: TAPT — Teamapt
status: active
personas:
  - merchant
  - business-owner
  - operations-team
channels:
  - WEB
  - API
problem: Monnify collects director name and date of birth through manual entry during
  onboarding, violating the CBN mandate for real-time identity validation. Identity
  details must be auto-populated from BVN and NIN rather than entered manually, leaving
  the platform non-compliant and exposed to data errors and identity fraud.
design_refs:
engineering_refs:
deprecation_reason:
---

## Description

KYC Identity Verification replaces manual director identity entry with automated lookup
and cross-validation using BVN and NIN. When a business owner submits their BVN and NIN
during onboarding, the system retrieves the director name and date of birth from each
source automatically. The names returned by BVN and NIN are then cross-checked: if they
match, the identity fields are auto-populated and the merchant may proceed; if they
differ, verification fails and the merchant cannot continue until the discrepancy is
resolved. This delivers a compliant, lower-friction, and more accurate KYC flow aligned
with the CBN real-time validation mandate.

## Success Metrics

| Metric | Target |
|---|---|
| Director records auto-populated (zero manual entry) | 100% |
| Director-name correction tickets post-launch | Reduction vs. baseline (TBD) |
| BVN/NIN name mismatches surfaced before submission | % tracked (TBD baseline) |

## Scope Boundaries

In scope: BVN lookup and name/DOB auto-population, NIN lookup and name auto-population,
cross-validation of BVN name against NIN name, surfacing a blocking error when names do
not match, and preventing submission until the mismatch is resolved.

Out of scope: verification of any individual other than the declared business
owner/director, KYB (business entity verification), re-verification of existing
onboarded merchants, and any identity check beyond BVN and NIN cross-validation.

## Dependencies

- **BVN provider** — external identity lookup; availability is a hard prerequisite for
  director name and DOB auto-population.
- **NIN provider** — external identity lookup; availability is a hard prerequisite for
  name cross-validation.

## Edge Cases and Failure Modes

- **BVN or NIN provider unavailable** — the verification step cannot proceed. The system
  surfaces an error and allows the merchant to retry; the onboarding flow is paused,
  not permanently failed.
- **BVN or NIN not found** — valid format but no record returned; merchant is shown an
  error prompting them to verify and re-enter the number.
- **Invalid BVN or NIN format** — caught at input validation before any provider call;
  merchant sees an inline error immediately.
- **BVN name ≠ NIN name** — verification fails. The merchant cannot proceed past this
  step. No partial approval is permitted.
- **BVN/NIN does not belong to the declared director** — covered by the name cross-check;
  a mismatch triggers the same blocking failure.
