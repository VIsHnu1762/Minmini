# Minmini Risk Register

Last updated: 30 March 2026
Scope: Minmini League + Minmini Lab (R&D to Pilot)

## Risk Scoring Model

- Likelihood: `Low`, `Medium`, `High`
- Impact: `Low`, `Medium`, `High`
- Priority: `P1` (critical), `P2` (major), `P3` (minor)

## Active Risks

| ID | Risk | Area | Likelihood | Impact | Priority | Early Warning Signal | Mitigation Plan | Owner |
|---|---|---|---|---|---|---|---|---|
| R-01 | Low event registrations | League Growth | Medium | High | P1 | Waitlist-to-registration conversion below 25% | Improve GTM, campus ambassador loop, early-bird incentives, referral campaigns | Growth Lead |
| R-02 | High drop from registration to submission | League Ops | High | High | P1 | Submission rate below 50% | Mid-event mentor check-ins, reminder automation, simplified submission form, checkpoint reviews | Program Lead |
| R-03 | Validation false positives block fair teams | Validation | Medium | High | P1 | Appeal rate above 10% of submissions | Human review lane for all blocker flags, threshold tuning, evidence logs, fallback to manual panel | Validation Lead |
| R-04 | Judge inconsistency across tracks | Evaluation | Medium | High | P1 | Wide scoring variance between judges on similar quality projects | Judge calibration session, shared anchor examples, normalized scoring pass, tie-break protocol | Jury Lead |
| R-05 | GitHub API limits/timeouts during final validation | Infrastructure | Medium | Medium | P2 | API error bursts near deadline | Queue-based retries, backoff, precompute snapshots, staged reveal instead of live compute | Platform Lead |
| R-06 | Sponsor dependency before product maturity | Business | Medium | Medium | P2 | Revenue forecast depends on unconfirmed sponsors | Use lean pilot budget, phase sponsorship to Season 2, prioritize user traction first | Founding Team |
| R-07 | Weak mentor availability during event | Community Quality | Medium | Medium | P2 | Mentor response time above 30 minutes | Mentor pool overbooking, shift schedule, alumni mentor opt-in, async Q&A channels | Community Lead |
| R-08 | Privacy concerns around LinkedIn/alumni visibility | Trust/Compliance | Medium | High | P1 | User complaints about unwanted visibility/contact | Consent-first defaults, granular visibility settings, explicit opt-in and instant opt-out | Product Lead |
| R-09 | Product confusion between League and Lab | Product | High | Medium | P1 | Users ask whether Lab score affects League rank | Clear mode separation in UX, separate docs, separate dashboards, explicit messaging | Product Lead |
| R-10 | Scope creep delays pilot launch | Execution | High | High | P1 | New features added weekly without pilot value | Strict MVP boundary, fortnightly freeze, priority gate by pilot metrics | PM |
| R-11 | Host partner quality varies widely | Network Model | Medium | High | P1 | Participant feedback variability by host | Standard host onboarding kit, mandatory quality checklist, host scorecard, probation model | Partner Ops |
| R-12 | Appeals process is unclear or slow | Governance | Medium | Medium | P2 | Appeals unresolved after 72 hours | SLA-backed appeal workflow, evidence template, designated review panel | Governance Lead |
| R-13 | AI feedback quality is generic/unhelpful | Lab Experience | Medium | Medium | P2 | Low usefulness rating on AI reports | Prompt iteration, rubric-grounded feedback, mandatory actionable recommendations | AI Lead |
| R-14 | Security leaks in submitted repositories | Trust/Security | Low | High | P2 | Secret detection alerts in multiple repos | Secret scanning checks, warning notices, private handling guide for teams | Security Lead |

## Closed or Watchlist Risks

| ID | Status | Notes |
|---|---|---|
| R-15 | Watchlist | Live numeric score reveal was rejected in favor of grade reveal with hidden numeric calculations |

## Monthly Review Cadence

1. Update risk likelihood and impact from real pilot data.
2. Move high-severity risks to weekly review.
3. Attach mitigation outcomes to each risk.
4. Archive resolved risks with date and evidence.

## Escalation Rule

- Any risk with `Priority P1` and no active mitigation owner must be escalated within 24 hours.
- Any risk that affects fairness, safety, or trust is automatically P1.
