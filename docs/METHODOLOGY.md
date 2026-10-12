# Methodology & Architecture (overview)

A high-level description of how the Execution Intelligence Observatory works, written for review.
It conveys approach and scope **without** disclosing the private implementation, exact parameters, or
unpublished results (see [What is intentionally omitted](#what-is-intentionally-omitted)).

## Thesis

On public blockchains, prices and pending activity are broadly observable, so profit rarely comes
from *prediction* — it comes from *execution*: who detects a transient opportunity first, controls
ordering, and secures inclusion. The program tests that premise empirically, **without risking
capital**, and treats a rigorously-evidenced negative result as a valuable outcome.

## The evidence ladder (how a hypothesis is graded)

Every candidate edge is driven through the same read-only pipeline and ends in one verdict:

1. **Observe** — read-only public data; pin block / transaction / log index; record provenance.
2. **Simulate** — re-execute on a deterministic mainnet fork of point-in-time state (auditable, repeatable).
3. **Cost model** — subtract swap fees, gas, price impact, and slippage; gross-positive but net-negative is not an edge.
4. **De-confound** — control for common drivers; permutation / placebo nulls.
5. **Out-of-sample** — forward-chaining (time-ordered) validation; correct for multiple testing.
6. **Tail stress** — check behaviour under historical stress-scale moves.
7. **Paper → shadow** — live-data paper, then a full production path with the sender disabled and fail-closed.
8. **Verdict + record** — written to an auditable registry.

## Verdict taxonomy (classification labels)

- **CONFIRMED (research)** — the mechanism is real on fork/read-only evidence (not necessarily tradeable).
- **FOUND** — survives the full ladder *and* the net-of-cost model (a real, operator-actionable edge).
- **FOUND_CANDIDATE** — reproducibly present but net-of-cost feasibility not yet established.
- **CLOSED** — rejected, with a measured reason and a precise reopen condition (e.g. *below-cost*, *no-edge*, *no-secondary-market*, *market/visibility-bound*).
- **Open flow** — a cross-venue signal that is reproducibly present but whose monetization is not yet established.

## Negative-knowledge registry

The program's largest output is a **canonical registry of CLOSED surfaces** — each with its measured
reason and reopen condition. This prevents rework and calibrates confidence in the few survivors:
many independent CLOSED verdicts around one mechanism make a surviving signal more credible, not less.

## From trading to measurement (the product lens)

Because operator-accessible trading edges mostly close under realistic costs, the durable value is
**measurement**: transaction-audit, execution-quality, MEV-loss (reported as a conservative
public-data lower bound), oracle-freshness, and liquidation-risk reporting — all reusing the same
fork / point-in-time machinery and requiring no trading capital.

## The retention lens

A unifying framework models **retention** `R = f(d, λ, h)` — the fraction of an opportunity's
theoretical value a winner actually keeps — as a function of competition density `d`, execution
latency `λ`, and infrastructure concentration `h`. It yields a four-regime map (efficient execution,
competitive compression, latency arms race, infrastructure capture) with welfare/market-design
readings. Reported honestly as an **associational, upper-bounded first-pass** framework.

## Infrastructure (generic)

- **Nodes:** self-hosted Ethereum execution clients (Erigon primary, Geth secondary), pruned full nodes (not an archive node).
- **Simulation:** deterministic forks (Foundry / Anvil) over recent point-in-time state.
- **Pipelines:** read-only collectors and analyzers on scheduled jobs; SQL / dashboard reporting.
- **Data:** public on-chain data and public market data only; no private order flow.

## Safety & ethics

- Read-only / paper / shadow by **default**; any live on-chain action is owner-gated, single-submitter, and kill-switched.
- Measurement-oriented: it quantifies extraction and its costs to inform market design and user protection; it does **not** perform front-running, sandwiching, or censorship.

## Reproducibility

Every reported number traces to pinned finalized blocks, the exact code commit, parameters, and
random seeds; monetary values use integer base-unit arithmetic with explicit token decimals; forks
are deterministic and therefore auditable.

## What is intentionally omitted

To protect the private edge and unpublished results, this repository does **not** contain: source
code; exact filters, thresholds, or ranking logic; profitable route classes; latency / builder /
priority-fee strategy; wallet or executor details; real transaction hashes; live PnL; the catalog of
researched edges; or the unpublished manuscripts. These can be discussed privately, on request,
under an appropriate confidentiality understanding.
