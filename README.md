# Qyrus QA · Consolidated Summary Report — Prototype

> Built as part of my application for the **Product Intern — AI Prototyping & Delivery Management** role at Qyrus.
> The Summary Report is listed as a real project in the JD. I built it before the interview.

**[→ Live Demo](https://luxury-profiterole-c3f66b.netlify.app/)**

---

## What this is

A single-page interactive prototype that simulates how Qyrus's Summary Report feature would aggregate QA test results across multiple workflow/folder executions — the artifact a QA lead or PM uses to make a go/no-go release decision.

This is the exact deliverable described in the JD under "Real Work":
> *"Build an interactive HTML prototype that simulates how the Summary Report feature aggregates results across multiple workflow and folder executions."*

---

## Product decisions made

| Decision | Rationale |
|---|---|
| Go/No-Go banner as the primary CTA | PMs need a single binary signal, not just raw numbers. The 90% pass threshold mirrors industry-standard release gates. |
| Live stat recalculation on suite toggle | QA leads often want to see impact of excluding a flaky suite — this makes that workflow instant |
| Expandable rows instead of a separate page | Keeps the PM in context; drill-down without navigation overhead |
| Filter by status (All / Failed / Passed / Skipped) | Reduces cognitive load during triage — failed-only view is the first thing a dev opens post-run |
| Export Summary instead of Download PDF | Named for the action, not the format — matches how PMs actually describe the artifact |

---

## Features

- **Multi-suite aggregation** — select/deselect test suites; all stats update live
- **Go/No-Go release decision** — auto-calculated against ≥90% pass threshold
- **Suite breakdown table** — pass/fail/skip counts, status badges, execution duration
- **Expandable test cases** — click any row to see individual test results
- **Status filter** — view All / Failed Only / Passed Only / Skipped Only
- **Generate Report modal** — summary view with release recommendation
- **Export Summary** — downloads a structured .txt report with the Go/No-Go verdict

---

## Tech

Single-file HTML/CSS/JS — no build step, no dependencies, no framework.
Deliberately kept simple: the goal was a fast, demoable prototype, not a production app.

---

## What I'd build next

If this were a real sprint:
- Connect to Qyrus's actual execution API to pull live run data
- Add Jira ticket linking — surface which open tickets map to failed tests (the current gap in most QA workflows)
- Release history timeline — compare pass rates across the last N builds
- Slack/email notification trigger on NO-GO decision

---

*Built by Hitan · April 2026*
