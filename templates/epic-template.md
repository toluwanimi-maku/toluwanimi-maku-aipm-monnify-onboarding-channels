# Epic: [Name]

> Copy this file to `epics/EPIC-[SUBCAP-CODE]-EP[00001].md` and fill it in.
> Delete all [bracketed placeholders] and this instruction block before committing.
> Reference the worked example at `epics/EPIC-TAPT-DDBT-MAND-EP00001.md` if unsure.

```yaml
id: EPIC-[SUBCAP-CODE]-EP[00001]
# Example: EPIC-TAPT-PTSP-PROV-EP00001

name: [Human-readable epic name]
subcapability: SUBCAP-[YOUR-CAP-CODE]-[4-CHAR]
capability: CAPABILITY-[YOUR-CAP-CODE]
platform: TAPT
status: active
owner: [Your full name]

goal: |
  [One to two sentences. What does this epic deliver, for whom, and what changes for them?
  This is the "so what" — not what you are building, but what becomes possible or better
  once this epic is shipped.]

jira_epic: [YOUR-PROJECT-KEY]-[TBC — populate after Jira sync]
```

---

## Stories

---

### [STORY-ID-00001] — [Story name]

> Story ID format: STORY-[EPIC-ID]-[00001]
> Example: STORY-TAPT-PTSP-PROV-EP00001-00001

**As a** [persona — e.g., merchant, agent, operations-team member],
**I want to** [specific action or capability],
**So that** [the outcome for them — not "so that the system does X" but "so that I can Y"].

**Acceptance Criteria:**

```
Given [the starting state or precondition]
And [any additional context]
When [the action the user or system takes]
Then [what the system does — specific, observable, testable]
And [additional outcome if needed]

Given [an alternative or error condition]
When [the action]
Then [what the system does — error handling, edge case, alternative path]
```

> Write at least two acceptance criteria blocks per story: the happy path and at least one
> failure or edge case. Each criterion must be testable by a QA engineer reading it cold.

**Events:**
- `[event.name]` — [when this fires and what it signals]
- [Add or remove events as needed. Events are the integration points for downstream systems.]

**Jira ticket:** [YOUR-PROJECT-KEY]-[TBC]

---

### [STORY-ID-00002] — [Story name]

**As a** [persona],
**I want to** [action],
**So that** [outcome].

**Acceptance Criteria:**

```
Given [precondition]
When [action]
Then [outcome]
And [additional outcome]

Given [error condition]
When [action]
Then [error handling]
```

**Events:**
- `[event.name]` — [description]

**Jira ticket:** [YOUR-PROJECT-KEY]-[TBC]

---

### [STORY-ID-00003] — [Story name]

**As a** [persona],
**I want to** [action],
**So that** [outcome].

**Acceptance Criteria:**

```
Given [precondition]
When [action]
Then [outcome]

Given [error condition]
When [action]
Then [error handling]
```

**Events:**
- `[event.name]` — [description]

**Jira ticket:** [YOUR-PROJECT-KEY]-[TBC]

---

## Out of scope for this epic

- [Thing 1 that is explicitly not covered — helps prevent scope creep]
- [Thing 2]
- [Link to a future epic or story if this will be covered later]
