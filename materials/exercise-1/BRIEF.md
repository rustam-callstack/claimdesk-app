# Exercise 1 — Context in, test plan out

**60 minutes.** You will need `SPEC.md`, `TICKET.md` and `PR-118.diff`.

Two parts, in order. Do not skip to the checklist.

---

## Part 1 — Groom the requirements

> Read the Claimdesk v1.0 spec as a QA engineer, before looking at the change.
>
> Report every requirement that is **untestable as written**, **contradicted elsewhere in the
> spec**, or **missing**. Quote the text and cite the REQ ID.
>
> Do not invent a corrected version. Report the problem, and say who needs to answer it.

## Part 2 — Checklist for CD-142

> Now read ticket CD-142 and PR #118, and produce a risk-ranked test checklist for
> **this change only**.
>
> Every item must quote the requirement text it comes from and cite its REQ ID. An item you
> cannot trace to quoted text does not belong on the list. An item unrelated to CD-142 does
> not belong on it either.

The scoping constraint in Part 2 is doing real work. Dumping every spec problem into the
checklist is not thoroughness — Part 1 is where breadth belongs, Part 2 is where discipline
does.

---

## What you hand back

- Your Part 1 grooming report.
- Your Part 2 checklist.
- Keep both. You will need the checklist again later, and it will matter more than you expect.

## The gate

You review every generated item and accept or reject it, saying why. The agent proposes;
you decide.
