<!-- nav:top -->[Contents](../README.md#contents) · Previous: [Domain 5: Security Program Management and Oversight](domains/5-security-program-management-and-oversight.md) · Next: [How Security+ scoring works](scoring.md)<!-- /nav:top -->

# Performance-based questions and pacing

Security+ mixes multiple-choice questions with performance-based questions (PBQs). PBQs are where many candidates lose time, not because they are impossible but because people meet them first, at the start of the exam, and spend too long on them.

## What PBQs are

A PBQ asks you to do something rather than pick a letter. In our own words, the common shapes are:

- **Drag and drop or match:** pair attacks with descriptions, controls with control types, or agreements with their purpose.
- **Order the steps:** put incident response or change management steps in sequence.
- **Configure:** choose firewall rules, wireless settings or account settings for a scenario.
- **Analyze:** read logs, alerts or scan results and choose what happened or what to do.
- **Place on a diagram:** decide where a WAF, IDS, jump server or VPN concentrator belongs.

CompTIA lists Security+ as a mix of multiple-choice and performance-based questions. It does not publish how many PBQs appear on a given exam or how they are weighted in the score, so treat any number you read online as hearsay.

## A pacing plan for 90 minutes

| Time on the clock | Where you should be |
|---|---|
| 0 to 2 minutes | Read the instructions. If the first questions are PBQs, read each one, make a quick attempt only if it is obviously short, and flag it |
| By 30 minutes | Roughly a third of the multiple-choice questions done |
| By 60 minutes | Roughly two thirds of the multiple-choice questions done |
| By 75 minutes | All multiple-choice questions answered, including guesses on the hard ones |
| 75 to 88 minutes | Return to the flagged PBQs and finish them |
| Last 2 minutes | Make sure nothing is left blank |

The idea is simple. A PBQ might be worth more than one multiple-choice item, but nobody outside CompTIA knows how much more. Fifteen quick multiple-choice questions you never reached because you were stuck on one PBQ are a certain loss. So bank the quick points first, then give PBQs the time that is left. Some candidates prefer to do PBQs first while fresh; that works if you set yourself a hard limit, such as 4 to 5 minutes each, and move on when it is up.

On average across the exam, you have about one minute per question. Short definition items take 30 to 45 seconds, which buys time for PBQs.

## How to approach a PBQ

1. **Read the whole task first,** including every tab or panel, before you click anything.
2. **Write down the goal in one line** on your notepad: "Allow web traffic to the DMZ server only" or "Order the IR steps".
3. **Do the parts you are sure of first.** Partial progress on a matching task is better than a blank screen.
4. **Check constraints** the task gives you, such as "least privilege" or "the server must stay reachable", against each choice.
5. **Look for a reset button** before experimenting, and note what the original state was.
6. **Stop at your time limit,** make your best choices, and move on.

## Practice task 1: order the steps

A company has discovered malware on several workstations. Put these incident response activities in the order CompTIA's process uses:

- Remove the malware and the attacker's persistence
- Hold a review meeting and update the playbook
- Disconnect the infected workstations from the network
- Confirm that the alerts are a real incident and judge its scope
- Restore the workstations and monitor them
- Notice unusual alerts from endpoint protection

<details>
<summary>Answer</summary>

1. Notice unusual alerts from endpoint protection (detection)
2. Confirm that the alerts are a real incident and judge its scope (analysis)
3. Disconnect the infected workstations from the network (containment)
4. Remove the malware and the attacker's persistence (eradication)
5. Restore the workstations and monitor them (recovery)
6. Hold a review meeting and update the playbook (lessons learned)

Preparation, the first step of the process, happens before the incident, so it is not in this list. See [Domain 4](domains/4-security-operations.md#48-incident-response).

</details>

## Practice task 2: build a firewall rule set

A web server sits in the screened subnet at 192.0.2.10. Requirements:

- Anyone on the internet can reach it over HTTPS.
- Only the admin subnet 10.10.50.0/24 can SSH to it.
- Nothing else may reach it.

Pick and order three of these rules. Rules are processed top to bottom, first match wins.

```
a  allow  tcp  any             -> 192.0.2.10  80
b  allow  tcp  any             -> 192.0.2.10  443
c  allow  tcp  10.10.50.0/24   -> 192.0.2.10  22
d  allow  tcp  any             -> 192.0.2.10  22
e  deny   ip   any             -> 192.0.2.10  any
```

<details>
<summary>Answer</summary>

Order: **b, c, e.** Rule b allows HTTPS from anywhere. Rule c allows SSH from the admin subnet only. Rule e denies everything else to the server. Rule a would open plain HTTP, which was not asked for, and rule d would open SSH to the whole internet. Putting e first would block everything. See [Domain 4](domains/4-security-operations.md#45-enhancing-enterprise-capabilities).

</details>

## Practice under time

PBQ skill improves fastest with timed practice. Work through the domain items in this repo, then take the [free Security+ (SY0-701) practice test on PrepClubs](https://prepclubs.com/free-practice-tests/security-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=security-plus) and check your pace against the plan above.

---

<!-- nav:bottom -->← Previous: [Domain 5: Security Program Management and Oversight](domains/5-security-program-management-and-oversight.md) | Next: [How Security+ scoring works](scoring.md) → | [Back to contents](../README.md#contents)<!-- /nav:bottom -->
