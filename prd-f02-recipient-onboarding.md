# F-02 · Recipient Onboarding Flow
## ClassWallet Feature PRD
**Author:** Deepshikha Dash, PM · [github.com/Deepshikhadash](https://github.com/Deepshikhadash)  
**Feature ID:** CW-F-02 · **Status:** Draft v1.0 · **Priority:** P0 — Q3 2026  
**Stakeholders:** Program Recipients · Agency Administrators · Design · Engineering · CSM

---

## 1. Problem Statement

Wallet activation is the critical first step for program recipients — and currently one of the highest-friction points in ClassWallet's experience. Recipients include low-income families, elderly individuals, and people with limited digital literacy. Activation flows designed for tech-comfortable users create abandonment, support call volume, and ultimately mean that public funds go unspent — a compliance and mission failure.

**If a recipient doesn't activate their wallet, the program has failed them before they spend a single dollar.**

> **PM Note:** My doctoral fieldwork in rural post-conflict communities in India (IIT Kharagpur) gave me direct insight into how non-digitally-fluent users interact with formal systems. The design principles in this PRD — progressive disclosure, SMS fallback, minimal steps, plain language — are grounded in that field experience, not just UX theory.

---

## 2. Target Users

| User | Context | Key Constraint |
|---|---|---|
| **Program Recipient** (primary) | Individual/family receiving grant funds | Variable digital literacy; often mobile-only; may not have email |
| **Agency Administrator** (secondary) | Configures activation settings per program | Responsible for utilization rates; high unactivated wallets = program failure signal |

---

## 3. Goals & Success Metrics

| Metric | Baseline (est.) | Target |
|---|---|---|
| Wallet activation within 24 hours of fund allocation | ~55% | ≥ 80% |
| Activation support tickets | Baseline TBD | ↓ 50% within 60 days |
| Activation completion rate on mobile | Unknown | ≥ 85% |
| Time-to-activate (standard flow) | Unknown | ≤ 5 minutes |
| First-time tour completion rate | N/A | ≥ 60% |

---

## 4. User Stories & Acceptance Criteria

---

### Story CW-F02-S1 — SMS-Based Activation

**As a** program recipient with limited email access,  
**I want to** activate my wallet via a text message link without needing an email account,  
**So that** I can access my funds regardless of my digital setup.

**Acceptance Criteria:**
- [ ] Agency admin can configure program to send SMS activation link (in addition to or instead of email)
- [ ] SMS delivers within 5 minutes of fund allocation trigger
- [ ] SMS link opens a mobile-optimized activation page — no app download required
- [ ] Activation flow: identity verification (last 4 SSN or DOB) → set PIN → view balance — **maximum 3 steps**
- [ ] SMS link expires after 72 hours; recipient can request a new link via a "Resend" option on the expired page
- [ ] Page renders correctly on Android and iOS default browsers (Chrome, Safari)
- [ ] All text at minimum 16px font size; form fields sized for thumb interaction on a 375px screen
- [ ] Error messages written at 6th-grade reading level with a clear next step

**Definition of Done:** ✅ Coded · ✅ QA tested · ✅ SMS delivery tested end-to-end · ✅ Mobile rendering verified (375px, 768px) · ✅ Expiry/resend flow tested · ✅ Accessibility checked (WCAG 2.1 AA) · ✅ Release notes updated

---

### Story CW-F02-S2 — Guided First-Time Wallet Tour

**As a** newly activated recipient,  
**I want to** see a brief guided tour of my wallet on first login,  
**So that** I understand my balance, what I can spend it on, and how to get help — without calling support.

**Acceptance Criteria:**
- [ ] Tour triggers automatically on first login after activation — not on subsequent logins
- [ ] Tour is **4 screens maximum:** balance overview → approved vendor marketplace → how to pay → how to get help
- [ ] Recipient can skip tour at any time; can replay it from the Help section
- [ ] All tour copy written at a 6th-grade reading level (validated via Flesch-Kincaid)
- [ ] Tour available in English and Spanish (v1); French and Arabic in v2
- [ ] Tour completion tracked per user — reported in admin dashboard as onboarding quality metric
- [ ] Tour does not trigger again if recipient clears cache or switches devices

**Definition of Done:** ✅ Coded · ✅ QA tested · ✅ Skip/replay flow tested · ✅ Reading level validated · ✅ ES translation reviewed by native speaker · ✅ Completion tracking verified · ✅ Release notes updated

---

## 5. RICE Prioritization

| Feature / Story | Reach | Impact | Confidence | Effort (wks) | RICE | Priority |
|---|---|---|---|---|---|---|
| SMS activation link | 8 | 10 | 8 | 4 | 160 | **P0** |
| 3-step mobile activation flow | 9 | 9 | 8 | 4 | 162 | **P0** |
| Guided first-time tour | 9 | 7 | 8 | 3 | 168 | **P0** |
| Spanish language support | 7 | 8 | 7 | 3 | 131 | P1 |
| Arabic language support | 4 | 8 | 7 | 3 | 75 | P2 |

---

## 6. Out of Scope (v1)

- App download / native mobile app (v2)
- Biometric login — Face ID, fingerprint (v2)
- Arabic and French language support (v2)
- Video tutorial option (v2)
- Caregiver/proxy activation flow (v2 — needed for elderly recipients)

---

## 7. One-Pager Summary

| | |
|---|---|
| **Problem** | Activation flows designed for tech-comfortable users create abandonment among low-income, elderly, and digitally-limited recipients — public funds go unspent, the program fails its mission. |
| **Users** | Program Recipient (variable digital literacy, often mobile-only) · Agency Administrator |
| **Solution** | SMS-based activation (no email required) · 3-step maximum mobile flow · Guided 4-screen first-time tour · 6th-grade reading level · Thumb-optimized at 375px |
| **In Scope (v1)** | SMS activation · 3-step flow · First-time tour · English + Spanish · Mobile-optimized |
| **Out of Scope (v1)** | App download · Biometric login · Arabic/French · Proxy activation |
| **Key Metrics** | Activation within 24hr ≥80% · Support tickets ↓50% · Mobile completion ≥85% · Time-to-activate ≤5 min |

---

*Deepshikha Dash · Product Manager · Austin, TX · [github.com/Deepshikhadash](https://github.com/Deepshikhadash)*
