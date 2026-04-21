
### The AI-Assisted Test System that turns user stories into running, self-healing test suites.

> From acceptance criteria to a running regression suite — without writing a line of code.

---

## The Problem

Software teams ship faster than QA can keep up.

- **Authoring is manual.** Every new story demands a human to translate acceptance criteria into test steps, hunt for elements in the UI, and write the script. Days per story. Multiply by every sprint.
- **Locators rot.** A trivial UI tweak silently breaks dozens of automated tests overnight. Maintenance often costs more than the original authoring.
- **Regression is a ritual, not a system.** Most teams run regression on a schedule, find half the failures are flaky, and lose trust in the suite.
- **Coverage is folklore.** "We test the important stuff" — but no one can point to which acceptance criteria are actually covered and which are not.
- **Tooling is fragmented.** Authoring tool, runner, dashboard, ticket sync, defect tracker — five tools, no learning loop between them.

---

## The Solution

StoryTest Pro is a single platform that covers the entire flow — from acceptance criterion to live regression — as one continuous, learning loop.

```
User Story + AC  →  AI Generation  →  AI Quality Audit  →  Live Execution  →  Self-Healing  →  Continuous Regression
```

### Before → After

| Before | After |
|---|---|
| Days of test authoring | Minutes from story to test cases |
| Locator breaks every sprint | Self-healing across UI changes |
| Manual regression cycles | 24/7 Heartbeat, alerts on drift |
| Coverage you guess at | Coverage you can measure |
| QA as a release bottleneck | QA as a release accelerator |

---

## Key Features

### AI Test Generation
- Reads Jira user stories and acceptance criteria (Gherkin or plain text)
- Produces a full set of test cases — positive, negative, edge, non-functional
- Story Readiness panel scores AC live before generation: estimates case count, flags ambiguity, identifies preconditions, surfaces domain-aware gap suggestions

### AI Quality Audit
- Scores every generated test case across five dimensions: Completeness, Clarity, Validity, Consistency, and Relevance
- Auto-fix or quarantine weak cases in one click
- Prevents bad test cases from polluting the regression suite

### Coverage Report & Gap Analysis
- Maps every test case back to the acceptance criterion it covers
- Highlights uncovered AC with severity at a glance
- One-click gap generation to fill missing coverage immediately
- Exportable coverage reports for compliance and release sign-off

### No-Code Automation Pipeline
- **Classifier** — evaluates every test case for automation feasibility and regression candidacy with a confidence score and risk level (HIGH / MED / LOW)
- **Expander** — expands high-level test steps into granular, executable Playwright browser actions
- Two modes: **Compact** (one step per AC line, runtime healing fills detail) and **Verbose** (full per-line, prerequisite-aware step spec)
- Auto-generated, industry-standard page object library

### Live Execution with Full Observability
- Runs each test against your real application in a real browser
- Every step is visible: duration, status, screenshots, and narration
- **AUTH badges** on sign-in scaffold steps; **HEALED badges** on rescued locators with strategy tooltip
- **Skip vs Blocked** rendered distinctly so triage never confuses intent with cascade failure
- Auto-login pre-flight handles environments that require sign-in before a scenario can begin

### 4-Layer Self-Healing Cascade
When a locator fails, four cooperating strategies attempt recovery before the step is allowed to fail:
1. **SiteModel** — re-bind via cached DOM model for the URL
2. **DOM Stabilise** — wait, re-snapshot, retry transient timing
3. **Synonyms** — try label variants (email/username, login/sign-in)
4. **LLM Fallback** — describe the element, cross-validate with token overlap

Each rescued step is logged with the strategy name. The system never silently guesses.

### Heartbeat — Continuous Regression as a Service
- Schedule any regression suite to run every N minutes, unattended
- 2x2 insights grid: pass rate, Jira sync health, rolling alerts, and healing log — scannable in five seconds
- Alerts raised for new flaky tests and locator drift
- Self-healing keeps the suite alive between human attention cycles

### Bidirectional Jira Integration
- Pull stories and acceptance criteria automatically on a configurable interval
- Push test execution summaries as comments on Jira issues
- Push approved story-improvement suggestions back to Jira
- Update Jira story status from test results
- Single-dialog configuration — connect, select projects, configure pull/push from one screen

### Story-Improvement Suggestion Workflow
- QA submits improvement suggestions on stories or test cases
- Product owners review, approve, reject, or push directly to Jira
- Closes the loop: better AC → better generated tests → fewer rework cycles

### Project Memory & Learning
- The platform accumulates knowledge of your product over time
- Each generation is shaped by what worked and what didn't in previous runs
- Compact mode gets sharper with every run as the runtime healer learns from the same memory

### Bring Your Own Key (BYOK)
- Supply your own AI provider credentials (OpenAI, Anthropic, or others)
- Story data and test artifacts never leave your account boundary
- Addresses data residency, cost control, and vendor risk concerns

---

## Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│  Frontend  (React + TypeScript + MUI + Zustand)                 │
│  Generator · Reports · Automate · Heartbeat · Settings          │
└────────────────────────┬────────────────────────────────────────┘
                         │  REST + SSE
┌────────────────────────▼────────────────────────────────────────┐
│  Backend  (Node.js + Express + TypeScript)                      │
│  AI Pipeline · Jira Routes · Nocode API · Heartbeat Scheduler   │
└──────────┬──────────────────────┬───────────────────────────────┘
           │                      │
┌──────────▼──────────┐  ┌────────▼──────────────────────────────┐
│  PostgreSQL          │  │  Playwright (Chromium/Firefox/WebKit)  │
│  (workspaces,        │  │  Executor Worker · Evidence Service   │
│   runs, memory)      │  │  Run Repository · Locator Engine      │
└─────────────────────┘  └────────────────────────────────────────┘
```

---

## Tech Stack

**Frontend:** React, TypeScript, MUI (Material UI), Zustand, Vite, SSE Streaming

**Backend:** Node.js, Express, TypeScript, PostgreSQL, Prisma

**Automation:** Playwright (Chromium, Firefox, WebKit), Self-Healing Locator Engine, Executor Worker

**AI:** OpenAI API, Anthropic API (BYOK — bring your own key)

**Integrations:** Jira REST API v3, JWT Authentication, CORS, Helmet.js

---

## Screens

| Screen | Purpose |
|---|---|
| Generator | Input user story + AC, view Story Readiness panel, generate test cases |
| Reports → Test Cases | Review, edit, quarantine, or mark cases for automation |
| Reports → Coverage | AC-by-AC coverage bars with gap generation |
| Reports → Quality Audit | 5-dimension AI audit with auto-fix |
| Reports → Execution Insights | Pass rate trend, flaky test list, one-click stabilisation |
| Reports → Suggestions | Story-improvement workflow with Jira push |
| Automate → Classifier | Automation feasibility scoring with confidence and risk levels |
| Automate → Expander | Step expansion with Compact/Verbose toggle and live pipeline progress |
| Live Execution | Real-browser step stream with AUTH/HEALED badges and activity feed |
| Results | Per-scenario artifacts: screenshot, video, trace, generated code |
| History | Full run history with trend metrics and self-healing ROI estimate |
| Heartbeat | Continuous regression dashboard with scheduling, alerts, healing log |
| Settings | AI providers (BYOK), browser engine, environments, Jira sync |

---

## What Makes This Different

1. **Starts at the story, not the click.** Recorders need a human to drive a browser. StoryTest Pro starts from the acceptance criterion, generates the test cases, and then drives the browser. The human reviews — doesn't author.

2. **Self-healing is a four-layer cascade, not a single trick.** Each rescue is logged with the strategy name so you can see the system's behaviour evolve over time.

3. **Every AI decision is auditable.** No black box. Every step has a screenshot, the chosen target, the heal strategy if any, and a confidence score — exportable, attachable to a Jira ticket, defensible in a compliance review.

4. **Human-in-the-loop, by design.** When confidence drops, the system pauses and asks. It never silently guesses. This is the difference between an experiment and an enterprise tool.

5. **The platform learns your product.** Project memory means the second story is generated better than the first, the tenth better than the second.

6. **One tool, not five.** Authoring, classification, expansion, execution, regression, dashboards, ticket sync — all in one platform. No fragile glue between vendors.

---

## Security

- JWT Authentication with workspace-scoped access control
- Bring Your Own Key — AI provider credentials stay in your account boundary
- API key encryption and environment variable secrets management
- CORS policy enforcement with configurable origins
- Helmet.js security headers

---

## License

Copyright © 2024–2025 Abhijath Kottikkal. All rights reserved.

This repository and all its contents — including but not limited to source code, design documents, architecture, product concepts, algorithms, and user interface designs — are the exclusive intellectual property of the author.

**No part of this project may be reproduced, copied, modified, distributed, sublicensed, sold, or used to build a competing or derivative product — in whole or in part — without the express written permission of the author.**

This is not an open-source project. No licence is granted to any third party by the act of viewing this repository. The presence of this code on a public or private hosting platform does not constitute a waiver of any intellectual property rights.

For licensing enquiries, contact the author directly.

---

