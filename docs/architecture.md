# Architecture

This document describes GLaunch at a system level. It intentionally omits implementation details and proprietary logic.

## System Layers

```
┌─────────────────────────────────────────────────────────┐
│                     Client (Browser)                     │
│  Next.js App Router · React 19 · Tailwind CSS           │
└──────────────────────────┬──────────────────────────────┘
                           │
┌──────────────────────────▼──────────────────────────────┐
│                   Application API                        │
│  Route handlers · Auth gates · Rate limits                 │
└──────────┬───────────────────────────────┬──────────────┘
           │                               │
┌──────────▼──────────┐         ┌──────────▼──────────┐
│   AI Orchestrator   │         │   Data & Market     │
│   GLA + Tool Exec   │         │   Charts · Tickers  │
└──────────┬──────────┘         └──────────┬──────────┘
           │                               │
┌──────────▼───────────────────────────────▼──────────────┐
│                    External Services                     │
│  Flaunch · Privy · Pinata · DexScreener · GeckoTerminal  │
└──────────────────────────┬──────────────────────────────┘
                           │
┌──────────────────────────▼──────────────────────────────┐
│                    Base (L2)                             │
│  Token deploys · Transfers · Claims                      │
└─────────────────────────────────────────────────────────┘
```

## Core Modules

### Terminal

The terminal is the primary interaction surface. User messages flow through an AI orchestrator that can invoke typed tools for on-chain and market actions.

### Market

Aggregates token metadata, pricing context, and embedded charts from third-party providers. Does not custody user funds.

### Wallet

Uses Privy for authentication and embedded wallet management. On-chain writes are initiated only after explicit user intent through GLA or UI actions.

### Launch Limits

Production deployments enforce configurable rate limits (e.g., daily deploy caps and cooldown windows) to protect users and infrastructure.

## Data Storage

Persistent state (deploy logs, user-linked metadata) is stored in PostgreSQL. Schema and migration scripts are maintained in the private codebase.

## Security Model

- Secrets never ship to the client
- Wallet actions require authenticated sessions
- Tool execution is server-side with validation
- Public repository contains no credentials or internal endpoints
