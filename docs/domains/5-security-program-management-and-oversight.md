<!-- nav:top -->[Contents](../../README.md#contents) · Previous: [Domain 4: Security Operations](4-security-operations.md) · Next: [Performance-based questions and pacing](../performance-based-questions.md)<!-- /nav:top -->

# Domain 5: Security Program Management and Oversight

**Weight:** 20% of the exam (CompTIA's figure). By our estimate that is roughly 18 of up to 90 questions. **Objectives:** 5.1 to 5.6.

This is the governance, risk and compliance domain. There is less technology and more vocabulary: policy vs standard vs procedure, risk appetite vs risk tolerance, SLA vs MOU, controller vs processor. Candidates with a technical background often underrate it, then lose easy marks because two similar terms blur. It is also the one place on the exam where you do arithmetic: single and annualized loss expectancy.

## What this domain measures

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 5.1 | Summarize effective security governance | Guidelines, policies, standards, procedures, external considerations, monitoring and revision, governance structures, roles such as owner, controller, processor and custodian |
| 5.2 | Explain the risk management process | Identification, assessment types, qualitative and quantitative analysis, SLE, ARO, ALE, risk register, tolerance and appetite, the four strategies, risk reporting, BIA with RTO, RPO, MTTR, MTBF |
| 5.3 | Explain third-party risk assessment and management | Vendor assessment, right-to-audit, vendor selection, agreement types (SLA, MOA, MOU, MSA, SOW, NDA, BPA), monitoring, questionnaires, rules of engagement |
| 5.4 | Summarize effective security compliance | Compliance reporting and monitoring, consequences of non-compliance, privacy roles and rights |
| 5.5 | Explain audits and assessments | Attestation, internal and external audits, penetration testing types and environments, passive and active reconnaissance |
| 5.6 | Implement security awareness practices | Phishing campaigns, anomalous behavior recognition, user training topics, reporting and monitoring, development and execution of a program |

## Key concepts explained

### 5.1 Security governance

**The document hierarchy.**

| Document | What it is | Mandatory? | Example |
|---|---|---|---|
| Policy | High-level statement of intent and rules, approved by leadership | Yes | Information security policy, acceptable use policy |
| Standard | Specific, measurable requirement that supports a policy | Yes | Passwords must be at least 14 characters |
| Procedure | Step-by-step instructions to carry out a task | Yes, for those who perform it | How to onboard a new employee |
| Guideline | Recommended practice | No | Tips for spotting phishing |

Policies on the objectives list: acceptable use (AUP), information security, business continuity, disaster recovery, incident response, software development lifecycle (SDLC) and change management. Standards on the list: password, access control, physical security and encryption. Procedures on the list: change management, onboarding and offboarding, and **playbooks** (step-by-step response guides for specific situations, such as a phishing report).

**External considerations** that shape governance: regulatory, legal, industry, and local or regional, national and global requirements.

**Monitoring and revision.** Policies are reviewed on a schedule and after major changes, incidents or new laws.

**Governance structures.** Boards and committees set direction and oversee risk. Government entities have their own structures. Governance can be **centralized** (one team sets policy for everyone) or **decentralized** (business units set their own within broad rules).

**Data roles.**

| Role | Responsibility |
|---|---|
| Owner | Senior person accountable for the data, decides classification and who may access it |
| Controller | Decides why and how personal data is processed |
| Processor | Processes personal data on the controller's behalf, such as a payroll provider |
| Custodian or steward | Looks after the data day to day: backups, storage, applying controls |

### 5.2 Risk management

**Steps.** Identify risks, assess them, analyze them, record them, choose a strategy, and report.

**Assessment frequency.** Ad hoc (when something prompts it), recurring (on a schedule), one-time (for a project) or continuous (automated, ongoing).

**Qualitative vs quantitative.** Qualitative analysis rates likelihood and impact on a scale such as low, medium, high, often in a heat map. Quantitative analysis puts numbers on it.

**The formulas.**

- **Exposure factor (EF):** the share of the asset's value lost in one event, as a percentage.
- **Single loss expectancy:** SLE = asset value x EF.
- **Annualized rate of occurrence (ARO):** how many times a year the event is expected. Once every four years is an ARO of 0.25.
- **Annualized loss expectancy:** ALE = SLE x ARO.

Worked example 1. A warehouse is worth 800,000. A flood would destroy 25% of it (EF = 0.25). Floods are expected once every 20 years (ARO = 0.05).

- SLE = 800,000 x 0.25 = 200,000
- ALE = 200,000 x 0.05 = 10,000 a year

Worked example 2. A laptop worth 1,500 is lost entirely when stolen (EF = 1.0). The company expects 12 thefts a year across its fleet of identical laptops (ARO = 12).

- SLE = 1,500 x 1.0 = 1,500
- ALE = 1,500 x 12 = 18,000 a year

A control is worth buying, in pure cost terms, when its annual cost is less than the reduction in ALE it delivers.

**Probability, likelihood and impact.** Likelihood is how probable the event is; impact is how bad it would be. Risk combines both.

**Risk register.** A list of risks with their owners, ratings, controls and status. It also holds **key risk indicators** (metrics that warn a risk is growing), **risk owners** (who is accountable for each risk) and the **risk threshold** (the level at which a risk must be acted on).

**Appetite vs tolerance.**

- **Risk appetite** is how much risk the organization is willing to take in pursuit of its goals, in broad terms. It can be **expansionary** (willing to take more risk to grow), **conservative** (avoids risk) or **neutral**.
- **Risk tolerance** is the acceptable variation around that appetite for a specific risk, often expressed as a measurable limit.

**Strategies.**

| Strategy | What you do | Example |
|---|---|---|
| Transfer | Shift the financial impact to someone else | Cyber insurance, outsourcing with contractual liability |
| Accept | Live with it, because the cost of acting is higher | A low-impact risk documented and signed off. An **exception** or **exemption** formally accepts not meeting a requirement |
| Avoid | Stop the activity that creates the risk | Do not launch a feature that would collect sensitive data |
| Mitigate | Reduce likelihood or impact with controls | Add MFA, patch, segment |

**Business impact analysis (BIA).**

| Metric | Meaning |
|---|---|
| RTO (recovery time objective) | The longest a system can be down before the impact is unacceptable |
| RPO (recovery point objective) | The most data, measured in time, the business can afford to lose; it drives backup frequency |
| MTTR (mean time to repair) | Average time to fix a failed component |
| MTBF (mean time between failures) | Average time a component runs before failing; higher is better |

Quick check: if backups run every 4 hours, the worst-case data loss is about 4 hours, so an RPO of 1 hour is not met.

### 5.3 Third-party risk

**Assessing a vendor.** Ask for penetration test results, evidence of internal audits and independent assessments, and analyze its supply chain. A **right-to-audit clause** in the contract lets you audit the vendor yourself.

**Selecting a vendor.** **Due diligence** checks its security, finances and reputation before signing. Check for **conflicts of interest**.

**Agreement types.**

| Agreement | Purpose |
|---|---|
| SLA (service-level agreement) | Measurable service commitments, such as 99.9% uptime and response times, with remedies if missed |
| MOA (memorandum of agreement) | A written agreement of cooperation with specific responsibilities, more binding than an MOU |
| MOU (memorandum of understanding) | A statement of shared intent; usually not legally binding |
| MSA (master service agreement) | The overall terms for an ongoing relationship; later work orders sit under it |
| WO or SOW (work order, statement of work) | The specific work, deliverables and timeline for one project |
| NDA (non-disclosure agreement) | Promise to keep shared information confidential |
| BPA (business partners agreement) | Terms between business partners, such as shared profits, responsibilities and decision rights |

**Ongoing management.** **Vendor monitoring** continues after signing. **Questionnaires** collect security information from vendors. **Rules of engagement** define what a tester or vendor may and may not do, when, and with whom to communicate.

### 5.4 Security compliance

**Reporting** can be internal (to management and the board) or external (to regulators, customers or auditors).

**Consequences of non-compliance:** fines, sanctions, reputational damage, loss of license, and contractual impacts.

**Monitoring.** **Due diligence** is investigating and understanding risk; **due care** is acting on it responsibly. **Attestation and acknowledgement** means people confirm in writing that they have read and will follow a policy, or that controls are in place. Internal and external monitoring and **automation** keep compliance checks continuous.

**Privacy.** Laws apply at local or regional, national and global levels. Terms to know:

| Term | Meaning |
|---|---|
| Data subject | The person the personal data is about |
| Controller vs processor | The controller decides purposes and means; the processor acts on its instructions |
| Ownership | Who is accountable for the data |
| Data inventory and retention | Knowing what personal data you hold, where, and how long you keep it |
| Right to be forgotten | A data subject's right, under some laws, to have their data erased |

### 5.5 Audits and assessments

**Attestation** is a formal statement, often by an independent party, that controls are in place and working.

| Internal | External |
|---|---|
| Compliance checks by the organization's own staff | Regulatory audits and examinations |
| Audit committee oversight | Assessments by outside firms |
| Self-assessments | Independent third-party audits |

**Penetration testing.**

| Type | Focus |
|---|---|
| Physical | Getting into buildings and rooms |
| Offensive | Acting as the attacker (red team) |
| Defensive | Defending and detecting (blue team) |
| Integrated | Attackers and defenders working together to improve |

| Environment | What testers are told |
|---|---|
| Known environment | Full information, such as network diagrams and source code |
| Partially known environment | Some information, such as IP ranges or a user account |
| Unknown environment | Nothing beyond the target's name, like a real outside attacker |

**Reconnaissance.** **Passive** reconnaissance gathers information without touching the target's systems (public websites, DNS records, social media). **Active** reconnaissance interacts with the target, such as port scans, and can be detected.

### 5.6 Security awareness

**Phishing campaigns.** Run simulated phishing to teach people to recognize attempts and to measure progress, and have a clear way to report and respond to suspicious messages.

**Anomalous behavior recognition.** Teach staff to notice behavior that is **risky** (for example disabling security software), **unexpected** (a colleague asking for access they never needed) or **unintentional** (accidentally emailing data to the wrong person).

**Training topics.** Policy and handbooks, situational awareness, insider threat, password management, removable media and cables (unknown USB devices and charging cables can carry malware), social engineering, operational security, and hybrid and remote work environments.

**Reporting and monitoring.** Track results at the **initial** training and on a **recurring** basis to see whether behavior improves.

**Development and execution.** Design the program for the audience and risks, then run it, measure it and adjust it.

## How questions look

Domain 5 items are mostly definition-in-context: "Which document...", "Which agreement...", "Which risk strategy...", "Which role...". A typical stem describes a business decision, such as buying insurance or dropping a product line, and asks you to name it. Expect at least one calculation of SLE or ALE, sometimes needing you to convert "once every five years" into an ARO of 0.2. Pen testing items describe what the testers were told and ask for the environment type. A performance-based item might ask you to match agreements to descriptions or to complete a small risk table.

## A method for these questions

1. Find the noun the question wants: a document, agreement, role, strategy, metric or test type.
2. Look for the deciding word: "must" (policy or standard), "recommended" (guideline), "steps" (procedure); "insurance" (transfer), "stop doing" (avoid).
3. For calculations, write the formula first, then plug in. Convert frequencies to a yearly rate before multiplying.
4. For BIA items, separate time down (RTO) from data lost (RPO).
5. For privacy roles, ask who decides the purpose (controller) and who just does the work (processor).
6. For pen testing, ask what the testers knew before they started.

## Traps that cost points

- **Policy vs standard.** A policy states intent; a standard gives the measurable rule. "Minimum 14 characters" is a standard.
- **Appetite vs tolerance.** Appetite is the overall stance; tolerance is the acceptable limit for a specific risk.
- **Insurance as mitigation.** Insurance does not reduce the likelihood or impact of the event itself. It transfers the financial loss.
- **RTO vs RPO.** RTO is about downtime. RPO is about data loss and drives backup frequency.
- **MOU as a contract.** An MOU usually records shared intent and is not legally binding. Use an SLA or MSA for enforceable terms.
- **ARO as "number of years".** Once every 10 years is an ARO of 0.1, not 10.
- **Passive recon that touches the target.** A port scan is active. Reading public DNS records or a website is passive.
- **Custodian as owner.** The custodian handles the data day to day; the owner is accountable and decides access.

## Timing

Definition items here are quick, often 30 to 45 seconds. Give calculation items up to two minutes and write the formula on your notepad before plugging in numbers.

## Practice items

These 10 items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider.

### Item 1

A company's security documentation says: "All remote access to company systems must use multifactor authentication." A separate document says: "VPN sessions must use a hardware security key and time out after 15 minutes of inactivity." What are these two documents, in order?

A. A guideline, then a procedure

B. A policy, then a standard

C. A standard, then a guideline

D. A procedure, then a policy

<details>
<summary>Answer and explanation</summary>

**Answer: B.** The first is a high-level rule of intent (policy). The second sets specific, measurable requirements that support it (standard). (Objective 5.1)

- **A** is wrong because neither is optional, so neither is a guideline, and the second is a requirement, not step-by-step instructions.
- **C** is wrong because the first is broader than a standard and the second is mandatory, not a recommendation.
- **D** is wrong because neither gives step-by-step instructions.

</details>

### Item 2

A server worth 40,000 would lose 50% of its value in a fire. Fires are expected once every 10 years. What is the annualized loss expectancy?

A. 2,000

B. 4,000

C. 20,000

D. 200,000

<details>
<summary>Answer and explanation</summary>

**Answer: A.** SLE = 40,000 x 0.5 = 20,000. ARO = 1 / 10 = 0.1. ALE = 20,000 x 0.1 = 2,000. (Objective 5.2)

- **B** is wrong because it uses the full asset value, 40,000 x 0.1, ignoring the exposure factor.
- **C** is wrong because 20,000 is the SLE, the loss from one fire, not the yearly figure.
- **D** is wrong because it multiplies the SLE by 10 instead of 0.1.

</details>

### Item 3

A company decides to buy a cyber insurance policy to cover the costs of a possible ransomware attack. Which risk strategy is this?

A. Avoid

B. Accept

C. Transfer

D. Mitigate

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Insurance shifts the financial impact of the risk to the insurer. (Objective 5.2)

- **A** is wrong because the company keeps doing the activity that creates the risk.
- **B** is wrong because acceptance means taking the loss yourself without transferring it.
- **D** is wrong because insurance does not make an attack less likely or less damaging to systems.

</details>

### Item 4

The business says its order system can be down for at most 2 hours, and it cannot lose more than 15 minutes of orders. Which pair of values does this describe?

A. MTTR of 2 hours, MTBF of 15 minutes

B. RPO of 2 hours, RTO of 15 minutes

C. MTBF of 2 hours, RTO of 15 minutes

D. RTO of 2 hours, RPO of 15 minutes

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Maximum downtime is the recovery time objective. Maximum data loss, measured in time, is the recovery point objective. (Objective 5.2)

- **A** is wrong because MTTR and MTBF describe repair times and reliability of components, not business targets.
- **B** is wrong because it swaps the two: downtime is RTO, data loss is RPO.
- **C** is wrong because MTBF measures time between failures, and the 15 minutes is about data loss, not downtime.

</details>

### Item 5

A company and a nonprofit want to record that they intend to cooperate on a community security training program. Neither wants a legally binding contract. Which document fits BEST?

A. Service-level agreement

B. Memorandum of understanding

C. Master service agreement

D. Statement of work

<details>
<summary>Answer and explanation</summary>

**Answer: B.** An MOU records shared intent and expectations without creating a binding contract. (Objective 5.3)

- **A** is wrong because an SLA sets measurable, enforceable service commitments.
- **C** is wrong because an MSA sets binding terms for an ongoing commercial relationship.
- **D** is wrong because an SOW defines specific deliverables, usually under a contract.

</details>

### Item 6

A retailer hires a payroll company to run its staff payroll. The retailer decides what data is collected and why; the payroll company processes it under the retailer's instructions. What is the payroll company's role?

A. Data subject

B. Data owner

C. Controller

D. Processor

<details>
<summary>Answer and explanation</summary>

**Answer: D.** A processor handles personal data on behalf of the controller, following its instructions. (Objective 5.4)

- **A** is wrong because the data subjects are the employees whose data it is.
- **B** is wrong because the retailer, not the payroll firm, is accountable for the data.
- **C** is wrong because the retailer decides the purposes and means, which makes the retailer the controller.

</details>

### Item 7

Penetration testers are given the company name and nothing else. They begin by reading the company's website, job adverts and public DNS records. Which description applies?

A. Known environment; active reconnaissance

B. Unknown environment; passive reconnaissance

C. Partially known environment; active reconnaissance

D. Unknown environment; active reconnaissance

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Testers with no inside information are working in an unknown environment. Reading public sources without touching the company's systems is passive reconnaissance. (Objective 5.5)

- **A** is wrong because they were given no internal details, and nothing they did touched the target's systems.
- **C** is wrong because no partial information, such as IP ranges or credentials, was provided.
- **D** is wrong because public websites and DNS records are read without interacting with the target's own systems in a detectable way.

</details>

### Item 8

Before signing with a new cloud backup provider, a company reviews the provider's independent audit reports, financial stability and history of breaches. What is this activity called?

A. Due diligence

B. Attestation

C. Rules of engagement

D. Right to be forgotten

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Investigating a vendor's security, finances and reputation before choosing it is due diligence. (Objectives 5.3 and 5.4)

- **B** is wrong because attestation is a formal statement that controls are in place; the company is reviewing evidence, not issuing one.
- **C** is wrong because rules of engagement set limits for testing or vendor activity.
- **D** is wrong because the right to be forgotten is a data subject's privacy right.

</details>

### Item 9

After a simulated phishing campaign, 18% of staff clicked the link. Three months later, after training, a second campaign shows 6% clicked and twice as many people reported the email. Which part of a security awareness program does this comparison represent?

A. Development of policy handbooks

B. Initial and recurring reporting and monitoring

C. Operational security training

D. Insider threat recognition

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Measuring results at the start and again on a recurring basis shows whether the program is changing behavior. (Objective 5.6)

- **A** is wrong because writing handbooks is part of development, not the measurement shown here.
- **C** is wrong because operational security is a training topic, not a way of measuring results.
- **D** is wrong because the campaign measured phishing responses, not recognition of insiders.

</details>

### Item 10

Choose two statements that are TRUE about risk.

A. Risk appetite is the organization's broad willingness to take risk to meet its goals.

B. Accepting a risk means it has been reduced to zero.

C. A risk register records risks along with their owners and ratings.

D. Avoiding a risk means buying insurance against it.

E. A higher MTBF means a component fails more often.

<details>
<summary>Answer and explanation</summary>

**Answer: A and C.** Appetite is the broad stance on taking risk, and the register is the record of risks, owners, ratings and controls. (Objective 5.2)

- **B** is wrong because acceptance means living with the risk as it is; nothing has been reduced.
- **D** is wrong because insurance is transfer. Avoidance means stopping the activity.
- **E** is wrong because a higher mean time between failures means the component runs longer between failures, so it fails less often.

</details>

## Score yourself

| Item | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Answer | B | A | C | D | B | D | B | A | B | A, C |
| Objective | 5.1 | 5.2 | 5.2 | 5.2 | 5.3 | 5.4 | 5.5 | 5.3 | 5.6 | 5.2 |

- **9 to 10:** governance vocabulary is solid. Keep the formulas handy and move on.
- **7 to 8:** list the pairs you mixed up (RTO and RPO, policy and standard, MOU and SLA) and drill them with flash cards.
- **6 or fewer:** reread [5.2 Risk management](#52-risk-management) and [5.3 Third-party risk](#53-third-party-risk), redo both worked examples on paper, then redo the items in two days.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. Pick one system you use at work or home and write a mini risk register entry for it: the risk, its owner, likelihood, impact, an SLE and ALE estimate, and which of the four strategies you would choose.
3. Take a timed run with the [free Security+ (SY0-701) practice test on PrepClubs](https://prepclubs.com/free-practice-tests/security-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=security-plus) to practise pacing across the whole exam.

---

<!-- nav:bottom -->← Previous: [Domain 4: Security Operations](4-security-operations.md) | Next: [Performance-based questions and pacing](../performance-based-questions.md) → | [Back to contents](../../README.md#contents)<!-- /nav:bottom -->
