# StoryTest Pro
### The AI-Assisted Test System that turns user stories into running, self-healing test suites.

---

## Cover

```
+==============================================================================+
|                                                                              |
|                        S T O R Y T E S T   P R O                             |
|                                                                              |
|          From acceptance criteria to a running regression suite              |
|                       without writing a line of code.                        |
|                                                                              |
+==============================================================================+
|                                                                              |
|   THE PROBLEM         Manual test scripting is slow, brittle, and never      |
|                       caught up with the backlog.                            |
|                                                                              |
|   THE OUTCOME         Stories become executable tests in minutes, run        |
|                       continuously against your live app, and heal           |
|                       themselves as the UI changes.                          |
|                                                                              |
+==============================================================================+
|                                                                              |
|                          B E F O R E    ->    A F T E R                      |
|                                                                              |
|   Days of test authoring        ->   Minutes from story to test cases        |
|   Locator breaks every sprint   ->   Self-healing across UI changes          |
|   Manual regression cycles      ->   24/7 heartbeat, alerts on drift         |
|   Coverage you guess at         ->   Coverage you can measure                |
|   QA as a release bottleneck    ->   QA as a release accelerator             |
|                                                                              |
+==============================================================================+
```

---

## 1. The Problem

Software teams ship faster than QA can keep up.

### For QA leaders
- **Authoring is manual.** Every new story still demands a human to translate acceptance criteria into test steps, hunt for elements in the UI, and write the script. Days per story. Multiply by every sprint.
- **Locators rot.** A trivial UI tweak — a renamed button, a moved class — silently breaks dozens of automated tests overnight. Maintenance often costs more than the original authoring.
- **Regression is a ritual, not a system.** Most teams run regression on a schedule, find half the failures are flaky, and lose trust in the suite.
- **Coverage is folklore.** "We test the important stuff" — but no one can point to which acceptance criteria are actually covered and which are not.

### For Engineering leaders
- **AI is the missing layer in QA.** Engineering teams ship AI features in the product, but the QA function still runs on a 2010-era toolchain.
- **Time-to-market is gated by QA.** Release cycles are paced not by code-complete, but by test-complete.
- **Tooling is fragmented.** Authoring tool, runner, dashboard, ticket sync, defect tracker — five tools, no learning loop between them.
- **No organisational memory.** Every new test starts from zero. The QA team's hard-won knowledge about how the app behaves never accumulates anywhere a machine can use it.

StoryTest Pro is a single platform that solves all four for QA, and all four for Engineering.

---

## 2. The Solution at a Glance

```
                            +-------------------------+
                            |   USER STORY  +  AC     |
                            |   (typed, pasted, or    |
                            |    pulled from Jira)    |
                            +------------+------------+
                                         |
                                         v
        +------------------------------------------------------------+
        |              A I   G E N E R A T I O N                     |
        |   Reads acceptance criteria. Produces a full set of        |
        |   test cases - positive, negative, edge, non-functional.   |
        +-----------------------------+------------------------------+
                                      |
                                      v
        +------------------------------------------------------------+
        |              A I   Q U A L I T Y   A U D I T               |
        |   Scores every case for completeness, clarity, validity,   |
        |   consistency, and relevance - flags what to fix or drop.  |
        +-----------------------------+------------------------------+
                                      |
                                      v
        +------------------------------------------------------------+
        |              L I V E   E X E C U T I O N                   |
        |   Runs each test against your real application in a real   |
        |   browser. Watches, screenshots, narrates, and proves it.  |
        +-----------------------------+------------------------------+
                                      |
                                      v
        +------------------------------------------------------------+
        |           S E L F - H E A L I N G                          |
        |   When the UI shifts, four cooperating strategies try to   |
        |   resolve the element before the step is allowed to fail.  |
        +-----------------------------+------------------------------+
                                      |
                                      v
        +------------------------------------------------------------+
        |      C O N T I N U O U S   R E G R E S S I O N             |
        |   The Heartbeat keeps the suite running 24/7, syncs        |
        |   results to Jira, and learns from every run.              |
        +------------------------------------------------------------+
```

### The five outcomes you can put on a slide

1. **Faster releases.** Test authoring drops from days to minutes per story.
2. **Lower QA cost.** Self-healing absorbs the maintenance work that used to consume sprint capacity.
3. **Higher coverage.** Every acceptance criterion is mapped to a test, with gap analysis built in.
4. **Less flake.** Confidence-scored locators and a four-layer heal cascade keep the suite stable as the app evolves.
5. **Better stories.** A feedback loop from QA back into product writing improves acceptance criteria over time.

---

## 3. Product Tour — Screen by Screen

Each screen below is presented as a wireframe, what the user does on it, and why it matters to the business.

---

### 3.1 Main Dashboard / Generator

```
+----------------------------------------------------------------------------+
|  STORYTEST PRO    [Generator] [Automate] [Heartbeat]      [cog]  Profile   |
+----------------------------------------------------------------------------+
|                                                                            |
|  +-------------------------------------+  +----------------------------+   |
|  |  STORY INPUT                        |  |  STORY READINESS           |   |
|  |  PROJECT                            |  |                            |   |
|  |  [ CHK ] [ PRO ] [ BIL ]   [refresh]|  |  Predicted output:         |   |
|  |                                     |  |   - ~24 test cases         |   |
|  |  USER STORY                         |  |   - Quality est. 89%       |   |
|  |  [ Apply discount code at checkout ]|  |   - 6 likely regression    |   |
|  |  (locked - press Clear to swap)     |  |     candidates             |   |
|  |                                     |  |                            |   |
|  |  STORY TITLE                        |  |  AC review hints:          |   |
|  |  +-------------------------------+  |  |   ! Step 3 ambiguous       |   |
|  |  |  Apply discount code...       |  |  |   ! No negative path       |   |
|  |  +-------------------------------+  |  |   ! Dependency: a logged-in|   |
|  |                                     |  |     cart with items must   |   |
|  |  ACCEPTANCE CRITERIA                |  |     exist before step 1    |   |
|  |  +-------------------------------+  |  |                            |   |
|  |  |                               |  |  |  [bolt] Compact mode will  |   |
|  |  |  (Gherkin or plain text)      |  |  |  collapse to ~14 reviewable|   |
|  |  |                               |  |  |  steps; runtime healing    |   |
|  |  +-------------------------------+  |  |  fills the rest.           |   |
|  |                                     |  |                            |   |
|  |  [   GENERATE TEST CASES   ]        |  |                  [ Clear ] |   |
|  +-------------------------------------+  +----------------------------+   |
|                                                                            |
+----------------------------------------------------------------------------+
```

**What you do**
- Pick the project you're working in. If your workspace has more than one project enabled in Settings, they appear as a small chip switcher; otherwise the active project is shown as a static label. A round refresh icon lives on the same line.
- Choose a user story from the dropdown. Once you've picked one, the dropdown locks (a tooltip explains why) so you can't accidentally swap stories mid-edit. Use the Clear button in the top-right of the panel to start over.
- Pull or paste the title and acceptance criteria. The Story Readiness panel reacts as you type: it scores the AC, flags ambiguity, identifies likely preconditions ("the user must already be logged in with a non-empty cart"), and surfaces domain-aware gap suggestions ("missing negative path", "no boundary case for minimum cart total").
- Read the compact-mode hint, then click **Generate Test Cases** and wait roughly half a minute.

**Why it matters**
- Catches weak acceptance criteria *before* a test gets written, not after a defect ships.
- The Story Readiness panel shows the system has memory: it knows the project's past patterns and tunes its output accordingly.
- The locking and Clear discipline prevents a common authoring mistake — losing in-flight edits when someone idly swaps the story dropdown.
- Replaces a multi-hour authoring task with a single click.

---

### 3.2 Reports — Test Cases Tab

```
+----------------------------------------------------------------------------+
|  < Story: "Apply discount code at checkout"                                |
|  [Test Cases] [Coverage] [Quality Audit] [Execution] [Suggestions]         |
+----------------------------------------------------------------------------+
|  Filter: [All v]  Priority: [All v]  Category: [All v]   Search: ______    |
|                                                                            |
|  +----------------------------------------------------------------------+  |
|  | >  TC-001  Apply valid discount code                  HIGH  POSITIVE |  |
|  | >  TC-002  Apply expired discount code                HIGH  NEGATIVE |  |
|  | v  TC-003  Apply discount code with min cart not met  MED   EDGE     |  |
|  |      Steps:                                                          |  |
|  |       1. Add item under £10 to cart                                  |  |
|  |       2. Open checkout                                               |  |
|  |       3. Enter code "SAVE20" in discount field                       |  |
|  |       4. Click Apply                                                 |  |
|  |      Expected:                                                       |  |
|  |       - Inline error: "Minimum spend £20 required"                   |  |
|  |       - Discount not applied to total                                |  |
|  |      [ Edit ]  [ Mark for automation ]  [ Quarantine ]               |  |
|  | >  TC-004  Stack two valid codes                      MED   EDGE     |  |
|  | >  TC-005  Code applies to sale items                 LOW   POSITIVE |  |
|  +----------------------------------------------------------------------+  |
+----------------------------------------------------------------------------+
```

**What you do**
- Expand any test case to see steps and expected results.
- Edit, quarantine weak cases, or mark strong ones for automation.

**Why it matters**
- Every test case is a complete, reviewable artifact — not just a one-line scenario.
- Categories (positive / negative / edge) and priorities are decided by the AI and editable by the QA lead.
- This is where the QA team retains authority. Nothing automated until a human approves.

---

### 3.3 Reports — Coverage Tab

```
+----------------------------------------------------------------------------+
|  COVERAGE REPORT - Apply discount code at checkout                         |
+----------------------------------------------------------------------------+
|  Overall coverage:        ###################...  78 %                     |
|                                                                            |
|  By acceptance criterion:                                                  |
|    AC1  Valid code applies discount      ############  100% (3 cases)      |
|    AC2  Expired code is rejected         ############  100% (2 cases)      |
|    AC3  Min cart enforced                ######......   50% (1 case)       |
|    AC4  Stacking rules                   ............    0% - UNCOVERED    |
|    AC5  Code visible on order summary    ########....   75% (2 cases)      |
|                                                                            |
|  Suggested additions:                                                      |
|    + Stack invalid + valid code          [ Generate ]                      |
|    + Stack two codes of same type        [ Generate ]                      |
|    + Apply code via promo URL            [ Generate ]                      |
|                                                                            |
|  [  Generate suggested cases  ]    [  Export coverage report  ]            |
+----------------------------------------------------------------------------+
```

**What you do**
- See coverage as a bar per acceptance criterion — gaps are obvious at a glance.
- Click **Generate** next to a suggested addition to fill a gap in seconds.

**Why it matters**
- Replaces the perennial "are we testing enough?" debate with a number you can put in a release report.
- Auditable for compliance teams (finance, healthcare, public sector).
- Closes the feedback loop between product (writing AC) and QA (covering it).

---

### 3.4 Reports — AI Quality Audit Tab

```
+----------------------------------------------------------------------------+
|  AI QUALITY AUDIT                                Overall score:  87%       |
+----------------------------------------------------------------------------+
|                                                                            |
|  Completeness   ############  PASS   All AC mapped, no orphan steps        |
|  Clarity        ##########..  WARN   3 steps use vague verbs               |
|  Validity       ############  PASS   Every step is executable on the app   |
|  Consistency    ############  PASS   No contradictions across cases        |
|  Relevance      #########...  WARN   2 cases reference removed feature     |
|                                                                            |
|  +----------------------------------------------------------------------+  |
|  | Issues to review                                                     |  |
|  +----------------------------------------------------------------------+  |
|  | [!] TC-007 step 4: "Verify everything looks right"   too vague       |  |
|  | [!] TC-009 step 2: "Click the thing"                 unclear target  |  |
|  | [!] TC-014: references "Promo Wallet" - removed in v3                |  |
|  | [!] TC-021 step 3: "Wait a bit"                      no condition    |  |
|  +----------------------------------------------------------------------+  |
|                                                                            |
|  [ Auto-fix WARN items ]   [ Quarantine FAIL items ]                       |
+----------------------------------------------------------------------------+
```

**What you do**
- Review the five-dimension score; act on warnings before sending tests downstream.
- Auto-fix or quarantine in one click.

**Why it matters**
- Bad test cases are the #1 source of flake. Catching them here prevents wasted execution time and false defects.
- A QA lead can confidently sign off on a generated suite knowing it's been independently audited by the AI.

---

### 3.5 Reports — Execution Insights Tab

```
+----------------------------------------------------------------------------+
|  EXECUTION INSIGHTS - last 30 days                                         |
+----------------------------------------------------------------------------+
|                                                                            |
|  Pass rate trend                                                           |
|    100% |              *****                                               |
|     90% |      ********     ********                                       |
|     80% |******                     *****                                  |
|         +----------------------------------                                |
|         Apr 1                                Apr 30                        |
|                                                                            |
|  Flaky tests (failed intermittently):                                      |
|   ^ TC-018  Search returns relevant results       7 fails / 24 runs        |
|   ^ TC-031  Checkout payment redirect             4 fails / 24 runs        |
|   ^ TC-044  Image upload preview                  3 fails / 24 runs        |
|                                                                            |
|  Suggestions:                                                              |
|   - TC-018 - Add explicit wait for results panel  [ Apply ]                |
|   - TC-031 - Use stable locator for "Pay" button  [ Apply ]                |
|   - TC-044 - Increase upload timeout to 10s       [ Apply ]                |
+----------------------------------------------------------------------------+
```

**What you do**
- See pass-rate trend, flaky test list, and ranked suggestions to fix each one.
- Apply a suggestion in a single click; it updates the underlying test step.

**Why it matters**
- Flake erodes trust in automation faster than any other failure mode. This screen surfaces it as a tractable, prioritised list.
- Engineering managers get a real metric for QA health they can plot in a board pack.

---

### 3.6 Reports — Suggestions Tab

```
+----------------------------------------------------------------------------+
|  STORY-IMPROVEMENT SUGGESTIONS                                             |
+----------------------------------------------------------------------------+
|  Filter: [Pending Review v]                                                |
|                                                                            |
|  +----------------------------------------------------------------------+  |
|  | Suggestion #014                                          PENDING     |  |
|  | Story: Apply discount code at checkout                               |  |
|  | Category: Missing edge case                                          |  |
|  |                                                                      |  |
|  | "AC doesn't cover what happens when a logged-in user has a saved     |  |
|  |  code on their profile and also enters one manually. Suggest         |  |
|  |  clarifying which code wins."                                        |  |
|  |                                                                      |  |
|  | Submitted by: J. Patel (QA)              [ Approve ]  [ Reject ]     |  |
|  |                                          [ Send to Jira ]            |  |
|  +----------------------------------------------------------------------+  |
|  +----------------------------------------------------------------------+  |
|  | Suggestion #015  Unclear step in TC-014                  APPROVED    |  |
|  +----------------------------------------------------------------------+  |
+----------------------------------------------------------------------------+
```

**What you do**
- QA submits improvement suggestions on stories or test cases.
- Product owners review and either approve, reject, or push them to Jira.

**Why it matters**
- Captures domain knowledge that today lives in QAs' heads.
- Closes the loop: better acceptance criteria -> better generated tests -> fewer rework cycles.

---

### 3.7 Automate Dashboard

```
+----------------------------------------------------------------------------+
|  AUTOMATE                                                                  |
+----------------------------------------------------------------------------+
|  [ Overview ]   [ Classifier ]   [ Expander ]                              |
+----------------------------------------------------------------------------+
|                                                                            |
|  STAT CARDS                                                                |
|  +-----------------+ +-----------------+ +-----------------+ +-----------+ |
|  | Total Executions| | Pass Rate       | | Failed Tests    | | Avg Time  | |
|  |  142            | |  92%            | |   8             | |  47s      | |
|  |  All time       | |  All time       | |  Needs attention| | Per run   | |
|  +-----------------+ +-----------------+ +-----------------+ +-----------+ |
|                                                                            |
|  RECENT EXECUTIONS                                  [refresh]  [View All]  |
|  +----------------------------------------------------------------------+  |
|  | o  Checkout v3 smoke      24 / 24 passed   2 min ago    [replay] [x] |  |
|  | o  Profile settings       11 / 12 passed   1 hr ago     [replay] [x] |  |
|  | o  Search                  9 / 12 passed   3 hr ago     [replay] [x] |  |
|  | o  Onboarding             18 / 18 passed   today        [replay] [x] |  |
|  +----------------------------------------------------------------------+  |
+----------------------------------------------------------------------------+
```

**What you do**
- Single command centre for all automation activity. Three stage tabs at the top — Overview, Classifier, Expander — let you jump between dashboard, the classification stage, and the step-expansion stage of the pipeline.
- See what's running now, what ran recently, and replay or delete past runs in place.

**Why it matters**
- Replaces a half-dozen tools (CI dashboards, test reporters, log aggregators) with one view.
- The stage-tab strip is also a mental map of the pipeline — operators learn the flow simply by clicking through.

---

### 3.8 Classifier Panel

```
+----------------------------------------------------------------------------+
|  CLASSIFIER - Test Case Classifier             [ MANUAL CLASSIFICATION ]   |
|  Evaluate test cases for automation feasibility and regression candidacy   |
+----------------------------------------------------------------------------+
|                                                                            |
|  SUMMARY                                                                   |
|  +---------------+ +---------------+ +---------------+ +---------------+   |
|  | Total         | | Automatable   | | Manual Only   | | Regression    |   |
|  |   24          | |   19          | |    5          | |   12          |   |
|  +---------------+ +---------------+ +---------------+ +---------------+   |
|                                                                            |
|  CLASSIFICATION RESULTS                                                    |
|  +----------------------------------------------------------------------+  |
|  | [v] TC-001 Apply valid code              [REGRESSION] [HIGH]  o 96% |  |
|  | [v] TC-002 Apply expired code            [REGRESSION] [HIGH]  o 92% |  |
|  | [v] TC-003 Below min cart                [REGRESSION] [MED ]  o 88% |  |
|  | [v] TC-007 Stack two codes               [REGRESSION] [MED ]  o 74% |  |
|  | [-] TC-014 Visual: badge animation                    [LOW ]    --  |  |
|  | [v] TC-019 A/B variant detection                      [LOW ]  o 62% |  |
|  +----------------------------------------------------------------------+  |
|                                                                            |
|  [ SEND TO EXPANSION  4 ]    [ EXPORT CLASSIFICATION ]                     |
+----------------------------------------------------------------------------+
```

**What you do**
- The header strip shows the panel title and a single **Manual Classification** button. Clicking it opens a modal where you can paste an array of test cases (or load a sample) for ad-hoc classification — the inline JSON editor that used to clutter the panel is now hidden behind that one button.
- For every case the table shows: an automatable yes/no icon, a regression chip when applicable, a colour-coded **regression risk level** (HIGH / MED / LOW), and the AI's automation confidence as a percentage.
- The **Send to Expansion** action filters automatically to automatable cases at >=80% confidence; the count next to the button tells you exactly how many cases will move on.
- **Export Classification** downloads the full grid as a CSV for archiving or board reporting.

**Why it matters**
- QA effort gets directed to the cases that pay back. No one wastes a week trying to automate a visual-only check.
- The risk-level chip lets a QA lead instantly slice the list into "must run on every release" vs "nice to have".
- Confidence scores plus the high-confidence handoff to expansion create a defensible, auditable rationale for what is and isn't automated.

---

### 3.9 Expansion Panel

```
+----------------------------------------------------------------------------+
|  EXPANDER - Step Expander                          [ MANUAL EXPANDER ]     |
|  Expand high-level test steps into granular, executable browser actions    |
|                                          [bolt COMPACT] [list VERBOSE]     |
+----------------------------------------------------------------------------+
|                                                                            |
|  PROGRESS  (during a run)                                                  |
|     (1 classify) -> (2 expand) -> (3 validate)                             |
|     "Validating step quality..."                                           |
|     [#####################................] 12 / 24 test cases             |
|                                                                            |
|  SUMMARY                                                                   |
|  +---------------+ +---------------+ +---------------+ +---------------+   |
|  | Test Cases    | | Total Steps   | | Avg Steps/Case| | Quality Score |   |
|  |   4           | |   18          | |    4.5        | |    94%        |   |
|  +---------------+ +---------------+ +---------------+ +---------------+   |
|                                                                            |
|  EXPANDED STEPS                                                            |
|  +----------------------------------------------------------------------+  |
|  | [v] Apply valid discount code              [94%] [auto-fixed] 7 steps|  |
|  |     1. Navigate to /login                                            |  |
|  |     2. Fill "Email" with customer@test.com                           |  |
|  |     3. Fill "Password" with ********                                 |  |
|  |     4. Click "Sign in"                                               |  |
|  |     5. Wait for "Welcome back" header                                |  |
|  |     6. Navigate to /cart                                             |  |
|  |     7. Confirm cart contains 3 items                                 |  |
|  +----------------------------------------------------------------------+  |
+----------------------------------------------------------------------------+
```

**What you do**
- The header strip carries the panel title, the **Manual Expander** button (which opens a modal for ad-hoc base URL + test cases JSON), and a Compact / Verbose segmented toggle.
- **Compact** is the default for new users: one step per acceptance-criterion line, with runtime healing filling in element details on the fly. Best for rapid iteration.
- **Verbose** produces a full per-line expansion with prerequisites, ideal when you want a reviewable, exportable test spec.
- Watch the live three-stage pipeline (classify -> expand -> validate) as it runs, then expand any test case to see the granular UI actions, an AI quality score, and any auto-corrections the validator applied.

**Why it matters**
- Bridges the gap between business language ("login as a customer") and machine actions.
- Compact mode lets a QA lead sign off on test intent in seconds; the runtime healer handles the messy element-resolution detail.
- Verbose mode satisfies auditors and CI exporters who need to see every keystroke.
- Test data is resolved automatically from the project's known sources — no hard-coded credentials in test cases.

---

### 3.10 Live Execution Panel

```
+----------------------------------------------------------------------------+
|  LIVE EXECUTION - Apply valid discount code               [pause] [stop]   |
+----------------------------------------------------------------------------+
|  STAT BAR                                                                  |
|  Status: Running   Tests Done: 4/8   Duration: 47s   Pass Rate: 100%       |
|                                                                            |
|  +--------------------------------------+   +---------------------------+  |
|  | LIVE STEP STREAM                     |   | ACTIVITY (300px scroll)   |  |
|  | Healing  o SiteModel  o DOM stabilise|   | [All] [Tests] [Failures]  |  |
|  |          o Synonyms   o LLM fallback |   |                           |  |
|  |                                      |   | [info] Auto-signed in     |  |
|  | Running now      4 of 8 scenarios    |   |        using configured   |  |
|  | "Apply valid discount code"          |   |        credentials        |  |
|  | [###################........] 7/9    |   | [pass] TC-002 passed 4.2s |  |
|  |                                      |   | [pass] TC-003 passed 5.1s |  |
|  | (1) Navigate to /login         [AUTH]|   | [warn] TC-004 step 3      |  |
|  | (2) Fill email                 [AUTH]|   |        healed via         |  |
|  | (3) Fill password              [AUTH]|   |        SiteModel          |  |
|  | (4) Click Sign in              [AUTH]|   | [run]  TC-005 step 7      |  |
|  | (5) Open /checkout                   |   |        Click Apply...     |  |
|  | (6) Fill code SAVE       [HEALED]    |   |                           |  |
|  | (7) Click Apply  <-- running         |   +---------------------------+  |
|  | (8) Verify total                     |                                  |
|  | (9) Verify badge -- blocked by       |                                  |
|  |     earlier failure                  |                                  |
|  +--------------------------------------+                                  |
|                                                                            |
|  (Run Results Summary card appears below once the run completes)           |
+----------------------------------------------------------------------------+
```

**What you do**
- A **Healing** chip row at the top of the live stream tells you which heal strategies are wired right now: SiteModel, DOM stabilise, Synonyms, and LLM fallback. Each chip is filled green when enabled and dimmed when disabled (LLM fallback, for example, lights up only when an LLM key is configured).
- Watch each test step run in a real browser. The current step is highlighted, completed steps show their duration, and the step number bubble carries the status colour.
- Auth-prefix steps wear a purple **AUTH** badge so it's obvious which actions belong to the sign-in scaffold rather than to the user's scenario.
- When the system rescues a locator, the step gets an amber **HEALED** badge with a hover tooltip showing the original target, the variant that worked, and which strategy resolved it.
- **Skipped** steps (system intentionally did not run, e.g. an auth-prefix step in bypass mode) render in muted grey with " — skipped" appended.
- **Blocked** steps (couldn't run because an earlier step in the same case failed) render with an amber number bubble and a red " — blocked by earlier failure" suffix, so you can tell propagation from intent at a glance.
- The Activity panel on the right is a fixed-height (300px) scrolling feed with All / Tests / Failures filters. The first thing you'll usually see is a single info row "Auto-signed in using configured credentials" — that's the auto-login pre-flight reporting in.

**Why it matters**
- Demystifies AI automation: every decision is visible, and you can tell at a glance whether a step passed because the locator just worked, because healing rescued it, or because vision fallback had to step in.
- The skip-vs-blocked distinction is what stops a single broken step from looking like ten broken steps in a triage meeting.
- The auto-login pre-flight removes a whole class of "tests fail because we forgot to log in" support tickets — the system notices the login screen, signs in with the configured credentials, and only then starts the user's scenario.

---

### 3.11 Run Results Summary (pinned at the bottom of execution)

```
+----------------------------------------------------------------------------+
|  RUN RESULTS                                                               |
|  24 / 24 passed   - Duration 2m 47s                                        |
|                                                                            |
|  +-----------+ +-----------------+ +-----------------+                     |
|  | HEALED  3 | | VISION FALLBACK | | CONFIRMATIONS 0 |                     |
|  +-----------+ +-----------------+ +-----------------+                     |
|                                       1                                    |
|  ARTIFACTS                                                                 |
|  +-----------------------------------+ +-----------------------------+     |
|  | [code] Test specs (executable)    | | [folder] Page object library|     |
|  |        3 spec files generated     | |          1 library file     |     |
|  |                       [ Download ]| |                  [ Download]|     |
|  +-----------------------------------+ +-----------------------------+     |
|  +-----------------------------------+ +-----------------------------+     |
|  | [cam] Step screenshots            | | [doc] Step audit trail      |     |
|  |       18 captures                 | |       audit-trail.json      |     |
|  |                       [ Download ]| |                  [ Download]|     |
|  +-----------------------------------+ +-----------------------------+     |
|  +-----------------------------------+                                     |
|  | [zip] Full session bundle (.zip)  |                                     |
|  |       artifacts-3f2a1c.zip        |                                     |
|  |                       [ Download ]|                                     |
|  +-----------------------------------+                                     |
+----------------------------------------------------------------------------+
```

**What you do**
- The summary card pins itself to the bottom of the execution view as soon as a run completes (and renders identically on the dedicated Results page).
- Read the headline counts: passed/total, duration, and three run signals — **Healed** (locator rescues), **Vision fallback** (LLM-resolved elements), **Confirmations** (human-in-the-loop interventions).
- Grab any of the five artifact tiles inline. Each tile lights up as soon as its file is written; tiles still being generated show a muted "Generating…" hint.

**Why it matters**
- One card, end of run, all the evidence — no clicking through tabs to find a screenshot or a spec.
- The signal counts give a QA lead a fast read on suite health: a clean run with zero healed/vision/confirmations means stable locators; a passing run with five heals is also passing, but flags the UI is drifting.
- Every artifact is a defensible record for compliance, post-mortems, or onboarding.

---

### 3.12 Automate Results — per-test-case detail

```
+----------------------------------------------------------------------------+
|  RESULTS - Checkout regression - Apr 18 14:22                              |
|  [Overview] [Video] [Screenshots] [Generated Code] [Scenarios]             |
+----------------------------------------------------------------------------+
|                                                                            |
|  SCENARIOS                                                                 |
|  +----------------------------------------------------------------------+  |
|  | (passed)  [TC-001]  Apply valid discount code                        |  |
|  |           4 of 4 passed - completed in 4.2s                       v  |  |
|  +----------------------------------------------------------------------+  |
|  | (passed)  [TC-002]  Below min cart                                   |  |
|  |           4 of 4 passed - 4 skipped - completed in 11.1s          v  |  |
|  | -- expanded:                                                         |  |
|  |     STEPS (8)                                                        |  |
|  |     (ok)   01  open_in_browser  Navigate to /login          0.4s     |  |
|  |     (ok)   02  edit             Fill "Email"                0.3s     |  |
|  |     (skip) 03  edit             Fill "Password" - skipped     -      |  |
|  |     (skip) 04  ads_click        Click "Sign in" - skipped     -      |  |
|  |     ...                                                              |  |
|  |     ARTIFACTS                                                        |  |
|  |     [ Screenshot ] [ Video ] [ Trace ] [ Code ]                      |  |
|  |     +--------------------------------------------------------+       |  |
|  |     | // auto-generated executable spec for TC-002           |       |  |
|  |     | test('Below min cart', async ({ page }) => {           |       |  |
|  |     |   await page.goto('/login')                            |       |  |
|  |     |   ... (full step-by-step spec, ready to run in CI)     |       |  |
|  |     +--------------------------------------------------------+       |  |
|  |                                       [ Copy ]   [ Download ]        |  |
|  +----------------------------------------------------------------------+  |
+----------------------------------------------------------------------------+
```

**What you do**
- Open the **Scenarios** tab to drill into individual test cases. Each row carries a TC-### badge, the scenario name, and a status breakdown line ("4 of 4 passed - 4 skipped - completed in 11.1s").
- Expand a scenario to reveal the full step list — each row shows a status icon, a zero-padded step number, the action text (with " — skipped" suffix when relevant), and the duration on the right. Errors render as an italic secondary line in red below the step.
- Each scenario also has its own artifact tab strip (Screenshot / Video / Trace / Code). The Code tab shows the auto-generated, executable test spec in a syntax-highlighted code editor with Copy and Download buttons.
- The full Run Results Summary card (see 3.11) is pinned to the bottom of this page too.

**Why it matters**
- Scenario-level artifacts mean engineers debugging a single failure don't have to scroll through hundreds of irrelevant screenshots.
- Auto-generated test specs are industry-standard, exportable, and copy-paste-ready — drop them straight into your existing CI repo.
- The skip/blocked/passed taxonomy carries through from live execution to results, so runbook language stays consistent.

---

### 3.13 Automate History

```
+----------------------------------------------------------------------------+
|  HISTORY                                                                   |
+----------------------------------------------------------------------------+
|  Filter: [Suite v] [Date v] [Status v]                                     |
|                                                                            |
|  +----------------------------------------------------------------------+  |
|  | Apr 18 14:22  Checkout regression  (ok) 24/24    2m 47s   [ View ]   |  |
|  | Apr 18 12:01  Login smoke           (ok)  8/8    0m 41s   [ View ]   |  |
|  | Apr 18 09:30  Profile settings      (!) 11/12    1m 12s   [ View ]   |  |
|  | Apr 17 23:00  Heartbeat: full       (ok)142/142 12m 03s   [ View ]   |  |
|  | Apr 17 14:22  Search                (!)  9/12    2m 50s   [ View ]   |  |
|  +----------------------------------------------------------------------+  |
|                                                                            |
|  Trends:                                                                   |
|   - Avg duration down 18% over 30 days                                     |
|   - Self-healing saved an estimated 9.4 engineer-hours this month          |
+----------------------------------------------------------------------------+
```

**What you do**
- Browse, filter, and replay any past run.
- Compare runs to see whether a regression was introduced this week.

**Why it matters**
- Persistent history means investigations are forensic, not anecdotal.
- The "self-healing saved X hours" line is a hard ROI number for the next budget conversation.

---

### 3.14 Heartbeat Panel

```
+----------------------------------------------------------------------------+
|  HEARTBEAT - Continuous regression                          o LIVE         |
+----------------------------------------------------------------------------+
|  HEADER METRICS                                                            |
|  Issue: CHK-142 Checkout regression (24 cases) | Schedule: every 60 min    |
|  Next run in 18 min   |   Jira sync: ON  (last push 12 min ago)            |
|  [ Pause ]   [ Configure ]   [ Delete ]                                    |
|                                                                            |
|  INSIGHTS GRID  (2x2)                                                      |
|  +-----------------------------------+ +-----------------------------+     |
|  | LAST 24 HOURS                     | | JIRA SYNC                   |     |
|  | ##############################__  | | Last push:  12 min ago      |     |
|  | 96.8% pass rate - 47/49 runs      | | Today:      23 pushes       |     |
|  +-----------------------------------+ +-----------------------------+     |
|  +-----------------------------------+ +-----------------------------+     |
|  | ALERTS                            | | HEALING LOG (last run)      |     |
|  | (!) 3 new flaky tests this week   | | - TC-031 step 4 -- healed   |     |
|  | (!) 1 locator drift on /checkout  | |   via SiteModel             |     |
|  |     - auto-healed                 | | - TC-077 step 2 -- healed   |     |
|  | (ok) Coverage stable at 92%       | |   via Synonyms (login/sign-in)|   |
|  +-----------------------------------+ +-----------------------------+     |
|                                                                            |
|  RUNS                                                                      |
|  +----------------------------------------------------------------------+  |
|  | (ok) Apr 18 14:22  CHK-142 (24 cases)  24/24  2m 47s     [ View ]    |  |
|  | (ok) Apr 18 13:22  CHK-142 (24 cases)  24/24  2m 51s     [ View ]    |  |
|  +----------------------------------------------------------------------+  |
+----------------------------------------------------------------------------+
```

**What you do**
- Configure a regression suite to run on a recurring schedule. The header shows the issue key, case count, schedule cadence, next-run countdown, and Jira sync status — plus quick Pause / Configure / Delete actions.
- Read the 2x2 Insights grid: **Last 24 hours** as a coloured pass-rate bar, **Jira sync** stats (last push + today's pushes), the rolling **Alerts** list, and the **Healing log** for the most recent run with the strategy name on each entry.
- Browse the runs list below — every row shows the issue key alongside a case count so you always know how many tests sat behind that score.

**Why it matters**
- Regression becomes a service, not an event. No one waits for "regression Friday."
- The 2x2 insights grid is built so an exec can scan it in five seconds: pass rate, sync health, anything to worry about, and the system's own self-rescue activity.
- Self-healing keeps the suite alive between human attention cycles, and the per-strategy log shows *which* heal layer rescued each step — useful evidence when triaging UI drift.

---

### 3.15 Settings & Jira Integration

```
+----------------------------------------------------------------------------+
|  SETTINGS                                                                  |
+----------------------+-----------------------------------------------------+
|  General             |  AI PROVIDERS  (bring your own key)                 |
|  AI Providers        |   (o)  Provider A    Key: ........       [ Verify ]|
|  Browser             |   ( )  Provider B    Key: ........       [ Verify ]|
|  Environments        |                                                     |
|  Jira Integration    |  Privacy: All story content stays in your tenant.   |
|  Heartbeat Schedule  |                                                     |
|  Team & Roles        |  BROWSER                                            |
|                      |   Engine: (o) Chromium  ( ) Firefox  ( ) WebKit     |
|                      |   Mode:   (o) Headless  ( ) Headed                  |
|                      |                                                     |
|                      |  ENVIRONMENTS                                       |
|                      |   - Dev      https://dev.app.example.com            |
|                      |   - Staging  https://staging.app.example.com        |
|                      |   - Prod     https://app.example.com  (read-only)   |
|                      |                                                     |
+----------------------+-----------------------------------------------------+

+----------------------------------------------------------------------------+
|  JIRA SYNC                                                                 |
+----------------------------------------------------------------------------+
|  o  [ Test connection ]   [ Reconfigure OAuth ]              [ ON | off ]  |
|                                                                            |
|  Workspace:   acme.atlassian.net                                           |
|                                                                            |
|  PROJECTS                                                                  |
|   [x] CHECKOUT   Checkout v3                                               |
|   [x] PROFILE    User profile                                              |
|   [ ] BILLING    Billing service                                           |
|                                                                            |
|  PULL                                                                      |
|   Auto-pull new stories:    [ ON | off ]    Interval: [ 15 ] min           |
|                                                                            |
|  PUSH                                                                      |
|   Master push:              [ ON | off ]                                   |
|   +------------------------------------------------------------+           |
|   | [x] (icon) Post test execution summary as a comment        |           |
|   |     on every run                                           |           |
|   +------------------------------------------------------------+           |
|   +------------------------------------------------------------+           |
|   | [x] (icon) Push approved suggestions back to Jira          |           |
|   +------------------------------------------------------------+           |
|   +------------------------------------------------------------+           |
|   | [x] (icon) Update Jira story status from test results      |           |
|   +------------------------------------------------------------+           |
|                                                                            |
+----------------------------------------------------------------------------+
```

**What you do**
- Bring your own AI provider keys — story data never leaves your account boundary.
- The Jira dialog is a single Sync view. The header strip carries a connection status dot, **Test connection** and **Reconfigure OAuth** buttons, and a master ON/off toggle. Clicking **Reconfigure OAuth** flips the same dialog into the credentials view in place — no separate Connection tab to navigate.
- The workspace name appears below the header. Below that, the projects in the workspace render as a checkbox list so you can pick one or several.
- Pull settings are a simple On/Off segmented toggle with an interval input.
- Push settings have their own master toggle, then three big-tile checkboxes: post every run as a comment, push approved suggestions, update Jira story status from results.

**Why it matters**
- "Bring your own key" addresses every common procurement objection (data residency, cost control, vendor risk).
- The single-dialog Jira flow removes a tab dance that used to confuse first-time admins.
- Multi-project selection lets an admin scope what flows in (and what flows out) per workspace, which is the bare minimum a security review will ask for.

---

## 4. End-to-End User Journeys

Five real-world flows, each presented as a top-down ASCII diagram.

---

### Journey A — Story to Executable Tests

```
   o  Product manager writes story in Jira
   |
   v
   +----------------------------------------------+
   |  QA opens Generator, picks project chip,     |
   |  selects user story (dropdown then locks)    |
   +----------------------------------------------+
   |
   v
   +----------------------------------------------+
   |  Story Readiness panel scores AC live:       |
   |   - estimated case count                     |
   |   - story-aware preconditions ("user must    |
   |     already be logged in with a non-empty    |
   |     cart")                                   |
   |   - semantic ambiguity messages              |
   |   - domain-aware gap suggestions             |
   |   - compact-mode collapse hint               |
   +----------------------------------------------+
   |
   v   <>  AC strong enough?
   |       --- no --->  Suggestion sent back to PM in Jira
   |       --- yes --+
   |                 v
   +----------------------------------------------+
   |  Generate test cases (about 30 sec)          |
   +----------------------------------------------+
   |
   v
   +----------------------------------------------+
   |  Quality Audit runs automatically            |
   |  Coverage report runs automatically          |
   +----------------------------------------------+
   |
   v
   o  QA reviews, edits, quarantines, marks for automation
   |
   v
   Outcome:  a reviewed, approved test suite - ready to automate.
```

---

### Journey B — No-Code Automation Path

```
   o  QA opens the Automate stage tabs
   |
   v
   +----------------------------------------------+
   |  CLASSIFIER                                  |
   |  Header strip + "Manual Classification".     |
   |  Each case shows: automatable Y/N,           |
   |  confidence %, regression chip, risk level.  |
   +----------------------------------------------+
   |
   v
   o  QA clicks "Send to Expansion <N>"
   |  (filters to automatable AND confidence >=80%)
   |
   v
   +----------------------------------------------+
   |  EXPANDER                                    |
   |  Compact / Verbose toggle (Compact default). |
   |  Pipeline: classify -> expand -> validate.   |
   |  Quality score per case + auto-corrections.  |
   +----------------------------------------------+
   |
   v
   +----------------------------------------------+
   |  LIVE EXECUTION                              |
   |  - Healing chip row (4 strategies)           |
   |  - AUTH badges on auth-prefix steps          |
   |  - HEALED badges with strategy tooltip       |
   |  - skip vs blocked rendered distinctly       |
   |  - Activity feed (300px scroll, filters)     |
   +----------------------------------------------+
   |
   v
   +----------------------------------------------+
   |  RESULTS SUMMARY (pinned at bottom)          |
   |  passed/total - duration                     |
   |  Healed / Vision fallback / Confirmations    |
   |  5 artifact tiles with Download buttons      |
   +----------------------------------------------+
   |
   v
   Outcome:  reusable, self-documenting automation in your CI pipeline.
```

Note: in today's flow, classification is bundled into the same pipeline as expansion. The classifier's high-confidence handoff button is the natural launchpad for the expander, and the expander's runtime is what actually drives the browser.

---

### Journey C — Continuous Regression with Self-Healing

```
   o  QA enables Heartbeat, picks suite & schedule
   |
   v
   +----------------------------------------------+
   |  Suite runs every N minutes, unattended      |
   |  (auto-login pre-flight signs in if the      |
   |   first navigation lands on a login page)    |
   +----------------------------------------------+
   |
   v   <>  Step locator hit?
   |       --- yes --->  Pass; record evidence
   |       --- no  ---+
   |                  v
   +----------------------------------------------+
   |  4-LAYER HEAL CASCADE                        |
   |   1. SiteModel       (re-bind via cached     |
   |                       DOM model for the URL) |
   |   2. DOM stabilise   (wait, re-snapshot,     |
   |                       retry transient timing)|
   |   3. Synonyms        (try variants:          |
   |                       email/username,        |
   |                       login/sign-in, ...)    |
   |   4. LLM fallback    (describe the element,  |
   |                       cross-validate with    |
   |                       token overlap)         |
   |  If still failing -> mark for human review   |
   +----------------------------------------------+
   |
   v
   +----------------------------------------------+
   |  Results posted to Heartbeat panel + Jira    |
   |  Healing log shows which strategy rescued    |
   |  each step. Alerts raised for new flake /    |
   |  drift.                                      |
   +----------------------------------------------+
   |
   v
   Outcome:  regression as a service - silent when healthy, loud when it matters.
```

The same 4-layer cascade runs in both bypass mode (where the underlying browser tooling handles auth and the auth-prefix steps are intentionally **skipped**) and normal mode. In bypass mode the auto-login pre-flight handles the rare case where the configured environment requires a sign-in before the user's scenario can begin.

---

### Journey D — Quality Improvement Loop

```
   o  Test runs over weeks accumulate execution data
   |
   v
   +----------------------------------------------+
   |  Execution Insights surfaces flaky tests     |
   |  + ranked stabilisation suggestions          |
   +----------------------------------------------+
   |
   v
   o  QA reviews, applies fix, re-runs
   |
   v
   +----------------------------------------------+
   |  Suggestions Panel surfaces story-level      |
   |  improvements:                               |
   |   - domain-aware gaps (auth, payment, infra  |
   |     all use different baselines)             |
   |   - deferred-vs-actual gap distinction       |
   |     (was it left for later, or genuinely     |
   |     missed?)                                 |
   |   - ambiguous AC, missing edge cases         |
   +----------------------------------------------+
   |
   v
   o  PO reviews, approves -> pushed back to Jira
   |
   v
   +----------------------------------------------+
   |  Project Memory updated -> next generation   |
   |  is shaped by what worked and what didn't.   |
   |  Compact-mode runs benefit immediately       |
   |  because the runtime healer learns from the  |
   |  same memory.                                |
   +----------------------------------------------+
   |
   v
   Outcome:  the system gets measurably better at *your* product over time.
```

---

### Journey E — Coverage-Driven Development

```
   o  Release manager asks "what's our coverage?"
   |
   v
   +----------------------------------------------+
   |  Coverage report shows AC-by-AC mapping      |
   |  Gaps highlighted with severity              |
   +----------------------------------------------+
   |
   v
   o  QA clicks "Generate" next to each gap
   |
   v
   +----------------------------------------------+
   |  New focused test cases produced and queued  |
   |  for review                                  |
   +----------------------------------------------+
   |
   v
   +----------------------------------------------+
   |  Coverage recomputed                         |
   +----------------------------------------------+
   |
   v
   Outcome:  coverage goes from a vague claim to a tracked, closeable number.
```

---

## 5. Capability Matrix

| Capability                                      | User outcome                                                 | Maturity |
|-------------------------------------------------|--------------------------------------------------------------|----------|
| AI test case generation from AC                 | Days of authoring -> minutes per story                       | Live     |
| AI quality audit (5-dimension)                  | Bad cases caught before they pollute the suite               | Live     |
| Coverage report & gap analysis                  | Defensible coverage number; targeted gap-filling             | Live     |
| Story Readiness panel (live AC scoring)         | Catches weak AC before generation runs                       | Live     |
| Domain-aware gap suggestions                    | Different baselines for auth / payment / infrastructure      | Live     |
| Story-aware dependency preconditions            | "Logged-in cart with items" surfaced before tests are made   | Live     |
| Compact / Verbose expansion modes               | Quick review or full audit-grade spec, on a toggle           | Live     |
| Compact-mode collapse hint                      | Predicts reviewable step count before generation             | Live     |
| Test classification & confidence                | Automation effort focused on cases that pay back             | Live     |
| Regression risk levels (high / med / low)       | Triage suite into "must run" vs "nice to have"               | Live     |
| Classification CSV export                       | Auditable, board-ready summaries                             | Live     |
| Live execution with visual narration            | No black-box AI; every decision is visible                   | Live     |
| 4-layer self-heal cascade                       | Routine UI changes don't break the suite                     | Live     |
| Auto-login pre-flight                           | Tests don't fail because the env required a sign-in          | Live     |
| Skip vs Blocked distinction                     | Triage doesn't confuse intent with cascade                   | Live     |
| AUTH and HEALED badges on live steps            | Operators see what is scaffolding and what was rescued       | Live     |
| Vision-based fallback (LLM element resolution)  | Works when DOM-based matching fails                          | Live     |
| Human-in-the-loop confirmation                  | Safety net when AI confidence is low                         | Live     |
| Run Results Summary card                        | One end-of-run view, five artifact tiles                     | Live     |
| Per-scenario artifacts (screenshot/video/trace) | Engineers debug a single failure, not a haystack             | Live     |
| Page object library auto-generation             | Industry-standard, maintainable test code                    | Live     |
| Continuous regression (Heartbeat)               | 24/7 monitoring, silent when healthy                         | Live     |
| Heartbeat 2x2 insights grid                     | Pass rate, sync health, alerts, healing - in one glance      | Live     |
| Project memory & learning                       | The platform improves on *your* product over time            | Live     |
| Bidirectional Jira sync (single-dialog)         | Connect, pick projects, configure pull/push from one screen  | Live     |
| Story-improvement suggestion workflow           | QA insights flow back into product writing                   | Live     |
| Multi-environment & multi-browser               | Works in Dev / Staging / Prod, multiple browser engines      | Live     |
| Bring-your-own AI provider key                  | Story data stays in your account; no vendor risk             | Live     |
| Suggestion-driven test data resolution          | No hard-coded credentials in tests                           | Live     |
| Dependency graph between stories                | Cross-story impact visible at a glance                       | Beta     |
| Visual regression snapshots                     | Catch unintended visual changes                              | Roadmap  |
| API + UI hybrid scenarios                       | End-to-end coverage spanning UI and back-end APIs            | Roadmap  |

---

## 6. What Makes This Different

There are many test-automation tools. Most do one thing: a recorder, a runner, a dashboard, an AI test-writer. **StoryTest Pro is the first platform that treats the entire flow — from acceptance criterion to live regression — as a single, learning loop.**

1. **It starts at the story, not the click.** Recorders need a human to drive a browser. StoryTest Pro starts from the acceptance criterion itself, generates the test cases, *and then* drives the browser. The human reviews, doesn't author.

2. **Self-healing is a four-layer cascade, not a single trick.** Every locator the system picks is backed by a cached site model, a DOM-stabilise retry, a synonym variant pass, and (when an LLM key is configured) an element-description fallback that cross-validates its answer with token overlap. Each rescue is logged with the strategy name, so you can see the system's behaviour evolve over time.

3. **Every AI decision is auditable.** No black box. Every step has a screenshot, the chosen target, the heal strategy if any, and a confidence score — exportable, attachable to a Jira ticket, defensible in a compliance review.

4. **Human-in-the-loop, by design.** When confidence drops, the system pauses and asks. It never silently guesses. This is the difference between an experiment and an enterprise tool.

5. **The platform learns your product.** Project memory means the second story is generated better than the first, the tenth better than the second. Compact mode in particular gets sharper because the runtime healer is consulting the same memory that the generator wrote.

6. **One tool, not five.** Authoring, classification, expansion, execution, regression, dashboards, ticket sync — it's all here. No fragile glue between vendors.

---

## 7. Glossary

- **Acceptance criterion (AC)** — a statement of what a story must do to be considered complete (typically Gherkin: Given / When / Then).
- **Test case** — a structured scenario with steps and expected results, derived from one or more acceptance criteria.
- **Regression suite** — the set of test cases that should always pass; run on every release (and, with Heartbeat, between releases).
- **Locator** — the instruction that tells the test framework how to find an element on a page (e.g. "the button labelled Apply").
- **Self-healing** — the system's ability to recover from a broken locator by trying alternates, synonym variants, vision matching, or known-good fallbacks.
- **Site model** — a per-URL cache of the elements the system has previously interacted with; the first thing the heal cascade consults when a locator misses.
- **Page object library** — auto-generated, reusable code modules that wrap the locators and actions for a single page or component, so tests don't repeat themselves.
- **Compact mode** — an expansion mode (now the default) that produces one step per acceptance-criterion line and relies on runtime healing to fill in element details. Best for rapid iteration.
- **Verbose mode** — an expansion mode that produces a full per-line, prerequisite-aware step list, ideal for exporting a reviewable test spec.
- **Skipped** — a step the system intentionally did not run (e.g. an auth-prefix step in bypass mode where sign-in is handled elsewhere).
- **Blocked** — a step that could not run because an earlier step in the same case failed; rendered distinctly so operators don't confuse it with intent.
- **Auto-login pre-flight** — a four-substep inline sign-in attempted at the start of a run when the first page navigation lands on a login screen and credentials are configured for the active environment.
- **Vision fallback** — using a screenshot-aware AI model to identify the most likely matching element when DOM-based matching fails. Counted as a run signal in the Results Summary.
- **Healed** — a step the heal cascade rescued. Appears as an amber badge on the step and as a count in the Results Summary.
- **Confidence score** — the system's self-rating, 0–100%, of how sure it is that a chosen locator points to the right element.
- **Confirmations** — human-in-the-loop interventions during a run, counted as a run signal in the Results Summary.
- **Flaky test** — a test that fails intermittently for reasons unrelated to the actual feature under test.
- **Heartbeat** — the continuous, scheduled regression service inside StoryTest Pro.
- **Project memory** — the per-project record of past generations, outcomes, and team feedback used to tune future AI output.
- **BYOK** — Bring Your Own Key. Customers supply their own AI provider credentials so story data and test artifacts stay in their account boundary.

---

*StoryTest Pro — turn every story into a test, every test into a guarantee.*
