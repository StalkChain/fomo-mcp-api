# Source of truth and maintenance

## Live references

1. [OpenAPI specification](https://data.stalkchain.com/api/v1/openapi.json): public current tool paths, per-tool `x-credits`, inputs, methods, and documented response codes. Generated specs can still lag real deployment: resolve disagreements with a safe authenticated runtime check.
2. Authenticated `GET https://data.stalkchain.com/api/v1/tools`: current catalog/schema from the service. Anonymous requests return 401; do not call this an outage.
3. [Tool reference](https://data.stalkchain.com/docs/tools/index), [credits documentation](https://data.stalkchain.com/docs/credits) and [agent summary](https://data.stalkchain.com/llms.txt): developer explanations and setup instructions.
4. [Landing page](https://data.stalkchain.com): public offer and messaging. Account/dashboard terms govern an individual's balance and promotions.

## Discrepancies observed before this repository was published

The public landing page advertised **73 tools**, the documentation introduction described **54**, and the OpenAPI description said **71** (the parsed specification had 71 per-tool paths). The REST tool list returned 401 without authentication, as expected. The OpenAPI tool entries showed paid StonkFun costs, while an older sentence in its description called StonkFun tools free. `llms.txt` also named three tools absent from the parsed OpenAPI (`stalkchain_api_info`, `stalkchain_fomo_notifications`, `stalkchain_fomo_token_search`), so they are not advertised here as available. The OpenAPI called the zero-credit health route keyless, but an anonymous GET returned **401**. Therefore this repo avoids a fixed tool total or static price table and does not equate free billing with keyless access. Check each tool's current authenticated registry/spec entry and your account before budgeting.

The planned $5 promotional grant for 7 days is **not asserted to be live** here. Purchased-pack terms and promotional balance/expiry must not be conflated. Change public copy only after the actual grant, dashboard and expiry behavior have been tested.

## Maintenance checklist

- Recheck the current registry, OpenAPI and client setup instructions before adding a new tool or changing a cost claim.
- Validate exact tool IDs and coverage; mark removed tools rather than silently inventing replacements.
- Exercise a free, keyless health call when permitted; do not use billable accounts without authorization.
- Check internal relative links, external official links, GitHub's rendered Markdown and the public `data.stalkchain.com` destination.
- Preserve editorial caveats: account identity, chain/contract, timing, incomplete PnL basis, and research versus execution.
- Prefer a compact update with an evidence URL and date to unverified claims of “real-time”, “all wallets”, or “guaranteed alpha”.

## Ownership and scope

This repository is a **StalkChain-maintained public documentation/discovery surface** pointing at hosted StalkChain Data. It does not include the service implementation or any private StalkChain repository. It is not affiliated with or endorsed by the FOMO app unless that relationship is separately established.
