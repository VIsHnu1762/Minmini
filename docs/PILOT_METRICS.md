# Minmini Pilot Metrics (Edition 1)

Last updated: 30 March 2026
Scope: Edition 1 pilot for independent Minmini model

## 1. Why These Metrics

This metric set is designed to answer one question:

Can Minmini deliver a fair, repeatable, useful builder experience across League and Lab in a real pilot?

## 2. Success Criteria Summary

Pilot is considered successful if:

- participation quality is healthy
- submission completion is strong
- validation is reliable
- judging is trusted
- users want to return

## 3. North Star and Primary KPIs

### North Star

- `Qualified submissions per edition`

Definition: Number of submissions that pass blocker validation and are eligible for ranking.

### Primary KPIs

| KPI | Target | Why it matters |
|---|---|---|
| Waitlist to registration conversion | >= 35% | Indicates messaging and onboarding fit |
| Registration to submission conversion | >= 60% | Shows operational and mentorship effectiveness |
| Blocker validation false-positive rate | <= 5% | Measures fairness and trust in validation |
| Appeal rate | <= 10% | Signal for rule clarity and validation confidence |
| Appeal reversal rate | <= 20% of appeals | Detects systemic scoring/validation errors |
| Participant satisfaction (post-event) | >= 4.2/5 | Product-market signal for repeatability |
| Intent to return for next edition | >= 65% | Early retention indicator |
| Mentor response SLA (active event) | <= 15 minutes median | Measures participant support quality |

## 4. League Operational Metrics

| Category | Metric | Target |
|---|---|---|
| Acquisition | Total registrations | Target set per host capacity |
| Team health | Valid team ratio (2-8 members) | >= 95% |
| Submission quality | Submissions with complete deliverables | >= 85% |
| Validation | Repo accessibility pass rate | >= 95% |
| Judging | Avg judge scoring completion on time | >= 95% |
| Reliability | Stage-time incident count | 0 critical incidents |
| Governance | Appeals resolved within SLA | >= 95% |

## 5. Lab Learning Metrics

| Metric | Definition | Target |
|---|---|---|
| First feedback time | Time from project connection to first actionable feedback | <= 5 minutes |
| Improvement adoption rate | % of users who fix at least one flagged issue | >= 60% |
| Readiness progression | % moving from `Improving` to `Hackathon Ready` | >= 40% |
| Feedback usefulness score | User rating of Lab suggestions | >= 4.0/5 |

## 6. Trust and Fairness Metrics

| Metric | Target |
|---|---|
| Judge variance outlier rate | <= 10% |
| Manual review turnaround | <= 24 hours |
| Transparency score (rules understood) | >= 80% affirmative |
| Consent compliance incidents | 0 |

## 7. Host Partner Metrics

| Metric | Target |
|---|---|
| Host onboarding completion before launch | 100% |
| Host checklist compliance | >= 95% |
| Host NPS (organizer confidence) | >= 40 |
| Repeat-host intent | >= 70% |

## 8. Instrumentation Plan

Capture metrics from:

- registration and submission events
- validation logs and outcome codes
- judging workflow timestamps
- appeals workflow states
- feedback forms and NPS surveys
- mentor help-desk response logs

Minimum implementation for pilot:

1. Single source sheet or database table per metric family.
2. Daily dashboard during active edition.
3. Final pilot report within 7 days after results.

## 9. Reporting Cadence

- Weekly pre-event tracking during onboarding and registrations
- Daily tracking during event window
- T+2 day fairness and appeals report
- T+7 day pilot outcome report

## 10. Go/No-Go Rules for Edition 2

Proceed to Edition 2 only if all are true:

- Registration to submission conversion >= 50%
- False-positive blocker rate <= 8%
- Participant satisfaction >= 4.0/5
- No unresolved critical fairness issues
- Host partner readiness confirmed

If not met, run a focused remediation sprint before next edition.

## 11. Pilot Retrospective Template

After pilot, document:

1. What exceeded target
2. What missed target and why
3. Which threshold should be revised
4. Which rule/process created friction
5. What must change before next edition
