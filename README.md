# Avery McQueen

**Operations systems engineer — Austin, Texas**

I build the systems that keep operational data trustworthy: CRM architecture, scheduled integration pipelines, and the validation layers that sit between them. Most of my work is the unglamorous middle of a business — the nightly sync that has to not fail silently, the reconciliation that decides which of two systems is right, the import that must not create four thousand duplicates.

I work across HubSpot, Salesforce, QuickBooks, and custom REST integrations, usually as the person who owns the whole path from source system to the report someone actually reads.

---

## What I work on

**Data architecture.** Rebuilding record models so that one entity has one authoritative record, with validation rules that govern creation and change rather than cleanup scripts that run after the damage is done.

**Integration pipelines.** Scheduled syncs on GitHub Actions between CRM systems, CMS database tables, and accounting platforms. Retries, rate limits, checkpointing, dry-run mode, and alerting that distinguishes a broken clock from a broken credential.

**Reconciliation.** Establishing which of two systems is correct when they disagree, and building the recurring check that catches drift before it becomes a quarter-end problem.

**Reporting.** Automated KPI reporting that makes data quality visible instead of assumed. Dashboards are only as good as the records underneath them, which is most of why I care about the layer below.

---

## Projects

| Project | What it does |
| --- | --- |
| [webhook-signature-verifier](https://github.com/averya34/webhook-signature-verifier) | Constant-time HMAC verification for inbound webhooks, with timestamp and delivery-ID replay protection. Adapters for the three common provider signature shapes. |
| [crm-data-quality](https://github.com/averya34/crm-data-quality) | Rule-driven validation, blocking-based duplicate detection with weighted scoring, and four-way reconciliation between systems that are supposed to agree. |
| [scheduled-api-sync](https://github.com/averya34/scheduled-api-sync) | A framework for scheduled sync jobs: exponential backoff with jitter, token-bucket rate limiting, durable checkpoints, log redaction, and a real dry-run mode. |

All three are standard library only, tested across Python 3.10–3.12, and linted in CI. Each README explains the design decisions rather than just the API, because the decisions are the interesting part.

---

## How I build

**Dry runs before writes.** Anything that touches a production CRM gets a mode that computes and reports everything and writes nothing. This is not a nicety — it is the difference between finding a mapping error in a report and finding it in 12,000 modified records.

**Rules as reviewable data.** The person who knows what "clean" means is usually the operations lead, not the engineer. Configuration that lives in version control and gets reviewed in a pull request beats logic buried in a script.

**Fail loudly, fail specifically.** A distinct error type per failure mode, so a misconfigured sender and an actual attack do not look the same in a log. A spike in one is an incident; a spike in the other is a clock.

**Documentation as a deliverable.** I write the SOPs and runbooks alongside the code, because a system only a consultant can operate is a system with an expiry date.

---

## Background

Seven years across operations, systems, and analytics. Currently consulting on CRM and operations systems — recent work spans a national trade association's membership platform, multi-project residential development portfolios, and integration pipelines between CRM, accounting, and CMS systems.

Before that, operations and events at scale: multi-venue tournaments with attendance from 300 to 70,000, where a schedule that breaks has to be rebuilt live and the throughput number is the only one that matters.

M.S. Data Science, Eastern University. B.S. Interdisciplinary Studies, Liberty University.

---

**Toolkit** · Python · JavaScript · SQL · Node.js · HTML/CSS · GitHub Actions · REST APIs and webhooks · HubSpot · Salesforce · QuickBooks Online · Google Apps Script · Power Automate · Tableau · Cloudflare

[avery-mcqueen.com](https://avery-mcqueen.com) · [LinkedIn](https://www.linkedin.com/in/avery-mcqueen-8757b715a)
