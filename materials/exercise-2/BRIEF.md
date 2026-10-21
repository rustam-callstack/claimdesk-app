# Exercise 2 — Give the agent a charter, not a script

**75 minutes.** You will need the running app, `SPEC.md`, and your Exercise 1 checklist.

Context for this round is in the [QA kickoff notes](https://docs.google.com/document/d/1qW-Ox4k-Qsujzj8XDN3S8vca6B7ZtSAZIt0ARxBFhdU/edit?tab=t.0) on Google Drive and the
[Claimdesk product workspace](https://app.notion.com/p/callstack/Claimdesk-product-workspace-workshop-data-4005d027c0f8817a86eaff990659c596) on Notion. Both are context; `SPEC.md` governs.

The app has defects deliberately planted in it. How many, and how hard they are, you find out
at scoring — not before.

Your job is not to find them by hand. It is to direct an agent that will, and then to judge
honestly what it reached and what it did not.

---

## 1. Fill in the charter

```
CHARTER

Explore      the claim submission flow of Claimdesk
with         the v1.0 spec and my Exercise 1 checklist
to discover  ways the app's behaviour departs from the spec.

Timebox      35 minutes of agent runtime.

Report       every finding with the REQ ID it violates and steps to reproduce.
             Also report what you could NOT reach, and why.
             An empty "could not reach" section will be treated as an incomplete report.
```

That last line is the point of the exercise. A report that claims complete coverage is
making a claim, not describing a run.

## 2. Write the permission envelope — before the agent starts

```
PERMISSION ENVELOPE                      agreed before the run

Target             <my instance URL>

May                read the page; click; type; navigate within the target origin;
                   create and edit draft claims; upload the provided sample receipts

May not            approve or reject claims — that is the approver role and outside
                     this charter
                   open any origin other than the target
                   install anything, or change browser settings
                   read or write files outside the run folder

Must stop and ask  before any action it cannot undo
                   before exceeding the timebox
                   if it needs a credential it was not given

Budget             <token ceiling> / <minutes>

Agreed by          <name>            at   <time>
```

Writing this takes three minutes, and it is the whole difference between an agent you can
leave running and one you have to watch. Of everything in this session, it is the piece most
likely to be useful on Monday.

## 3. Run, then report

Hand back a run report containing:

- every finding, with the REQ ID it violates and steps to reproduce
- what the agent could not reach, and why
- what the run cost — tokens and minutes

## The gate

The permission envelope is agreed **before** the agent runs, not after it surprises someone.
