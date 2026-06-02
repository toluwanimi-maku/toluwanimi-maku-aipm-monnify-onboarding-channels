# Epic: Mandate Creation and Activation

> **WORKED EXAMPLE** — This file shows what a completed epic looks like.
> Read it fully before writing your own. Then copy `templates/epic-template.md`.

```yaml
id: EPIC-TAPT-DDBT-MAND-EP00001
name: Mandate Creation and Activation
subcapability: SUBCAP-TAPT-DDBT-MAND
capability: CAPABILITY-TAPT-DDBT
platform: TAPT
status: active
owner: Nancy Muorah

goal: |
  Enable merchants to create a direct debit mandate for a customer and track it through
  to bank activation — entirely through the Monnify API or web dashboard, without
  involving the Teamapt operations team.

jira_epic: ADD-[TBC — populate after Jira sync]
```

---

## Stories

---

### STORY-TAPT-DDBT-MAND-EP00001-00001 — Merchant creates a new mandate

**As a** merchant,
**I want to** submit a new direct debit mandate for a customer,
**So that** I can begin collecting recurring payments from them without calling the ops team.

**Acceptance Criteria:**

```
Given the merchant is authenticated on the Monnify API or web dashboard
And the customer account number and bank are valid
When the merchant submits a mandate creation request with: customer account, bank code,
     amount, frequency, start date, and merchant reference
Then the system creates the mandate record with status PENDING_BANK_APPROVAL
And returns a mandate ID and the customer authorisation URL
And sends the customer an authorisation notification via email and SMS
And logs the mandate creation event with timestamp and merchant ID

Given the merchant submits a mandate with a missing required field (account number,
      bank code, amount, or frequency)
When the request is received
Then the system returns a 400 error with the specific field that failed validation
And does not create a mandate record
```

**Events:**
- `mandate.created` — fired on successful mandate record creation
- `mandate.validation_failed` — fired when required field validation fails

**Jira ticket:** ADD-[TBC]

---

### STORY-TAPT-DDBT-MAND-EP00001-00002 — Merchant tracks mandate status

**As a** merchant,
**I want to** see the real-time status of a mandate I have created,
**So that** I know when it is approved and ready for debit without waiting for an ops team update.

**Acceptance Criteria:**

```
Given a mandate exists with any status
When the merchant calls GET /mandates/{mandateId} or views the mandate in the dashboard
Then the system returns the current mandate status and the last status change timestamp
And the status reflects the actual bank approval state within 60 seconds of any update

Given the bank has approved the mandate
When the merchant queries the mandate status
Then the status is ACTIVE
And the merchant receives a webhook notification to their registered callback URL
And the mandate is available for debit instruction submission

Given the bank has rejected the mandate
When the merchant queries the mandate status
Then the status is REJECTED with the rejection reason code
And the merchant receives a webhook notification with the rejection reason
```

**Events:**
- `mandate.activated` — fired when bank approval is received and status set to ACTIVE
- `mandate.rejected` — fired when bank rejects the mandate

**Jira ticket:** ADD-[TBC]

---

### STORY-TAPT-DDBT-MAND-EP00001-00003 — Merchant cancels an active mandate

**As a** merchant,
**I want to** cancel an active direct debit mandate,
**So that** I can stop recurring collections for a customer who has ended their subscription or requested cancellation.

**Acceptance Criteria:**

```
Given a mandate with status ACTIVE exists
When the merchant submits a cancellation request for that mandate
Then the system sets the mandate status to CANCELLED
And returns a confirmation with the cancellation timestamp
And sends the customer a cancellation notification via email and SMS
And the mandate is no longer eligible for debit instruction submission

Given a mandate with status PENDING_BANK_APPROVAL exists
When the merchant submits a cancellation request
Then the system sets the mandate status to CANCELLED
And notifies the bank of the withdrawal via the NIBSS direct debit channel
And confirms cancellation to the merchant

Given a mandate that does not belong to the requesting merchant
When a cancellation request is submitted
Then the system returns a 403 Forbidden error
And does not modify the mandate record
```

**Events:**
- `mandate.cancelled` — fired on any successful mandate cancellation

**Jira ticket:** ADD-[TBC]

---

## Out of scope for this epic

- Mandate amendment (amount or frequency changes) — separate epic
- Customer-initiated cancellation via the merchant's product — separate epic
- Debit instruction submission against an active mandate — separate epic
- Bulk mandate creation — separate epic
