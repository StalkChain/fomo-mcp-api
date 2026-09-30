# Tools and workflows

**Authoritative reference:** [live tools and inputs](https://data.stalkchain.com/docs/tools/index) · [public OpenAPI](https://data.stalkchain.com/api/v1/openapi.json) · [agent summary](https://data.stalkchain.com/llms.txt). This guide organizes jobs rather than republishing a frozen schema. Check the live specification before coding: tool availability, inputs, credit cost, coverage, and account entitlements can change.

## FOMO traders and social graph

**Job:** turn an attributed trader handle into investigable wallets, positions, fills and actual exposure, not just a social profile.

- `stalkchain_fomo_search`: find an attributed trader and wallet leads.
- `stalkchain_fomo_resolve_trader`: composite profile with linked wallets and performance windows.
- `stalkchain_fomo_trader_positions`, `stalkchain_fomo_trader_swaps`, `stalkchain_fomo_trader_balances`: current positions, trade fills and balances.
- `stalkchain_fomo_trader_following`, `stalkchain_fomo_trader_followers`: social graph; following is not ownership or endorsement.
- `stalkchain_fomo_trader_spotlight`, `stalkchain_fomo_trader_report`, `stalkchain_fomo_compare_traders`: notable activity, composite reports, and comparisons.

**Ask:** “Compare these two attributed traders over the same window. Show wallet addresses, closed versus open positions, trade counts, fees and missing cost basis. What would invalidate a high PnL figure?”

**Check:** a handle can change, attribution can be wrong, and one open winner or incomplete basis can dominate an estimate. Use immutable wallet and transaction IDs when possible.

## Leaderboards and token boards

- `stalkchain_fomo_leaderboard`: ranked trader candidates over supported windows.
- `stalkchain_fomo_token_board`: tokens drawing activity or tracked holdings.

**Ask:** “From this window's leaderboard, shortlist repeat traders with sufficient sample size; separate activity/volume from realized profit and show the exact wallet proof to inspect next.”

A board is a discovery surface, not a backtest or independently audited ranking.

## Token discovery, holders and concentration

- `stalkchain_fomo_token_holders`, `stalkchain_fomo_kol_holders`: attributed holders and KOL exposure.
- `stalkchain_fomo_token_devs`, `stalkchain_fomo_token_stats`, `stalkchain_fomo_token_candles`: developer exposure, flow and price history.
- `stalkchain_fomo_coordinated_activity`, `stalkchain_fomo_kol_sell_pressure`: clustered entries and tracked-holder exits.
- `stalkchain_fomo_analyze_token`, `stalkchain_fomo_trending_analysis`: composite analysis; check the live cost first.
- `stalkchain_fomo_top_traders_for_tokens`, `stalkchain_fomo_token_launch_research`: trader and launch context.
- `stalkchain_fomo_token_snapshot`, `stalkchain_fomo_compare_snapshots`: observation snapshots and change comparison.

**Ask:** “Given this exact token address and chain, show tracked holders, recent net flow, dev activity and tracked sells. State when each observation was taken and what portion of all holders the tracked set represents.”

A tracked-wallet count is not the complete holder universe; a net inflow is not proof of executable liquidity.

## Written theses, trades and comments

- `stalkchain_fomo_theses_recent`, `stalkchain_fomo_theses_for_token`, `stalkchain_fomo_theses_by_trader`: what traders wrote, with source/time context.
- `stalkchain_fomo_trade_detail`, `stalkchain_fomo_trade_comments`: fills and discussion around a trade.

**Ask:** “What thesis did these holders publish before buying, what did they buy and later sell, and which statements are merely opinions rather than verifiable product events?”

Do not translate a popular thesis into factual validation or infer causal alpha from a retrospective post.

## Live activity and convergence

- `stalkchain_fomo_alerts`: bounded recent activity. The agent summary also mentions notifications, but that tool was absent from the public OpenAPI checked for this release; do not rely on it without live registry confirmation.
- `stalkchain_fomo_multi_trader_entries`: tokens entered by multiple tracked traders in a window.
- `stalkchain_fomo_watch_stream`: bounded stream sampling; inspect live docs for duration and entitlement.

**Ask:** “Which exact token addresses saw several tracked traders enter in the last hour? Give the time window and each wallet's entry, check whether they still hold, and flag possible related wallets, exits and thin liquidity.”

A fast cluster is *not* proof of independent buyers, future returns or a safe entry. Building a recurring scan requires your own authorized scheduler and a call budget.

## StonkFun launchpad

The live catalog documents `stonk_tokens`, `stonk_token`, `stonk_token_burns`, `stonk_token_rewards`, `stonk_token_airdrop`, `stonk_token_fees`, `stonk_token_backing`, `stonk_launches`, `stonk_launch_status`, `stonk_pairs`, `stonk_launchlab_pricing`, `stonk_stats`, `stonk_revenue`, `stonk_rewards`, and `stonk_token_report`. Verify which are available and billable today: older prose elsewhere gives conflicting prices.

**Ask:** “Research this exact StonkFun mint: current launch state, burns, actual reward distributions, creator-fee exposure, backing and source timestamps. Separate realized transfers from modeled future payout.”

No tool here implies that this documentation repo can launch a token or place a trade. The launchpad is a separate product and its live rules govern actions.

## Solana on-chain safety and wallet evidence

- `stalkchain_token_onchain`, `stalkchain_token_deployer`, `stalkchain_token_early_buyers`: holders, authorities, deployer history and first buyers.
- `stalkchain_token_pnl_leaders`, `stalkchain_wallet_pnl`: estimated historical trader PnL with coverage caveats.
- `stalkchain_token_exit_check`, `stalkchain_token_quality`, `stalkchain_token_prices`: exit feasibility, market-quality indicators and pricing.
- `stalkchain_milestone_study`: cohort research; check inputs, denominator and substantially higher current cost before running.

**Ask:** “For this Solana mint, distinguish pool buys from allocations, show whether early wallets sold, identify mint/LP authority evidence, and estimate exit capacity for a specified size.”

Wallet labels are not identities. A quote, pool TVL or historical print is not a guaranteed executable exit.

## Cross-chain wallet and token data

- `stalkchain_wallet_portfolio`, `stalkchain_wallet_transfers`, `stalkchain_wallet_age`: holdings, movements and account history across supported chains.
- `stalkchain_token_prices_multichain`, `stalkchain_price_history`, `stalkchain_token_info`: pricing, historical context and token identity.

**Ask:** “Identify this contract on the exact chain, trace this wallet's recent transfers, and distinguish swaps, deposits, bridge flows and internal reshuffles. Cite transaction IDs where available.”

The same ticker can name unrelated assets. Chain ID and contract/mint take priority over symbols.

## DeFi and price confidence

- `stalkchain_chain_health`, `stalkchain_token_yields`, `stalkchain_protocol_report`, `stalkchain_defi_hacks`, `stalkchain_price_confidence`.

**Ask:** “Compare the quoted price and yield with the pricing source, liquidity, window, exploit history and data-quality flags. Which part is measured and which is estimated?”

Do not call protocol TVL revenue, infer safety from a quoted APY, or present an unpriced asset as zero.

## Account, costs and service state

- `stalkchain_health`, `stalkchain_account`, `stalkchain_usage`: liveness, account balance and usage where available. Health may cost zero credits but still require authentication.
- [REST `GET /api/v1/me`](https://data.stalkchain.com/docs): authenticated balance/usage. Anonymous `GET /api/v1/tools` returns 401.

Before scheduling anything, confirm per-tool costs and billing semantics, set a maximum spend in your own application, and stop or alert on exhausted credits. One natural-language question can call several tools. Promotional credits, if offered, may expire on a different schedule from purchased packs.

## Example application designs

1. **FOMO token research page:** accept chain + contract; resolve asset; show timestamped flow/holder/developer evidence, thesis quotes and coverage warnings. Refresh independently of the reader's UI rendering.
2. **Tracked-trader watchlist:** store user-approved immutable wallet IDs; compare recent fills, open inventory and old claims; de-duplicate aliases and indicate basis gaps.
3. **Read-only convergence alert:** periodically query activity, require distinct wallets and a recent time window, cross-check market liquidity, then send a link-rich research alert. Persist seen event IDs and budget per cycle; never label the alert “guaranteed alpha.”
4. **Creator research brief:** compare trader theses with actual fills and published product events; produce a claim ledger that distinguishes marketing narrative from on-chain confirmation.

**Next:** [Developer guide](DEVELOPER-GUIDE.md) · [Troubleshooting](TROUBLESHOOTING.md) · [Live tool schema](https://data.stalkchain.com/api/v1/openapi.json).
