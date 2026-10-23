# Incident Response & Risk Assessment — Practice Portfolio

**Six hands-on exercises in incident documentation, threat modeling, access-control analysis, and risk assessment — completed as personal practice alongside the Google Cybersecurity Certificate, and written up here to show the actual reasoning, not just the finished answer.**

## What this is

Every activity in this repository started life as a Coursera practice or portfolio exercise from Google's Cybersecurity Certificate — the incident handler's journal, PASTA threat modeling, USB attack-vector analysis, an access-control worksheet, a data-leak worksheet, and a full vulnerability assessment report. I completed each one, then wrote it up here in the original document format (DOCX/XLSX/PPTX where a template exists) alongside a plain-language README explaining *why* I answered the way I did — the correlation work behind a conclusion, not just the conclusion itself.

**A note on originality:** these completed files are personal practice work, reconstructed and published here for portfolio purposes — they were not submitted to Coursera for grading. Coursera's own Honor Code prohibits submitting AI-assisted work for a grade, and this repository doesn't do that; it's a public write-up of independent practice, built the same way my [TryHackMe write-ups](https://github.com/theworldofricharda/tryhackme-ctf-writeups) are: as a record of my own reasoning, not a shortcut around anyone's coursework.

## The activities

| # | Activity | Framework / focus | What it demonstrates |
|---|----------|-------------------|----------------------|
| 01 | [Incident Handler's Journal](activities/01-incident-handlers-journal/README.md) | The 5 W's of incident documentation | Structuring a first response entry for a ransomware attack on a health care clinic — and flagging the HIPAA question the scenario doesn't ask for |
| 02 | [PASTA Threat Model](activities/02-pasta-threat-model/README.md) | PASTA (7-stage threat modeling) | Threat-modeling a mobile app end to end — business objectives through to prioritized security controls — scored 100% |
| 03 | [USB Attack Vectors](activities/03-usb-attack-vectors/README.md) | USB baiting / social engineering | Reading a found USB drive from both the target's and the attacker's side, and recreating the activity's template from scratch |
| 04 | [Data Leak Worksheet](activities/04-data-leak-worksheet/README.md) | NIST SP 800-53: AC-6 (Least Privilege) | Tracing an accidental external leak back to an over-broad access grant, not the human error that triggered it |
| 05 | [Access Control Worksheet](activities/05-access-control-worksheet/README.md) | Authorization / offboarding failure | Correlating a suspicious event-log entry against an employee directory to catch a dormant contractor account being used for payroll fraud |
| 06 | [Vulnerability Assessment Report](activities/06-vulnerability-assessment-report/README.md) | NIST SP 800-30 Rev. 1 (risk assessment) | A full report — scope, scored risk table, methodology, and remediation — for a production database server |

## How each activity is written up

Every folder holds the **completed original file** (the DOCX/XLSX a grader or reviewer could open directly) plus a README that:

1. States what the activity is testing and which framework it's built around.
2. Reproduces the scenario and the completed answers in readable markdown.
3. Explains the reasoning that isn't visible in the finished worksheet — how a conclusion was actually reached, not just what it says.

Two activities carry their own extra materials: the PASTA worksheet ships with its two supporting diagrams (data flow + attack tree), and the access-control worksheet ships with the source spreadsheet (event log + employee directory) the analysis was built from.

## Skills demonstrated

`Incident Documentation` · `PASTA Threat Modeling` · `Attack Tree & Data Flow Analysis` · `USB Baiting / Social Engineering Analysis` · `NIST SP 800-53 (Access Control)` · `NIST SP 800-30 Rev. 1 (Risk Assessment)` · `Log & Directory Correlation` · `Least-Privilege Analysis` · `Vulnerability Assessment Reporting` · `Technical Writing for Security Audiences`

## About me

I'm **Akintomide R F**, aka **Syntaxfoxx**, working through the Google Cybersecurity Certificate and TryHackMe as part of moving into a security career. This portfolio and my [TryHackMe write-ups](https://github.com/theworldofricharda/tryhackme-ctf-writeups) are both built the same way: complete the work first, then explain it clearly enough that someone else could follow the reasoning.

## Licence

Released under the [MIT Licence](LICENSE) — read it, share it, reuse it; attribution is appreciated.
