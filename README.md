# Minmini

> Small sparks. Big impact.

Minmini is currently being researched as an independent builder ecosystem with two connected layers:

- **Minmini League**: a recurring competitive hackathon league with rankings, grades, validation, and leaderboards.
- **Minmini Lab**: an open project validation and beginner-guidance layer that helps builders improve projects anytime.

This repository is still in the **R&D and planning phase**. It is not in active development yet.

The earlier institution-hosted version of the plan is preserved in [Campus minmini.MD](Campus%20minmini.MD).

---

## Current Direction

The current research direction is to make Minmini an **independent recurring platform**, not a single-institution product.

That means:

- Minmini owns the platform, rules, validation engine, and season structure.
- Colleges, clubs, communities, and chapters can become **host partners** instead of platform owners.
- Builders keep one persistent identity across multiple editions and host partners.
- Competitive hackathons and beginner project-building support exist in the same ecosystem, but as separate product layers.

---

## Why This Pivot Makes Sense

An institution-only model is useful, but it limits reach and network effects. An independent platform creates stronger long-term value because:

- builders can participate across multiple events, not just one campus event
- rankings and tiers can persist across seasons
- host partners do not need to build their own operations system
- Minmini can support both competition and learning
- beginner users can enter through Lab before they are ready for League

The campus model still matters, but now it becomes one deployment mode inside a larger platform strategy.

---

## Product Model

### 1. Minmini League

Minmini League is the competitive layer.

It includes:

- recurring hackathon editions
- official submission intake
- Git and repository validation
- track-based judging
- internal numeric scoring with public grade-based reveal
- division and leaderboard systems
- builder points, tiers, and hall of fame
- post-event AI improvement reports

League is designed for fairness, repeat participation, and visible recognition.

### 2. Minmini Lab

Minmini Lab is the learning and project-improvement layer.

It includes:

- open project validation for anyone, anytime
- beginner-friendly project guidance
- repo health checks
- documentation and structure feedback
- Git hygiene guidance
- AI coaching and improvement suggestions
- project readiness states such as `Improving`, `Hackathon Ready`, or `Showcase Ready`

Lab is designed to reduce confusion for beginners and help them build real, presentable projects.

---

## The Core Problem We Are Researching

Beginners usually do not struggle because they lack interest.

They struggle because they can write code in small pieces, follow tutorials, or use AI to generate code, but they do not know how to turn that into a complete project that is structured, documented, and presentable.

The gap is not just coding knowledge. The gap is **project-building clarity**.

Minmini Lab is meant to solve that gap, while Minmini League gives builders a place to apply and prove those skills in recurring competitions.

---

## What Beginners Usually Lack

These are the main beginner problems currently being researched.

| Beginner gap | What it looks like in practice | How Minmini Lab can help |
|---|---|---|
| Project direction | "I learned React/Python, but I don't know what to build." | Guided project prompts, beginner tracks, use-case suggestions |
| Scoping ability | Ideas are too big, too vague, or impossible for current skill level | Break ideas into MVP, core, and optional features |
| Repo structure | Random folders, unclear naming, no consistent layout | Structure checks, templates, repo health feedback |
| README quality | Missing setup, weak problem statement, no usage instructions | Guided README checklist and AI suggestions |
| Architecture thinking | Can build pages or functions, but cannot explain how the system works | Simple architecture explanation prompts and improvement cues |
| Git confidence | Few commits, poor messages, Git used like file storage | Git hygiene feedback and commit-quality guidance |
| Deployment gap | Project works locally but is never shipped anywhere | Deploy-readiness guidance and project completion checklist |
| Quality benchmark | Builder does not know whether the project is actually good enough | Grades, readiness states, category-wise signals |
| Feedback loop | No mentor, no reviewer, no consistent feedback source | Continuous validation and AI-assisted improvement reports |
| Portfolio awareness | Project exists, but is not presentable in public | Showcase-ready checklist: title, problem, demo, repo, architecture |
| Safe AI usage | Builder can generate code but cannot refine or validate it properly | AI-assisted building guidance and validation-first workflows |
| Iteration habit | Builder stops after version 1 | Progress tracking and suggested next improvements |

---

## What Minmini Is Actually Trying To Build

Minmini is not just trying to host hackathons.

It is trying to build a full builder lifecycle:

1. Learn how real projects are structured.
2. Build with guidance inside Minmini Lab.
3. Improve based on validation and feedback.
4. Enter Minmini League when ready.
5. Compete fairly in recurring editions.
6. Accumulate reputation, points, tiers, and portfolio strength over time.

That lifecycle is the main strategic idea under research.

---

## Research Focus Areas Right Now

### 1. League-Lab Separation

We are explicitly treating League and Lab as different product modes.

- **League** behaves like an official evaluator.
- **Lab** behaves like a coach.

This separation matters because a system cannot be both highly supportive and highly punitive in the same user flow without confusing users.

### 2. Independent Platform Model

We are researching Minmini as a platform that can support:

- campus-hosted editions
- club-hosted editions
- community-hosted editions
- independent online editions

This requires a host-partner model instead of a single admin model.

### 3. Validation System Design

The validation system currently being explored has three layers:

- **Eligibility validation**: repo exists, required deliverables present, no blocker issues
- **Common quality validation**: documentation, structure, execution, demo clarity
- **Track-specific evaluation**: field-specific depth depending on the problem category

### 4. Grade-Based Public Reveal

We are leaning toward:

- keeping internal numeric scoring for audits, fairness, and tie-breaks
- showing only grades publicly during results and on public dashboards

This reduces score arguments while keeping the system defensible.

### 5. Beginner Project Readiness

We are researching how Minmini Lab can tell a beginner:

- what is missing from the project
- what to improve next
- whether the repo is becoming hackathon-ready or showcase-ready

That is a more useful beginner outcome than a single opaque score.

---

## How Different Types Of Projects Should Be Validated

Projects from different fields should not be judged by one flat meaning of "best".

The current thinking is:

### Universal Validation

This applies to every project:

- repo identity and submission integrity
- required documentation
- event-window contribution checks
- deliverable completeness
- anti-plagiarism and security blockers

### Common Execution Validation

This also applies across fields:

- problem clarity
- technical execution
- completeness
- documentation quality
- demo clarity
- practical usefulness

### Track-Specific Evaluation

This changes by domain:

- AI / ML
- Web / SaaS
- DevTools
- IoT / Hardware
- Social Impact
- HealthTech
- EdTech
- Open Innovation

AI can help with common quality checks, but human judges should still evaluate domain depth.

---

## Platform Roles In The Independent Model

### Builder

- uses Lab to improve projects
- joins League editions
- builds profile, points, tier, and portfolio

### Judge

- evaluates projects using common + track-specific rubric
- focuses on quality and domain fit, not manual repo policing

### Host Partner

- runs a Minmini edition under shared rules
- handles venue, local logistics, and possibly local judges

### Central Minmini Admin

- owns validation rules
- owns scoring logic and platform governance
- manages seasons, rankings, appeals, and product consistency

---

## What Still Belongs To The Campus Version

The following ideas are still valid for a campus deployment model and remain preserved in [Campus minmini.MD](Campus%20minmini.MD):

- institution-facing hackathon operations
- faculty and organizer workflows
- campus-specific divisions and logistics
- local event management structure
- institution-led rollout framing

That document remains useful as a host-partner or campus-edition adaptation of Minmini.

---

## Working Principles For The Independent Platform

- Builders own one identity across editions.
- Host partners run events, but Minmini owns standards.
- Lab should be supportive, not punitive.
- League should be strict, transparent, and auditable.
- Public score display should be simplified to grades.
- Private numeric scoring should remain available for appeals and tie-breaks.
- Consent must be explicit for public identity fields such as LinkedIn, alumni visibility, and future contact.

---

## Current Research Questions

These are the major unanswered questions still under exploration.

### Product Questions

- What is the minimum useful version of Minmini Lab?
- What should be rule-based vs AI-based in the first version?
- How much of project guidance should be universal vs stack-specific?

### Competition Questions

- Which project tracks should exist in the first season?
- What grade bands should be public?
- What minimum validation threshold should make a project rank-eligible?

### Operations Questions

- How should host partners be onboarded?
- How should appeals work across different hosts?
- What should be centralized vs delegated locally?

### Community Questions

- How should builder tiers influence visibility and recognition?
- How should alumni and mentor discovery work with full consent?
- How should Lab users convert into League participants over time?

---

## Immediate R&D Deliverables

The planning work currently points toward these next documents or design tasks:

1. Independent platform PRD
2. Minmini League vs Minmini Lab feature split
3. Track-based judging framework
4. Git validation policy and thresholds
5. Host-partner operating model
6. Beginner journey and Lab feedback model

---

## Summary

Minmini is now being shaped as an **independent recurring hackathon league plus a beginner project-building support layer**.

The key insight is simple:

> Most beginners do not fail because they cannot code. They fail because they do not yet know how to build, validate, present, and improve real projects.

Minmini Lab addresses that gap. Minmini League gives builders a place to prove growth over time.

That is the main direction currently under research.