<!-- nav:top -->[Contents](../../README.md#contents) · Previous: [Domain 2: Threats, Vulnerabilities, and Mitigations](2-threats-vulnerabilities-and-mitigations.md) · Next: [Domain 4: Security Operations](4-security-operations.md)<!-- /nav:top -->

# Domain 3: Security Architecture

**Weight:** 18% of the exam (CompTIA's figure). By our estimate that is roughly 16 of up to 90 questions. **Objectives:** 3.1 to 3.4.

Domain 3 asks you to think like the person drawing the network diagram. Where does the firewall go, and which kind? What happens to traffic if the IPS fails? Who patches the server in the cloud, you or the provider? Which backup site gets you running in an hour? The questions reward clear mental models more than memorized lists.

## What this domain measures

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 3.1 | Compare security implications of architecture models | Cloud and the responsibility matrix, hybrid, IaC, serverless, microservices, physical isolation and segmentation, SDN, on-premises, centralized vs decentralized, containers, virtualization, IoT, ICS and SCADA, RTOS, embedded, and the trade-offs (availability, cost, patching, power, compute) |
| 3.2 | Apply security principles to enterprise infrastructure | Device placement, security zones, failure modes, active vs passive, inline vs tap, jump servers, proxies, IDS and IPS, load balancers, sensors, port security and 802.1X, firewall types, VPN, TLS, IPsec, SD-WAN, SASE |
| 3.3 | Compare strategies to protect data | Data types, classifications, data states, sovereignty, geolocation, and methods: encryption, hashing, masking, tokenization, obfuscation, segmentation, permissions |
| 3.4 | Explain resilience and recovery | Load balancing vs clustering, hot, warm and cold sites, geographic dispersion, platform diversity, multi-cloud, continuity, capacity planning, testing, backups, replication, journaling, power |

## Key concepts explained

### 3.1 Architecture models

**The cloud responsibility matrix.** Security duties split between you and the provider, and the split depends on the service model.

| Who secures it | IaaS | PaaS | SaaS |
|---|---|---|---|
| Physical data center, hardware | Provider | Provider | Provider |
| Hypervisor and host OS | Provider | Provider | Provider |
| Guest OS, patching | Customer | Provider | Provider |
| Runtime and middleware | Customer | Provider | Provider |
| Application code | Customer | Customer | Provider |
| Data and user access | Customer | Customer | Customer |

The last row is always yours. Even in SaaS, you decide who has accounts and what data goes in.

| Model | What it is | Main security implication |
|---|---|---|
| Hybrid cloud | On-premises plus cloud, connected | Consistent identity and policy across both is hard |
| Third-party vendors | Others run parts of your stack | Their weakness becomes yours; assess and contract for security |
| Infrastructure as code | Servers and networks defined in files | Repeatable, reviewable builds; but a bad template spreads a flaw everywhere, and secrets must stay out of the code |
| Serverless | You deploy functions, the provider runs everything else | Less to patch; focus shifts to code, permissions and event inputs |
| Microservices | An app split into small independent services | More APIs to secure; one flaw is contained if services are isolated |
| Physical isolation (air gap) | No network connection at all | Strongest separation; updates and data move by hand, which brings its own risks |
| Logical segmentation | VLANs, subnets, firewall rules | Limits lateral movement without separate hardware |
| SDN | Network behavior controlled by software, separate control and data planes | Central control is powerful; protect the controller |
| On-premises | You own everything | Full control and full responsibility |
| Centralized vs decentralized | One point of control or many | Centralized is easier to manage but a single point of failure |
| Containerization | Apps share the host OS kernel, isolated from each other | Lightweight; a kernel flaw can affect all containers |
| Virtualization | Full guest OSs on a hypervisor | Stronger isolation than containers; VM escape and VM sprawl are risks |
| IoT | Small connected devices | Weak defaults, rare patches |
| ICS and SCADA | Systems that control physical processes, such as power and water | Availability and safety come first; often old and hard to patch |
| RTOS | OS that must respond within strict time limits | Little room for security software |
| Embedded systems | Computers built into devices | Long lifetimes, firmware rarely updated |

Considerations the exam lists for comparing designs: availability, resilience, cost, responsiveness, scalability, ease of deployment, risk transference, ease of recovery, patch availability, inability to patch, power and compute.

### 3.2 Securing enterprise infrastructure

**Placement and zones.** Put controls where traffic crosses between zones of different trust: internet to screened subnet (DMZ), DMZ to internal network, user network to server network. Keep the attack surface small: fewer exposed services, fewer open ports.

**Failure modes.**

| Mode | If the device fails | Choose it when |
|---|---|---|
| Fail-open | Traffic keeps flowing, uninspected | Availability matters more than security, for example a life-safety system |
| Fail-closed | Traffic stops | Security matters more than availability, for example a firewall protecting payment systems |

**Device attributes.**

| Attribute | Meaning |
|---|---|
| Active | Can take action, such as blocking (IPS) |
| Passive | Only observes and alerts (IDS) |
| Inline | Traffic passes through the device; it can block, and its failure affects traffic |
| Tap or monitor | Gets a copy of traffic from a network tap or SPAN port; cannot block, no effect on traffic if it fails |

**Network appliances.**

| Appliance | Purpose |
|---|---|
| Jump server | A hardened host admins connect to first, then reach sensitive systems from it |
| Proxy server | Makes requests on behalf of clients; can filter, cache and log web traffic |
| IDS | Detects and alerts |
| IPS | Detects and blocks, sits inline |
| Load balancer | Spreads traffic across servers |
| Sensors | Collect network data for monitoring tools |

**Port security and 802.1X.** Port security limits which devices can use a switch port. **802.1X** is port-based network access control: the device (supplicant) must authenticate through the switch or access point (authenticator) to an authentication server, usually RADIUS, before it gets network access. **EAP** (Extensible Authentication Protocol) is the framework that carries the authentication messages.

**Firewall types.**

| Type | What it inspects |
|---|---|
| Layer 4 firewall | IP addresses, ports, protocols |
| Layer 7 firewall | Application content and behavior |
| NGFW | Layer 7 awareness plus features like IPS and user or app identification |
| UTM | One box with many functions: firewall, antivirus, filtering, VPN; common for small offices |
| WAF | Protects web applications from attacks such as SQL injection and XSS |

**Secure communication.**

| Technology | Use |
|---|---|
| VPN, remote access | Encrypted tunnel for a user to the corporate network |
| TLS | Encrypts application traffic, such as HTTPS; also used by some VPNs |
| IPsec | Encrypts at the network layer; common for site-to-site tunnels |
| SD-WAN | Software-managed links between sites over several connection types |
| SASE | Cloud-delivered networking and security (such as secure web gateway, zero trust access) close to the user |

### 3.3 Protecting data

**Data types:** regulated (covered by law, such as health or card data), trade secrets, intellectual property, legal information, financial information, and human-readable vs non-human-readable (for example barcodes or encoded data).

**Classifications.** Organizations choose their own labels. The exam lists sensitive, confidential, public, restricted, private and critical. Public data can be released freely; restricted and confidential data need the tightest controls.

**Data states.**

| State | Where it is | How to protect it |
|---|---|---|
| At rest | Stored on disks, databases, backups | Disk, file or database encryption, permissions |
| In transit | Moving across a network | TLS, IPsec, VPN |
| In use | In memory being processed | Secure enclaves, access control, careful handling |

**Sovereignty and geolocation.** **Data sovereignty** means data is subject to the laws of the country where it is stored. **Geolocation** and **geographic restrictions** control where data may be stored or accessed from.

**Methods to secure data.** Encryption (reversible with a key), hashing (one-way, for integrity), masking (hide part of a value), tokenization (substitute a token), obfuscation (make data hard to understand), segmentation (keep sensitive data on separate systems or networks) and permission restrictions.

### 3.4 Resilience and recovery

**Load balancing vs clustering.** Load balancing spreads requests across several servers that each work independently. Clustering makes several servers act as one system, often sharing storage, with failover if one node stops.

**Recovery sites.**

| Site | Ready to go? | Cost | Recovery speed |
|---|---|---|---|
| Hot | Fully equipped, data current or nearly current | Highest | Minutes to hours |
| Warm | Hardware and connectivity in place, data needs restoring | Medium | Hours to a day or more |
| Cold | Space and power only | Lowest | Days to weeks |

**Geographic dispersion** puts sites far enough apart that one disaster cannot hit both. **Platform diversity** uses different OSs or vendors so one flaw does not take everything down. **Multi-cloud** spreads services across providers.

**Continuity of operations** keeps essential functions running during a disruption. **Capacity planning** covers people, technology and infrastructure: enough staff, systems and space to handle demand and recovery.

**Testing resilience.**

| Test | What happens |
|---|---|
| Tabletop exercise | People talk through a scenario around a table; no systems touched |
| Failover | Actually switch to the backup system |
| Simulation | Act out an incident, for example a mock phishing campaign or a staged outage |
| Parallel processing | Run the backup system alongside the primary and compare results |

**Backups.** Decide onsite vs offsite copies, how often to back up (frequency sets how much data you can lose), encrypt backups, and test recovery. **Snapshots** capture a system's state at a point in time. **Replication** copies data to another location continuously or on a schedule. **Journaling** records changes so data can be replayed to a point in time.

**Power.** A **UPS** gives battery power instantly so systems ride through short outages and shut down safely. A **generator** supplies power for long outages but takes time to start, which the UPS covers.

## How questions look

Scenario stems describe a design need and a constraint: "must keep running even if the sensor fails", "the ICS cannot be patched", "the company needs to be running within one hour of a disaster at the lowest cost that meets that". Others ask where to place a device or which firewall type fits. Data items give a kind of data and ask for its state or the right protection. A performance-based item might show a network diagram and ask you to place a WAF, IDS and jump server, or match sites and backup types to recovery needs.

## A method for these questions

1. Identify the asset and the constraint: availability, security, cost, time to recover, or the inability to patch.
2. For placement, find the trust boundary the traffic crosses, and put the control there.
3. For failure modes, ask which is worse here: an outage or uninspected traffic.
4. For cloud items, find the service model first, then read the responsibility matrix.
5. For recovery items, match the stated recovery time and budget to hot, warm or cold.
6. For data items, name the data state before picking the control.

## Traps that cost points

- **IDS vs IPS.** An IDS on a tap cannot block anything. If the stem needs blocking, the answer is an inline IPS.
- **Assuming the cloud provider does it all.** In IaaS, you patch the guest OS. In every model, you manage data and user access.
- **Fail-open for security devices by default.** Fail-open keeps the business running but lets attacks through. Read which priority the stem gives.
- **Containers are VMs.** Containers share the host kernel, so isolation is weaker than with full VMs.
- **A warm site is "almost hot".** It still needs data restored, so it cannot meet very short recovery targets.
- **A UPS replaces a generator.** A UPS covers seconds to minutes. Long outages need a generator.
- **Air gap means perfectly safe.** Removable media and people still move data across the gap.
- **Hashing to protect stored data you must read.** Hashing is one-way. Use encryption if the data must be recovered.

## Timing

Most items take under a minute. Diagram-based PBQs in this domain can take several minutes: flag them, finish the multiple-choice items, and return with your remaining time.

## Practice items

These 10 items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider.

### Item 1

A company runs its web servers on IaaS virtual machines. A critical vulnerability is announced in the guest operating system. Who is responsible for patching it?

A. The cloud provider, because it owns the infrastructure

B. The customer

C. The hypervisor vendor

D. Nobody, because IaaS images are patched automatically

<details>
<summary>Answer and explanation</summary>

**Answer: B.** In IaaS the provider secures the physical hosts and hypervisor, and the customer manages the guest OS, including patching. (Objective 3.1)

- **A** is wrong because the provider's responsibility stops at the hypervisor in IaaS.
- **C** is wrong because the hypervisor vendor has nothing to do with the customer's guest OS.
- **D** is wrong because a running IaaS VM is not patched for you; keeping it current is part of the customer's job.

</details>

### Item 2

A hospital installs a device that inspects traffic to its patient monitoring network. The monitors must never lose connectivity, even if the security device fails. How should the device be configured?

A. Inline, fail-closed

B. Inline, fail-open

C. As an IPS that blocks all traffic when it restarts

D. In front of the monitors as a WAF

<details>
<summary>Answer and explanation</summary>

**Answer: B.** If availability matters most, the device must fail open, so traffic keeps flowing when it fails. (Objective 3.2)

- **A** is wrong because fail-closed stops traffic when the device fails, which would cut off the monitors.
- **C** is wrong because blocking all traffic during a restart is fail-closed behavior.
- **D** is wrong because a WAF protects web applications, and the question is about failure mode, not the type of inspection.

</details>

### Item 3

Administrators must manage database servers in a restricted zone. Security wants one hardened, heavily logged entry point for all admin sessions into that zone. What should be deployed?

A. A forward proxy

B. A load balancer

C. A jump server

D. A honeypot

<details>
<summary>Answer and explanation</summary>

**Answer: C.** A jump server is a hardened host that admins connect to first, and from which they reach the sensitive systems. It concentrates access and logging in one place. (Objective 3.2)

- **A** is wrong because a forward proxy handles outbound requests, usually web traffic for users.
- **B** is wrong because a load balancer spreads traffic across servers; it does not control admin access.
- **D** is wrong because a honeypot is a decoy for attackers, not an access path for admins.

</details>

### Item 4

A company wants new laptops plugged into office wall ports to get no network access until the device authenticates to a RADIUS server. What should it implement?

A. 802.1X

B. MAC filtering only

C. A screened subnet

D. SD-WAN

<details>
<summary>Answer and explanation</summary>

**Answer: A.** 802.1X is port-based network access control: the switch holds the port closed until the device authenticates, usually via EAP to a RADIUS server. (Objective 3.2)

- **B** is wrong because MAC filtering does not authenticate the device and MAC addresses are easy to spoof.
- **C** is wrong because a screened subnet is a zone for public-facing servers, not an access control for wall ports.
- **D** is wrong because SD-WAN manages links between sites.

</details>

### Item 5

A retailer must be able to resume online sales within one hour of losing its primary data center. Which recovery site meets the requirement?

A. Cold site

B. Warm site

C. Tabletop site

D. Hot site

<details>
<summary>Answer and explanation</summary>

**Answer: D.** A hot site has equipment and current data ready, so it can take over within minutes to hours. (Objective 3.4)

- **A** is wrong because a cold site has only space and power; recovery takes days or more.
- **B** is wrong because a warm site still needs data restored and usually cannot meet a one-hour target.
- **C** is wrong because there is no such site type; a tabletop is a discussion-based exercise.

</details>

### Item 6

A payroll file is being sent from HR to an external accounting firm over the internet. Which state is the data in, and what control fits it?

A. In use; a secure enclave

B. At rest; full-disk encryption

C. In transit; TLS

D. At rest; tokenization

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Data moving across a network is in transit, and TLS encrypts it on the way. (Objective 3.3)

- **A** is wrong because data in use is being processed in memory, not sent between organizations.
- **B** is wrong because full-disk encryption protects stored data, not data on the wire.
- **D** is wrong because the file is moving, and tokenization substitutes values rather than protecting a transfer.

</details>

### Item 7

A web application keeps being hit by SQL injection and cross-site scripting attempts. Which control is designed to inspect HTTP requests for these attacks?

A. Layer 4 firewall

B. UPS

C. Network tap

D. Web application firewall

<details>
<summary>Answer and explanation</summary>

**Answer: D.** A WAF inspects HTTP traffic for web attacks such as SQL injection and XSS. It complements, and does not replace, fixing the code. (Objective 3.2)

- **A** is wrong because a Layer 4 firewall sees only addresses and ports, so it cannot tell a malicious query from a normal one on port 443.
- **B** is wrong because a UPS provides power, not inspection.
- **C** is wrong because a tap only copies traffic for monitoring and cannot block anything.

</details>

### Item 8

A factory's industrial control system runs software that the vendor says cannot be patched without voiding its safety certification. Which approach BEST reduces risk?

A. Patch it anyway during the next maintenance window

B. Connect it directly to the corporate network so it can be monitored more easily

C. Isolate it on its own segment, or air gap it, and tightly control what can reach it

D. Replace its RTOS with a general-purpose OS

<details>
<summary>Answer and explanation</summary>

**Answer: C.** When a system cannot be patched, you reduce exposure: isolation or segmentation, strict access rules and monitoring at the boundary. (Objective 3.1)

- **A** is wrong because it ignores the stated constraint and risks the safety certification.
- **B** is wrong because joining it to the corporate network increases its attack surface.
- **D** is wrong because swapping the OS is not something the operator can do to a certified control system, and it would break the real-time requirements.

</details>

### Item 9

A backup administrator needs to restore a database to its state at 14:37 yesterday, between two nightly backups. Which capability makes this possible?

A. Journaling

B. A cold site

C. Load balancing

D. A generator

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Journaling records each change, so the database can be restored from the last full backup and the journal replayed up to a chosen point in time. (Objective 3.4)

- **B** is wrong because a cold site is an empty facility; it says nothing about restore points.
- **C** is wrong because load balancing spreads traffic; it does not keep history.
- **D** is wrong because a generator provides power.

</details>

### Item 10

A company is designing a new branch office network. Choose two statements that are TRUE.

A. A passive sensor on a SPAN port can block attacks in real time.

B. Containers on one host share the host's OS kernel.

C. A UPS is meant to power the office for several days during a long outage.

D. Data sovereignty means data is subject to the laws of the country where it is stored.

E. In SaaS, the provider is responsible for deciding which employees get accounts.

<details>
<summary>Answer and explanation</summary>

**Answer: B and D.** Containers share the host kernel, which is why they are lighter but less isolated than VMs. Data sovereignty ties data to the laws of the country where it is stored. (Objectives 3.1 and 3.3)

- **A** is wrong because a passive device on a SPAN port only receives a copy of traffic and cannot block it.
- **C** is wrong because a UPS covers short outages and safe shutdown; long outages need a generator.
- **E** is wrong because user access is always the customer's responsibility, even in SaaS.

</details>

## Score yourself

| Item | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Answer | B | B | C | A | D | C | D | C | A | B, D |
| Objective | 3.1 | 3.2 | 3.2 | 3.2 | 3.4 | 3.3 | 3.2 | 3.1 | 3.4 | 3.1, 3.3 |

- **9 to 10:** you can reason about designs. Move on.
- **7 to 8:** check whether your misses were about failure modes, cloud responsibility or recovery sites, and reread that table in [Key concepts](#key-concepts-explained).
- **6 or fewer:** draw a simple network from memory with internet, firewall, DMZ, internal LAN and server zone, and place a WAF, IPS, jump server and load balancer on it. Then reread [3.2 Securing enterprise infrastructure](#32-securing-enterprise-infrastructure) and redo the items.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. Write the IaaS, PaaS and SaaS responsibility matrix from memory, then check it against the table above.
3. Take a timed run with the [free Security+ (SY0-701) practice test on PrepClubs](https://prepclubs.com/free-practice-tests/security-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=security-plus) to practise pacing across the whole exam.

---

<!-- nav:bottom -->← Previous: [Domain 2: Threats, Vulnerabilities, and Mitigations](2-threats-vulnerabilities-and-mitigations.md) | Next: [Domain 4: Security Operations](4-security-operations.md) → | [Back to contents](../../README.md#contents)<!-- /nav:bottom -->
