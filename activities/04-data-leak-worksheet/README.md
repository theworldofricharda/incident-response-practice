# Data Leak Worksheet

> **Course:** Google Cybersecurity Certificate — asset, threat & vulnerability track (NIST SP 800-53 access control)
> **Activity type:** Coursera activity template · **Framework applied:** NIST SP 800-53: AC-6 (Least Privilege)
> **Completed file:** [Data-Leak-Worksheet-Completed.docx](Data-Leak-Worksheet-Completed.docx)

## What this activity is

This worksheet walks through a real access-control failure and asks you to trace it back to the specific NIST SP 800-53 control it violates, then recommend a fix and justify why that fix actually closes the gap — not just "add more security," but a specific control mapped to a specific cause.

## The scenario

A sales manager shared access to a folder of internal-only documents with their team during a meeting. The folder held files about an unannounced product, plus customer analytics and promotional materials. After the meeting, the manager never revoked that access — but did warn the team to wait for approval before sharing the promotional materials externally.

Later, on a video call with a business partner, a sales rep forgot that warning. Intending to share a link to just the promotional materials, the rep accidentally shared the link to the **internal folder** instead. The business partner, assuming it was the promotional content, posted the link on their company's social media page.

## The completed worksheet

| Field | Content |
|---|---|
| **Control** | Least privilege *(given by the activity as the relevant control)* |
| **Issue(s)** | The sales manager granted the whole team access to an internal-only folder for a meeting and never revoked that access afterward, so a team member retained standing access far beyond what the promotional-materials task required. That excess access, combined with the rep sharing the wrong link, let unpublished product, analytics, and internal files leak outside the company. |
| **Review** | NIST SP 800-53: AC-6 (Least Privilege) states that only the minimal access and authorization required to complete a task or function should be granted to users, processes, and roles, so that no one operates with more privilege than their job requires. |
| **Recommendation(s)** | Instead of sharing the entire internal folder, the manager should have created a separate, restricted folder containing only the approved promotional materials and granted time-limited access to just that folder for the meeting. Internal-only access should also be automatically reviewed and revoked once the meeting concludes. |
| **Justification** | Limiting access to only the approved promotional folder means that even if a link is shared with the wrong person by mistake, the internal-only product, analytics, and customer files stay protected. Automatically revoking temporary access also removes the standing exposure that let a single mistake turn into a public leak. |

## Why the fix targets the *access grant*, not the mistake

It would be easy to write this up as "the rep should have been more careful with links" — but that treats a predictable human error as the root cause, when the actual root cause is a control failure: the team never should have had standing access to internal-only files for a task that only needed the promotional subset. A least-privilege fix (a scoped folder, time-limited access) means the *same human mistake* — sharing the wrong link — stops being catastrophic, because there's no longer a sensitive internal folder sitting behind that link. That's the difference between a recommendation that reduces one specific incident's odds and one that closes the underlying gap.

---

*Part of my [Incident Response Practice portfolio](../../README.md).*
