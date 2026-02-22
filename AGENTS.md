# Land Documentation – Agent Instructions

## Project

This is the developer documentation for the Land B2B lending data API, built with [Mintlify](https://mintlify.com).

## Terminology

Use the Land domain model consistently:

| Term | Definition |
| --- | --- |
| Wallet | An on-chain address identified by `chain` + `address` |
| Obligation | A wallet's lending position within a specific pool |
| Position | A single supply or borrow within an obligation |
| Market | A single asset in a lending pool (supply/borrow rates, risk params) |
| Token | Asset metadata (symbol, decimals, chain address) |
| Price | Oracle-reported USD price with staleness tracking |
| Health factor | Distance from liquidation (< 1.0 = liquidatable) |
| LTV | Loan-to-value ratio (borrow value / collateral value) |

**Do not use:** "reserve" (use "market"), "account" (use "wallet"), "vault" (use "pool"), "transaction" (use "event" or "transfer").

## Style

- Developer-focused, concise, second person ("you")
- Code examples in TypeScript using `@trylandeu/land-sdk`
- Curl examples for API Reference pages
- Present tense, active voice
- No marketing language or superlatives
- No emojis

## Content Scope

- **In scope:** Public data-plane API (`/wallets`, `/markets`, `/obligations`, `/tokens`, `/prices`, `/history`, `/webhooks`, `/healthz`, `/readyz`) and the TypeScript SDK
- **Out of scope:** Internal control-plane endpoints (`/cp/v1/*`), admin console UI, deployment/infrastructure

## Keeping Docs in Sync

When the backend API changes (new endpoints, modified schemas, new query parameters):
1. Update `api-reference/openapi.json` to match the live spec, enriching any new response schemas
2. Update the relevant guide pages with new SDK examples
3. Update `docs.json` navigation if new endpoint groups are added
