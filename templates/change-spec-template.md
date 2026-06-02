# Change Spec — [Release Name]

> Copy this file to `release/change-spec.md` on your working branch and fill it in.
> Delete all [bracketed placeholders] and this instruction block before committing.
> Reference the worked example at `release/change-spec.md` on the main branch.
> Do not sync to Jira until this file is committed to your branch.

```yaml
id: RELEASE-[SUBCAP-CODE]-[001]
# Example: RELEASE-TAPT-PTSP-PROV-001

name: [Release name — same as your epic name is fine for Phase 1]
branch: feature/[your-branch-name]
subcapability: SUBCAP-[YOUR-CAP-CODE]-[4-CHAR]
owner: [Your full name]
status: draft
jira_epic_slice: [YOUR-PROJECT-KEY]-[TBC — populate after Jira sync]
```

---

## Problem and Motivation

[2-3 sentences. What problem does this release solve and why does it matter now?
This is the business case in plain language. A product lead or senior stakeholder should
be able to read this and immediately understand what is broken today and why shipping
this makes things better. Do not describe what you are building — describe the problem.]

---

## Current Behaviour

[Bullet points or short paragraph. What does the world look like today, before this release?
Be specific. "Users cannot do X" is better than "X is not yet available". Include any
manual steps, workarounds, or operational costs if relevant.]

---

## Desired Behaviour

[Bullet points or short paragraph. What does the world look like after this release ships?
Mirror the structure of Current Behaviour. Each point in Current Behaviour should have a
corresponding point here showing what changes.]

---

## Channels

[List only the channels this release affects.]

- `[CHANNEL]` — [brief description of what changes on this channel]

---

## Release Impact

| Area | Impact |
|---|---|
| [User group or system] | [What changes for them] |
| [User group or system] | [What changes for them] |
| [Engineering] | [New endpoints, services, or changes required] |
| [Compliance / Ops] | [Any regulatory or operational changes, or "No change"] |

---

## Changes

### New stories in this release

| Story ID | Name | Jira |
|---|---|---|
| [STORY-ID] | [Story name] | [YOUR-PROJECT-KEY]-[TBC] |
| [STORY-ID] | [Story name] | [YOUR-PROJECT-KEY]-[TBC] |
| [STORY-ID] | [Story name] | [YOUR-PROJECT-KEY]-[TBC] |

### Modified artifacts

- Added: `subcapabilities/[YOUR-SUBCAP-FILE].md`
- Added: `epics/[YOUR-EPIC-FILE].md`

---

## Out of scope

- [Explicit exclusion 1 — what is NOT in this release]
- [Explicit exclusion 2]
