# Capability: Monnify Channel Enablement

> **Practice capability for Toluwanimi Maku — Stage 2 assignment**
> Write your subcapability under this capability. Choose the payment channel
> most relevant to what your squad is currently working on.

```yaml
id: CAPABILITY-TAPT-MCHE
name: Monnify Channel Enablement
platform: TAPT
status: active
owner: Head of Platform (Idris Aliyu — acting, pre-platformisation)

personas:
  - merchant
  - developer
  - operations-team

channels:
  - WEB
  - API
  - INTERNAL_SYSTEM

dependencies:
  - CAPABILITY-TAPT-MCOB  # Monnify Channels and Onboarding (parent)
  - CAPABILITY-TAPT-COLL  # Collections and Payments
  - CAPABILITY-TAPT-TRXN  # Transaction Processing Suite
  - Card schemes (Visa, Mastercard, Verve)
  - NIP (bank transfer processing)

description: |
  Monnify Channel Enablement covers the process by which an activated Monnify
  merchant turns on specific payment collection channels — bank transfer, card,
  USSD — after their account has been approved. This includes channel configuration,
  integration key provisioning, sandbox testing, and production go-live for each
  payment method. A channel is considered enabled when the merchant has made at
  least one successful live transaction through it.

success_metrics:
  - Channel activation success rate >= 95% post-onboarding approval
  - Time from channel activation request to first live transaction <= 24 hours
  - Sandbox-to-production migration success rate >= 90%
  - API key provisioning time <= 5 minutes
  - Merchant integration support resolution time <= 4 hours
```

---

## Subcapabilities under this capability

| Subcapability | Owner | Status |
|---|---|---|
| *(To be created by Toluwanimi Maku — Stage 2 assignment)* | Toluwanimi Maku | Pending |

---

## Suggested subcapability slices for Stage 2

Pick ONE of these to write your subcapability:

- **Bank transfer channel setup** — enabling NIP-based bank transfer collections for a merchant, including virtual account provisioning and webhook configuration
- **Card payment enablement** — activating card acceptance for a merchant, including Visa/Mastercard/Verve setup and 3DS configuration
- **API key and integration management** — the flow for generating, rotating, and revoking API keys and webhook endpoints for merchant integrations
