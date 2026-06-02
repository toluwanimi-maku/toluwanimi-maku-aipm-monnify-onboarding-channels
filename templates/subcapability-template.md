# Subcapability: [Name]

> Copy this file to `subcapabilities/SUBCAP-[YOUR-CAP-CODE]-[4-CHAR].md` and fill it in.
> Delete all [bracketed placeholders] and this instruction block before committing.
> Reference the worked example at `subcapabilities/SUBCAP-TAPT-DDBT-MAND.md` if unsure.

```yaml
id: SUBCAP-[YOUR-CAP-CODE]-[4-CHAR]
# Example: SUBCAP-TAPT-PTSP-PROV for "Terminal Provisioning" under PTSP

name: [Human-readable name — e.g., "Terminal Provisioning"]
capability: CAPABILITY-[YOUR-CAP-CODE]
# Example: CAPABILITY-TAPT-PTSP

platform: TAPT
status: active
owner: [Your full name]

personas:
  - [persona-1]  # e.g., merchant, agent, developer, operations-team
  - [persona-2]

channels:
  - [CHANNEL]  # Options: MOBILE_APP, WEB, POS, USSD, ATM, API, INTERNAL_SYSTEM

dependencies:
  - [Dependency 1]  # e.g., another capability ID or external system name
  # Remove this section entirely if there are no dependencies

problem: |
  [ONE sentence. Name the specific user and their specific pain.
  NOT: "Enable merchants to do X" — that is a feature description.
  YES: "Merchants who need to do X cannot do so without [manual step], causing [specific pain]."
  This is the most important field in this file. Get it right before moving on.]

description: |
  [2-3 sentences describing what this subcapability covers — the scope of what it does
  and does not do. Think of this as what you would say to a new engineer joining the team
  to explain what this subcapability is responsible for.]

success_metrics:
  - [Metric 1 — specific and measurable. Example: "Mandate activation rate >= 85% within 24 hours"]
  - [Metric 2]
  - [Metric 3]
  # Aim for 3-5 metrics. Each must be measurable — avoid "improve X" without a target.
```

---

## Epics under this subcapability

| Epic | Name | Status |
|---|---|---|
| [Will be populated as epics are created] | | |
