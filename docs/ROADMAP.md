# SIA Roadmap

This roadmap describes the engineering direction of the project. Ordering may change as testing reveals new failure modes.

## Stage A — Deterministic Planning

Status: **Implemented**

Focus:
- planning controller
- requirement extraction
- artifact manifest
- plan validation gate
- duplicate/no-progress protection

## Stage B — Verification & Repair

Status: **Implemented / being hardened**

Focus:
- project-wide verification
- validation controller
- self-review
- bounded repair
- stale-evidence invalidation
- completion gate

## Stage C — Reliable Tool Intelligence

Status: **In progress**

Focus:
- unified tool registry
- capability-based tool discovery
- intent-to-tool resolution
- schema validation
- deterministic argument repair
- permissions
- result validation
- recovery taxonomy
- reliability telemetry from Stage C onward
- model/tool call metrics
- repair and verification-failure metrics
- execution-time and resource/context measurements

## Stage D — MCP Integration

Status: **Planned**

Focus:
- MCP discovery
- MCP-to-SIA adapter
- stable tool IDs
- trust and scope controls
- approvals
- timeouts
- output limits
- OpenAPI-to-tool/MCP importer
- later exporter/generator experiments

## Stage E — Context Intelligence

Status: **Planned**

Focus:
- context router
- budget management
- compaction
- large-output handling
- persistent agent state independent of the UI
- durable Goal / Plan / Artifacts / Evidence / Tool State / Progress

## Stage F — Skills

Status: **Planned**

Focus:
- reusable workflows
- skill metadata
- capability routing
- verified documentation-to-skill experiments

## Stage G — Controlled Workers

Status: **Architecture exploration / later implementation**

Focus:
- controller-owned workers
- narrow task scopes
- sequential operation on limited hardware
- independent verification
- chief/controller delegation
- bounded build → verify → repair loops
- worker isolation so multi-agent capability cannot bypass SIA reliability gates

## Stage H — Model Routing

Status: **Later stage**

Focus:
- optional model routing
- preserve single-model mode
- choose models by capability and resource budget

## Benchmark track

An initial public-safe benchmark harness is available in `benchmarks/v0`. It is designed to compare the same model with and without SIA under controlled conditions while keeping proprietary runtime details private.

Current v0 measurements:
- end-to-end task success
- tool-call success
- invalid arguments
- repair frequency
- verification failures
- false completion
- elapsed time
- resource usage

Status: **Harness available; controlled comparative results pending.**

Telemetry should begin during Stage C and mature alongside later stages rather than being postponed until the end of the roadmap.

Public benchmark results should be published only after an actual controlled run. Synthetic or placeholder values must not be presented as evidence of SIA performance.
