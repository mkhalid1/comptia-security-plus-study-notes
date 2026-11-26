# CompTIA Security+ SY0-701 Study Notes

A free, complete study guide for the CompTIA Security+ SY0-701 exam. For each of the five official domains you get a plain-English explanation of every objective, comparison tables for the terms that get confused, how the questions look, a step-by-step method, the traps that cost points, and original practice items with full explanations: 20 across the domains, plus a 5-item diagnostic. Every exam fact comes from CompTIA's own pages and the official objectives document, each one [cited](docs/sources.md).

> **Version note.** CompTIA launched Security+ **SY0-801** on November 17, 2026. **SY0-701** stays available until June 11, 2027 (English) and August 13, 2027 (Japanese, Portuguese, Spanish, Thai). These notes cover SY0-701. Not sure which to book? Read [SY0-701 or SY0-801](docs/which-version.md).

Want to see where you stand first? Take the [free timed Security+ (SY0-701) practice test on PrepClubs](https://prepclubs.com/free-practice-tests/security-plus?utm_source=github&utm_medium=referral&utm_campaign=4s76wr&utm_content=security-plus), or the shorter [5-minute diagnostic](docs/diagnostic.md) in this repo.

## Start here

1. **Find your weak domains.** Take the [5-minute diagnostic](docs/diagnostic.md): one item from each domain, with a results table that tells you where to start.
2. **Fix the weakest heavy domain first.** Open its guide below, read "Key concepts" and "Traps that cost points", then do its practice items. Security Operations is 28% of the exam, so a gap there costs the most.
3. **Follow a plan.** Use the [7-day plan](docs/study-plans.md#7-day-plan), or the [2-day plan](docs/study-plans.md#2-day-plan) if your exam is close.

## Quick facts

| | |
|---|---|
| Exam | CompTIA Security+ SY0-701 (V7) |
| Questions | A maximum of 90, multiple-choice and performance-based |
| Time | 90 minutes |
| Passing score | 750 on a scale of 100 to 900 |
| Domains | 5 (see below) |
| Recommended experience | Network+ plus two years in a security or systems administrator role |
| Languages | English, Japanese, Portuguese, Spanish, Thai |
| Delivery | Pearson VUE test center or online (OnVUE) |
| Retires | June 11, 2027 (English); August 13, 2027 (other languages) |
| Renewal | Three-year cycle, 50 continuing education units |

Sources: [CompTIA Security+ V7](https://www.comptia.org/en-us/certifications/security/v7/), the [official SY0-701 objectives](https://lecbyo.files.cmp.optimizely.com/download/cf25ec24b8a511ef9ecbb69c0f9687be) and [CompTIA continuing education](https://www.comptia.org/en-us/resources/ce/learn/earn-continuing-education-units-ceus/), checked 24 November 2026.

## The five domains at a glance

| Domain | Weight | What it covers | Items | Guide |
|---|---|---|---|---|
| 1. General Security Concepts | 12% | Control types, CIA, AAA, Zero Trust, change management, cryptography and PKI | 4 | [Domain 1](docs/domains/1-general-security-concepts.md) |
| 2. Threats, Vulnerabilities, and Mitigations | 22% | Threat actors, vectors, vulnerabilities, attack indicators, mitigations | 4 | [Domain 2](docs/domains/2-threats-vulnerabilities-and-mitigations.md) |
| 3. Security Architecture | 18% | Cloud and on-premises models, secure infrastructure, data protection, resilience and recovery | 4 | [Domain 3](docs/domains/3-security-architecture.md) |
| 4. Security Operations | 28% | Hardening, assets, vulnerability management, monitoring, firewalls and email security, identity, automation, incident response, investigations | 4 | [Domain 4](docs/domains/4-security-operations.md) |
| 5. Security Program Management and Oversight | 20% | Governance, risk and its formulas, third parties, compliance, audits, awareness | 4 | [Domain 5](docs/domains/5-security-program-management-and-oversight.md) |

Every domain guide has the same parts: what the domain measures (objective by objective), key concepts explained, how the questions look, a method, the traps that cost points, timing, original practice items with explanations, and a score table.

## Contents

<!-- toc:start -->

**Start here**

- [The Security+ SY0-701 exam explained](docs/exam-overview.md)
  - [Quick facts](docs/exam-overview.md#quick-facts)
  - [The five domains and their weights](docs/exam-overview.md#the-five-domains-and-their-weights)
  - [Who the exam is for](docs/exam-overview.md#who-the-exam-is-for)
  - [How the questions work](docs/exam-overview.md#how-the-questions-work)
  - [How the objectives document works](docs/exam-overview.md#how-the-objectives-document-works)
  - [Booking and taking the exam](docs/exam-overview.md#booking-and-taking-the-exam)
  - [Retakes and renewal](docs/exam-overview.md#retakes-and-renewal)
  - [Practice the real format](docs/exam-overview.md#practice-the-real-format)
- [SY0-701 or SY0-801: which version to take](docs/which-version.md)
  - [The two versions side by side](docs/which-version.md#the-two-versions-side-by-side)
  - [How the domains changed](docs/which-version.md#how-the-domains-changed)
  - [Is SY0-701 still valid?](docs/which-version.md#is-sy0-701-still-valid)
  - [Which should you choose?](docs/which-version.md#which-should-you-choose)
  - [What these notes cover](docs/which-version.md#what-these-notes-cover)
- [5-minute diagnostic](docs/diagnostic.md)
  - [Part A: Domain 1, General Security Concepts](docs/diagnostic.md#part-a-domain-1-general-security-concepts)
  - [Part B: Domain 2, Threats, Vulnerabilities, and Mitigations](docs/diagnostic.md#part-b-domain-2-threats-vulnerabilities-and-mitigations)
  - [Part C: Domain 3, Security Architecture](docs/diagnostic.md#part-c-domain-3-security-architecture)
  - [Part D: Domain 4, Security Operations](docs/diagnostic.md#part-d-domain-4-security-operations)
  - [Part E: Domain 5, Security Program Management and Oversight](docs/diagnostic.md#part-e-domain-5-security-program-management-and-oversight)
  - [Answer key](docs/diagnostic.md#answer-key)
  - [What your result means](docs/diagnostic.md#what-your-result-means)

**The five domains**

- [Domain 1: General Security Concepts](docs/domains/1-general-security-concepts.md)
  - [What this domain measures](docs/domains/1-general-security-concepts.md#what-this-domain-measures)
  - [Key concepts explained](docs/domains/1-general-security-concepts.md#key-concepts-explained)
  - [How questions look](docs/domains/1-general-security-concepts.md#how-questions-look)
  - [A method for these questions](docs/domains/1-general-security-concepts.md#a-method-for-these-questions)
  - [Traps that cost points](docs/domains/1-general-security-concepts.md#traps-that-cost-points)
  - [Timing](docs/domains/1-general-security-concepts.md#timing)
  - [Practice items](docs/domains/1-general-security-concepts.md#practice-items)
  - [Score yourself](docs/domains/1-general-security-concepts.md#score-yourself)
- [Domain 2: Threats, Vulnerabilities, and Mitigations](docs/domains/2-threats-vulnerabilities-and-mitigations.md)
  - [What this domain measures](docs/domains/2-threats-vulnerabilities-and-mitigations.md#what-this-domain-measures)
  - [Key concepts explained](docs/domains/2-threats-vulnerabilities-and-mitigations.md#key-concepts-explained)
  - [How questions look](docs/domains/2-threats-vulnerabilities-and-mitigations.md#how-questions-look)
  - [A method for these questions](docs/domains/2-threats-vulnerabilities-and-mitigations.md#a-method-for-these-questions)
  - [Traps that cost points](docs/domains/2-threats-vulnerabilities-and-mitigations.md#traps-that-cost-points)
  - [Timing](docs/domains/2-threats-vulnerabilities-and-mitigations.md#timing)
  - [Practice items](docs/domains/2-threats-vulnerabilities-and-mitigations.md#practice-items)
  - [Score yourself](docs/domains/2-threats-vulnerabilities-and-mitigations.md#score-yourself)
- [Domain 3: Security Architecture](docs/domains/3-security-architecture.md)
  - [What this domain measures](docs/domains/3-security-architecture.md#what-this-domain-measures)
  - [Key concepts explained](docs/domains/3-security-architecture.md#key-concepts-explained)
  - [How questions look](docs/domains/3-security-architecture.md#how-questions-look)
  - [A method for these questions](docs/domains/3-security-architecture.md#a-method-for-these-questions)
  - [Traps that cost points](docs/domains/3-security-architecture.md#traps-that-cost-points)
  - [Timing](docs/domains/3-security-architecture.md#timing)
  - [Practice items](docs/domains/3-security-architecture.md#practice-items)
  - [Score yourself](docs/domains/3-security-architecture.md#score-yourself)
- [Domain 4: Security Operations](docs/domains/4-security-operations.md)
  - [What this domain measures](docs/domains/4-security-operations.md#what-this-domain-measures)
  - [Key concepts explained](docs/domains/4-security-operations.md#key-concepts-explained)
  - [How questions look](docs/domains/4-security-operations.md#how-questions-look)
  - [A method for these questions](docs/domains/4-security-operations.md#a-method-for-these-questions)
  - [Traps that cost points](docs/domains/4-security-operations.md#traps-that-cost-points)
  - [Timing](docs/domains/4-security-operations.md#timing)
  - [Practice items](docs/domains/4-security-operations.md#practice-items)
  - [Score yourself](docs/domains/4-security-operations.md#score-yourself)
- [Domain 5: Security Program Management and Oversight](docs/domains/5-security-program-management-and-oversight.md)
  - [What this domain measures](docs/domains/5-security-program-management-and-oversight.md#what-this-domain-measures)
  - [Key concepts explained](docs/domains/5-security-program-management-and-oversight.md#key-concepts-explained)
  - [How questions look](docs/domains/5-security-program-management-and-oversight.md#how-questions-look)
  - [A method for these questions](docs/domains/5-security-program-management-and-oversight.md#a-method-for-these-questions)
  - [Traps that cost points](docs/domains/5-security-program-management-and-oversight.md#traps-that-cost-points)
  - [Timing](docs/domains/5-security-program-management-and-oversight.md#timing)
  - [Practice items](docs/domains/5-security-program-management-and-oversight.md#practice-items)
  - [Score yourself](docs/domains/5-security-program-management-and-oversight.md#score-yourself)

**Scores and strategy**

- [Performance-based questions and pacing](docs/performance-based-questions.md)
  - [What PBQs are](docs/performance-based-questions.md#what-pbqs-are)
  - [A pacing plan for 90 minutes](docs/performance-based-questions.md#a-pacing-plan-for-90-minutes)
  - [How to approach a PBQ](docs/performance-based-questions.md#how-to-approach-a-pbq)
  - [Practice under time](docs/performance-based-questions.md#practice-under-time)
- [How Security+ scoring works](docs/scoring.md)
  - [The scaled score](docs/scoring.md#the-scaled-score)
  - [What CompTIA does not publish](docs/scoring.md#what-comptia-does-not-publish)
  - [What your score report shows](docs/scoring.md#what-your-score-report-shows)
  - [Answer every question](docs/scoring.md#answer-every-question)
  - [What practice score to aim for](docs/scoring.md#what-practice-score-to-aim-for)
  - [If you do not pass](docs/scoring.md#if-you-do-not-pass)
- [Study plans: 7 days and 2 days](docs/study-plans.md)
  - [7-day plan](docs/study-plans.md#7-day-plan)
  - [2-day plan](docs/study-plans.md#2-day-plan)
  - [What not to do](docs/study-plans.md#what-not-to-do)
- [Security+ for DoD and government contractor roles](docs/dod-8140.md)
  - [What CompTIA lists](docs/dod-8140.md#what-comptia-lists)
  - [What that means for you](docs/dod-8140.md#what-that-means-for-you)
  - [Study priorities for these roles](docs/dod-8140.md#study-priorities-for-these-roles)
- [Exam-day checklist](docs/exam-day-checklist.md)
  - [The day before](docs/exam-day-checklist.md#the-day-before)
  - [Test center or online](docs/exam-day-checklist.md#test-center-or-online)
  - [In the first minute](docs/exam-day-checklist.md#in-the-first-minute)
  - [During the exam](docs/exam-day-checklist.md#during-the-exam)
  - [Afterwards](docs/exam-day-checklist.md#afterwards)
  - [Last practice before the real one](docs/exam-day-checklist.md#last-practice-before-the-real-one)

**Reference**

- [FAQ](docs/faq.md)
  - [Is SY0-701 still valid?](docs/faq.md#is-sy0-701-still-valid)
  - [How many questions are on Security+, and how long is it?](docs/faq.md#how-many-questions-are-on-security-and-how-long-is-it)
  - [What is the passing score?](docs/faq.md#what-is-the-passing-score)
  - [How difficult is the Security+ exam?](docs/faq.md#how-difficult-is-the-security-exam)
  - [How much does the Security+ exam cost?](docs/faq.md#how-much-does-the-security-exam-cost)
  - [Can I pass Security+ in 3 weeks?](docs/faq.md#can-i-pass-security-in-3-weeks)
  - [Do I need Network+ or A+ first?](docs/faq.md#do-i-need-network-or-a-first)
  - [Can I get a job with just a CompTIA Security+?](docs/faq.md#can-i-get-a-job-with-just-a-comptia-security)
  - [Is CompTIA Security+ worth it?](docs/faq.md#is-comptia-security-worth-it)
  - [How long is Security+ valid?](docs/faq.md#how-long-is-security-valid)
  - [Which CompTIA certs never expire?](docs/faq.md#which-comptia-certs-never-expire)
  - [Can I take Security+ online?](docs/faq.md#can-i-take-security-online)
  - [Are there performance-based questions?](docs/faq.md#are-there-performance-based-questions)
  - [What happens if I fail?](docs/faq.md#what-happens-if-i-fail)
  - [Is 25 (or 35, or 45) too late to start in cybersecurity?](docs/faq.md#is-25-or-35-or-45-too-late-to-start-in-cybersecurity)
  - [Is there an official practice test?](docs/faq.md#is-there-an-official-practice-test)
  - [Where can I practice for free?](docs/faq.md#where-can-i-practice-for-free)
- [Glossary](docs/glossary.md)
- [Sources](docs/sources.md)
  - [CompTIA exam pages](docs/sources.md#comptia-exam-pages)
  - [Objectives document](docs/sources.md#objectives-document)
  - [CompTIA policies and help pages](docs/sources.md#comptia-policies-and-help-pages)
  - [Search data](docs/sources.md#search-data)
  - [What is our own guidance](docs/sources.md#what-is-our-own-guidance)
  - [Practice items](docs/sources.md#practice-items)
  - [Not affiliated](docs/sources.md#not-affiliated)

<!-- toc:end -->

## How to use this repo

- **Read on GitHub.** Every page has links to the previous page, the next page and back to these contents, so you can read it start to finish like a book.
- **Test yourself honestly.** Answers are hidden under "Answer and explanation". Commit to an answer before you open it.
- **Read every explanation,** including for items you got right. Each one says why every wrong option is wrong, which is where most of the learning is.
- **Keep a miss log.** For each miss, write what you confused and the word in the stem that should have stopped you. The [study plans](docs/study-plans.md#how-to-review-a-missed-item) show how.
- **Practice timed.** The notes teach the content. A timed run, such as the [free one on PrepClubs](https://prepclubs.com/free-practice-tests/security-plus?utm_source=github&utm_medium=referral&utm_campaign=4s76wr&utm_content=security-plus), teaches the pace.
- **Clone or fork it** to annotate your own copy. The structure also works as a GitBook space: see [SUMMARY.md](SUMMARY.md).

## About the practice items

All practice and diagnostic items are original, written for these notes. None are taken from CompTIA's exams or materials, or from any prep provider or "brain dump" site. They follow the published SY0-701 objectives so the reasoning transfers to the real exam.

## Contributing

Spotted an error, a changed fact or an item you think has a different answer? Please [open an issue](https://github.com/mkhalid1/comptia-security-plus-study-notes/issues) or a pull request. Corrections to exam facts need a link to CompTIA's own page.

## Licence and disclaimer

Released under the [MIT License](LICENSE).

These notes are independent and not affiliated with, endorsed by or sponsored by CompTIA or Pearson VUE. CompTIA and Security+ are trademarks of CompTIA, Inc.
