# Apply the PASTA Threat Model Framework

> **Course:** Google Cybersecurity Certificate — Course 5, *Assets, Threats, and Vulnerabilities* · Module 4
> **Activity type:** Practice assignment (unlimited attempts) · **Result:** Completed — **100%**
> **Completed file:** [PASTA-Worksheet-Completed.docx](PASTA-Worksheet-Completed.docx)
> **Supporting diagrams:** [PASTA-data-flow-diagram.pptx](PASTA-data-flow-diagram.pptx) · [PASTA-attack-tree.pptx](PASTA-attack-tree.pptx)

## What this activity is

**PASTA** (Process for Attack Simulation and Threat Analysis) is a seven-stage framework security teams use to threat-model an application *before* it ships — working from business objectives down to concrete, prioritized defenses. This activity walks all seven stages against a single scenario: a mobile app that lets sneaker collectors buy and sell shoes.

## The scenario

A sneaker-reselling company is building a mobile app connecting buyers and sellers. It needs to support account sign-up/login, direct buyer–seller messaging, seller ratings, and — the part that matters most for threat modeling — payment processing with several payment options, since improper payment handling creates real legal exposure.

## The seven stages, as completed

| Stage | Answer |
|---|---|
| **I. Business objectives** | Provide a seamless, secure sign-up/login/account-management experience for buyers and sellers; protect user data and give customers confidence it's handled responsibly; support clear, quick, and legally sound payment processing with multiple payment options. |
| **II. Technical scope** | I would prioritize evaluating **PKI** first, since it protects the app's most sensitive data — credit card information and key exchange — using AES and RSA encryption. A flaw here creates the highest business impact (financial loss, legal liability, loss of customer trust), which aligns directly with the company's stated data-privacy and payment-handling objectives. |
| **III. Decompose application** | See the data flow diagram — it models the "Product search" process: a buyer submits a search query and the app returns current inventory listings, marking where user-supplied input enters the system. |
| **IV. Threat analysis** | (1) A threat actor delivers malware — e.g. via a phishing email to an employee — to compromise authentication or steal stored credentials. (2) A threat actor social-engineers an employee (e.g. a support agent) to gain unauthorized access to customer accounts or internal admin tools. |
| **V. Vulnerability analysis** | (1) SQL-based database queries could be exploited via SQL injection if user input (e.g. search terms) isn't properly sanitized or parameterized. (2) The checkout form could expose credit card data if fields aren't encrypted, or allow account takeover via session hijacking if login credentials are weak. |
| **VI. Attack modeling** | See the attack tree — it maps two paths to compromising user data: SQL injection enabled by a lack of prepared statements, and session hijacking enabled by weak login credentials — both tracing directly back to Stage V. |
| **VII. Risk analysis & controls** | (1) Input validation and parameterized queries to prevent SQL injection. (2) MFA and strong password policies to reduce session-hijacking risk. (3) End-to-end encryption (AES at rest, TLS/RSA in transit) for all sensitive data. (4) Regular security-awareness and phishing-simulation training for employees. |

## Why I prioritized PKI in Stage II over the other technologies

The app touches four technologies — API, PKI, SHA-256, and SQL — and the task was to justify which to evaluate first. I picked PKI because it's the one directly guarding the data with the steepest cost if it fails: raw payment card data. A SQL flaw is serious, but its blast radius (inventory/seller data) is smaller than a PKI flaw exposing card numbers in transit, which triggers PCI-DSS and legal consequences the business explicitly said it wants to avoid.

## How Stage IV threats map to Stage V vulnerabilities

I deliberately kept the threats (Stage IV) and vulnerabilities (Stage V) paired with the attack tree: phishing/social-engineering threats target the *authentication* surface, while SQL injection and session hijacking are the *vulnerabilities* that let those threats actually succeed. That's the same logic the attack tree visualizes — a threat needs a vulnerability to walk through, and Stage VII's controls (MFA, parameterized queries, encryption, training) map one-to-one back onto that pairing rather than being a generic checklist.

## The supporting diagrams

Two small reference diagrams came with this activity and are reproduced alongside the worksheet:
- **Data flow diagram** — the single "Product search" process: a buyer's search query flows in, current inventory listings flow out.
- **Attack tree** — the goal "User data" is compromised via two branches: SQL injection (enabled by a lack of prepared statements) or session hijacking (enabled by weak login credentials).

Real applications like this normally have far larger, more complex versions of both — these are deliberately simplified to teach the shape of the technique.

---

*Part of my [Incident Response Practice portfolio](../../README.md).*
