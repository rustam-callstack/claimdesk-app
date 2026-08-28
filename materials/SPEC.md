# Claimdesk — Product Specification v1.0

**Status:** Approved for build
**Last updated:** 2026-08-26
**Audience:** engineering, QA

Claimdesk is an internal tool for submitting and approving employee expense claims. This
document is the source of truth for v1.0 behaviour. Requirement IDs are stable — reference
them by ID in test artifacts and pull requests.

---

## 1. Roles

| Role | Can |
|---|---|
| **Submitter** | Create, edit and submit their own claims; view their own claim history. |
| **Approver** | View claims routed to them; approve or reject with a comment. |

A user may hold both roles but may never approve their own claim.

---

## 2. Flow

1. **My claims** — list of the submitter's claims with status.
2. **New claim** — claim-level details.
3. **Line items** — add, edit and remove individual expenses.
4. **Review & submit** — read-only summary, then submit.
5. **Approval queue** — approver's list of pending claims.
6. **Decision** — approve or reject with a comment.

---

## 3. Claim-level requirements

- **REQ-1** A claim has a title, a currency and one or more line items.
- **REQ-1.1** Title is required, 10–120 characters.
- **REQ-1.2** Currency in v1.0 is **EUR only**. The euro symbol (`€`) must be shown
  wherever a monetary amount is displayed, on every screen.
- **REQ-1.3** A claim total is the sum of its line-item amounts, shown to two decimal places.
- **REQ-1.4** The total claim amount must not exceed **2,500.00**.
- **REQ-1.5** A claim may contain at most **20** line items.
- **REQ-1.6** The **Submit** action is disabled until the claim has at least one line item
  and a valid title.

---

## 4. Line-item requirements

- **REQ-2** A line item has a date, a category, a description, an amount, and optionally a receipt.
- **REQ-2.1** Amount is required, minimum **0.01**, maximum **500.00** per line item.
- **REQ-2.2** Description is required, 10–200 characters.
- **REQ-2.3** Category is one of: `Travel`, `Meals`, `Accommodation`, `Equipment`, `Other`.
- **REQ-2.4** Date must not be in the future.
- **REQ-2.5** Date must not be more than **90 days** before the current date.
- **REQ-2.6** Line items may be removed individually while the claim is in `Draft`.

### 4.1 Category sub-limits

- **REQ-3** Some categories carry a limit stricter than the general per-item maximum in REQ-2.1.
  Where a sub-limit applies, it takes precedence.
- **REQ-3.1** A `Meals` line item must not exceed **40.00**.
- **REQ-3.2** An `Equipment` line item requires a description of at least 30 characters.
- **REQ-3.3** No sub-limit applies to `Travel`, `Accommodation` or `Other` beyond REQ-2.1.

---

## 5. Receipts

- **REQ-4** A receipt may be attached to any line item.
- **REQ-4.1** A receipt is **required** for any line item with an amount above **25.00**.
  Submission must be blocked while any such line item has no receipt, and the offending
  line item must be indicated to the user.
- **REQ-4.2** Accepted formats are PNG, JPG and PDF, maximum 5 MB per file.
- **REQ-4.3** One receipt per line item. Attaching a second replaces the first.

### 5.1 Policy summary

For reference, the thresholds above are summarised here:

| Rule | Threshold |
|---|---|
| Receipt required above | 20.00 |
| Per line item maximum | 500.00 |
| `Meals` line item maximum | 40.00 |
| Claim total maximum | 2,500.00 |
| Maximum line items | 20 |
| Backdating window | 90 days |

---

## 6. Submission and approval

- **REQ-5** On submit, a claim moves from `Draft` to `Pending`.
- **REQ-5.1** A submitted claim is immutable while `Pending`.
- **REQ-5.2** Submitting the same claim must never create more than one claim record.
- **REQ-5.3** A claim with a total above **1,000.00** requires two distinct approvers.
  Both must approve before the claim reaches `Approved`.
- **REQ-6** An approver may approve or reject. A rejection requires a comment of at least
  20 characters.
- **REQ-6.1** An approver must not be able to act on their own claim.
- **REQ-6.2** Claim statuses are: `Draft`, `Pending`, `Approved`, `Rejected`.

---

## 7. Drafts, state and accessibility

- **REQ-7** A `Draft` claim is autosaved. Reloading the page must restore the draft,
  including any line items already added.
- **REQ-7.1** All interactive controls must be reachable and operable by keyboard, and must
  expose an accessible name.
- **REQ-7.2** Validation errors must be associated with the field they concern.
- **REQ-7.3** The claim list should load quickly.

---

## 8. Out of scope for v1.0

Multi-currency, mileage calculation, per-team budgets, delegated approval, receipt OCR,
mobile-native clients, email notification, export to accounting systems.

---

## 9. Open questions

None recorded.
