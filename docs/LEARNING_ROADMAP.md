# Learning roadmap — DeFi execution / crypto-fintech

The structured path I use to learn (and teach) this domain, from first principles to job-ready. It
doubles as a map of the skills exercised by the Execution Intelligence Observatory. (It is backed by
a private first-principles curriculum I maintain; this public version keeps the ordering, the
external references, the tech stack, and the role mapping.)

Each phase: **Theory → Tech to build with → why it matters for the work / for roles.**

| # | Phase | Theory | Tech to practice |
|---|-------|--------|------------------|
| 0 | Reasoning & data hygiene | evidence vs assertion, reproducibility, time value, probability basics | Python (pandas/numpy), git, SQL, Jupyter |
| 1 | Math, probability, statistics | estimation, hypothesis testing, regression, overfitting, multiple testing | scipy, statsmodels, scikit-learn; OOS validation |
| 2 | Markets & price discovery | participants, auctions, how information becomes price | market-data ingest (REST/WebSocket), time series |
| 3 | Microstructure & execution | order books, liquidity, adverse selection, market impact, slippage, TCA, optimal execution | order-book reconstruction, TCA, impact curves |
| 4 | Derivatives, vol, portfolio & risk | futures/perps funding & basis, greeks, implied vs realized vol, VRP; sizing, Sharpe traps, capacity | options pricing (py_vollib/QuantLib), walk-forward backtester |
| 5 | Ethereum & smart contracts | accounts/state, EVM, gas, mempool, consensus, nodes | Solidity, Foundry (forge/anvil/cast), ethers/viem, JSON-RPC, running a node |
| 6 | DeFi protocol mechanics | AMMs (v2/v3/v4), lending & health factor, oracles, liquidations, stablecoins, LVR | fork-simulate a liquidation / arb, subgraphs |
| 7 | MEV & execution markets | MEV taxonomy, priority-gas auctions, PBS, builders/relays, concentration, ethics | mempool streaming, Flashbots bundles, backrun simulation |
| 8 | Measurement & the observatory | metric design (MEV-loss, execution quality, oracle freshness), point-in-time reconstruction | data pipelines, Dune/SQL dashboards, fork replay at scale |
| 9 | Strategy research, price discovery & practice | backtest integrity, lead-lag / cointegration / information shares, evidence products | rigorous validation harness, lead-lag estimation, clean write-ups |

## Target roles → what to emphasize

| Role | Priority phases | Interview focus |
|------|-----------------|-----------------|
| Quant researcher / trader (crypto) | 0,1,3,4,7,9 | stats rigor, microstructure, backtest overfitting, risk |
| MEV searcher / searcher-strategist | 0,5,6,7,8 | EVM/mempool, PBS/Flashbots, net-of-cost, latency |
| Smart-contract / protocol engineer | 0,5,6 | Solidity, EVM gas/security, AMM/lending mechanics |
| Blockchain data engineer / on-chain analyst | 0,1,5,6,8 | SQL/Dune, EVM data model, reproducibility |
| Execution / TCA / microstructure analyst | 0,1,3,8,9 | spread/impact/slippage, optimal execution, information shares |
| DeFi risk engineer | 0,1,6,8 | health factor, oracle lag, liquidation cascades, LVR |

## Tech stack checklist

- **Languages:** Python (pandas, numpy, scipy, statsmodels, scikit-learn, matplotlib), SQL, Solidity, TypeScript/JavaScript (Node). Bonus: Rust.
- **Blockchain dev:** Foundry (forge/anvil/cast), Hardhat, ethers.js/viem/web3.py, JSON-RPC, The Graph/subgraphs.
- **Node & infra:** Erigon/Geth, Anvil mainnet forks, Linux, git, cron/PM2, REST/WebSocket APIs, Docker.
- **MEV:** Flashbots (bundles, mev-boost concepts), mempool streaming, builder/relay endpoints.
- **Data/quant:** Dune Analytics (Dune SQL), backtesting with walk-forward CV, deflated Sharpe, TCA, options/vol tooling.

## Canonical references (study alongside)

- **Microstructure/markets:** Harris, *Trading and Exchanges*; O'Hara, *Market Microstructure Theory*; Hasbrouck, *Empirical Market Microstructure*. Papers: Kyle (1985), Glosten–Milgrom (1985), Hasbrouck (1991), Almgren–Chriss (2000).
- **Derivatives/portfolio/quant:** Hull, *Options, Futures, and Other Derivatives*; Natenberg, *Option Volatility and Pricing*; Grinold–Kahn, *Active Portfolio Management*; López de Prado, *Advances in Financial Machine Learning*.
- **Blockchain/DeFi/MEV:** Antonopoulos & Wood, *Mastering Ethereum*; ethereum.org docs; Uniswap v2/v3/v4 whitepapers; Aave & Chainlink docs; Flashbots docs. Papers: Daian et al. *Flash Boys 2.0* (2020); Milionis et al. *LVR* (2022); Qin/Zhou/Gervais (2022).
