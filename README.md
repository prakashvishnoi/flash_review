# Execution Intelligence Observatory

**Independent research & engineering program on DeFi execution quality, MEV, and on-chain risk.**


---

## Overview

The Execution Intelligence Observatory studies **how
value is won or lost at the moment a transaction executes on Ethereum** — the gap between a strategy that looks profitable on paper and what a single, independent operator can actually capture once latency, competition, fees, and market impact are accounted for.

It began as an applied trading/MEV investigation and deliberately evolved into a **measurement
discipline**: instead of claiming edges, it measures them end to end on realistic replays and keeps an auditable record of what works, what doesn't, and why. 


---

## What's built

**Execution & MEV measurement.** A read-only pipeline that reconstructs on-chain situations, replays
them on mainnet forks, and measures the realistic outcome of candidate execution strategies
(arbitrage, liquidations, oracle-driven opportunities) after costs. Results feed a structured
registry of verdicts instead of one-off scripts.

**Aave liquidation stack.** A flash-loan-based liquidation smart contract plus an off-chain
subscriber/executor that monitors borrower health and builder inclusion. Designed around strict
safety gates: shadow/paper mode by default, a single authorized submitter, and no live action
without explicit sign-off.

**Oracle & market-microstructure research.** Studies of price-feed freshness, oracle-vs-market
lead/lag, and the relationship between competition, latency advantage, and how much measured value
an operator can actually retain.

**Derivatives & volatility research (paper/shadow).** Exploratory work on variance-risk-premium and
options structures, run as paper trades for research only — never live capital.

**Data & analytics.** Collectors and analyzers that turn raw on-chain and market data into
reproducible metrics, with SQL/dashboard reporting for execution-quality and MEV-loss analysis.

---

## Research approach

- **Measure, don't assume.** Claims are backed by cost-aware fork replays, not idealized backtests.
- **Negative results are results.** Disproven ideas are documented with the measured reason and a
  reopen condition — the registry of closed surfaces is treated as a primary asset.
- **Statistical honesty.** Out-of-sample / forward-chaining validation, multiple-testing
  adjustment, small-sample interval widening, and explicit *associational-not-causal* labeling where
  identification isn't established.
- **Reproducibility.** Pinned block ranges, commit hashes, parameters, and seeds; deterministic
  replays so every reported number can be regenerated.
- **Safety first.** Live execution is gated behind human authorization; research runs read-only.

---

## Selected outcomes (high level)

- A systematic sweep of operator-accessible execution edges returned **mostly honest "closed"
  verdicts** once real costs were included.
- One market-bound opportunity (oracle-lag-driven liquidation) was **confirmed but shown to be
  competition-limited** for a single operator — captured as a precise, bounded finding.
- The program **pivoted from trading to measurement**: producing transaction-audit reports.

*(Specific figures, thresholds, routes, and methods remain in the private manuscripts and codebase.)*

---

## Tech stack & skills

**Languages:** JavaScript / TypeScript (Node.js), Solidity, Python, SQL.

**Blockchain / DeFi:** Ethereum & the EVM, Aave v3, Uniswap v2 / v3 / v4, AMMs, Chainlink oracles,
flash loans, MEV / proposer-builder separation, transaction/bundle construction.

**Infrastructure:** self-hosted execution clients (Erigon, Geth), Foundry / Anvil deterministic
forks, Hardhat, process management (PM2), Linux server operations, scheduled data pipelines.

**Quant / research:** market microstructure, applied statistics (regression, multiple-testing
control, out-of-sample validation), reproducible experiment design, Dune / SQL analytics.

**Engineering practice:** safety-gated system design, trade-secret / IP discipline, honest
negative-results methodology, thorough technical writing and documentation.

---

## Research & writing

Two manuscripts are in preparation from this work:

1. Fork-based DeFi execution system classifying edges with net PnL.
2. **An empirical model** relating competition, latency advantage, and concentration to the value an operator actually retains.

Both are accompanied by a literature review, a reproducibility manifest, and an internal
research-integrity and legal/IP review process.

---

## Why there's no source code here

The implementation and the unpublished manuscripts are kept private — the code as a **trade secret**,
the papers pending an **internal legal/IP review**. This public page therefore describes the work at a
level that conveys scope and skill **without disclosing the private edge or unpublished results**.

Deeper technical discussion, a code walkthrough, or the draft manuscripts can be shared **privately,
on request**, under an appropriate confidentiality understanding.

---

## About

**Prakash Vishnoi** — Independent DeFi execution researcher & engineer.

- GitHub: [@prakashvishnoi](https://github.com/prakashvishnoi)
- Contact: prakashvishnoi63@gmail.com 

> This repository intentionally contains documentation only. No source code, datasets, private
> keys, infrastructure details, or unpublished research results are published here.
