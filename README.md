# Execution Intelligence Observatory

**Independent research & engineering program on DeFi execution quality, MEV, and on-chain risk.**


---

## Overview

The Execution Intelligence Observatory studies **how
value is won or lost at the moment a transaction executes on Ethereum** — the gap between a strategy that looks profitable on paper and what a single, independent operator can actually capture once latency, competition, fees, and market impact are accounted for.

It began as an applied trading/MEV investigation and deliberately evolved into a **measurement
discipline**: instead of claiming edges, it measures them end to end on realistic replays and keeps an auditable record of what works, what doesn't, and why. 


---

## Repository contents

A **review repository**: documentation, the research preprints, and one of the books. Start here:

- **[docs/METHODOLOGY.md](docs/METHODOLOGY.md)** — how the system works end to end (the evidence ladder, verdict taxonomy, the retention lens, infrastructure, safety).
- **[docs/LEARNING_ROADMAP.md](docs/LEARNING_ROADMAP.md)** — the structured theory + tech path behind the work, with target-role mapping and canonical references.
- **[papers/](papers)** — the two research preprints:
  - *Paper 1 — Fork-Based DeFi Execution Research* (read-only methodology + honest FOUND/CLOSED verdicts).
  - *Paper 2 — Execution Intelligence: Latency, Competition, and Value Retention* (the `R = f(d, λ, h)` model).
- **[books/](books)** — *Execution Intelligence II: Price Discovery and Market Leadership*.

Source code and datasets remain private (see [Why there's no source code here](#why-theres-no-source-code-here)).

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

Two research preprints from this work are included in **[papers/](papers)**:

1. **Fork-Based DeFi Execution Research** — a read-only methodology that drives every edge to a FOUND/CLOSED verdict with net-of-cost grading.
2. **Execution Intelligence: Latency, Competition, and Value Retention** — an empirical model `R = f(d, λ, h)` relating competition, latency, and infrastructure concentration to retained value.

Both are accompanied by a literature review and a reproducibility manifest, and are **preprints** (not yet peer-reviewed).

---

## Why there's no source code here

The research papers and one book are included for review; the **implementation (source code) is kept
private as a trade secret**, as are the datasets, infrastructure details, and the internal edge
catalog. This repository conveys the research and framework **without disclosing the private
execution edge**.

Deeper technical discussion, a code walkthrough, or the draft manuscripts can be shared **privately,
on request**, under an appropriate confidentiality understanding.

---

## About

**Prakash Vishnoi** — Independent DeFi execution researcher & engineer.

- GitHub: [@prakashvishnoi](https://github.com/prakashvishnoi)
- Contact: prakashvishnoi63@gmail.com 

> This repository contains documentation, research preprints, and selected writing. No source code,
> datasets, private keys, infrastructure details, or the internal edge catalog are published here.
