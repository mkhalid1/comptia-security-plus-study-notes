<!-- nav:top -->
[Contents](../README.md#contents) · Previous: [SY0-701 or SY0-801: which version to take](which-version.md) · Next: [Domain 1: General Security Concepts](domains/1-general-security-concepts.md)
<!-- /nav:top -->

# 5-minute diagnostic

Five original items, one from each SY0-701 domain, to show you where to start. Set a timer for 5 minutes, answer everything without looking anything up, then check each answer and use the table at the bottom.

These items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider. They are different from the practice items on the domain pages, so you can still use those afterwards.

If you would rather start with a full timed run in the real format, take the [free Security+ (SY0-701) practice test on PrepClubs](https://prepclubs.com/free-practice-tests/security-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=security-plus) instead, then come back here.

## Part A: Domain 1, General Security Concepts

### D1

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

### D2

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

### D3

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

### D4

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

### D5

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

Want more? The [free timed Security+ (SY0-701) practice test on PrepClubs](https://prepclubs.com/free-practice-tests/security-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=security-plus) has 25 questions across all five domains, with your score split by domain.

## Answer key

| Part | Item | Answer |
|---|---|---|
| Part A | D1 | C |
| Part B | D2 | B |
| Part C | D3 | A |
| Part D | D4 | D |
| Part E | D5 | D |

## What your result means

Mark each part as correct or missed.

| Part | Domain weight | Missed | Correct |
|---|---|---|---|
| A. [General Security Concepts](domains/1-general-security-concepts.md) | 12% | Study this domain early: its vocabulary is used everywhere | Light review only |
| B. [Threats, Vulnerabilities, and Mitigations](domains/2-threats-vulnerabilities-and-mitigations.md) | 22% | Study the attack and indicator tables | Light review only |
| C. [Security Architecture](domains/3-security-architecture.md) | 18% | Study the full guide | Light review only |
| D. [Security Operations](domains/4-security-operations.md) | 28% | Top priority: the heaviest domain | Still do the items: it is over a quarter of the exam |
| E. [Security Program Management and Oversight](domains/5-security-program-management-and-oversight.md) | 20% | Study the risk and agreement tables | Light review only |

If two domains tie, start with the one with the higher weight: a gap in a 28% domain costs more than the same gap in a 12% domain.

Then pick a plan: the [7-day plan](study-plans.md#7-day-plan) if you have a week, or the [2-day plan](study-plans.md#2-day-plan) if your exam is close.

---

<!-- nav:bottom -->
← Previous: [SY0-701 or SY0-801: which version to take](which-version.md) | Next: [Domain 1: General Security Concepts](domains/1-general-security-concepts.md) → | [Back to contents](../README.md#contents)
<!-- /nav:bottom -->
