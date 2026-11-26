<!-- nav:top -->
[Contents](../../README.md#contents) · Previous: [Domain 1: General Security Concepts](1-general-security-concepts.md) · Next: [Domain 3: Security Architecture](3-security-architecture.md)
<!-- /nav:top -->

# Domain 2: Threats, Vulnerabilities, and Mitigations

**Weight:** 22% of the exam (CompTIA's figure). By our estimate that is roughly 19 of up to 90 questions. **Objectives:** 2.1 to 2.5.

This domain is about the attacker's side of the table: who attacks, how they get in, which weaknesses they use, what an attack looks like in logs and alerts, and what you do to shut the door. Most items are scenarios, and the marks go to people who can read the clue words. "Impossible travel", "the file name in the URL has `../`", "the attack uses DNS servers that answer with large responses": each one points to one answer.

## What this domain measures

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 2.1 | Compare threat actors and their motives | Nation-state, unskilled attacker, hacktivist, insider, organized crime, shadow IT; internal or external, funding, sophistication; motives from data exfiltration to war |
| 2.2 | Explain threat vectors and attack surfaces | Message, image and file based vectors, voice, removable media, vulnerable and unsupported software, unsecure networks, open ports, default credentials, supply chain, social engineering |
| 2.3 | Explain types of vulnerabilities | Memory injection, buffer overflow, race conditions, malicious updates, OS and web flaws (SQLi, XSS), hardware, virtualization, cloud, supply chain, crypto, misconfiguration, mobile, zero-day |
| 2.4 | Analyze indicators of malicious activity in a scenario | Malware types, physical attacks, network attacks, application attacks, crypto attacks, password attacks, and indicators such as lockouts, impossible travel and missing logs |
| 2.5 | Explain mitigation techniques | Segmentation, ACLs and permissions, allow lists, isolation, patching, encryption, monitoring, least privilege, configuration enforcement, decommissioning, hardening |

## Key concepts explained

### 2.1 Threat actors and motivations

| Actor | Typical resources | Typical motive | Clue words in a stem |
|---|---|---|---|
| Nation-state | Very high funding and skill, patient | Espionage, disruption, war | Long-term, stealthy, advanced persistent threat, critical infrastructure |
| Unskilled attacker | Low, uses ready-made tools | Curiosity, notoriety, disruption | Downloaded exploit kit, noisy, obvious |
| Hacktivist | Low to medium | Philosophical or political beliefs | Defaced website, leaked documents to make a point |
| Insider threat | Has legitimate access | Revenge, financial gain | Employee, contractor, recently passed over, already authorized |
| Organized crime | High, run like a business | Financial gain | Ransomware, extortion, card theft |
| Shadow IT | Internal staff, not malicious by intent | Convenience | Unapproved cloud app, personal file-sharing service |

Attributes to compare: **internal vs external** (inside the organization or not), **resources and funding**, and **level of sophistication**. Motivations on the list: data exfiltration, espionage, service disruption, blackmail, financial gain, philosophical or political beliefs, ethical (for example a researcher who discloses a flaw), revenge, disruption or chaos, and war.

### 2.2 Threat vectors and attack surfaces

A **vector** is the path an attack uses. The **attack surface** is the total of all the paths that exist.

| Vector | Examples |
|---|---|
| Message-based | Malicious email, SMS, instant messages |
| Image-based | Malicious code or links hidden in image files |
| File-based | Weaponized documents, macros, archives |
| Voice call | Phone scams, vishing |
| Removable device | Infected USB drives left in a car park |
| Vulnerable software | Unpatched apps. Client-based scanning needs an installed agent; agentless scanning works over the network without one |
| Unsupported systems and applications | End-of-life OS that no longer gets patches |
| Unsecure networks | Open Wi-Fi, unsecured wired ports, Bluetooth left discoverable |
| Open service ports | Services listening that nobody needs |
| Default credentials | Admin/admin on a router or camera |
| Supply chain | Managed service providers, vendors, suppliers whose access or products are compromised |

**Social engineering terms.**

| Term | What happens |
|---|---|
| Phishing | Fraudulent email to steal credentials or deliver malware |
| Vishing | Voice phishing by phone |
| Smishing | Phishing by SMS |
| Misinformation and disinformation | False information; disinformation is spread on purpose |
| Impersonation | Pretending to be someone trusted, such as IT support |
| Business email compromise | Using a real or spoofed executive or supplier mailbox to request payments or data |
| Pretexting | Inventing a believable story to get information ("I'm from the auditor's office...") |
| Watering hole | Compromising a website the target group already visits |
| Brand impersonation | Fake emails or sites copying a known brand |
| Typosquatting | Registering look-alike domains such as `examp1e.com` |

### 2.3 Vulnerabilities

| Type | What goes wrong | Typical fix |
|---|---|---|
| Memory injection | Attacker places code into a running process's memory | Endpoint protection, patching, memory protections |
| Buffer overflow | Input longer than the buffer overwrites nearby memory, sometimes letting code run | Input validation, safe languages and libraries, patching |
| Race condition (TOC/TOU) | The system checks something, then uses it later; the attacker changes it in between (time-of-check to time-of-use) | Atomic operations, locking |
| Malicious update | A trusted update channel delivers malware | Code signing, vendor verification, staged rollout |
| SQL injection | User input changes a database query | Parameterized queries, input validation |
| Cross-site scripting (XSS) | Attacker's script runs in another user's browser via the site | Output encoding, input validation, content security policy |
| Hardware: firmware | Flawed or malicious firmware | Firmware updates from the vendor, secure boot |
| Hardware: end-of-life, legacy | No more fixes from the vendor | Replace, isolate, compensating controls |
| VM escape | Code in a guest VM breaks out to the hypervisor or other guests | Patch hypervisors, limit guest privileges |
| Resource reuse | Memory or storage from one tenant or VM is handed to another without being cleared | Proper clearing by the platform |
| Cloud-specific | Misconfigured storage, weak identity settings, exposed keys | Configuration checks, least privilege |
| Supply chain | A service, hardware or software provider is compromised | Vendor assessment, verification of components |
| Cryptographic | Weak algorithms, poor key handling | Current algorithms, key management |
| Misconfiguration | Default settings, open shares, debug mode in production | Baselines and configuration enforcement |
| Mobile: side loading, jailbreaking | Apps from outside the official store; removing OS restrictions | MDM policies that block both |
| Zero-day | A flaw with no vendor fix yet | Defense in depth, monitoring, isolation |

### 2.4 Indicators of malicious activity

**Malware.**

| Malware | Key behavior |
|---|---|
| Ransomware | Encrypts data and demands payment |
| Trojan | Looks like useful software, carries a hidden payload |
| Worm | Spreads by itself across the network, no user action needed |
| Virus | Attaches to files or programs, needs a host and usually user action to spread |
| Spyware | Watches activity and sends it out |
| Bloatware | Unwanted preinstalled software that adds attack surface |
| Keylogger | Records keystrokes |
| Logic bomb | Runs when a condition is met, such as a date or an employee's account being disabled |
| Rootkit | Hides deep in the OS (or firmware) to keep privileged, hidden access |

**Physical attacks:** brute force against doors or locks, RFID cloning (copying badge signals), and environmental attacks (for example on power or cooling).

**Network attacks.**

- **DDoS:** many sources flood a target. **Reflected:** the attacker spoofs the victim's address so third-party servers send their replies to the victim. **Amplified:** the reflected replies are much larger than the requests, for example small DNS queries that trigger large answers.
- **DNS attacks:** poisoning resolver caches, hijacking domains, or using DNS for amplification.
- **Wireless:** rogue access points, evil twins, deauthentication floods.
- **On-path:** the attacker sits between two parties and reads or changes traffic.
- **Credential replay:** captured credentials or tokens are sent again to log in.
- **Malicious code:** scripts or binaries delivered over the network.

**Application attacks.**

| Attack | Clue |
|---|---|
| Injection | Input such as `' OR 1=1 --` reaches a query or command |
| Buffer overflow | Very long input, crash, unexpected code running |
| Replay | A valid request captured and resent |
| Privilege escalation | A normal user gains admin rights |
| Forgery | A request is made on the user's behalf without their intent, as in cross-site request forgery |
| Directory traversal | `../` sequences in a path to read files outside the web root |

**Cryptographic attacks.** A **downgrade** attack forces a weaker protocol or cipher. A **collision** is two inputs producing the same hash. A **birthday** attack uses probability to find collisions far faster than brute force would suggest.

**Password attacks.** **Spraying** tries a few common passwords against many accounts, to stay under lockout limits. **Brute force** tries many passwords against one account (online) or a stolen hash (offline).

**Indicators to recognize.**

| Indicator | What it suggests |
|---|---|
| Account lockout | Brute force against that account |
| Concurrent session usage | The same account active from two places at once |
| Blocked content | Security tools are stopping something; check what and why |
| Impossible travel | Logins from places too far apart for the time between them |
| Resource consumption | Unusual CPU, memory, disk or bandwidth use: crypto-mining, DDoS, exfiltration |
| Resource inaccessibility | Files or services suddenly unavailable: ransomware, DoS |
| Out-of-cycle logging | Log entries at times when nothing should be running |
| Published or documented | The attack or leak is already public, for example on a leak site |
| Missing logs | Gaps in logs: an attacker covering their tracks |

### 2.5 Mitigation techniques

| Technique | What it does |
|---|---|
| Segmentation | Splits the network so a breach in one part cannot reach everything |
| Access control (ACLs, permissions) | Allows or denies specific traffic or actions |
| Application allow list | Only approved software can run |
| Isolation | Moves a system or process into its own space, such as quarantining an infected host |
| Patching | Removes known vulnerabilities |
| Encryption | Protects data if it is stolen |
| Monitoring | Finds attacks that got past other controls |
| Least privilege | Gives only the access each person or process needs |
| Configuration enforcement | Keeps systems at an approved baseline and corrects drift |
| Decommissioning | Retires systems properly, including wiping data and removing accounts and DNS records |
| Hardening | Encryption, endpoint protection, host-based firewall, HIPS, disabling unused ports and protocols, changing default passwords, removing unnecessary software |

## How questions look

Expect short scenarios that end with "Which threat actor is MOST likely responsible?", "Which attack is this?", or "Which mitigation would BEST prevent this?". Some include a log extract or a web request in a code block; your job is to spot the one string that names the attack (`../`, `' OR '1'='1`, many failed logins across many accounts, a login from two continents within an hour). Choose-two items often pair a mitigation with a detection. A performance-based item might ask you to match attacks to descriptions, or pick mitigations for several hosts.

## A method for these questions

1. Find the clue words first: who, how they got in, what changed, what the logs show.
2. Name the category before the specific answer: actor, vector, vulnerability, attack or mitigation.
3. For attacks, look for the single distinguishing behavior (self-spreading means worm, triggered by a date means logic bomb).
4. For actors, weigh resources and motive together: stealthy and patient with huge resources is a nation-state; money is organized crime.
5. For mitigations, match the fix to the root cause, not the symptom: SQL injection is fixed in code with parameterized queries, not with a bigger firewall.
6. When two answers both help, pick the one that addresses the stated weakness most directly.

## Traps that cost points

- **Worm vs virus.** If it spreads with no user action, it is a worm.
- **Spraying vs brute force.** Many accounts and few passwords is spraying. One account and many passwords is brute force.
- **Reflected vs amplified.** Reflection is about bouncing replies to the victim. Amplification is about the replies being bigger than the requests. A DNS attack can be both.
- **Insider means authorized.** If the person already had access, it is an insider threat even if they are a contractor.
- **Shadow IT is not a hacker.** It is staff using unapproved technology. The fix is policy, discovery and approved alternatives.
- **Fixing the symptom.** A WAF can help against SQL injection, but "BEST" usually points to fixing the code with parameterized queries and input validation.
- **Zero-day means no patch.** Do not pick "apply the vendor patch" when the stem says no patch exists.
- **Missing logs are an indicator.** A gap in logging is evidence, not just a technical fault.

## Timing

Most items here are quick once you spot the clue. Aim for under a minute each. Log-based items can take longer: read the question first, then scan the log for the one line that matters instead of reading every line.

## Practice items

These 4 items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider.

### Item 1

A water utility discovers that attackers had quiet access to its control network for 14 months. The attackers used custom tools, avoided triggering alerts and took no money. Which threat actor is MOST likely responsible?

A. Unskilled attacker

B. Hacktivist

C. Nation-state

D. Organized crime

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Long, stealthy access to critical infrastructure using custom tools, with no financial motive, fits a well-funded nation-state pursuing espionage or preparing for disruption. (Objective 2.1)

- **A** is wrong because unskilled attackers use off-the-shelf tools and are rarely patient or quiet for over a year.
- **B** is wrong because hacktivists usually want publicity for a cause, such as a defaced site or leaked files.
- **D** is wrong because organized crime is driven by money, and nothing was monetized here.

</details>


### Item 2

The authentication logs show the following pattern over one hour:

```
2,400 accounts  x  1 attempt each  password: Winter2026!
2,400 accounts  x  1 attempt each  password: Welcome1
No account exceeded 2 failed attempts
```

Which attack is this?

A. Brute force against a single account

B. Password spraying

C. Credential replay

D. Birthday attack

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A few common passwords tried once each across many accounts, staying below lockout thresholds, is password spraying. (Objective 2.4)

- **A** is wrong because brute force hammers one account with many passwords and would trigger lockouts.
- **C** is wrong because replay resends captured valid credentials or tokens; these attempts are guesses.
- **D** is wrong because a birthday attack targets hash collisions, not logins.

</details>


### Item 3

A developer's code builds this query from a search box: `"SELECT * FROM products WHERE name = '" + input + "'"`. Which change BEST removes the vulnerability?

A. Put a web application firewall in front of the site

B. Encrypt the database at rest

C. Use parameterized queries

D. Run the database server on a separate VLAN

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Concatenating user input into SQL creates SQL injection. Parameterized queries keep input as data so it can never change the query's structure. (Objective 2.3)

- **A** is wrong because a WAF can block some attacks but leaves the flawed code in place, so it is not the best fix.
- **B** is wrong because encryption at rest does not stop a query that the application itself runs.
- **D** is wrong because the attack comes through the application, which can still reach the database on any VLAN.

</details>


### Item 4

A legacy medical device runs an operating system that the vendor no longer supports and cannot be replaced for a year. Choose two mitigations that BEST reduce its risk.

A. Place the device on an isolated network segment

B. Install the latest vendor patch

C. Restrict traffic to it with ACLs that allow only the systems it must talk to

D. Raise the account lockout threshold on the device

E. Allow the device to reach the internet so it can download updates

<details>
<summary>Answer and explanation</summary>

**Answer: A and C.** An unsupported system cannot be fixed, so you limit who can reach it. Segmentation and tight ACLs shrink its attack surface. (Objective 2.5)

- **B** is wrong because an end-of-life system gets no new patches.
- **D** is wrong because a higher lockout threshold makes guessing easier, not harder.
- **E** is wrong because internet access increases exposure and no updates exist to download.

</details>

Want more? The [free timed Security+ (SY0-701) practice test on PrepClubs](https://prepclubs.com/free-practice-tests/security-plus?utm_source=github&utm_medium=referral&utm_campaign=4s76wr&utm_content=security-plus) has 25 questions across all five domains, with your score split by domain.

## Score yourself

| Item | 1 | 2 | 3 | 4 |
|---|---|---|---|---|
| Answer | C | B | C | A, C |
| Objective | 2.1 | 2.4 | 2.3 | 2.5 |

- **4:** you read attacks well. Keep the indicator table fresh and move on.
- **3:** look at whether your misses were actors, attacks or mitigations, then reread that part of [Key concepts](#key-concepts-explained).
- **2 or fewer:** make flash cards from the malware, application attack and indicator tables in [2.4 Indicators of malicious activity](#24-indicators-of-malicious-activity), and redo the items in two days.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. Open the security or sign-in log on a system you are allowed to inspect (for example Windows Event Viewer, Security log) and find a failed logon event. Note which fields would reveal spraying, brute force or impossible travel.
3. Take a timed run with the [free Security+ (SY0-701) practice test on PrepClubs](https://prepclubs.com/free-practice-tests/security-plus?utm_source=github&utm_medium=referral&utm_campaign=4s76wr&utm_content=security-plus) to practice pacing across the whole exam.

---

<!-- nav:bottom -->
← Previous: [Domain 1: General Security Concepts](1-general-security-concepts.md) | Next: [Domain 3: Security Architecture](3-security-architecture.md) → | [Back to contents](../../README.md#contents)
<!-- /nav:bottom -->
