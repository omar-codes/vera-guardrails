# vera-guardrails

Safety guardrail configuration for the [Vera](https://github.com/omar-codes/vera) AI orchestrator.

## Structure

```
config/
  guardrails.yaml   # Main guardrail rules
```

## Configuration

The `config/guardrails.yaml` file defines:

- **forbidden** — Actions that are always blocked
- **escalate_to_human** — Actions requiring human approval
- **autonomous** — Actions that can run without approval
- **cost_thresholds** — Spending limits per objective and per day
- **worker_constraints** — Timeout and retry limits for workers

## Usage

Set the `VERA_GUARDRAILS_REPO` environment variable to point to this repo:

```
VERA_GUARDRAILS_REPO=omar-codes/vera-guardrails
```

Vera pulls this config on daemon startup and enforces the rules at runtime.
