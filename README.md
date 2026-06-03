<div align="center">

<img src="assets/banner.jpg" alt="Glaunch — Launch Your Potential" width="100%" />

<br /><br />

# GLaunch

**Launch tokens that keep moving while you build.**

[![Website](https://img.shields.io/badge/Website-glaunch.world-E91E8C?style=for-the-badge&logo=google-chrome&logoColor=white)](https://glaunch.world/)
[![X](https://img.shields.io/badge/Follow-%40Glaunchworld-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/Glaunchworld)
[![Base](https://img.shields.io/badge/Chain-Base-0052FF?style=for-the-badge&logo=coinbase&logoColor=white)](https://base.org)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Early%20Access-success?style=for-the-badge)](https://glaunch.world/)

[Terminal](https://glaunch.world/terminal) · [Market](https://glaunch.world/market) · [Documentation](docs/overview.md) · [Report Bug](https://github.com/Glaunchpad/Glaunch/issues/new?template=bug_report.yml) · [Request Feature](https://github.com/Glaunchpad/Glaunch/issues/new?template=feature_request.yml)

</div>

---

## Overview

**GLaunch** is an AI-powered launch desk on **Base**. Deploy tokens, scan markets, manage wallets, and track performance — all from a single conversational terminal powered by **GLA**, your on-chain launch assistant.

> This repository is the **public home** for GLaunch: product docs, community templates, and release notes.  
> **Application source code is not published here** to protect integrations, infrastructure, and launch logic.

---

## Features

| Module | Description |
|--------|-------------|
| **Terminal** | Chat with GLA to deploy tokens, transfer funds, claim earnings, and run market scans |
| **Market** | Browse trending launches, live charts, and token discovery on Base |
| **Wallet** | Privy-powered auth with embedded wallet, withdrawals, and royalty claims |
| **My Launches** | Dashboard for your Flaunch deployments and revenue |
| **PnL Analytics** | Portfolio and performance tracking across your positions |

### GLA — AI Launch Assistant

GLA handles the operational layer so you can focus on building:

- Natural-language token deploys via [Flaunch](https://flaunch.gg)
- Market scans, token search, and portfolio reads
- Wallet actions: transfer, claim, and on-chain execution
- Smart guardrails: daily deploy limits and cooldown enforcement

---

## Tech Stack

<p align="center">
  <img src="https://img.shields.io/badge/Next.js-15-black?style=flat-square&logo=next.js" alt="Next.js" />
  <img src="https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React" />
  <img src="https://img.shields.io/badge/TypeScript-5.7-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Tailwind-3.4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS" />
  <img src="https://img.shields.io/badge/Privy-Wallet-7C3AED?style=flat-square" alt="Privy" />
  <img src="https://img.shields.io/badge/Viem-2.x-8B5CF6?style=flat-square" alt="Viem" />
  <img src="https://img.shields.io/badge/PostgreSQL-DB-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL" />
</p>

**Integrations:** [Flaunch](https://flaunch.gg) · [Privy](https://privy.io) · [DexScreener](https://dexscreener.com) · [GeckoTerminal](https://www.geckoterminal.com) · [CoinGecko](https://www.coingecko.com)

---

## Architecture

High-level flow — no proprietary implementation details:

```mermaid
flowchart LR
    User([User]) --> Terminal[GLA Terminal]
    Terminal --> AI[AI Orchestrator]
    AI --> Tools[Action Tools]
    Tools --> Flaunch[Flaunch API]
    Tools --> Chain[Base Network]
    Terminal --> Market[Market Layer]
    Market --> Charts[Chart Providers]
    User --> Privy[Privy Auth]
    Privy --> Wallet[Embedded Wallet]
    Wallet --> Chain
```

See [docs/architecture.md](docs/architecture.md) for a deeper (still non-source) overview.

---

## Getting Started

GLaunch is a hosted product. There is **no public self-host bundle** in this repository.

1. Visit **[glaunch.world](https://glaunch.world/)**
2. Sign in with **Google**, **X**, or **Farcaster** via Privy
3. Open the **Terminal** and tell GLA what you want to launch

For environment and deployment concepts (reference only), see [docs/overview.md](docs/overview.md).

---

## Roadmap

- [x] AI terminal with deploy, transfer, and claim tools
- [x] Market discovery and live charts
- [x] Wallet dashboard and royalty claims
- [x] PnL analytics
- [ ] Public API for launch partners
- [ ] Mobile-optimized terminal
- [ ] Multi-chain expansion

Track progress in [CHANGELOG.md](CHANGELOG.md) and [GitHub Issues](https://github.com/Glaunchpad/Glaunch/issues).

---

## Community

<div align="center">

[![X](https://img.shields.io/badge/X-%40Glaunchworld-000?style=social&logo=x)](https://x.com/Glaunchworld)
[![GitHub Org](https://img.shields.io/badge/GitHub-Glaunchpad-181717?style=social&logo=github)](https://github.com/Glaunchpad)
[![Issues](https://img.shields.io/github/issues/Glaunchpad/Glaunch?style=social&logo=github)](https://github.com/Glaunchpad/Glaunch/issues)
[![Stars](https://img.shields.io/github/stars/Glaunchpad/Glaunch?style=social&logo=github)](https://github.com/Glaunchpad/Glaunch/stargazers)

</div>

We welcome bug reports, feature ideas, and documentation improvements. See [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Security

Found a vulnerability? Please **do not** open a public issue. Read [SECURITY.md](SECURITY.md) for responsible disclosure.

---

## License

This repository is licensed under the [MIT License](LICENSE).

Application source, proprietary integrations, and production infrastructure are **not** included in this public repository.

---

<div align="center">

**Built on Base** · Powered by **GLA**

<br />

<sub>GLaunch © 2026 Glaunchpad. All rights reserved.</sub>

</div>
