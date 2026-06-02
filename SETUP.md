# AIPM Onboarding Setup Guide

Complete each stage in order. Do not skip ahead — each stage's output is the input for the next.

---

## Before you start

You need:
- A personal GitHub account — create one at https://github.com if you don't have one
- Cowork desktop app — install from the Moniepoint internal tools page
- The PM Coaching plugin — install from the Cowork plugin marketplace

---

## Stage 1 — Environment Setup (Week 1, Days 1-2)

**Goal:** Your forked repo is live and the PM Coaching plugin reads it correctly.

1. Fork this repo to your personal GitHub account (click **Fork** at the top right of this page)
2. Rename your fork: `[your-name]-aipm-[your-squad]`
   - Examples: `mark-momoh-aipm-ptsp`, `nancy-muorah-aipm-directdebit`
3. Open Cowork and sign in with your Moniepoint email
4. Install the **PM Coaching** plugin from the Cowork plugin marketplace
5. In Cowork, open your forked repo folder (or connect it via the folder picker)
6. Type: `What capabilities are in this repo?` — the plugin should list the six capabilities
7. Share your GitHub repo URL with Idris via Slack DM

**Done when:** Idris confirms your repo is visible and the plugin responds correctly.

---

## Stage 2 — First Subcapability (Week 1, Days 3-5)

**Goal:** A committed subcapability file for your real product area.

**Read first:** Open `subcapabilities/SUBCAP-TAPT-DDBT-MAND.md` — this is the worked example. Read it fully before using the plugin.

1. In Cowork, use the PM Coaching plugin:
   > *"Create a subcapability for [describe your squad's primary product function in one sentence]"*
2. The plugin will ask you questions about: problem statement, personas, channels, success metrics
3. **Stop and check before committing:** Does the problem statement name a specific user and their problem — or does it describe a feature? If it describes a feature, rewrite it. See Section "What good looks like" below.
4. Save the file as `subcapabilities/SUBCAP-TAPT-[YOUR-CAP-CODE]-[4-CHAR].md`
   - Find your capability code in `capabilities/` — e.g., Nancy's is `TAPT-DDBT`
5. Commit: `git commit -m "feat: add [subcap name] subcapability"`
6. Share the GitHub file link with Idris for one round of feedback

**Done when:** File is committed and Idris has given feedback (one round only).

### What good looks like

| Bad (feature description) | Good (problem statement) |
|---|---|
| "Enable merchants to set up direct debit mandates" | "Merchants cannot initiate recurring payment collections without a manual bank process, causing delays of 5-10 days per mandate setup" |
| "Allow users to view their transaction history" | "Business owners have no real-time visibility into which transactions have settled, forcing them to call customer support for status updates" |

---

## Stage 3 — First Epic and Stories (Week 2)

**Goal:** An epic with three or more stories on a working branch.

**Read first:** Open `epics/EPIC-TAPT-DDBT-MAND-EP00001.md` — worked example.

1. Create a working branch:
   ```
   git checkout -b feature/[short-epic-name]
   ```
2. In Cowork, use the PM Coaching plugin:
   > *"Create an epic for [the specific problem your subcapability addresses]"*
3. Write at least three stories. Each story must have:
   - A clear user outcome (not a task description)
   - At least two acceptance criteria in **Given / When / Then** format
   - A placeholder Jira ticket reference (you will sync this in Stage 4)
4. Run the pre-merge gate before committing:
   > *"Run my pre-merge safety gate"*
   Fix anything it flags before committing.
5. Commit to your branch:
   ```
   git commit -m "feat: add [epic name] epic with stories"
   ```
6. Share your branch link with Idris

**Done when:** Branch is visible in GitHub with the epic file committed and the pre-merge gate passed.

---

## Stage 4 — First Change Spec and Jira Sync (Week 3)

**Goal:** A change spec committed to your branch and at least two stories synced to Jira.

1. While on your working branch, use the PM Coaching plugin:
   > *"Create my change spec"*
2. Fill in all sections: Problem and Motivation, Current Behaviour, Desired Behaviour, Release Impact
3. Sync to Jira:
   > *"Sync my change spec"*
4. The plugin will create Jira tickets from your stories — **review each one before confirming**
5. In Jira, verify each synced ticket has:
   - A description (not blank)
   - Story points estimated
   - Parent Epic linked
   - Acceptance criteria in the description
6. Share the Jira Epic URL with Idris

**Done when:** Jira Epic URL shared and at least two tickets are synced and verified.

---

## Stage 5 — First Review and Merge (Week 4)

**Goal:** Working branch merged to main after a review session with Idris.

1. Run merge readiness:
   > *"Is my release ready to merge?"*
2. Fix anything flagged
3. Slack Idris the branch link to schedule a 20-minute review session
4. Apply feedback from the session
5. Raise a pull request to `main` in your personal repo
6. Idris approves and merges

**Done when:** PR is merged. First AIPM cycle complete.

---

## Naming reference

| Your squad | Your capability code | Your capability file |
|---|---|---|
| PTSP | TAPT-PTSP | CAPABILITY-TAPT-PTSP.md |
| Monnify Disbursement | TAPT-DISB | CAPABILITY-TAPT-DISB.md |
| TPP | TAPT-TPPC | CAPABILITY-TAPT-TPPC.md |
| Aptpay Transactions | TAPT-TRXN | CAPABILITY-TAPT-TRXN.md |
| Direct Debit | TAPT-DDBT | CAPABILITY-TAPT-DDBT.md |
| Monnify Collections | TAPT-COLL | CAPABILITY-TAPT-COLL.md |

### Subcapability ID format
`SUBCAP-[CAPABILITY-CODE]-[4-CHAR-CODE]`

Example: `SUBCAP-TAPT-DDBT-MAND` (Mandate Management under Direct Debit)

The 4-char code is a short abbreviation of your subcapability name. You choose it — keep it memorable.

### Epic ID format
`EPIC-[SUBCAP-CODE]-EP[5-digit-number]`

Example: `EPIC-TAPT-DDBT-MAND-EP00001`

Start at EP00001 for your first epic.

### Story ID format
`STORY-[EPIC-CODE]-[5-digit-number]`

Example: `STORY-TAPT-DDBT-MAND-EP00001-00001`

---

## Common mistakes to avoid

- **Do not write a feature description as your problem statement.** The problem statement names a user and their pain — not a solution.
- **Do not skip the pre-merge gate.** It exists to catch format errors before they become bad habits.
- **Do not sync to Jira until your change spec is committed.** Sync flows Git to Jira — Git is always the source of truth.
- **Do not force-push to main.** Use branches and PRs.
