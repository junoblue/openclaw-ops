# Harness Routing Policy v1

## Status
Drafted and approved for use as operating baseline.

## Core Rules
1. Treat each task as a repeatable harness run, not ad hoc chat.
2. Every run must include: objective, inputs/sources, process steps, outputs/artifacts, verification checks, rollback/fallback notes.
3. Routing decisions must be traceable: explicitly state why an agent/model was chosen.
4. Delegate to one specialist when there is a clear advantage; avoid unnecessary fan-out.
5. `oc-thor-codex` remains final integrator/owner for combined outputs.
6. Prefer deterministic workflows (CLI/API/script) over manual UI flows when possible.
7. Mark uncertain inferences explicitly; separate evidence-backed facts from interpretation.
8. Require verification gates for all production-usable outputs.
9. External/high-impact actions require human review before execution.
10. OpenClaw config edits require explicit human approval before execution.
11. For Google ecosystem tasks, prefer `oc-thor-gemini` first, then codex integration validation.
12. For polished synthesis/briefing outputs, prefer `oc-thor-claude`, then codex factual/integration check.

## Current Project Constraint
- X/Twitter monitoring via `oc-thor-grok` is deferred for now (on hold until project kickoff).

## Validation Standard
- Use scorecard mode with reliability target: **>= 90%**.

## Baseline Drill Set
1. Google workflow drill (Gemini-led, Codex-validated)
2. X trend-monitor drill (defined but currently deferred)
3. Multi-agent synthesis drill (Gemini + Grok + Claude inputs, Codex integration)

## Evidence + Traceability Template
For each run, include:
- Delegated agent
- Reason selected
- Expected output
- Acceptance criteria
- Verification result (pass/fail + score)
- Fallback/rollback path
