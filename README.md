# Verify.et API Skill

A portable Agent Skill for integrating and debugging Verify.et transaction verification flows.

The skill is designed for agents helping developers build server-side Verify.et adapters, checkout verification, webhook receivers, polling/SSE status flows, idempotency handling, and bank-specific request validation.

## Contents

```text
verify-et-api/
|-- verify-et-api/
|   |-- SKILL.md
|   |-- references/
|   |   |-- api-endpoints.md
|   |   |-- bank-specs.md
|   |   `-- error-codes.md
|   |-- patterns/
|   |   |-- integration-methods.md
|   |   `-- webhooks.md
|   `-- debugging/
|       |-- common-mistakes.md
|       `-- production-checklist.md
`-- LICENSE
```

## What It Covers

- API-key authentication with `x-api-key`
- `POST /api/verify`, status polling, SSE, history, and test-webhook flows
- Explicit bank payloads and universal receipt/reference routing
- `200` inline completion versus `202` queued verification handling
- Webhook receiver validation, retries, and idempotent processing
- Error classification, retry decisions, credits/quota, and rate-limit behavior
- Production security, logging, and testing checks

## Install

```bash
npx skills add NegusNati/verify-et-api-skill --skill verify-et-api
```

## Validation

Recommended checks before publishing:

```bash
python3 /Users/negusnati/.codex/skills/.system/skill-creator/scripts/quick_validate.py .
```

Also run a markdown link check from the skill root to ensure every relative file reference resolves.

## Maintenance

Keep `SKILL.md` concise and move detailed contracts into `references/`, `patterns/`, or `debugging/`. When Verify.et API behavior changes, update the relevant reference first, then adjust the main workflow only if the agent's top-level decision process changes.
