# CD-142 · Enforce category sub-limits on line items

**Type:** Story
**Status:** In Review
**Assignee:** dev
**Sprint:** 26.19
**Linked PR:** #118

---

## Description

Finance has asked for per-category limits on top of the existing per-line-item maximum.
The policy was agreed and added to the spec last sprint (REQ-3 and its sub-requirements) —
this ticket is the implementation only. No policy decisions needed here.

Right now a line item is validated against the general per-item maximum and nothing else,
so a €120 lunch is accepted. That is what Finance flagged.

## Acceptance criteria

- **AC1** — Category sub-limits from REQ-3 are enforced at line-item level, and take
  precedence over the general per-item maximum in REQ-2.1.
- **AC2** — REQ-3.1 is enforced.
- **AC3** — REQ-3.2 is enforced.
- **AC4** — Categories with no sub-limit (REQ-3.3) behave exactly as before.
- **AC5** — Validation messages name the limit that was breached, so the user knows which
  rule applied.

## Out of scope

Approval routing, receipt rules, the claim-level total. Not touching those.

---

## Comments

**QA** — Which limit message wins if a line item breaches both a sub-limit and the general
maximum? Assuming the sub-limit, since REQ-3 says it takes precedence, but confirm.

**dev** — Sub-limit wins, yes. Only one message is shown per field so it short-circuits on
the first failure.

**dev** — Implemented, PR #118 up. Kept the change inside the existing validation function
rather than adding a layer. Note that tightening limits means more rejections coming back
through the approval flow than before — worth a look at that path too, though I have not
changed anything there.

**Finance** — Thanks. The €40 one is the one we care about most, it is where nearly all the
overspend sits.
