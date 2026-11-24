<!-- nav:top -->[Contents](../../README.md#contents) · Previous: [Domain 3: Security Architecture](3-security-architecture.md) · Next: [Domain 5: Security Program Management and Oversight](5-security-program-management-and-oversight.md)<!-- /nav:top -->

# Domain 4: Security Operations

**Weight:** 28% of the exam (CompTIA's figure), the heaviest domain. By our estimate that is roughly 25 of up to 90 questions. **Objectives:** 4.1 to 4.9.

This is the day job of a security analyst or administrator: hardening systems, tracking assets, finding and fixing vulnerabilities, watching alerts, tuning firewalls and filters, running identity and access, automating routine work, handling incidents and digging through logs. More than a quarter of the exam lives here, and many performance-based questions do too. If you only have time to master one domain, make it this one.

## What this domain measures

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 4.1 | Apply security techniques to computing resources | Secure baselines, hardening targets, wireless site surveys and heat maps, MDM and BYOD, COPE, CYOD, WPA3, RADIUS, application security, sandboxing, monitoring |
| 4.2 | Explain asset management's security implications | Procurement, ownership, classification, inventory, enumeration, sanitization, destruction, certification, data retention |
| 4.3 | Explain vulnerability management | Scans, static and dynamic analysis, package monitoring, threat feeds, pen testing, bug bounties, false positives and negatives, CVSS, CVE, exposure factor, response options, validation, reporting |
| 4.4 | Explain alerting and monitoring | Log aggregation, alerting, quarantine, alert tuning, SCAP, benchmarks, agents, SIEM, antivirus, DLP, SNMP traps, NetFlow, vulnerability scanners |
| 4.5 | Modify enterprise capabilities to enhance security | Firewall rules, screened subnets, IDS and IPS signatures and trends, web filtering, Group Policy, SELinux, secure protocols, DNS filtering, SPF, DKIM, DMARC, FIM, DLP, NAC, EDR and XDR, user behavior analytics |
| 4.6 | Implement identity and access management | Provisioning, identity proofing, federation, SSO with LDAP, OAuth and SAML, access control models, MFA factors, password practices, passwordless, privileged access management |
| 4.7 | Explain automation and orchestration | Use cases, benefits, and costs such as complexity, single points of failure and technical debt |
| 4.8 | Explain incident response | The response process, training, testing, root cause analysis, threat hunting, digital forensics |
| 4.9 | Use data sources in an investigation | Firewall, application, endpoint, OS, IDS and IPS, network logs, metadata, scans, reports, dashboards, packet captures |

## Key concepts explained

### 4.1 Securing computing resources

**Secure baselines** are the approved, hardened configuration for a type of system. You **establish** them (from vendor guidance or benchmarks), **deploy** them (images, Group Policy, configuration tools) and **maintain** them (review and update as threats and software change).

**Hardening targets and what hardening means for each.**

| Target | Typical hardening |
|---|---|
| Mobile devices | MDM enrollment, screen lock, encryption, app restrictions, remote wipe |
| Workstations | Patching, endpoint protection, host firewall, remove admin rights, disable unused services |
| Switches and routers | Change default credentials, disable unused ports, use SSH not Telnet, restrict management access |
| Cloud infrastructure | Least-privilege IAM, no public storage by default, logging on, secure templates |
| Servers | Minimal installed roles, patching, host firewall, logging |
| ICS and SCADA, embedded, RTOS, IoT | Segment them, change defaults, update firmware where possible, monitor at the boundary |

**Wireless installation.** A **site survey** checks the space, interference and where access points should go. A **heat map** shows signal strength across the floor plan so you can find dead spots and signal leaking outside the building.

**Mobile deployment models.**

| Model | Who owns the device | Who chooses it |
|---|---|---|
| BYOD (bring your own device) | Employee | Employee |
| COPE (corporate-owned, personally enabled) | Company | Company, with personal use allowed |
| CYOD (choose your own device) | Company | Employee picks from an approved list |

Connection methods to secure: cellular, Wi-Fi and Bluetooth.

**Wireless security settings.** WPA3 is the current Wi-Fi security standard. WPA3-Personal uses SAE (Simultaneous Authentication of Equals) in place of the older pre-shared key handshake, which resists offline password guessing. Enterprise Wi-Fi uses 802.1X with a **RADIUS** server for AAA, so each user logs in with their own credentials.

**Application security.**

| Technique | What it does |
|---|---|
| Input validation | Rejects input that is the wrong type, length or format |
| Secure cookies | Cookies flagged Secure (sent only over HTTPS) and HttpOnly (not readable by scripts) |
| Static code analysis | Reviews source code without running it |
| Code signing | Proves who published the code and that it was not changed |
| Sandboxing | Runs code in an isolated environment so it cannot harm the system |

### 4.2 Asset management

You cannot protect what you do not know you have.

| Stage | Security point |
|---|---|
| Acquisition and procurement | Buy from approved vendors, check security requirements before purchase |
| Assignment and accounting | Every asset has an owner and a classification |
| Monitoring and asset tracking | Keep an **inventory**, and use **enumeration** (discovery scans) to find devices that are not in it |
| Disposal and decommissioning | **Sanitization** (wipe data so it cannot be recovered), **destruction** (shred, degauss, incinerate), **certification** (a record proving the data was destroyed), and **data retention** (keep what laws and policy require, for as long as required, then dispose of it) |

### 4.3 Vulnerability management

**Finding vulnerabilities.**

| Method | What it is |
|---|---|
| Vulnerability scan | Automated check for known flaws; credentialed scans log in and see more |
| Static analysis | Code review without running it (SAST) |
| Dynamic analysis | Testing the running application (DAST), for example fuzzing |
| Package monitoring | Watching third-party libraries and dependencies for known flaws |
| Threat feeds | OSINT, commercial or third-party feeds, information-sharing organizations, dark web monitoring |
| Penetration testing | People actively try to exploit weaknesses |
| Responsible disclosure and bug bounty | Outsiders report flaws through an agreed channel, sometimes for a reward |
| System or process audit | Reviewing how systems and processes are actually run |

**Analysis.**

- **False positive:** the scanner reports a flaw that is not there. Wastes time.
- **False negative:** the scanner misses a real flaw. More dangerous, because nobody looks.
- **CVE** is the identifier for a specific publicly known vulnerability, such as CVE-2026-12345.
- **CVSS** gives a severity score from 0.0 to 10.0. It describes the vulnerability, not your environment.
- Then adjust for **exposure factor** (how much of the asset would be lost), **environmental variables** (is the system internet-facing, does it hold sensitive data), **industry or organizational impact**, and **risk tolerance**.

**Responding.** Patching is the usual fix. Other options: buy **insurance** (transfer some financial risk), **segmentation** (limit who can reach the flaw), **compensating controls**, or a formal **exception or exemption** when the risk is accepted for a period with sign-off.

**Validating the fix.** **Rescan** to confirm the finding is gone, **audit** the change and **verify** it worked. Then **report** to the people who own the risk.

### 4.4 Alerting and monitoring

**What to monitor:** systems, applications and infrastructure.

**Activities.** Log aggregation (collect logs in one place), alerting, scanning, reporting, archiving (keep logs as long as required), and alert response: **quarantine** a suspicious host or file, and **alert tuning** to cut false positives without hiding real attacks.

| Tool | Purpose |
|---|---|
| SIEM | Collects and correlates logs from many sources, raises alerts, supports investigation |
| SCAP | A set of standards that lets tools check configurations and vulnerabilities in a common format |
| Benchmarks | Published secure configuration guides, such as CIS Benchmarks |
| Agents vs agentless | Agents run on each host and see more; agentless tools work over the network with nothing installed |
| Antivirus | Detects and removes known malware |
| DLP | Detects and blocks sensitive data leaving where it should not |
| SNMP traps | Devices push alerts to a management station when something happens |
| NetFlow | Records who talked to whom, when, and how much, without full packet contents |
| Vulnerability scanners | Find known weaknesses on hosts and applications |

### 4.5 Enhancing enterprise capabilities

**Firewalls.** Rules are processed top to bottom and the first match wins, usually with an implicit deny at the end. Use access lists and specific ports and protocols, and put public-facing servers in a **screened subnet** (DMZ).

A rule set read top to bottom:

```
1  allow  tcp  any          -> 203.0.113.10  443
2  deny   tcp  any          -> 203.0.113.10  any
3  allow  tcp  10.0.5.0/24  -> 10.0.9.20     22
4  deny   ip   any          -> any           any
```

Rule 1 lets anyone reach the web server on HTTPS. Rule 2 blocks every other TCP port to it. Rule 3 lets only the admin subnet SSH to one server. Rule 4 denies everything else. If you put rule 4 first, nothing would work.

**IDS and IPS.** **Signature-based** detection matches known attack patterns; it is accurate for known attacks and blind to new ones. **Trend** or anomaly-based detection learns normal behavior and flags deviations; it can catch new attacks but raises more false positives.

**Web filtering.** Agent-based (software on each device, works off-network) or a centralized proxy. Methods: URL scanning, content categorization (block "gambling"), block rules and reputation.

**OS security.** **Group Policy** pushes settings to Windows machines in a domain. **SELinux** enforces mandatory access control on Linux.

**Secure protocols.** Choose the secure protocol, the right port and a secure transport. Common swaps:

| Insecure | Secure replacement | Secure port |
|---|---|---|
| Telnet (23) | SSH | 22 |
| FTP (20, 21) | SFTP (runs over SSH) or FTPS | 22 for SFTP; 990 for implicit FTPS |
| HTTP (80) | HTTPS | 443 |
| LDAP (389) | LDAPS | 636 |
| SNMPv1 and v2c | SNMPv3 | 161, traps 162 |
| SMTP without encryption (25) | SMTP with TLS submission | 587 |
| POP3 (110), IMAP (143) | POP3S, IMAPS | 995, 993 |

**DNS filtering** blocks lookups for known bad domains, which stops many malware callbacks and phishing sites.

**Email security.**

| Control | What it does |
|---|---|
| SPF | A DNS record listing which servers may send mail for a domain |
| DKIM | A digital signature on outgoing mail, checked with a public key in DNS |
| DMARC | Tells receivers what to do when SPF or DKIM checks fail (none, quarantine, reject) and where to send reports |
| Gateway | Filters inbound and outbound mail for spam, malware and phishing |

**Other capabilities.** **File integrity monitoring** alerts when important files change. **DLP** blocks sensitive data leaving. **NAC** checks devices (identity, patch level, antivirus) before letting them on the network. **EDR** watches endpoints for suspicious behavior and can respond; **XDR** extends that across endpoints, network, cloud and email. **User behavior analytics** flags users acting unlike their normal pattern.

### 4.6 Identity and access management

**Account lifecycle.** **Provisioning** creates accounts with the right access; **de-provisioning** removes access promptly when people leave or change roles. **Identity proofing** checks that people are who they claim before an account is issued.

**Federation and SSO.**

| Technology | Role |
|---|---|
| Federation | Trust between organizations so one's identities work at the other |
| SSO | Log in once, reach many applications |
| LDAP | Directory protocol for looking up and authenticating users |
| SAML | XML-based standard to pass authentication and authorization assertions between an identity provider and a service, common for web SSO |
| OAuth | Authorization framework that lets an app access resources on a user's behalf without the user's password, using tokens |

**Interoperability** means systems can exchange identity information. **Attestation** is a formal confirmation, for example a manager reviewing and confirming that their team's access is still correct, or a device proving its integrity.

**Access control models.**

| Model | Who decides | Example |
|---|---|---|
| Mandatory (MAC) | The system, from labels and clearances | Classified government systems |
| Discretionary (DAC) | The owner of the resource | A user shares their own folder |
| Role-based (RBAC) | Permissions follow job roles | All "Payroll Clerk" accounts get payroll access |
| Rule-based | System-wide rules | No logins after 20:00 |
| Attribute-based (ABAC) | Attributes of user, resource and context | Managers in the EU can view EU records from a managed device |

Also: time-of-day restrictions and least privilege.

**MFA.** Factors: something you know (password, PIN), something you have (token, phone, security key), something you are (biometrics), somewhere you are (location). MFA means factors from **different** categories. A password plus a PIN is still one factor type.

**Passwords.** Length matters most; complexity rules, avoiding reuse, and sensible expiration and minimum age (to stop users cycling straight back to an old password) are listed on the objectives. Use password managers. **Passwordless** methods, such as security keys and biometrics on a trusted device, remove the password entirely.

**Privileged access management tools.** **Just-in-time permissions** grant admin rights only when needed and remove them after. **Password vaulting** stores privileged passwords and checks them out under control. **Ephemeral credentials** are short-lived and expire automatically.

### 4.7 Automation and orchestration

Use cases: user and resource provisioning, guard rails, security groups, ticket creation, escalation, enabling and disabling services and access, continuous integration and testing, and integrations through APIs.

Benefits: efficiency, enforcing baselines, standard configurations, secure scaling, employee retention (less boring repetitive work), faster reaction time, and acting as a workforce multiplier.

Costs and risks: complexity, cost, a single point of failure if the automation breaks, technical debt, and ongoing supportability.

### 4.8 Incident response

The process, in order:

1. **Preparation:** plans, tools, training and contacts ready before anything happens.
2. **Detection:** noticing that something is wrong.
3. **Analysis:** confirming it is an incident, its scope and severity.
4. **Containment:** stopping it spreading, for example isolating hosts.
5. **Eradication:** removing the cause, such as malware and attacker accounts.
6. **Recovery:** restoring systems to normal operation and monitoring them.
7. **Lessons learned:** reviewing what happened and improving.

**Training** and **testing** (tabletop exercises and simulations) keep the team ready. **Root cause analysis** finds why it happened. **Threat hunting** searches proactively for attackers who have not triggered alerts.

**Digital forensics.**

| Term | Meaning |
|---|---|
| Legal hold | An instruction to preserve relevant data because of litigation; normal deletion stops |
| Chain of custody | A record of everyone who handled evidence, when and why |
| Acquisition | Collecting evidence, ideally most volatile first (memory before disk) |
| Reporting | Documenting findings clearly |
| Preservation | Keeping evidence unchanged, for example working from a verified copy with matching hashes |
| E-discovery | Finding and producing electronic information for legal proceedings |

### 4.9 Data sources for investigations

| Source | What it tells you |
|---|---|
| Firewall logs | Allowed and blocked connections by source, destination and port |
| Application logs | What users and processes did inside an app |
| Endpoint logs | Activity on a host, including EDR detections |
| OS-specific security logs | Logons, privilege use, policy changes (for example the Windows Security log) |
| IPS and IDS logs | Matched signatures and blocked attacks |
| Network logs | Switch, router, DHCP, DNS and VPN records |
| Metadata | Data about data: email headers, file timestamps, photo location data |
| Vulnerability scans | Which weaknesses existed on a host |
| Automated reports and dashboards | Summaries and trends |
| Packet captures | The full contents of traffic, the most detail available |

## How questions look

This domain has the widest range of formats. Expect "Given a scenario" stems about a new mobile policy, a vulnerability report to prioritize, a SIEM alert, an email that passed or failed SPF, an incident in progress ("What should the analyst do FIRST?"), or a forensic task ("What must the investigator document?"). Exhibits include firewall rule sets, log lines and scan results. Performance-based items commonly ask you to order incident response steps, configure firewall rules, pick wireless settings, or match tools to tasks.

## A method for these questions

1. Decide which objective you are in: hardening, assets, vulnerabilities, monitoring, controls, identity, automation, incident response or investigation.
2. For "FIRST" or "NEXT" items, place the scenario on the relevant sequence (incident response steps, vulnerability lifecycle) and pick the step that comes next, not the one that feels most urgent.
3. For tool items, ask what data the tool sees: flows (NetFlow), full packets (packet capture), correlated logs (SIEM), endpoint behavior (EDR).
4. For identity items, separate authentication (who you are) from authorization (what you can do), and check factor categories for MFA.
5. For firewall items, read rules top to bottom and stop at the first match.
6. For vulnerability items, adjust severity for the environment before choosing what to fix first.

## Traps that cost points

- **Skipping containment.** During an active incident, containment comes before eradication. Wiping a machine before isolating the rest of the network lets the attacker keep spreading.
- **Recovery before eradication.** Restoring systems while the cause is still present invites reinfection.
- **Two of the same factor.** Password plus security question is not MFA. Both are something you know.
- **OAuth for authentication.** OAuth is about authorization (delegated access). SAML commonly carries authentication for web SSO.
- **CVSS alone sets priority.** A 9.8 on an isolated lab box may matter less than a 7.5 on an internet-facing payment server.
- **False negative feels safe.** It is the worse error, because the flaw is real and nobody knows.
- **SPF, DKIM, DMARC mixed up.** SPF lists allowed servers, DKIM signs the message, DMARC sets the policy for failures.
- **Shutting down to preserve evidence.** Pulling the power destroys memory contents. Acquire volatile data first if forensics matters.
- **Rule order ignored.** A broad deny above a specific allow blocks the allowed traffic.

## Timing

With roughly a quarter of the exam here, pace matters. Keep multiple-choice items to about a minute. Leave firewall and ordering PBQs for a second pass if they look long, but do come back: they cover a lot of ground in this domain.

## Practice items

These 14 items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider.

### Item 1

A company lets staff pick a phone from a list of three approved models. The company buys and owns the phones and manages them with MDM. Which deployment model is this?

A. BYOD

B. CYOD

C. COPE

D. VDI

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Choose your own device means the employee chooses from an approved list of company-owned devices. (Objective 4.1)

- **A** is wrong because in BYOD the employee owns the device.
- **C** is wrong because in COPE the company chooses and issues the device; the defining feature here is that the employee picks from a list.
- **D** is wrong because VDI is a way of delivering desktops, not a device ownership model.

</details>

### Item 2

An IT team is retiring 40 laptops that held customer data. The auditors want proof that the data cannot be recovered. What should the team obtain?

A. A purchase order from the recycling company

B. An updated asset inventory showing the laptops as missing

C. A certificate of sanitization or destruction

D. A data retention policy

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Certification documents that the media was sanitized or destroyed, giving auditors evidence. (Objective 4.2)

- **A** is wrong because a purchase order proves a transaction, not data destruction.
- **B** is wrong because marking devices as missing is the opposite of controlled disposal.
- **D** is wrong because a retention policy says how long to keep data; it is not proof of destruction.

</details>

### Item 3

A scan reports these findings. Which should the team remediate FIRST?

```
Host            Exposure          Data held            CVSS
lab-test-07     internal lab      none                 9.8
pay-web-01      internet-facing   cardholder data      8.1
hr-file-02      internal          employee records     6.5
print-srv-01    internal          none                 7.2
```

A. lab-test-07, because it has the highest CVSS score

B. hr-file-02, because it holds personal data

C. print-srv-01, because printers are often ignored

D. pay-web-01, because it is internet-facing and holds cardholder data

<details>
<summary>Answer and explanation</summary>

**Answer: D.** CVSS describes the flaw, but priority also depends on exposure and impact. A high-severity flaw on an internet-facing server holding card data carries the greatest risk. (Objective 4.3)

- **A** is wrong because the lab host is internal and holds no data, so its real risk is lower despite the score.
- **B** is wrong because hr-file-02 is internal and has the lowest score.
- **C** is wrong because "often ignored" is not a reason to put it ahead of an exposed payment server.

</details>

### Item 4

A vulnerability scanner reports that a web server is missing a patch. An administrator checks and confirms the patch was installed last week and the version string is current. What is this?

A. False negative

B. False positive

C. True positive

D. Zero-day

<details>
<summary>Answer and explanation</summary>

**Answer: B.** The scanner reported a problem that does not exist, which is a false positive. (Objective 4.3)

- **A** is wrong because a false negative is a real problem the scanner missed.
- **C** is wrong because the finding turned out not to be real.
- **D** is wrong because a zero-day is an unpatched, unknown flaw, not a scanner mistake.

</details>

### Item 5

A security team wants to see which internal hosts talked to an external IP address last night and how much data each sent, without storing full packet contents. Which data source fits BEST?

A. NetFlow

B. SNMP traps

C. Packet captures

D. Antivirus logs

<details>
<summary>Answer and explanation</summary>

**Answer: A.** NetFlow records conversations: source, destination, ports, times and volume, without payloads. (Objectives 4.4 and 4.9)

- **B** is wrong because SNMP traps are device alerts, such as an interface going down.
- **C** is wrong because packet captures store full contents, which the team does not want and may not have for last night.
- **D** is wrong because antivirus logs record malware detections, not traffic volumes.

</details>

### Item 6

Read this firewall rule set. Rules are processed top to bottom, first match wins.

```
1  deny   tcp  any          -> 10.0.9.20  22
2  allow  tcp  10.0.5.0/24  -> 10.0.9.20  22
3  allow  tcp  any          -> 10.0.9.20  443
4  deny   ip   any          -> any        any
```

An admin at 10.0.5.14 cannot SSH to 10.0.9.20. What is the fix?

A. Delete rule 3

B. Change rule 4 to allow

C. Move rule 2 above rule 1

D. Add a rule allowing UDP 22

<details>
<summary>Answer and explanation</summary>

**Answer: C.** The admin's SSH traffic matches rule 1 (deny) before it reaches rule 2 (allow). Putting the specific allow above the broad deny fixes it. (Objective 4.5)

- **A** is wrong because rule 3 is for HTTPS and does not affect SSH.
- **B** is wrong because changing the final rule to allow would open everything.
- **D** is wrong because SSH uses TCP 22, and the problem is rule order.

</details>

### Item 7

A company receives reports that phishing emails appear to come from its own domain. It wants receiving mail servers to reject messages that fail authentication checks and to send it reports. Which record should it publish?

A. SPF only

B. A DMARC policy set to reject

C. A DKIM selector only

D. An MX record pointing to the gateway

<details>
<summary>Answer and explanation</summary>

**Answer: B.** DMARC tells receivers what to do when SPF or DKIM fails (here, reject) and where to send aggregate reports. (Objective 4.5)

- **A** is wrong because SPF lists allowed sending servers but does not by itself set a policy or request reports.
- **C** is wrong because DKIM signs mail but does not tell receivers what to do on failure.
- **D** is wrong because an MX record routes inbound mail to the domain; it does not authenticate outbound mail.

</details>

### Item 8

A user logs in with a password and then enters a code from an authenticator app on her phone. Which two factor categories are used?

A. Something you know and something you are

B. Something you have and somewhere you are

C. Something you know twice

D. Something you know and something you have

<details>
<summary>Answer and explanation</summary>

**Answer: D.** The password is something you know, and the app on her phone is something you have. (Objective 4.6)

- **A** is wrong because no biometric is used.
- **B** is wrong because location is not checked, and the password is a knowledge factor.
- **C** is wrong because the code comes from a device she possesses, which is a different category.

</details>

### Item 9

A partner portal lets employees of a supplier sign in with their own company's credentials. The supplier's identity provider sends signed XML assertions to the portal. Which technology is this?

A. LDAP

B. RADIUS

C. SAML

D. Kerberos within a single domain

<details>
<summary>Answer and explanation</summary>

**Answer: C.** SAML passes XML-based authentication assertions from an identity provider to a service provider, enabling federated SSO between organizations. (Objective 4.6)

- **A** is wrong because LDAP queries a directory; it does not exchange signed assertions between organizations.
- **B** is wrong because RADIUS provides AAA for network access such as VPN and Wi-Fi.
- **D** is wrong because the trust here crosses two organizations, which is federation, not a single internal domain.

</details>

### Item 10

Database administrators currently hold permanent admin rights. The CISO wants admin rights granted only for an approved task and removed automatically when it ends. Which approach fits?

A. Just-in-time permissions

B. Password expiration every 30 days

C. Role-based access control with a permanent admin role

D. Single sign-on

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Just-in-time permissions, a privileged access management feature, grant elevated rights for a limited time and remove them afterwards. (Objective 4.6)

- **B** is wrong because changing passwords does not remove standing admin rights.
- **C** is wrong because a permanent role is exactly what the CISO wants to get rid of.
- **D** is wrong because SSO makes logging in easier; it does not limit privilege duration.

</details>

### Item 11

An analyst confirms that ransomware is active on three file servers and spreading. What should the team do FIRST?

A. Restore the file servers from last night's backups

B. Isolate the affected servers from the network

C. Write the lessons-learned report

D. Reimage every workstation in the company

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Once an incident is confirmed and spreading, containment comes next: isolate the affected systems to stop further damage. (Objective 4.8)

- **A** is wrong because restoring before containment and eradication risks the restored data being encrypted again.
- **C** is wrong because lessons learned comes at the end.
- **D** is wrong because company-wide reimaging is drastic, slow, and still does not stop the active spread on the servers first.

</details>

### Item 12

A laptop is being collected as evidence in a fraud investigation. Choose two actions that support its use in court.

A. Record every person who handles the laptop, with times and reasons

B. Boot the laptop to check what is on it before imaging

C. Create a forensic image and compare hash values of the original and the copy

D. Delete temporary files to make analysis faster

E. Let the user keep the laptop until the investigation is complete

<details>
<summary>Answer and explanation</summary>

**Answer: A and C.** Chain of custody records who handled the evidence. Imaging and matching hashes show the copy is identical and the original was not changed. (Objective 4.8)

- **B** is wrong because booting the laptop changes data on it and can damage the evidence.
- **D** is wrong because deleting anything alters the evidence.
- **E** is wrong because leaving it with the user breaks the chain of custody.

</details>

### Item 13

A security team writes a script that creates a ticket and disables a user's VPN access automatically whenever the SIEM detects impossible travel for that user. Which is a benefit of this automation, and which is a risk? Choose the BEST pair.

A. Benefit: reaction time. Risk: the script becomes a single point of failure if it breaks.

B. Benefit: more complexity. Risk: faster response.

C. Benefit: removes the need for a SIEM. Risk: none.

D. Benefit: employee retention. Risk: reduced reaction time.

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Automation responds in seconds, which improves reaction time. If the script fails and nobody notices, every such alert goes unhandled: a single point of failure. (Objective 4.7)

- **B** is wrong because it swaps a cost (complexity) and a benefit (faster response).
- **C** is wrong because the script depends on the SIEM, and every automation carries some risk.
- **D** is wrong because automation improves reaction time; it does not reduce it.

</details>

### Item 14

An investigator wants to know whether a suspicious photo attached to an email was taken at the company's warehouse. Which data source is MOST likely to help?

A. Firewall logs

B. Vulnerability scans

C. The photo's metadata

D. IPS logs

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Image metadata can include the capture time, device and GPS coordinates. (Objective 4.9)

- **A** is wrong because firewall logs show connections, not where a photo was taken.
- **B** is wrong because scans show weaknesses on hosts.
- **D** is wrong because IPS logs record attacks matched on the network.

</details>

## Score yourself

| Item | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Answer | B | C | D | B | A | C | B | D | C | A | B | A, C | A | C |
| Objective | 4.1 | 4.2 | 4.3 | 4.3 | 4.4 | 4.5 | 4.5 | 4.6 | 4.6 | 4.6 | 4.8 | 4.8 | 4.7 | 4.9 |

- **13 to 14:** strong. Keep this domain warm with mixed practice, since it carries the most weight.
- **10 to 12:** list the objectives you missed. Firewall order, email authentication and incident steps are the usual weak spots; reread those parts of [Key concepts](#key-concepts-explained).
- **9 or fewer:** spend two study sessions here. Write the incident response steps and the MFA factor list from memory, then read [4.5 Enhancing enterprise capabilities](#45-enhancing-enterprise-capabilities) and [4.6 Identity and access management](#46-identity-and-access-management) again before redoing the items.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. Look up the SPF, DKIM and DMARC records for a domain you use (for example with `nslookup -type=txt example.com`, or the DMARC record at `_dmarc.example.com`) and explain what each one says.
3. Take a timed run with the [free Security+ (SY0-701) practice test on PrepClubs](https://prepclubs.com/free-practice-tests/security-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=security-plus) to practise pacing across the whole exam.

---

<!-- nav:bottom -->← Previous: [Domain 3: Security Architecture](3-security-architecture.md) | Next: [Domain 5: Security Program Management and Oversight](5-security-program-management-and-oversight.md) → | [Back to contents](../../README.md#contents)<!-- /nav:bottom -->
