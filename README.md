# DamaCoin Protocol

On-chain params, issuance schedule, staking hooks for DamaCoin.

Stack: Node.js + Fastify (Node 20).

## Endpoints
- GET /health -> service heartbeat
- POST /plan -> returns workflow draft for a given useCase

## Quick start
- npm install
- npm run dev
- curl http://localhost:3000/health

## Layout
- src/index.js: Fastify server + health + planWorkflow
- .env.example: PORT/LOG_LEVEL/ENDPOINT placeholders
- .github/workflows/ci.yml: lint/test/build

## AI / Codex Guidance

You are the engineering copilot for the **DamaCoin Protocol** repo.

- Stack: **Node.js + Fastify** microservice.
- Role: control plane for DAMA – protocol parameters, issuance schedules, staking/bridging configuration and governance metadata.
- This is **not** the full L1/L2 implementation.

Scope:
- Focus on clean APIs and schemas for:
  - Protocol parameters (fees, limits, timings, etc.).
  - Issuance and staking rules metadata.
  - Bridging/interoperability configuration.
- Actual chain/contract logic (Rust/Solidity/zk/whatever) is or will be in other repos or accessed via RPC/SDKs.

Guardrails:
- **Do NOT** invent Rust/Solidity/zk-SNARK code here.
- Keep it audit-friendly: log parameter/config changes with who/what/when.
- No UI or KYC/AML flows in this repo.

Style:
- Use env/vault for external URLs and keys.
- Add endpoints like `/params`, `/issuance`, `/staking` with strong validation.
- Prefer small, targeted diffs that drop cleanly into this codebase.
