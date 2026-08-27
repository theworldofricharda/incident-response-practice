# Access Controls Worksheet — Dormant Contractor Account

> **Course:** Google Cybersecurity Certificate — access control & authorization track
> **Activity type:** Coursera activity template, paired with a source event log / employee directory
> **Completed file:** [Access-Control-Worksheet-Completed.docx](Access-Control-Worksheet-Completed.docx)
> **Source data:** [Accounting-Exercise-Source-Data.xlsx](Accounting-Exercise-Source-Data.xlsx)

## What this activity is

Unlike the other worksheets in this portfolio, this one comes with real (simulated) log data instead of a prose scenario — an event log entry and an employee directory spreadsheet — and the task is to do the actual correlation work: read the log, find the account, cross-reference it against who that account belongs to, and decide whether the access was legitimate.

## The evidence

**Event log** (`Accounting-Exercise-Source-Data.xlsx`, sheet *Event log*):

```
Event Type: Information
Event Source: AdsmEmployeeService
Event ID: 1227
Date: 10/03/2023   Time: 8:29:57 AM
User: Legal\Administrator
Computer: Up2-NoGud
IP: 152.207.255.255
Description: Payroll event added. FAUX_BANK
```

**Employee directory** (same file, sheet *Employee directory*) — the relevant row:

| Name | Role | IP address | Status | Authorization | Start date | End date |
|---|---|---|---|---|---|---|
| Robert Taylor Jr. | Legal attorney | 152.207.255.255 | Contractor | Admin | 2019-09-04 | **2019-12-27** |

## The completed worksheet

| Field | Content |
|---|---|
| **Note(s)** | The event log shows a payroll event was added on 10/03/2023 at 8:29:57 a.m. by the account 'Legal\Administrator' from a workstation named 'Up2-NoGud' at IP 152.207.255.255. Cross-referencing the employee directory shows that IP and the 'Legal attorney' role both belong to Robert Taylor Jr., a contractor whose engagement — and access — should have ended on 12/27/2019. |
| **Issue(s)** | Robert Taylor Jr.'s contractor engagement ended in December 2019, nearly four years before this event, yet his account remained active with full Admin-level authorization. An offboarded contractor account should not still be able to create payroll entries, especially one referencing an unfamiliar 'FAUX_BANK' destination — a strong indicator of fraudulent payroll diversion rather than a legitimate business action. |
| **Recommendation(s)** | Implement an automated offboarding process that disables or deletes user accounts on their documented end date, paired with a periodic (e.g., quarterly) access review that flags any account whose authorization exceeds its current job function or employment status — a technical control (automatic deprovisioning) backed by a managerial control (scheduled access audits). |

## How I actually found this

The directory has ten employees, so the log entry's `IP: 152.207.255.255` was the pivot — matching it against the directory's IP address column narrows it to exactly one row: Robert Taylor Jr. Once his row is isolated, three details line up into one story:

1. His **End date is 2019-12-27** — nearly four years before the log's **2023-10-03** timestamp.
2. His account is still marked **Authorization: Admin** — never downgraded or disabled.
3. The workstation name in the log, **`Up2-NoGud`**, is a strong tell on its own — that's not a real corporate asset-tag naming convention, and reads as either an attacker-renamed machine or a very unsubtle joke someone should have flagged long before this event.

Put together, the description `Payroll event added. FAUX_BANK` isn't a routine HR action — it's a dormant, over-privileged account being used to route payroll to a bank account that doesn't belong in the system, four years after the person who owned that account should have lost access entirely.

## Why the fix is deprovisioning, not just "watch this account"

The tempting narrow fix is "disable Robert Taylor Jr.'s specific account." But the real issue is the *process* gap that let any contractor's access survive their end date for years — so the recommendation targets automatic deprovisioning tied to the documented end date, plus a recurring audit as a backstop for whatever the automation misses. That's the difference between patching one dormant account and closing the mechanism that let it go dormant-but-active in the first place.

---

*Part of my [Incident Response Practice portfolio](../../README.md).*
