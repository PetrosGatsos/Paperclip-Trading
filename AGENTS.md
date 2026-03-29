# Trading Bot Project Rules

## Project scope
This repository defines the V1 long-only Nasdaq-500 trading-bot system.

Primary objective:
- design, document, validate, and operationalize a multi-agent trading workflow for the 500 largest Nasdaq-listed companies by market capitalization

V1 constraints:
- long-only
- daily or end-of-day cadence
- explainable logic
- strict risk controls
- backtesting before paper trading
- paper trading before any live rollout
- artifact-first workflow

## Workspace boundary
- Treat the current project workspace as the only writable working area.
- Do not access or modify any `/instructions/` path during normal project execution.
- Do not rely on agent-local managed instruction bundles as the project source of truth when the repo workspace is active.
- If the current run is not bound to the repo workspace, stop any bootstrap/hiring workflow and report `FALLBACK_WORKSPACE_ACTIVE`.

## Source of truth
The repository is the canonical source of truth for this project.

Use these folders as the role definitions:
- `lead_systems_architect/`
- `universe_manager/`
- `market_data_agent/`
- `feature_engineer/`
- `signal_engine/`
- `risk_manager/`
- `portfolio_manager/`
- `backtest_agent/`
- `execution_agent/`
- `monitoring_agent/`

Each role folder contains:
- `AGENTS.md`
- `HEARTBEAT.md`
- `SOUL.md`
- `TOOLS.md`

## Project outputs
Create and maintain outputs only inside:
- `docs/`
- `artifacts/`
- `state/`

Expected structure:
- `docs/architecture/`
- `docs/strategy/`
- `docs/execution/`
- `artifacts/universe/`
- `artifacts/data/`
- `artifacts/features/`
- `artifacts/signals/`
- `artifacts/risk/`
- `artifacts/portfolio/`
- `state/reports/`

## Manager / worker model
The Lead Systems Architect is the workflow manager.

The expected org structure is:
- Lead Systems Architect
  - Universe Manager
  - Market Data Agent
  - Feature Engineer
  - Signal Engine
  - Risk Manager
  - Portfolio Manager
  - Backtest Agent
  - Execution Agent
  - Monitoring Agent

The Lead Systems Architect must:
- reconcile system design
- create dependency-safe tasks
- delegate work in order
- validate downstream handoffs
- keep progress documented

Worker agents must:
- stay within assigned scope
- produce explicit markdown artifacts
- avoid broad architectural rewrites unless explicitly asked
- escalate missing upstream dependencies instead of guessing

## Required dependency order
Use this order unless a documented blocker requires deviation:

1. Universe Manager
2. Market Data Agent
3. Feature Engineer
4. Signal Engine
5. Risk Manager
6. Portfolio Manager
7. Backtest Agent
8. Execution Agent
9. Monitoring Agent

## Hiring rules
- Hiring must use actual Paperclip hire approvals, not plain issues named “Hire X”.
- Do not treat a normal task as a successful hire.
- Do not claim the org is initialized unless actual hire approvals exist and the agents appear in the org chart.

## Project-binding rules
Before bootstrapping agents or delegating major work, verify:
- the run is bound to the repo-backed project workspace
- repo files are visible from the active working directory
- outputs land inside the project workspace
- project rules are actually being applied

If these conditions are not true:
- report the mismatch clearly
- do not continue org bootstrap
- do not continue workspace-dependent setup
- do not pretend initialization succeeded

## Write behavior
- If a file already exists and the new content is not materially different, do not call an edit tool.
- Return exactly: `No document changes required.`
- Prefer updating existing artifacts over duplicating them.

## Safety and quality rules
- Prefer deterministic rules over vague heuristics.
- Prefer documented handoffs over hidden assumptions.
- Prefer explicit schemas over prose-only descriptions.
- Prefer auditable decisions over clever but opaque logic.
- Protect capital before optimizing returns.

## Minimum completion standard
A task is only complete when:
- the requested artifact exists
- the artifact is written in the project workspace
- downstream inputs and outputs are clear
- blockers are explicitly documented if progress is limited
