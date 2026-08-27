# Identify the Attack Vectors of a USB Drive

> **Course:** Google Cybersecurity Certificate — Course 5, *Assets, Threats, and Vulnerabilities* · Module 3
> **Activity type:** Practice assignment (ungraded toward course score)
> **Completed file:** [Parking-Lot-USB-Exercise-Completed.docx](Parking-Lot-USB-Exercise-Completed.docx)

## What this activity is

This one is about **USB baiting** — a social-engineering attack where a threat actor strategically leaves an infected USB drive somewhere an employee will find it, relying on curiosity to do the rest of the work. The activity asks you to reason about a found drive from both the *target's* side (what's actually on it) and the *attacker's* side (how that content could be weaponized).

## The scenario

You're on the security team at Rhetorical Hospital. You find a USB stick with the hospital's logo in the parking lot and, out of curiosity, bring it back to the office. Rather than plugging it into a real machine, you inspect it inside **virtualization software** — a simulated instance of a computer, isolated from other files and networks, so an infected drive can't reach anything real. Inside, the contents belong to **Jorge Bailey**, the hospital's HR manager: family and pet photo folders, a new hire letter, vacation ideas, shift schedules, an employee budget spreadsheet, a wedding-planning slideshow, and Jorge's own resume.

## The completed worksheet

| Field | Answer |
|---|---|
| **Contents** | The drive mixes personal and work files: family and pet photos, a wedding-planning slideshow, and Jorge's resume, alongside hospital work documents like a new hire letter and employee shift and budget spreadsheets. Several files — the resume, new hire letter, and shift schedule — likely contain personally identifiable information (PII) about Jorge and his coworkers. |
| **Attacker mindset** | An attacker could use the resume and wedding details to craft a convincing spear-phishing or vishing pretext against Jorge or his fiancée, Wendy. The new hire letter and shift schedule could reveal employee names, roles, and work patterns, helping an attacker impersonate HR or time a physical intrusion for when specific staff are off-site. |
| **Risk analysis** | Even though this drive contained no malware, USB baiting is a real risk: a malicious drive could carry code that installs a backdoor, keylogger, or ransomware the moment it's opened outside a safe, isolated environment. Technical controls like disabling USB autorun and running antivirus/EDR scans, operational controls like mandatory sandboxing of unknown drives, and managerial controls like a written policy banning personal USB use and requiring staff to report found devices to security would all reduce this risk. |

## Why "was this staged?" matters

The activity brief explicitly prompts you to consider whether the whole find was staged, and I think that's the real point of the exercise: a drive full of *personal* photos next to *work* documents isn't an accident, it's bait. Mixing Jorge's wedding plans and family photos in with the shift schedule makes the drive feel authentically "found," lowering suspicion — a purely work-only drive would read as more obviously planted. That's why the attacker-mindset answer treats the personal content not as irrelevant clutter but as the thing that makes the pretext (and the bait itself) convincing.

## Technical / operational / managerial — why all three

The risk-analysis answer deliberately spans all three control categories rather than picking one, because USB baiting isn't purely a technical problem: a perfect antivirus scan doesn't stop an employee who never brings the drive to a security team in the first place. Autorun-disabling and EDR scanning close the technical gap, mandatory sandboxing is the operational step that makes "isolate it first" the default rather than a judgment call, and a written USB policy plus a reporting culture (managerial) is what turns "found a USB in the lot" into an incident report instead of a silent plug-in at someone's desk.

## A note on the template

The original activity uses a Google Doc template ("Parking lot USB exercise") with no DOCX attachment on file for offline use, so I recreated it in DOCX form directly from the exercise brief's own "Response Template Structure" section, keeping the same three rows and field intent.

---

*Part of my [Incident Response Practice portfolio](../../README.md).*
