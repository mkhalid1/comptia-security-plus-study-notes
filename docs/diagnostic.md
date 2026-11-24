<!-- nav:top -->[Contents](../README.md#contents) · Previous: [SY0-701 or SY0-801: which version to take](which-version.md) · Next: [Domain 1: General Security Concepts](domains/1-general-security-concepts.md)<!-- /nav:top -->

# 15-minute diagnostic

Fifteen original items, three from each SY0-701 domain, to show you where to start. Set a timer for 15 minutes, answer everything without looking anything up, then check each answer and use the table at the bottom.

These items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider. They are different from the practice items on the domain pages, so you can still use those afterwards.

If you would rather start with a full timed run in the real format, take the [free Security+ (SY0-701) practice test on PrepClubs](https://prepclubs.com/free-practice-tests/security-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=security-plus) instead, then come back here.

## Part A: Domain 1, General Security Concepts

### D1

A login screen shows the message "Unauthorized access is prohibited and will be prosecuted." What type of control is this?

A. Detective

B. Deterrent

C. Corrective

D. Compensating

<details>
<summary>Answer and explanation</summary>

**Answer: B.** The banner discourages an attempt but cannot stop one, which makes it a deterrent. (Objective 1.1)

- **A** is wrong because the banner does not discover or record anything.
- **C** is wrong because nothing is being repaired after an incident.
- **D** is wrong because the banner is not standing in for a control that could not be deployed.

</details>

### D2

Bob wants to send Alice a file that only Alice can read. Which key should Bob use to encrypt it?

A. Bob's private key

B. Bob's public key

C. Alice's private key

D. Alice's public key

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Anything encrypted with Alice's public key can only be decrypted with Alice's private key, which only Alice holds. (Objective 1.4)

- **A** is wrong because encrypting with Bob's private key is how a signature works; anyone with Bob's public key could decrypt it.
- **B** is wrong because only Bob could decrypt it, with his own private key.
- **C** is wrong because Bob does not have Alice's private key, and should never have it.

</details>

### D3

A team updates a production database server. Before the work, they wrote down the exact steps to restore the previous version if the update fails. Afterwards, they updated the network diagram. Which item in this change was the restore procedure?

A. Impact analysis

B. Standard operating procedure

C. Backout plan

D. Version control

<details>
<summary>Answer and explanation</summary>

**Answer: C.** A backout plan is the documented way to return to the previous state if a change fails. (Objective 1.3)

- **A** is wrong because impact analysis estimates what the change could affect; it is not a restore procedure.
- **B** is wrong because an SOP describes how to carry out routine tasks the same way each time, not how to undo this specific change.
- **D** is wrong because version control tracks changes to files and configurations over time; the restore steps are the backout plan.

</details>

## Part B: Domain 2, Threats, Vulnerabilities, and Mitigations

### D4

An employee who was told last week that his contract will not be renewed copies the customer database to a personal USB drive. Which threat actor is this?

A. Hacktivist

B. Insider threat

C. Shadow IT

D. Unskilled attacker

<details>
<summary>Answer and explanation</summary>

**Answer: B.** He already has authorized access and is misusing it, likely from revenge or for gain. That is an insider threat. (Objective 2.1)

- **A** is wrong because there is no political or philosophical cause.
- **C** is wrong because shadow IT is unapproved technology used for convenience, not deliberate theft.
- **D** is wrong because he is an employee using his own access, not an outside attacker with downloaded tools.

</details>

### D5

A malicious script starts deleting payroll files on the first day after a specific administrator's account is disabled. Which type of malware is this?

A. Rootkit

B. Worm

C. Logic bomb

D. Spyware

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Code that waits for a condition, here the account being disabled, and then runs its payload is a logic bomb. (Objective 2.4)

- **A** is wrong because a rootkit's purpose is hidden, persistent privileged access, not a delayed trigger.
- **B** is wrong because nothing spreads across the network.
- **D** is wrong because spyware collects and sends information; it does not delete files on a trigger.

</details>

### D6

During a TLS connection, an attacker on the network forces the client and server to agree on an old, weak protocol version that the attacker can break. What is this called?

A. Collision attack

B. Downgrade attack

C. Replay attack

D. Directory traversal

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Forcing two parties to fall back to a weaker protocol or cipher is a downgrade attack. (Objective 2.4)

- **A** is wrong because a collision is two inputs producing the same hash.
- **C** is wrong because replay resends a captured valid message; it does not change the protocol version.
- **D** is wrong because directory traversal is a web attack on file paths.

</details>

## Part C: Domain 3, Security Architecture

### D7

A company wants a sensor that alerts on suspicious traffic but must never be able to slow or block production traffic, even if it crashes. How should it be deployed?

A. Inline as an IPS, fail-closed

B. Passive, on a network tap or SPAN port

C. Inline as a WAF

D. As a jump server

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A passive sensor fed by a tap or SPAN port only sees a copy of the traffic, so it cannot block it and its failure does not affect traffic. (Objective 3.2)

- **A** is wrong because an inline, fail-closed device stops traffic if it fails.
- **C** is wrong because an inline WAF sits in the traffic path and can block or slow requests.
- **D** is wrong because a jump server is an admin access point, not a sensor.

</details>

### D8

Which recovery site provides space, power and cooling, but no installed equipment or data?

A. Hot site

B. Warm site

C. Cold site

D. Multi-cloud site

<details>
<summary>Answer and explanation</summary>

**Answer: C.** A cold site is the cheapest option and offers only the facility; everything else must be brought in and restored. (Objective 3.4)

- **A** is wrong because a hot site is fully equipped with current data.
- **B** is wrong because a warm site has hardware and connectivity in place.
- **D** is wrong because multi-cloud is a strategy of using several cloud providers, not a site type.

</details>

### D9

A medical records system is being moved to a SaaS provider. Which responsibility stays with the customer?

A. Managing which staff have accounts and what they can access

B. Physical security of the data center

C. Patching the application servers

D. Maintaining the hypervisor

<details>
<summary>Answer and explanation</summary>

**Answer: A.** In SaaS the provider runs the application and everything beneath it, but the customer still controls its data and user access. (Objective 3.1)

- **B** is wrong because the provider secures its data centers.
- **C** is wrong because the SaaS provider patches its own application and servers.
- **D** is wrong because the provider runs the hypervisor and hosts.

</details>

## Part D: Domain 4, Security Operations

### D10

During an incident, the team has isolated an infected server and removed the malware and the attacker's backdoor account. Which incident response step comes NEXT?

A. Detection

B. Containment

C. Recovery

D. Preparation

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Isolation was containment and removing the malware and account was eradication. Next is recovery: restoring the server to normal operation and watching it closely. (Objective 4.8)

- **A** is wrong because detection already happened at the start.
- **B** is wrong because the server is already isolated.
- **D** is wrong because preparation comes before any incident.

</details>

### D11

An email arrives from a domain whose published SPF record does not list the server that sent it. Which statement is TRUE?

A. The message fails SPF, and the domain's DMARC policy tells the receiver what to do with it.

B. The message passes SPF because DKIM is not checked.

C. DKIM will repair the SPF failure automatically.

D. SPF failures can only be detected by the sender.

<details>
<summary>Answer and explanation</summary>

**Answer: A.** SPF lists which servers may send for a domain, so mail from an unlisted server fails. DMARC is where the domain owner says how receivers should treat failures. (Objective 4.5)

- **B** is wrong because SPF and DKIM are separate checks; an unlisted server fails SPF regardless of DKIM.
- **C** is wrong because DKIM is a signature check; it does not change an SPF result.
- **D** is wrong because the receiving server performs the SPF check.

</details>

### D12

Which access control model grants permissions based on a person's job function, so that everyone in the "Accounts Payable" group gets the same access?

A. Mandatory access control

B. Discretionary access control

C. Attribute-based access control

D. Role-based access control

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Role-based access control ties permissions to roles, and users get access by being placed in a role. (Objective 4.6)

- **A** is wrong because MAC uses security labels and clearances set by the system.
- **B** is wrong because DAC lets each resource owner decide who gets access.
- **C** is wrong because ABAC evaluates many attributes, such as location and device, not just job role.

</details>

## Part E: Domain 5, Security Program Management and Oversight

### D13

A laptop worth 2,000 is fully lost when stolen. The company expects 5 thefts a year. What is the annualized loss expectancy?

A. 400

B. 2,000

C. 10,000

D. 1,000

<details>
<summary>Answer and explanation</summary>

**Answer: C.** SLE = 2,000 x 1.0 = 2,000. ALE = SLE x ARO = 2,000 x 5 = 10,000. (Objective 5.2)

- **A** is wrong because it divides by the ARO instead of multiplying.
- **B** is wrong because 2,000 is the single loss expectancy, not the yearly figure.
- **D** is wrong because it treats five thefts a year as an ARO of 0.5.

</details>

### D14

An agreement between a company and its hosting provider guarantees 99.95% monthly uptime and gives service credits if the target is missed. What type of agreement is this?

A. NDA

B. MOU

C. BPA

D. SLA

<details>
<summary>Answer and explanation</summary>

**Answer: D.** A service-level agreement sets measurable service commitments, such as uptime, and remedies when they are missed. (Objective 5.3)

- **A** is wrong because an NDA covers confidentiality.
- **B** is wrong because an MOU records shared intent and usually is not binding.
- **C** is wrong because a BPA sets terms between business partners, such as profit sharing and responsibilities.

</details>

### D15

Which document gives step-by-step instructions that the service desk follows every time a new employee joins?

A. Onboarding procedure

B. Acceptable use policy

C. Password standard

D. Security guideline

<details>
<summary>Answer and explanation</summary>

**Answer: A.** A procedure lists the exact steps for a task; onboarding is one of the procedures named on the objectives. (Objective 5.1)

- **B** is wrong because an AUP states what users may and may not do with company systems.
- **C** is wrong because a standard sets measurable requirements, such as password length.
- **D** is wrong because a guideline is a recommendation, not mandatory steps.

</details>

## Answer key

| Part | Items | Answers |
|---|---|---|
| Part A | D1 to D3 | B, D, C |
| Part B | D4 to D6 | B, C, B |
| Part C | D7 to D9 | B, C, A |
| Part D | D10 to D12 | C, A, D |
| Part E | D13 to D15 | C, D, A |

## What your result means

Count your correct answers in each part. A choose-two item counts only if both choices are right.

| Part | Domain weight | Score 0 or 1 | Score 2 | Score 3 |
|---|---|---|---|---|
| A. [General Security Concepts](domains/1-general-security-concepts.md) | 12% | Study this domain early: its vocabulary is used everywhere | Do its practice items | Light review only |
| B. [Threats, Vulnerabilities, and Mitigations](domains/2-threats-vulnerabilities-and-mitigations.md) | 22% | Study the attack and indicator tables | Do its practice items | Light review only |
| C. [Security Architecture](domains/3-security-architecture.md) | 18% | Study the full guide | Do its practice items | Light review only |
| D. [Security Operations](domains/4-security-operations.md) | 28% | Top priority: the heaviest domain | Read Key concepts, then all 14 items | Still do the items: it is over a quarter of the exam |
| E. [Security Program Management and Oversight](domains/5-security-program-management-and-oversight.md) | 20% | Study the risk and agreement tables | Do its practice items | Light review only |

If two domains tie, start with the one with the higher weight: a gap in a 28% domain costs more than the same gap in a 12% domain.

Then pick a plan: the [7-day plan](study-plans.md#7-day-plan) if you have a week, or the [2-day plan](study-plans.md#2-day-plan) if your exam is close.

---

<!-- nav:bottom -->← Previous: [SY0-701 or SY0-801: which version to take](which-version.md) | Next: [Domain 1: General Security Concepts](domains/1-general-security-concepts.md) → | [Back to contents](../README.md#contents)<!-- /nav:bottom -->
