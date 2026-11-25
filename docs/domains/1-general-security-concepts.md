<!-- nav:top -->
[Contents](../../README.md#contents) · Previous: [5-minute diagnostic](../diagnostic.md) · Next: [Domain 2: Threats, Vulnerabilities, and Mitigations](2-threats-vulnerabilities-and-mitigations.md)
<!-- /nav:top -->

# Domain 1: General Security Concepts

**Weight:** 12% of the exam (CompTIA's figure). By our estimate that is roughly 10 of up to 90 questions. **Objectives:** 1.1 to 1.4.

This is the smallest domain, but its vocabulary runs through the other four. If you cannot say at once whether a control is detective or corrective, or which key signs and which key encrypts, you will lose marks on scenario questions in every domain, not just this one.

## What this domain measures

Domain 1 checks that you speak the language of security: how controls are classified, what the core principles mean, how change is managed safely, and how cryptography is used in practice.

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 1.1 | Compare and contrast types of security controls | Four categories (technical, managerial, operational, physical) and six types (preventive, deterrent, detective, corrective, compensating, directive) |
| 1.2 | Summarize fundamental security concepts | CIA, non-repudiation, AAA, gap analysis, Zero Trust control and data planes, physical security, deception technology |
| 1.3 | Explain change management and its security impact | Approval, ownership, stakeholders, impact analysis, test results, backout plan, maintenance window, SOPs, technical implications, documentation, version control |
| 1.4 | Explain appropriate cryptographic solutions | PKI, encryption levels, symmetric and asymmetric, key exchange, TPM, HSM, secure enclave, obfuscation, hashing, salting, signatures, key stretching, blockchain, certificates and revocation |

## Key concepts explained

### 1.1 Security controls

Every control has a **category** (who or what carries it out) and a **type** (what it does to an incident). The exam often gives you one and asks for the other, so keep the two lists separate in your head.

| Category | Carried out by | Examples |
|---|---|---|
| Technical | Systems and software | Firewalls, encryption, MFA, antivirus, ACLs |
| Managerial | Policy and oversight | Risk assessments, security policies, hiring procedures |
| Operational | People doing day-to-day tasks | Security guards' patrols, awareness training, backup jobs run by staff |
| Physical | Barriers in the real world | Fences, locks, bollards, mantraps |

| Type | When it acts | Examples |
|---|---|---|
| Preventive | Before, stops the event | Door lock, firewall rule that blocks a port |
| Deterrent | Before, discourages the attempt | Warning sign, visible camera, login banner |
| Detective | During or after, finds the event | IDS alert, log review, motion sensor |
| Corrective | After, fixes the damage | Restoring from backup, reimaging a host, patching after a breach |
| Compensating | Instead of the ideal control | Extra monitoring on a legacy server that cannot be patched |
| Directive | Tells people what to do | Policy requiring screen locks, "authorized staff only" instructions |

How to tell close pairs apart:

- **Preventive vs deterrent:** a preventive control works even if the attacker is not put off (a lock). A deterrent only works on someone who notices it and changes their mind (a sign).
- **Detective vs corrective:** detective tells you something happened. Corrective restores the system. An antivirus that only alerts is detective; one that quarantines the file is also acting correctively.
- **Compensating:** look for words like "cannot", "legacy", "until", "temporary". The ideal control is not possible, so something else reduces the same risk.
- **One control can have more than one type.** A guard can deter, detect and prevent. Pick the type the question stresses.

### 1.2 Fundamental concepts

**CIA triad.** Confidentiality (only the right people can read it: encryption, access control), Integrity (it has not been changed without authorization: hashing, signatures), Availability (it is there when needed: redundancy, backups, DDoS protection).

**Non-repudiation.** The sender cannot credibly deny sending something. Digital signatures provide it, because only the holder of the private key could have produced the signature. A shared secret such as a symmetric key or a shared password cannot give non-repudiation, because more than one party holds it.

**AAA.**

- **Authentication:** proving identity. People authenticate with something they know, have or are; systems authenticate with certificates, keys or tokens (for example a device certificate on a laptop for 802.1X).
- **Authorization:** what an authenticated subject may do. Authorization models include discretionary (owner decides), mandatory (labels and clearances), role-based (permissions follow job role), rule-based (system-wide rules such as time of day) and attribute-based (decisions from attributes of user, resource and context).
- **Accounting:** recording what was done, for audit. Logs and session records.

**Gap analysis.** Compare where you are against where you need to be (a framework, a regulation, a target state), then list the gaps and plan to close them.

**Zero Trust.** No implicit trust based on network location. Every request is checked.

| Plane | Part | What it does |
|---|---|---|
| Control plane | Adaptive identity | Uses context (device health, location, behavior) when deciding |
| Control plane | Threat scope reduction | Limits what any one identity or segment can reach |
| Control plane | Policy-driven access control | Decisions come from defined policy, not ad hoc rules |
| Control plane | Policy Engine | Makes the allow or deny decision |
| Control plane | Policy Administrator | Acts on the decision, for example issues the session token or tells the enforcement point |
| Data plane | Subject or system | The user or device asking for access |
| Data plane | Policy Enforcement Point | Sits in the path and allows or blocks traffic as instructed |
| Data plane | Implicit trust zones | The area behind the enforcement point; Zero Trust aims to keep these as small as possible |

A quick way to remember it: the engine **decides**, the administrator **delivers** the decision, the enforcement point **does** it.

**Physical security.**

| Control | Purpose |
|---|---|
| Bollards | Stop vehicles reaching a building entrance |
| Access control vestibule | Two doors, only one opens at a time, stops tailgating |
| Fencing | Defines and protects the perimeter |
| Video surveillance | Detects and records; also deters |
| Security guard | Can judge situations, check IDs, respond |
| Access badge | Identifies and authorizes people at doors |
| Lighting | Deters and helps cameras and guards see |
| Sensors | Detect presence: infrared (body heat), pressure (weight on a floor or mat), microwave (reflected signal, covers larger areas), ultrasonic (sound waves) |

**Deception and disruption.** A **honeypot** is a single decoy system, a **honeynet** is a network of decoys, a **honeyfile** is a decoy file (for example "passwords.xlsx") that alerts when opened, and a **honeytoken** is a fake credential or data record that should never be used, so any use of it is an alert.

### 1.3 Change management

Change management exists so that a fix does not become an outage or a hole. The exam wants you to know the parts and why each one protects security.

| Part | Why it matters for security |
|---|---|
| Approval process | Someone accountable reviews the risk before work starts, often a change advisory board |
| Ownership | One named person is responsible for the change |
| Stakeholders | People affected are consulted and informed |
| Impact analysis | What could break, who is affected, what new risks appear |
| Test results | Evidence it works in a test environment first |
| Backout plan | How to return to the previous state if it fails |
| Maintenance window | An agreed time with the least business impact |
| Standard operating procedure | Repeatable, documented steps for routine changes |

Technical implications to check before a change: allow lists and deny lists that may need updating, restricted activities, expected downtime, whether a service or application restart is needed, legacy applications that may not tolerate the change, and dependencies (other systems that rely on this one). Afterwards, update diagrams, policies and procedures, and keep everything under **version control** so you can see what changed and roll back.

### 1.4 Cryptographic solutions

**Symmetric vs asymmetric.**

| | Symmetric | Asymmetric |
|---|---|---|
| Keys | One shared secret key | Key pair: public and private |
| Speed | Fast, good for bulk data | Slow, used for small data |
| Typical use | Encrypting disks, files, session traffic | Key exchange, digital signatures, certificates |
| Examples | AES | RSA, elliptic curve (ECC), Diffie-Hellman for key exchange |
| Main problem | Getting the key to the other side safely | Speed |

Real systems combine them: asymmetric cryptography (or Diffie-Hellman) agrees or protects a symmetric session key, and the symmetric key encrypts the data. That is how TLS works.

**Which key does what.** To send someone a secret, encrypt with **their public key**; only their private key decrypts it. To sign, use **your private key**; anyone checks the signature with your public key. Mixing these up is the most common crypto mistake on the exam.

**Key length.** For the same algorithm, a longer key is harder to brute-force. Do not compare key lengths across algorithm families: a 256-bit ECC key and a 3072-bit RSA key give roughly similar strength.

**Encryption levels.**

| Level | What is protected | Example |
|---|---|---|
| Full-disk | The whole drive, including the OS | BitLocker on a laptop |
| Partition or volume | One partition or volume | An encrypted data volume |
| File | Individual files | Encrypting one document |
| Database | The whole database | Transparent database encryption |
| Record | Individual rows or fields | Encrypting the card number column only |
| Transport or communication | Data in transit | TLS, IPsec, SSH |

**Tools.**

- **TPM (Trusted Platform Module):** a chip on the motherboard that stores keys for one device, supports secure boot measurements and full-disk encryption.
- **HSM (hardware security module):** a dedicated, tamper-resistant appliance or card that generates and stores keys for many systems, for example a CA's signing keys.
- **Key management system:** software or a service that creates, rotates, stores and retires keys centrally.
- **Secure enclave:** an isolated area of a processor that keeps keys and sensitive processing away from the main OS.

**Key escrow.** A trusted third party holds a copy of keys so data can be recovered if a key is lost.

**Obfuscation.**

| Method | What it does | Reversible? |
|---|---|---|
| Steganography | Hides data inside other data, such as an image | Yes, if you know where to look |
| Tokenization | Swaps sensitive data for a token; the real value sits in a secure vault | Only through the vault |
| Data masking | Shows part or a fake version, such as `****-****-****-4821` | No, for the viewer |

**Hashing and its helpers.**

- **Hashing** produces a fixed-length digest. Same input, same output; any change to the input changes the digest. It is one-way, so it gives integrity, not confidentiality. Examples: SHA-256.
- **Salting** adds a random value to each password before hashing, so identical passwords get different hashes and precomputed (rainbow) tables fail.
- **Key stretching** runs the hash many times or uses a slow algorithm (PBKDF2, bcrypt) so each guess costs the attacker more time.
- **Digital signature:** hash the message, then encrypt the hash with the sender's private key. It gives integrity, authentication and non-repudiation.

**Blockchain and open public ledger.** A blockchain is a chain of blocks, each including a hash of the previous one, so changing an old record breaks every later link. An open public ledger is one that anyone can read and verify.

**Certificates and PKI.**

| Term | Meaning |
|---|---|
| Certificate authority (CA) | Issues and signs certificates |
| Root of trust | The root CA certificate everything else chains up to |
| Third-party certificate | Issued by a public CA browsers already trust |
| Self-signed | Signed by its own key; no outside trust, fine for internal testing |
| Wildcard | Covers one level of subdomains, such as `*.example.com` |
| CSR | Certificate signing request: the public key and identity details sent to a CA; the private key never leaves the requester |
| CRL | A list the CA publishes of revoked certificates |
| OCSP | A real-time query to ask whether one certificate is still valid |

A wildcard for `*.example.com` covers `www.example.com` and `mail.example.com`, but not `example.com` itself or `a.b.example.com`.

## How questions look

Most Domain 1 items are short scenarios with one deciding detail. "A company installs a sign that says..." asks for a control type. "The legacy system cannot be patched, so the team..." points to a compensating control. Crypto items describe a goal ("prove the email came from the CFO", "make sure the file was not altered", "protect the card number but keep the last four digits") and ask for the method. Change management items describe a change going wrong and ask which step was skipped. Some items ask you to choose two. A performance-based item might ask you to match controls to types, or pick certificate settings for a scenario.

## A method for these questions

1. Underline the goal word: prevent, deter, detect, recover, prove, hide, verify, recover a lost key.
2. For control questions, decide the type and the category separately, then check which one the question asks for.
3. For crypto questions, map the goal to a property: secrecy means encryption, unchanged means hashing, proof of sender means a signature, hide existence means steganography.
4. For key questions, say out loud whose key and which half: "their public to encrypt to them, my private to sign".
5. For change questions, walk the lifecycle (request, impact analysis, approval, test, schedule, implement, verify, document) and find the missing step.
6. Eliminate answers that solve a different CIA property than the one asked about.

## Traps that cost points

- **Calling hashing encryption.** A hash cannot be decrypted. If the goal is to read the data later, hashing is wrong.
- **Signing with the public key.** Signatures are made with the sender's private key. Encryption for a recipient uses the recipient's public key.
- **Thinking a deterrent prevents.** A sign or a dummy camera stops nobody determined. If the control physically or logically blocks, it is preventive.
- **Missing compensating controls.** When the stem says the proper fix is impossible or delayed, the answer is the substitute that reduces the same risk.
- **Treating symmetric keys as proof of identity.** Two parties share the key, so either could have created the message. No non-repudiation.
- **Over-reading wildcards.** A wildcard covers one subdomain level only.
- **Confusing TPM and HSM.** TPM is one chip in one device. HSM is a dedicated device protecting keys for many systems.
- **Skipping the backout plan.** If a change fails and nobody can roll back, the missing piece is the backout plan, not more testing in production.
- **Mixing tokenization and masking.** Tokenization replaces data with a token that maps back through a vault; masking simply hides characters for display.

## Timing

Domain 1 items are usually short. Aim for 45 to 60 seconds each so you bank time for performance-based questions elsewhere. If a crypto item is taking longer, write the four-line key table (encrypt to someone, sign as yourself) on your notepad and decide from it.

## Practice items

These 4 items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider.

### Item 1

A data center cannot install a mantrap at a side entrance for another six months. Until then, the security manager posts a guard at that door during business hours and reviews badge logs daily. What type of control is the guard and log review, taken together?

A. Directive

B. Compensating

C. Deterrent

D. Corrective

<details>
<summary>Answer and explanation</summary>

**Answer: B.** The ideal control (the vestibule) is not yet possible, so other measures reduce the same risk in the meantime. That is the definition of a compensating control. (Objective 1.1)

- **A** is wrong because a directive control tells people what to do, such as a policy. A guard and log review are not instructions.
- **C** is wrong because although a guard deters, the scenario is about substituting for a missing control, and log review does not deter anyone.
- **D** is wrong because corrective controls restore systems after an incident. Nothing here repairs damage.

</details>


### Item 2

An accountant receives an email that claims to come from the CFO approving a large payment. The finance team wants proof that the CFO really sent it and that the amount was not changed in transit. What should the CFO use?

A. Encrypt the email with the accountant's public key

B. Hash the email and attach the hash in plain text

C. Digitally sign the email with the CFO's private key

D. Encrypt the email with a symmetric key shared by the whole finance team

<details>
<summary>Answer and explanation</summary>

**Answer: C.** A digital signature, made with the CFO's private key, proves the sender (only the CFO holds that key) and integrity (the signed hash would not match an altered message). It also provides non-repudiation. (Objective 1.4)

- **A** is wrong because encrypting with the accountant's public key keeps the message secret but proves nothing about who sent it; anyone can use a public key.
- **B** is wrong because an attacker who changes the email can simply compute a new hash and replace the attached one.
- **D** is wrong because everyone on the team holds the shared key, so it cannot prove the CFO in particular sent the message.

</details>


### Item 3

A web team buys one certificate for `*.shop.example` to cover its sites. Which hostname will the certificate NOT cover?

A. `www.shop.example`

B. `api.shop.example`

C. `pay.shop.example`

D. `eu.api.shop.example`

<details>
<summary>Answer and explanation</summary>

**Answer: D.** A wildcard matches one label in place of the asterisk. `eu.api.shop.example` has two labels before `shop.example`, so it is not covered. (Objective 1.4)

- **A**, **B** and **C** are wrong because each has exactly one label in front of `shop.example`, which is what the wildcard covers.

</details>


### Item 4

A company is choosing where to keep the private signing keys for its internal certificate authority. The keys must be protected in tamper-resistant hardware and used by several servers. Choose two of the following that are TRUE.

A. A TPM in each server is the best fit for keys shared by several servers.

B. An HSM is designed to generate and protect keys for multiple systems.

C. The CA's private key should be included in every certificate signing request.

D. Key escrow lets a trusted party hold a copy of keys for recovery.

E. Self-signed certificates are trusted by browsers without any extra setup.

<details>
<summary>Answer and explanation</summary>

**Answer: B and D.** An HSM is a dedicated, tamper-resistant device that protects keys used by many systems, which fits a CA. Key escrow is the practice of a trusted third party holding keys so they can be recovered. (Objective 1.4)

- **A** is wrong because a TPM is bound to one device and is not meant for keys shared across servers.
- **C** is wrong because a CSR contains the requester's public key and identity details. No private key, and certainly not the CA's, goes into a CSR.
- **E** is wrong because browsers do not trust self-signed certificates unless someone installs them as trusted.

</details>

Want more? The [free timed Security+ (SY0-701) practice test on PrepClubs](https://prepclubs.com/free-practice-tests/security-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=security-plus) has 25 questions across all five domains, with your score split by domain.

## Score yourself

| Item | 1 | 2 | 3 | 4 |
|---|---|---|---|---|
| Answer | B | C | D | B, D |
| Objective | 1.1 | 1.4 | 1.4 | 1.4 |

- **4:** your foundations are solid. Move on to the heavier domains, especially [Domain 4](4-security-operations.md).
- **3:** check which objective your misses share. If they are crypto items, redraw the symmetric vs asymmetric table and the "which key does what" rule in [Key concepts](#14-cryptographic-solutions) from memory.
- **2 or fewer:** reread [1.1 Security controls](#11-security-controls) and [1.4 Cryptographic solutions](#14-cryptographic-solutions), then redo the items a day later without looking at the explanations.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. Open a website in your browser, view its certificate, and find the issuer, the validity dates, the subject alternative names and whether it chains to a root you trust. Then explain each field in one sentence.
3. Take a timed run with the [free Security+ (SY0-701) practice test on PrepClubs](https://prepclubs.com/free-practice-tests/security-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=security-plus) to practice pacing across the whole exam.

---

<!-- nav:bottom -->
← Previous: [5-minute diagnostic](../diagnostic.md) | Next: [Domain 2: Threats, Vulnerabilities, and Mitigations](2-threats-vulnerabilities-and-mitigations.md) → | [Back to contents](../../README.md#contents)
<!-- /nav:bottom -->
