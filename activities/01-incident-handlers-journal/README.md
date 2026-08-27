# Document an Incident with an Incident Handler's Journal

> **Course:** Google Cybersecurity Certificate — Course 6, *Sound the Alarm: Detection and Response* · Module 1
> **Activity type:** Graded portfolio assignment (5 points) · **Format:** Incident handler's journal (DOCX)
> **Completed file:** [Incident-Handlers-Journal-Completed.docx](Incident-Handlers-Journal-Completed.docx)

## What this activity is

An incident handler's journal is exactly what it sounds like — a running, dated log an analyst keeps while working an incident, so the reasoning and timeline survive past the moment the alert fires. This activity asks for one properly structured entry: a date and entry number, a short description, any tools used, the **5 W's** of the incident, and a space for open questions.

## The scenario

A small U.S. health care clinic was hit on a Tuesday at 9:00 a.m. A phishing email carrying a malicious attachment led to ransomware being deployed, encrypting the clinic's files. The attackers left a ransom note demanding payment for the decryption key.

## Entry 1 — as recorded

| Field | Content |
|---|---|
| **Date / Entry** | August 27, 2026 · Entry 1 |
| **Description** | Initial documentation of a ransomware incident affecting a small U.S. health care clinic. A staff phishing email led to file encryption and a ransom demand, severely disrupting clinic operations. |
| **Tool(s) used** | None specified in the initial incident report. Forensic follow-up is expected to involve email gateway logs, endpoint detection and response (EDR) alerts, and SIEM log review. |
| **Who** | An organized group of unethical hackers (a ransomware gang) caused the incident by targeting a clinic employee with a phishing email. |
| **What** | A staff member downloaded a malicious attachment from a phishing email, which deployed ransomware that encrypted the organization's computer files; the attackers left a ransom note demanding payment for the decryption key. |
| **When** | The incident occurred on Tuesday at 9:00 a.m. |
| **Where** | The incident occurred on the clinic's internal computer network, beginning with a compromised staff email account. |
| **Why** | The incident happened because an employee opened a malicious email attachment, and the clinic's email filtering and/or security awareness training did not stop the phishing message from reaching and deceiving the employee. |
| **Additional notes** | It is not yet confirmed whether the ransomware spread beyond the initially affected workstation, or whether patient data (protected health information) was accessed before encryption — this should be confirmed early given the clinic's HIPAA breach-notification obligations. |

## Why I flagged HIPAA in the notes

The scenario doesn't ask for it explicitly, but the target is a **health care clinic**, and ransomware that encrypts files typically means an attacker had read/write access to the file system first — which raises the question of whether patient records were also viewed or copied before encryption. A U.S. clinic has breach-notification obligations under HIPAA that kick in fast, so flagging that gap as an open question (rather than assuming "just encryption, no exfiltration") is the kind of thing a real incident handler would want on record from entry 1, not added later.

## Template note

The source template includes six identical entry tables so a handler can log multiple entries over time. Only **Entry 1** was required by this activity, so entries 2–6 are left as blank templates in the completed file, matching the original design.

---

*Part of my [Incident Response Practice portfolio](../../README.md).*
