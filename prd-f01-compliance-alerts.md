# F-01 · Proactive Compliance Alerts
## ClassWallet Feature PRD
**Author:** Deepshikha Dash, PM · [github.com/Deepshikhadash](https://github.com/Deepshikhadash)  
**Feature ID:** CW-F-01 · **Status:** Draft v1.0 · **Priority:** P0 — Q3 2026  
**Stakeholders:** Agency Administrators · CSM Team · Compliance/Legal · Engineering

---

## Table of Contents
1. [Problem Statement](#1-problem-statement)
2. [Target Users](#2-target-users)
3. [Goals & Success Metrics](#3-goals--success-metrics)
4. [User Stories & Acceptance Criteria](#4-user-stories--acceptance-criteria)
5. [RICE Prioritization](#5-rice-prioritization)
6. [Out of Scope (v1)](#6-out-of-scope-v1)
7. [One-Pager Summary](#7-one-pager-summary)

---

## 1. Problem Statement

Agency administrators managing public fund programs are reactive by default. They discover compliance issues — unspent fund balances, ineligible spend patterns, approaching program deadlines — only after they become problems: via audit findings, support escalations, or end-of-period reconciliation. By then, the cost of remediation is high and the reputational risk to the program is real.

The root cause is not negligence. Admins managing 2,000+ recipients across multiple programs cannot manually monitor every account. **They need the system to watch for them.**

> **PM Note:** This problem is directly informed by my experience designing monitoring frameworks for state education agencies at EDC — program administrators consistently named "finding out too late" as their biggest operational pain. This feature translates MEL (Monitoring, Evaluation & Learning) logic into a product capability.

---

## 2. Target Users

| User | Role | Pain Point |
|---|---|---|
| **Agency Administrator** (primary) | State/local government staff managing 500–10,000 recipient accounts | No proactive visibility — discovers problems reactively via audit or support |
| **Program Director** (secondary) | Senior agency leader accountable to legislators | Wants executive summary visibility without log-level detail |

---

## 3. Goals & Success Metrics

| Metric | Baseline (est.) | Target (90 days post-launch) |
|---|---|---|
| End-of-program unspent fund rate | ~12% avg across programs | ≤ 6% |
| Admin-initiated compliance interventions | Reactive (post-flag) | ≥ 40% proactive (pre-flag) |
| Support tickets: deadline/balance issues | Baseline TBD | ↓ 30% |
| Admin weekly digest open rate | N/A (new feature) | ≥ 65% |

**Leading indicators (week 1–2 post-launch):**
- Weekly digest delivery success rate ≥ 98%
- Alert Center daily active admin rate
- Time-to-first-action on High-severity alerts

---

## 4. User Stories & Acceptance Criteria

---

### Story CW-F01-S1 — Weekly Program Health Digest

**As an** agency administrator,  
**I want to** receive a weekly digest every Monday summarizing at-risk recipients and compliance flags,  
**So that** I can take proactive action before issues become audit findings without monitoring every account manually.

**Acceptance Criteria:**
- [ ] Digest delivered to admin's registered email every Monday between 7–8 AM in their timezone
- [ ] Digest includes: (a) recipients with <20% utilization and ≤30 days to program deadline, (b) recipients with 3+ declined transactions in past 7 days, (c) top 3 support ticket categories by volume
- [ ] Each recipient flag includes a deep link directly to their account in the ClassWallet dashboard
- [ ] Admin can configure digest preferences: on/off, day/time, and threshold values (e.g., change <20% to <30%)
- [ ] If no flags exist for the week, digest still sends with a "All programs on track" confirmation
- [ ] Admin can unsubscribe from digest without affecting other notification settings
- [ ] Digest renders correctly in Gmail, Outlook, and Apple Mail on desktop and mobile

**Definition of Done:** ✅ Coded · ✅ QA tested · ✅ Email rendering tested (Gmail/Outlook/Apple Mail) · ✅ Deep links verified · ✅ Preference config tested · ✅ Audit log confirmed · ✅ Release notes updated

---

### Story CW-F01-S2 — In-App Alert Center

**As an** agency administrator,  
**I want to** view all active compliance alerts in a dedicated in-app Alert Center,  
**So that** I have a single place to triage and act on flags without leaving the platform.

**Acceptance Criteria:**
- [ ] Alert Center accessible from main navigation — visible badge count of unresolved alerts
- [ ] Alerts displayed in reverse chronological order with: alert type, recipient ID, severity (High / Medium / Low), and date triggered
- [ ] Admin can mark an alert as "Reviewed" with a required action note — logged to audit trail
- [ ] Resolved alerts move to an archive accessible for 90 days
- [ ] Admin can filter alerts by program, severity, and date range
- [ ] High-severity alerts trigger an immediate email notification in addition to in-app badge
- [ ] Badge count updates in real time — no page refresh required

**Definition of Done:** ✅ Coded · ✅ QA tested · ✅ Real-time badge tested · ✅ Email notification delivery tested · ✅ Archive persistence verified · ✅ Audit log verified · ✅ Release notes updated

---

## 5. RICE Prioritization

`RICE = (Reach × Impact × Confidence) ÷ Effort`

| Feature / Story | Reach | Impact | Confidence | Effort (wks) | RICE | Priority |
|---|---|---|---|---|---|---|
| Weekly digest delivery | 9 | 8 | 8 | 3 | 192 | **P0** |
| In-app Alert Center | 9 | 9 | 8 | 5 | 130 | **P0** |
| Admin configurable thresholds | 7 | 7 | 8 | 3 | 131 | P1 |
| Director executive summary view | 5 | 7 | 7 | 4 | 61 | P2 |

---

## 6. Out of Scope (v1)

- SMS/push notification delivery (v2 — requires carrier integration)
- Automated recipient outreach triggered by alerts (v2)
- ML-based predictive alerts — "recipient X likely to have unspent funds" (v3)
- Director-level executive digest (P1 — separate feature)

---

## 7. One-Pager Summary

| | |
|---|---|
| **Problem** | Admins discover compliance issues reactively — after audit findings or end-of-period reconciliation. By then remediation costs are high and program trust is damaged. |
| **Users** | Agency Administrator · Program Director |
| **Solution** | Weekly email digest + in-app Alert Center surfacing at-risk recipients before they become compliance failures. Admins configure thresholds; alerts deep-link to recipient accounts. |
| **In Scope (v1)** | Weekly digest · In-app Alert Center with badge · Alert severity tiers · Admin-configurable thresholds · Audit trail logging |
| **Out of Scope (v1)** | SMS/push · Automated recipient outreach · ML predictive alerting · Executive digest |
| **Key Metrics** | Unspent fund rate ↓ ≤6% · ≥40% proactive interventions · Support tickets ↓30% · Digest open rate ≥65% |

---

*Deepshikha Dash · Product Manager · Austin, TX · [github.com/Deepshikhadash](https://github.com/Deepshikhadash)*
