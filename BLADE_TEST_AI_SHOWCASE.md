# Blade Test — AI Engineering Showcase

### An AI-assisted platform that turns user stories into executable, self-healing test suites — backed by a production-grade LLM quality, safety, and observability stack.

> From an acceptance criterion to a running regression suite — without writing a line of code.

This document showcases the **AI capabilities** and **product features** of Blade Test. It focuses on *what the system does* and *how the AI behaves*, illustrated with flow diagrams — not internal implementation.

---

## The Problem It Solves

Software teams ship faster than QA can keep up. Test authoring is manual and slow, automation locators break every sprint, regression is a flaky ritual rather than a system, and nobody can point to exactly which acceptance criteria are actually covered. Meanwhile, the user stories themselves are often ambiguous or incomplete — defects that only surface *after* a test (or a feature) has already been built on top of them.

**Blade Test closes that entire loop.** It pulls user stories straight from Jira, analyses them for gaps and ambiguity, generates a complete test suite from the acceptance criteria, converts the automatable cases into real Playwright automation, runs them in a live browser with screenshot/video evidence, self-heals when the UI changes, and syncs the results back to Jira, Xray, TestRail, Azure DevOps, and Zephyr — continuously.

## End-to-End Capability Map

```
   JIRA / CONFLUENCE                BLADE TEST                       TEST MANAGEMENT
   ┌──────────────┐         ┌────────────────────────┐         ┌──────────────────┐
   │ User stories │ ──pull─►│ 1. Gap analysis &      │         │ Jira             │
   │ + acceptance │         │    story improvement   │ ──sync─►│ Xray             │
   │ criteria     │         │ 2. AI test generation  │         │ TestRail         │
   │ + spec docs  │         │ 3. Quality & safety    │         │ Azure DevOps     │
   └──────────────┘         │    audit               │         │ Zephyr Scale     │
                            │ 4. No-code automation  │         └──────────────────┘
                            │ 5. Playwright MCP exec │
                            │    + screenshots/video │
                            │ 6. Self-healing        │
                            │ 7. Continuous regress. │
                            └────────────────────────┘
```

---

## What's Inside

**Core AI pipeline:** What It Does · AI Generation Flow · Story Gap Analysis · Coverage Analysis · Quality & Safety Audit · PII Protection

**Automation & execution:** No-Code Automation · Playwright MCP · Test Script Generation · Screenshot/Video/Evidence · Self-Healing Cascade

**Test generation inputs:** Jira/Confluence Integrations · API Test Generation · Generate from a Live URL

**Test types & quality:** Visual Regression · Accessibility · Flaky Detection · Lifecycle Governance · Continuous Regression

**Platform:** Team Dashboard · Observability & Cost Governance · Enterprise Security · MCP Tool Server

**Reference:** Capability Summary · Technology · What Makes It Different

---

## What It Does — In One Picture

```
        ┌─────────────────────────────────────────────────────────────┐
        │                      USER STORY + AC                         │
        │            (typed, pasted, or pulled from Jira)              │
        └───────────────────────────┬─────────────────────────────────┘
                                     │
                                     ▼
        ╔═════════════════════════════════════════════════════════════╗
        ║   1.  AI GENERATION                                          ║
        ║       Reads acceptance criteria → produces a full set of    ║
        ║       test cases: positive, negative, edge, non-functional. ║
        ╠═════════════════════════════════════════════════════════════╣
        ║   2.  AI QUALITY & SAFETY AUDIT                              ║
        ║       Scores every case; flags hallucination, bias, PII,    ║
        ║       ambiguity, and out-of-scope content before it ships.  ║
        ╠═════════════════════════════════════════════════════════════╣
        ║   3.  NO-CODE AUTOMATION                                     ║
        ║       Classifies automatable cases, expands them into       ║
        ║       executable browser steps — no scripting required.     ║
        ╠═════════════════════════════════════════════════════════════╣
        ║   4.  LIVE EXECUTION + SELF-HEALING                         ║
        ║       Runs each test in a real browser. When the UI shifts, ║
        ║       a multi-strategy healer recovers the element.         ║
        ╠═════════════════════════════════════════════════════════════╣
        ║   5.  CONTINUOUS REGRESSION (HEARTBEAT)                      ║
        ║       Runs the suite 24/7, syncs results to Jira, and       ║
        ║       learns from every run.                                ║
        ╚═════════════════════════════════════════════════════════════╝
```

---

## The AI Generation Flow

The system does **not** make a single naive prompt call. Generation is a staged flow where deterministic analysis guides the LLM, and every output is independently validated.

```
   Acceptance Criteria
          │
          ▼
   ┌───────────────────────────────┐
   │  CRITERIA ANALYSIS            │   Detects test categories, coverage gaps,
   │  (deterministic, no LLM)      │   ambiguity, contradictions, and domain
   └───────────────┬───────────────┘   (auth / payment / infra each differ).
                   │
                   ▼
   ┌───────────────────────────────┐
   │  PIPELINE SHAPING             │   Confidence-scored signals choose a
   │  (zero-LLM signal engine)     │   strategy: depth · breadth · hybrid ·
   └───────────────┬───────────────┘   risk-focused, and estimate case count.
                   │
                   ▼
   ┌───────────────────────────────┐
   │  CONTEXT RETRIEVAL (RAG)      │   Hybrid keyword + semantic retrieval of
   │  keyword + semantic + diversity│  relevant past generations and patterns.
   └───────────────┬───────────────┘
                   │
                   ▼
   ┌───────────────────────────────┐
   │  PROMPT ASSEMBLY              │   Instruction hierarchy + few-shot
   │                               │   examples + injected context blocks.
   └───────────────┬───────────────┘
                   │
                   ▼
   ┌───────────────────────────────┐
   │  LLM GENERATION               │   OpenAI · Groq · or your own key (BYOK).
   └───────────────┬───────────────┘
                   │
                   ▼
   ┌───────────────────────────────┐
   │  POST-LLM VALIDATION          │   Hallucination · bias · PII · grounding ·
   │  (see Quality & Safety)       │   consistency — before anything is shown.
   └───────────────────────────────┘
```

**AI skills demonstrated:** prompt engineering with explicit instruction hierarchies, few-shot grounding, retrieval-augmented generation, domain-aware pipeline control, and multi-provider LLM orchestration.

---

## User Story Gap Analysis & Improvement Suggestions

Before a single test is written, Blade Test reads the user story and tells you whether it is actually ready. It scores the acceptance criteria live, surfaces hidden assumptions, and proposes concrete rewrites that flow back into Jira — so weak stories are fixed *before* they cost a defect.

```
   User Story + AC (from Jira)
          │
          ▼
   ┌────────────────────────────────────────────────┐
   │  STORY READINESS ANALYSIS                        │
   │  • Estimated test-case count & quality forecast  │
   │  • Ambiguity detection ("Step 3 is vague")       │
   │  • Contradiction detection                       │
   │  • Missing-path detection (no negative case,     │
   │    no boundary/edge case, no NFR coverage)       │
   │  • Implicit precondition surfacing               │
   │    ("user must be logged in with a non-empty     │
   │     cart before step 1")                         │
   │  • Domain-aware gaps (auth / payment / infra     │
   │    each judged against different baselines)      │
   └───────────────────────┬──────────────────────────┘
                           │
                           ▼
   ┌────────────────────────────────────────────────┐
   │  IMPROVEMENT SUGGESTIONS                         │
   │  Specific, reviewable rewrites of the story/AC   │
   │  → Approve / Reject → push back to Jira          │
   └────────────────────────────────────────────────┘
```

The suggestion workflow captures domain knowledge that normally lives only in QAs' heads: a QA proposes an improvement, a product owner reviews it, and approved suggestions sync straight back to the Jira issue. The loop is closed — **better stories produce better tests, which produce fewer rework cycles.**

**AI skills demonstrated:** requirements analysis with an LLM, ambiguity/contradiction detection, coverage-gap reasoning, and a human-governed AI suggestion workflow.

---

## Coverage Analysis — From Folklore to a Number

```
   COVERAGE REPORT  —  per acceptance criterion
   ────────────────────────────────────────────────
   AC1  Valid code applies discount     ████████████ 100%  (3 cases)
   AC2  Expired code is rejected         ████████████ 100%  (2 cases)
   AC3  Minimum cart enforced            ██████······  50%  (1 case)
   AC4  Stacking rules                   ············   0%  UNCOVERED
   AC5  Code shown on order summary      █████████···  75%  (2 cases)
   ────────────────────────────────────────────────
   Suggested additions →  [ Generate ]  one click to fill each gap
```

Every test case is mapped back to the acceptance criterion it covers. Gaps are obvious at a glance, and a single click generates focused cases to close them. Coverage stops being a vague claim and becomes a tracked, exportable number for release sign-off and compliance.

---

## AI Quality & Safety Audit

Every generated suite passes through an automated evaluation layer before a human ever sees it. Deterministic checks run first (fast, free, repeatable); only when signals are weak does the system escalate to an LLM judge.

```
   Generated Test Cases
          │
          ▼
   ┌──────────────────────────────────────────────┐
   │  DETERMINISTIC CHECKS  (fast · no LLM cost)    │
   │  ┌────────────────┐ ┌────────────────┐         │
   │  │ Hallucination  │ │ Bias detection │         │
   │  │ guard          │ │ (role/locale/  │         │
   │  │ (grounding vs  │ │  demographic/  │         │
   │  │  the AC)       │ │  data/privilege)│        │
   │  └────────────────┘ └────────────────┘         │
   │  ┌────────────────┐ ┌────────────────┐         │
   │  │ PII detection  │ │ Relevance &    │         │
   │  │ & redaction    │ │ consistency    │         │
   │  └────────────────┘ └────────────────┘         │
   └───────────────────────┬────────────────────────┘
                           │
              signals weak?│
                  ┌────────┴────────┐
               NO │                 │ YES
                  ▼                 ▼
          ┌──────────────┐  ┌─────────────────────────┐
          │ Pass / Warn  │  │  LLM-JUDGE FALLBACK      │
          │ /Fail report │  │  faithfulness +          │
          │              │  │  relevance evaluation    │
          └──────────────┘  └─────────────────────────┘
                  │                 │
                  └────────┬────────┘
                           ▼
                ┌───────────────────────┐
                │  5-DIMENSION SCORECARD │
                │  Completeness ·        │
                │  Clarity · Validity ·  │
                │  Consistency ·         │
                │  Relevance             │
                └───────────────────────┘
```

**AI skills demonstrated:** LLM-as-a-judge evaluation, hallucination/groundedness scoring, bias auditing, PII scrubbing before any data reaches a model, and a cost-aware "escalate only when uncertain" evaluation strategy.

---

## PII Protection — Data Never Leaves Clean

```
   Story content
        │
        ▼
   ┌──────────────────┐      scrub       ┌──────────────────┐
   │  Detect PII      │ ───────────────► │  Safe placeholders│
   │  (email, card,   │                  │  sent to the LLM  │
   │   token, ID…)    │                  │                   │
   └──────────────────┘                  └─────────┬────────┘
                                                    │
                                                    ▼
                                          ┌──────────────────┐
                                          │  LLM response     │
                                          └─────────┬────────┘
                                                    │ rehydrate
                                                    ▼
                                          ┌──────────────────┐
                                          │  Original values  │
                                          │  restored locally │
                                          └──────────────────┘
```

No raw PII is ever transmitted to an AI provider. Sensitive values are swapped for deterministic placeholders before the call and restored afterward — with a validation guard ensuring every placeholder is accounted for.

---

## No-Code Automation Flow

```
   Approved Test Cases
        │
        ▼
   ┌────────────────────────┐
   │  CLASSIFIER            │   Scores each case for automation feasibility
   │                        │   and regression candidacy + confidence %.
   └───────────┬────────────┘
               │  high-confidence cases only
               ▼
   ┌────────────────────────┐
   │  STEP EXPANDER         │   Expands plain-language steps into granular,
   │                        │   executable browser actions. Quality-scored
   │                        │   and auto-corrected.
   └───────────┬────────────┘
               ▼
   ┌────────────────────────┐
   │  EXECUTABLE SUITE      │   Runnable specs + reusable page-object library.
   └────────────────────────┘
```

**AI skills demonstrated:** automation-feasibility classification with calibrated confidence, natural-language-to-action expansion, and automated quality validation with self-correction.

---

## Live Execution + Self-Healing Cascade

When a locator fails at runtime, the system does not give up — it escalates through progressively broader recovery strategies, ending in AI vision analysis.

```
   Step runs in a real browser
        │
        ▼
   Locator found?  ──── yes ───►  Pass · capture evidence
        │ no
        ▼
   ┌─────────────────────────────────────────────────────┐
   │            SELF-HEALING CASCADE                       │
   │   1. Wait for DOM to stabilise → re-scan             │
   │   2. Scroll element into view → re-scan              │
   │   3. Fuzzy text + synonym matching                   │
   │   4. Structural proximity (nearby labels/siblings)   │
   │   5. Stable-attribute substring matching             │
   │   6. AI VISION analysis (screenshot reasoning)       │
   │   7. Full-page scroll + vision for off-screen items  │
   └───────────────────────┬─────────────────────────────┘
                           │
              still failing?│
                  ┌─────────┴─────────┐
               NO │                   │ YES
                  ▼                   ▼
          ┌──────────────┐   ┌────────────────────┐
          │ Healed ·     │   │ Human-in-the-loop  │
          │ log strategy │   │ confirmation prompt │
          └──────────────┘   └────────────────────┘
```

Vision-based recovery uses **Claude** (primary) with **GPT-4o** fallback to identify elements from a screenshot when DOM matching fails. Every heal is logged with the strategy that rescued it, so UI drift is visible over time.

**AI skills demonstrated:** multimodal (vision) LLM use, confidence-thresholded escalation, human-in-the-loop safety gating, and resilient agent design.

---

## Playwright MCP Browser Automation

Execution is driven through the **Model Context Protocol (MCP)** — the same open standard used to give AI models structured tool access. Blade Test speaks MCP to a Playwright browser, so the AI agent perceives and acts on the page through a typed, structured interface rather than brittle string selectors.

```
   AI EXECUTION AGENT
        │
        │  Model Context Protocol (MCP)
        ▼
   ┌────────────────────────────────────────────────┐
   │  PLAYWRIGHT MCP BROWSER                          │
   │  • Structured page snapshots (accessibility tree)│
   │  • Navigate · click · type · assert · wait       │
   │  • Multi-engine: Chromium · Firefox · WebKit     │
   │  • Headless or headed                            │
   └───────────────────────┬──────────────────────────┘
                           │
                           ▼
   ┌────────────────────────────────────────────────┐
   │  REAL APPLICATION UNDER TEST                     │
   │  Dev · Staging · Prod (read-only)               │
   └────────────────────────────────────────────────┘
```

Because the agent works from structured, AI-friendly page snapshots, it can reason about elements semantically — which is exactly what makes the self-healing and vision-fallback strategies possible. An **auto-login pre-flight** detects when the first navigation lands on a sign-in page and authenticates before the user's scenario begins, removing a whole class of "tests failed because we forgot to log in" failures.

**AI skills demonstrated:** Model Context Protocol integration, agentic tool use, structured-perception-driven automation, and multi-environment orchestration.

---

## Test Script Generation

Every run doesn't just pass or fail — it produces **real, exportable, industry-standard Playwright code**. The plain-language test cases are compiled into runnable TypeScript specs plus a reusable page-object library, ready to drop into an existing CI repository.

```
   Plain-language test case
        │
        ▼
   ┌────────────────────────────────────────────────┐
   │  SCRIPT GENERATION                               │
   │  • Executable Playwright spec per scenario       │
   │  • Auto-generated Page Object Model library      │
   │  • Stable locators with ranked fallbacks         │
   │  • Assertions derived from expected results      │
   │  • Test data resolved from project sources       │
   │    (no hard-coded credentials in scripts)        │
   └───────────────────────┬──────────────────────────┘
                           │
                           ▼
   ┌────────────────────────────────────────────────┐
   │  EXPORT  →  copy-paste-ready · CI-ready          │
   └────────────────────────────────────────────────┘
```

**AI skills demonstrated:** code generation, page-object abstraction, assertion synthesis from natural-language expected results, and secure test-data handling.

---

## Screenshot, Video & Evidence Capture

Nothing about an AI-driven run is a black box. Every step is recorded as visual, downloadable evidence — defensible in a compliance review, attachable to a Jira ticket, and invaluable in a post-mortem.

```
   LIVE RUN
        │
        ├──► 📸 Per-step screenshots        (what the page looked like at each action)
        ├──► 🎬 Full session video           (the entire run, replayable)
        ├──► 🔎 Playwright trace             (step-by-step debug timeline)
        ├──► 📄 Step audit trail (JSON)      (chosen target, heal strategy, confidence)
        └──► 🗜️  Full session bundle (.zip)   (everything, one download)
```

Each artifact tile lights up the moment its file is written. The run summary headlines three signals — **Healed** (locator rescues), **Vision fallback** (AI-resolved elements), and **Confirmations** (human interventions) — giving a QA lead an instant read on suite health and UI drift.

**Engineering demonstrated:** browser artifact capture and retention, trace/video recording, and structured evidence bundling for auditability.

---

## Integrations — Pull Requirements, Push Results

Blade Test sits in the middle of an existing toolchain, pulling requirements from documentation sources and pushing test artifacts and results to test-management platforms — bidirectionally.

```
   ── PULL (requirements) ──►          BLADE TEST          ──► PUSH (tests + results) ──►

   ┌──────────────┐                ┌──────────────┐               ┌──────────────────┐
   │  Jira        │  stories/AC    │              │  test cases   │  Jira            │
   │  Confluence  │  spec docs ───►│  generate ·  │──── runs ────►│  Xray            │
   │              │                │  automate ·  │   suggestions │  TestRail        │
   │              │                │  validate    │   status      │  Azure DevOps    │
   └──────────────┘                └──────────────┘               │  Zephyr Scale    │
                                                                   └──────────────────┘
```

| Integration | Direction | What flows |
|---|---|---|
| **Jira** | Bidirectional | Pull stories + AC; push test summaries, status updates, and approved story suggestions |
| **Confluence** | Pull | Ingest specification/documentation pages as generation context |
| **Xray** | Push | Sync generated tests and execution results into Xray |
| **TestRail** | Push | Export test cases and runs into TestRail suites |
| **Azure DevOps** | Bidirectional | Sync work items and test artifacts with ADO |
| **Zephyr Scale** | Push | Publish tests and results into Zephyr |

Auto-pull keeps new stories flowing in on a configurable interval; master push controls what flows back out — execution summaries as comments, approved suggestions, and story-status updates from test results. Everything runs on a **Bring-Your-Own-Key** model, so story content and test artifacts stay inside your own account boundary.

**Engineering demonstrated:** multi-platform API integration (REST), bidirectional sync with conflict handling, documentation ingestion for RAG context, and OAuth/token-based authentication.

---

## API Test Generation — From a Spec to a Suite

Blade Test doesn't stop at UI tests. Point it at an API contract and it generates a full API test suite automatically — no manual request-building.

```
   OpenAPI · Postman · HAR · cURL
          │  (auto-detected format)
          ▼
   ┌────────────────────────────────────────────────┐
   │  API TEST SYNTHESIS                              │
   │  • Happy-path tests for every endpoint           │
   │  • Property mutation tests (invalid types,       │
   │    boundaries, missing/extra fields)             │
   │  • Stateful workflow tests (CRUD chains —         │
   │    create → read → update → delete)              │
   │  • BOLA security tests (broken object-level       │
   │    authorization: can user A read user B's data?) │
   │  • Auth fixtures auto-attached where the spec     │
   │    declares security schemes                      │
   └───────────────────────┬──────────────────────────┘
                           │
                           ▼
   Runnable API tests with assertions, extraction,
   and chaining — executed and reported like any other suite.
```

Specs can be **pasted or fetched** (with SSRF protection against internal addresses), and Postman collections, HAR captures, and raw cURL commands are all importable. Authentication is handled by reusable **auth fixtures** — static bearer tokens, OAuth client-credentials, or scripted login flows — stored encrypted at rest and never returned in plaintext.

**Engineering demonstrated:** OpenAPI/Postman/HAR/cURL parsing, property-based & boundary test synthesis, stateful workflow generation, automated security (BOLA) testing, and secure credential management.

---

## Generate Tests from a Live URL

No spec, no story? Give Blade Test a URL and it explores the live site to generate tests against what it actually finds.

```
   Target URL  (+ optional focus area & login state)
          │
          ▼
   ┌────────────────────────────────────────────────┐
   │  SITE EXPLORATION (crawl)                        │
   │  • Discovers pages up to a configurable depth    │
   │  • Captures structure + vision screenshots       │
   │  • Infers interactive flows                       │
   └───────────────────────┬──────────────────────────┘
                           │  live cost preview before spend
                           ▼
   ┌────────────────────────────────────────────────┐
   │  AI TEST INFERENCE → draft test cases            │
   │  streamed live (page-by-page) to the UI          │
   └────────────────────────────────────────────────┘
```

The crawl streams progress live over the browser, enforces a **per-workspace concurrency cap**, and shows an **estimated LLM cost preview** — requiring explicit acceptance before spending above a configurable threshold. Client disconnect cleanly aborts the job.

**AI skills demonstrated:** autonomous web exploration, vision-assisted flow inference, streaming generation, and cost-gated AI execution.

---

## Visual Regression Testing

Beyond functional pass/fail, Blade Test catches *unintended visual change*. Screenshots are captured per viewport and diffed against an approved baseline; humans approve or reject what changed.

```
   Run captures screenshot
          │
          ▼
   Compare against approved baseline (per route + viewport)
          │
     pixel diff?
     ┌────┴────┐
   no│         │yes
     ▼         ▼
   Pass    ┌──────────────────────────────┐
           │  REVIEW QUEUE                 │
           │  approve → new baseline       │
           │  reject  → flagged regression │
           │  bulk-approve supported       │
           └──────────────────────────────┘
```

Baselines are versioned, filterable by status / project / commit / viewport, and every approve/reject is recorded in the audit log with the actor and reason.

**Engineering demonstrated:** pixel-diff visual regression, baseline versioning, viewport-aware comparison, and human-governed approval workflow.

---

## Accessibility Checks

During execution, pages are scanned for accessibility issues (roles, labels, contrast, structure), surfacing a11y defects as part of the same run — so accessibility becomes a continuous check, not a one-off audit.

---

## Flaky Test Detection & Quarantine

Flake erodes trust in automation faster than any other failure mode. Blade Test treats it as a tractable, ranked problem.

```
   Execution history accumulates
          │
          ▼
   ┌────────────────────────────────────────────────┐
   │  FLAKINESS ANALYSIS                              │
   │  • Detects tests that fail intermittently        │
   │  • Clusters failures by likely root cause        │
   │  • Auto-quarantines chronically flaky tests      │
   │  • Ranked stabilisation suggestions              │
   └───────────────────────┬──────────────────────────┘
                           │
                           ▼
   Quarantine queue → review → release back to active
```

Quarantined tests are isolated from the main signal so a known-flaky test doesn't block a release, while remaining visible for a human to fix and release.

**AI skills demonstrated:** statistical flake detection, failure clustering, and automated reliability triage.

---

## Test Lifecycle & Review Governance

Nothing becomes a trusted, automated test without passing through a governed lifecycle. The AI proposes; humans approve.

```
   DRAFT  ──►  IN REVIEW  ──►  APPROVED  ──►  ACTIVE
                                                 │
                                                 ▼
                                           QUARANTINED
   (role-gated transitions · full audit trail · every change attributed)
```

Permissions are role-aware (Viewer, QA, QA Lead, Workspace Admin, Owner, Platform Admin), so who can create, review, approve, run, or delete tests is enforced by the platform — not by convention.

---

## Continuous Regression (Heartbeat)

```
   ┌──────────────┐   every N min   ┌──────────────────────────┐
   │  Schedule    │ ───────────────►│  Unattended suite run     │
   │  a suite     │                 │  (auto-login if needed)   │
   └──────────────┘                 └─────────────┬─────────────┘
                                                   │
                          ┌────────────────────────┼────────────────────────┐
                          ▼                         ▼                        ▼
                  ┌──────────────┐         ┌──────────────┐        ┌──────────────┐
                  │ Pass-rate    │         │ Alerts on    │        │ Jira sync:   │
                  │ trend        │         │ flake/drift  │        │ results +    │
                  │              │         │              │        │ status push  │
                  └──────────────┘         └──────────────┘        └──────────────┘
```

Regression becomes a **service, not an event** — silent when healthy, loud when it matters, with self-healing keeping the suite alive between human attention cycles.

---

## Team Dashboard & AI Daily Summary

A role-aware command centre summarises the state of testing for the active sprint — and an AI writes the human-readable briefing on top of it.

```
   ┌──────────────────────────────────────────────────────┐
   │  DASHBOARD  (scope: today · sprint · all)              │
   │  • Counts: generated · in-review · approved · active   │
   │  • Active Jira sprint window                           │
   │  • "Your queue" — role-aware work items                │
   │  • Unread notifications                                │
   │  ┌──────────────────────────────────────────────────┐ │
   │  │  AI SUMMARY                                        │ │
   │  │  Plain-language briefing of what changed,          │ │
   │  │  what needs attention, and what's at risk.         │ │
   │  └──────────────────────────────────────────────────┘ │
   └──────────────────────────────────────────────────────┘
```

The queue adapts to the viewer's role — a QA sees their drafts and reviews; a QA Lead sees everything in review; an admin sees approved and recently-active tests.

**AI skills demonstrated:** AI-generated natural-language summarisation over structured metrics, with role-aware data shaping.

---

## Observability, Cost Governance & Audit

Every AI action is traced, costed, and auditable — and spend is actively governed, not just measured.

```
   Every LLM call
        │
        ├──► Tracing (full prompt/response lineage, Langfuse)
        ├──► Per-call token + USD cost attribution
        ├──► Workspace / purpose / requester tagging
        └──► Internal event stream for live monitoring

   ┌────────────────────────────────────────────────┐
   │  LLM BUDGET GOVERNANCE                           │
   │  • Monthly spend + linear projection             │
   │  • Soft cap (warn) and hard cap (block)          │
   │  • Cost breakdown by purpose                     │
   └────────────────────────────────────────────────┘

   ┌────────────────────────────────────────────────┐
   │  CORRELATION TIMELINE                            │
   │  One ID joins audit + LLM + test + run records   │
   │  → trace any action end-to-end                   │
   └────────────────────────────────────────────────┘
```

Each AI interaction is attributed to a workspace, a purpose (generate / expand / audit / vision / classify), and a requester. A **correlation ID** threads through every action so an entire operation can be reconstructed across logs, model calls, and test runs — and monthly LLM spend is capped with soft (warn) and hard (block) limits.

**Engineering demonstrated:** LLM tracing & evaluation tooling, cost attribution and budget enforcement, and end-to-end correlation for forensic observability.

---

## Enterprise Security & Access Control

Blade Test is built for teams, with the access controls a security review expects.

```
   ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
   │  RBAC        │  │  MFA          │  │  SSO          │  │  PAT          │
   │  6 roles ·   │  │  TOTP +       │  │  Entra ·      │  │  scoped       │
   │  permission  │  │  backup codes │  │  Google ·     │  │  personal     │
   │  gates       │  │  + step-up    │  │  SAML         │  │  access tokens│
   └──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘

   • Multi-workspace isolation (data scoped per workspace)
   • Encrypted secrets vault for credentials & auth fixtures
   • Full audit log — every action attributed to an actor
   • Bring-Your-Own-Key: AI provider keys stay in your tenant
```

- **RBAC:** six roles (Viewer → Platform Admin) with fine-grained permission gates on every sensitive route.
- **MFA:** TOTP enrolment, backup codes, trusted-device cookies, and **step-up authentication** for high-risk actions.
- **SSO:** Microsoft Entra, Google, and SAML (with per-workspace SP metadata) — with email-domain discovery on the login page.
- **PAT:** scoped personal access tokens for CI and automation, revocable by the user or an admin.
- **Secrets** (API keys, auth-fixture credentials) are encrypted at rest and never returned in plaintext.

**Engineering demonstrated:** RBAC with permission gating, TOTP MFA with step-up, SAML/OIDC SSO, token-scoped API access, encrypted secret storage, and comprehensive audit logging.

---

## Blade Test as an AI Tool (MCP Server)

Blade Test doesn't just *use* MCP to drive browsers — it also *exposes* itself as an MCP server, so external AI agents and IDEs can call it as a tool.

```
   External AI agent / IDE
        │   JSON-RPC over Streamable HTTP (Bearer auth)
        ▼
   ┌────────────────────────────────────────────────┐
   │  BLADETEST MCP SERVER                            │
   │  Tools:                                          │
   │   • generate_from_url                            │
   │   • generate_from_openapi                        │
   │   • list_pending_visual_baselines                │
   │  • Per-workspace bearer token (rotatable)        │
   │  • Per-tool allow-list                           │
   │  • Per-token hourly rate limit                   │
   │  • Every invocation audited                      │
   └────────────────────────────────────────────────┘
```

This makes the platform composable: another agent can ask Blade Test to "generate tests for this URL" or "list visual baselines awaiting review" through the open Model Context Protocol standard, with workspace-scoped auth and rate limiting.

**AI skills demonstrated:** building an MCP server (tool provider), agent-to-agent interoperability, and secure, rate-limited tool exposure.

---

## Capability Summary

| Capability | What it delivers | AI / engineering technique |
|---|---|---|
| Jira story ingestion | Stories + AC pulled automatically | REST integration, ADF parsing |
| Story gap analysis | Weak stories fixed before they cost a defect | Requirements analysis with an LLM |
| Improvement suggestions | QA insights flow back to product | Human-governed AI suggestion workflow |
| Coverage analysis | Coverage becomes a tracked number | AC-to-test traceability mapping |
| Test generation from AC | Days of authoring → minutes | Prompt engineering, RAG, few-shot |
| Pipeline shaping | Right depth/breadth per story | Deterministic signal scoring |
| Quality & safety audit | Bad cases caught pre-ship | LLM-judge + deterministic eval |
| Hallucination guard | Output grounded in the AC | Semantic grounding scoring |
| Bias detection | Flags ungrounded assumptions | Pattern analysis |
| PII protection | No raw PII reaches the model | Scrub-and-rehydrate |
| Automation classifier | Effort focused where it pays | Confidence-scored classification |
| Step expansion | Plain language → browser actions | NL-to-action generation |
| Playwright MCP execution | AI drives a real browser | Model Context Protocol tool use |
| Test script generation | Exportable, CI-ready Playwright code | Code generation + POM abstraction |
| Screenshot / video / trace | Every run is auditable evidence | Browser artifact capture |
| Self-healing execution | UI changes don't break tests | Multi-strategy + vision fallback |
| Vision element recovery | Works when DOM matching fails | Multimodal LLM (Claude + GPT-4o) |
| Human-in-the-loop | Safety net on low confidence | Threshold-gated confirmation |
| Multi-platform sync | Tests + results in your tools | Jira/Xray/TestRail/ADO/Zephyr |
| API test generation | Full API suite from a spec | OpenAPI/Postman/HAR/cURL synthesis |
| Security testing | Authorization flaws caught | BOLA test synthesis |
| URL-based generation | Tests from a live site | Autonomous crawl + vision inference |
| Visual regression | Catches unintended UI change | Pixel-diff + baseline review |
| Accessibility checks | a11y defects surfaced per run | Automated accessibility scanning |
| Flaky detection | Flake stops blocking releases | Statistical detection + clustering |
| Lifecycle governance | AI proposes, humans approve | Role-gated state machine |
| Team dashboard | Sprint status at a glance | AI summarisation over metrics |
| Continuous regression | 24/7 monitoring, Jira sync | Scheduled agent orchestration |
| Cost governance | Spend capped, not just measured | Budget caps + projection |
| Observability | Full trace + cost per call | LLM tracing, correlation IDs |
| Enterprise security | Team-ready access control | RBAC · MFA · SSO · PAT · audit |
| MCP tool server | Callable by external AI agents | MCP server (tool provider) |

---

## Technology

**Languages & Frameworks:** TypeScript · Node.js · Express · React

**AI / LLM:** OpenAI · Anthropic Claude (vision) · Groq · Model Context Protocol (MCP — both client & server) · Bring-Your-Own-Key (BYOK) · Langfuse tracing & evaluation · hybrid RAG (BM25 + semantic)

**Automation:** Playwright (Chromium / Firefox / WebKit) · self-healing locator engine · vision-based element recovery · auto-generated page objects

**Test Generation Inputs:** Jira stories/AC · Confluence docs · OpenAPI/Swagger · Postman collections · HAR · cURL · live URL crawl

**Test Types:** functional UI · API (property/mutation, stateful workflow, BOLA security) · visual regression · accessibility · regression suites

**Integrations:** Jira REST API v3 (bidirectional) · Confluence · Xray · TestRail · Azure DevOps · Zephyr Scale

**Evidence & Reporting:** per-step screenshots · session video · Playwright traces · JSON audit trails · exportable test specs & page objects · coverage & report exports (PDF / DOCX / CSV)

**Security & Access:** RBAC (6 roles) · TOTP MFA + step-up · SSO (Entra / Google / SAML) · scoped PATs · encrypted secrets vault · full audit log · multi-workspace isolation

**Quality & Safety:** hallucination guard · bias detection · PII scrubbing · LLM-as-a-judge · groundedness & relevance scoring · LLM cost budgets

---

## What Makes It Different

1. **It starts at the story, not the click.** The system generates the tests *and then* drives the browser. The human reviews — they don't author.
2. **One platform, every test type.** UI, API, security, visual, and accessibility tests — from stories, specs, docs, or a live URL — in a single tool instead of five.
3. **Self-healing is a cascade, not a trick.** Seven escalating strategies, ending in AI vision, each logged with the strategy that rescued the step.
4. **Every AI decision is auditable.** Screenshots, chosen targets, heal strategies, confidence scores, correlation IDs, and full cost lineage — defensible in a compliance review.
5. **Safety by design.** PII never reaches a model; low-confidence actions pause for a human; quality is scored before anything ships; spend is capped.
6. **It learns the product.** Past generations inform future ones through retrieval and project memory.
7. **Composable.** It both uses MCP to drive browsers and exposes itself as an MCP server other AI agents can call.

---

*Blade Test — turn every story into a test, every test into a guarantee.*

---

### License & IP Notice

Copyright © 2024–2026 Abhijath Kottikkal. All rights reserved. This document describes proprietary capabilities at a conceptual level. No internal architecture, algorithms, or source are disclosed herein, and no rights to reproduce the underlying ideas are granted.
