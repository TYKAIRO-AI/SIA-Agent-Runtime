# SIA — Structured Intelligence Agent


> **A TYKAIRO AI product** — Founded by **Mahmoud Hisham**
### SIA Agent Runtime

**Local-first reliability layer for small language models.**

**SIA (Structured Intelligence Agent)** is an experimental AI agent runtime focused on making smaller local models more dependable at real software-development work. Instead of relying only on a larger model, SIA moves more reliability into the runtime: planning, tool selection, validation, verification, recovery, and evidence-based completion.

> **Public showcase repository**  
> This repository intentionally contains architecture notes, design documents, and safe examples only. The proprietary SIA implementation is not published here.

## Why SIA?

Small local models can often understand a coding task, but reliability drops when they must:

- plan multi-step work,
- select and call tools correctly,
- modify multiple project files,
- recover from invalid tool arguments,
- verify that changes really worked,
- and avoid declaring success too early.

SIA explores a runtime-first approach to those problems.

## Core Architecture

```text
User Goal
   |
   v
Requirements
   |
   v
Deterministic Planning
   |
   v
Tool Resolution -> Schema Validation -> Permission Gate
   |
   v
Execution
   |
   v
Result Validation
   |
   v
Project-Wide Verification
   |
   v
Self Review -> Bounded Repair
   |
   v
Evidence-Based Completion
```

## Project Status — September 27, 2026

SIA is currently in the **reliability hardening and tool-intelligence phase**.

Current public-safe status:

- deterministic planning and requirement/artifact tracking are implemented
- project-wide verification, self-review, bounded repair, stale-evidence invalidation, and completion gates are implemented and being hardened
- reliable tool intelligence is the active engineering focus
- the public benchmark harness v0 is available, while controlled comparative SIA-vs-baseline results are still pending
- reliability telemetry is being brought forward into the current stage so tool/model calls, repairs, verification failures, execution time, and resource usage can be measured early
- persistent agent state is planned for goals, plans, artifacts, evidence, tool state, and progress independent of the UI
- MCP interoperability remains a major next layer, including an OpenAPI-to-tool/MCP import path
- controlled worker-agent / multi-agent orchestration is now under architecture exploration, but broader autonomy will stay behind SIA's verification and reliability gates

> Private development regression suites have reached large passing-test milestones across development iterations. These internal counts are engineering evidence, not public benchmark scores.

## Current Focus

### Planning & execution control
- deterministic planning before project changes
- explicit requirement tracking
- artifact-aware task execution
- duplicate/no-progress protection

### Verification & recovery
- project-wide verification
- self-review before completion
- bounded repair loops
- stale-evidence invalidation
- completion gates to reduce false success

### Tool intelligence
The active architecture layer focuses on:
- unified native/MCP/custom tool registry
- capability-aware intent-to-tool routing
- input schema validation
- deterministic repair of simple argument errors
- permission and risk controls
- tool-result verification
- recovery taxonomy and reliability telemetry

## Design Principles

- **Local-first** — designed for local models and ordinary developer hardware
- **Model-agnostic runtime** — keep orchestration outside the model where possible
- **Deterministic where practical** — do not ask the LLM to solve problems normal code can solve reliably
- **Evidence over confidence** — task completion should be supported by verification
- **Bounded recovery** — retries and repairs must have clear limits
- **Simple user experience** — complexity belongs inside the runtime, not in the prompt

## Roadmap

| Area | Status |
|---|---|
| Deterministic planning | Implemented |
| Artifact / requirement tracking | Implemented |
| Project-wide verification | Implemented |
| Self-review and bounded repair | Implemented |
| Reliable tool intelligence | **In progress** |
| Reliability telemetry | **Starting in current stage** |
| MCP interoperability | Planned |
| OpenAPI → Tool/MCP import | Planned |
| Context intelligence | Planned |
| Persistent agent state | Planned |
| Reusable skills/workflows | Planned |
| Controlled worker agents | Architecture exploration / later implementation |
| Benchmark harness | **Public v0 available; controlled comparison pending** |

See [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) and [docs/ROADMAP.md](docs/ROADMAP.md).

## Benchmark Philosophy

SIA should be measured against the **same local model on the same hardware and task set**, comparing:

1. the raw model / basic agent loop
2. the same model running through SIA

Useful metrics include task success, tool-call success, invalid arguments, repair count, verification failures, false completion, runtime, and resource usage.

A small public-safe benchmark harness is available in [`benchmarks/v0`](benchmarks/v0). It defines fixed generic reliability cases, a result schema, and a dependency-free scorer. **No comparative SIA performance numbers are published yet**; those should only be added after controlled runs using the same model, hardware, task set, and evaluation conditions.


## Progress Reports

Follow SIA's AI-native development journey through simple public progress reports:

- [Report #001 — English](reports/001-ai-native-development-report.en.md)
- [Report #001 — العربية](reports/001-ai-native-development-report.ar.md)

## Repository Scope

This public repository is meant to communicate the engineering direction of SIA without exposing its private production code.

Included:
- architecture documentation
- reliability design notes
- safe illustrative examples
- roadmap and benchmarking methodology
- public-safe benchmark cases, result format, and scorer

Not included:
- proprietary runtime implementation
- private prompts or internal policies
- production orchestration code
- private test corpus

## Project Ownership

**Project Owner & Creator:** Mahmoud Hisham  
**Role:** Founder, product direction, development direction, testing, verification, and final approval of SIA — Structured Intelligence Agent  
**GitHub:** [@Turkeyz1](https://github.com/Turkeyz1)

---

Copyright © 2026 Mahmoud Hisham. All rights reserved.  
No license is granted for the proprietary SIA implementation.
