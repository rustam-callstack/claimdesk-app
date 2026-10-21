# QA AI Workshop — Part 2 · participant materials

Everything here is what you need on the day. Nothing here tells you the answers.

**The app:** https://rustam-callstack.github.io/claimdesk-app/

Claimdesk is a small expense-claim tool. It runs entirely in your browser — there is nothing
to install, nothing to clone and no account to create. Your claims are stored in your own
browser only, so everyone gets an independent copy of the app and nobody can affect anyone
else's run.

If you want more than one independent instance, add `?p=` and a name:
`https://rustam-callstack.github.io/claimdesk-app/?p=ana`

## What to bring

A laptop, a browser, and the agent setup from Part 1. That is all.

## Contents

| | |
|---|---|
| `SPEC.md` | Claimdesk v1.0 product specification. The source of truth for how the app is meant to behave. Requirement IDs (`REQ-1.1`, `REQ-3.1`, …) are stable — reference them by ID. |
| `exercise-1/` | Brief, plus the ticket and pull request you will review. |
| `exercise-2/` | Brief, plus the charter and permission-envelope templates you will fill in. |

Exercise 3's materials arrive on the day — they contain information that would spoil
Exercise 2 if read beforehand.

## Context from other sources

Real QA work pulls context from more than one system, so this workshop does too. Two sources
outside this repository hold supporting context. Reach them through your agent's Notion and
Google Drive MCP connections — you need a Callstack account to open them.

| | |
|---|---|
| [Claimdesk — product workspace](https://app.notion.com/p/callstack/Claimdesk-product-workspace-workshop-data-4005d027c0f8817a86eaff990659c596) | Notion. The backlog, and links to further documents. Start here. |
| [QA kickoff notes, 24 Sep 2026](https://docs.google.com/document/d/1qW-Ox4k-Qsujzj8XDN3S8vca6B7ZtSAZIt0ARxBFhdU/edit?tab=t.0) | Google Drive. The decisions taken at the QA kickoff. |

**This repository stays the source of truth.** Tickets, notes and policy documents elsewhere are
context. Where any of them disagrees with `SPEC.md`, the specification wins: report the
disagreement, quoting both sources, and leave the decision to Product.

## Reading ahead

Reading `SPEC.md` in advance is welcome and will not spoil anything. The exercises are about
how well you can direct an agent, not about whether you have memorised the spec.
