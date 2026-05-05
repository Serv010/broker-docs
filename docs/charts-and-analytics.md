# Charts And Analytics

BRO-ker provides chart and PnL cards to help users understand positions and token movement inside Telegram.

## Chart Cards

Chart cards can show recent price or market cap movement for a token. The user can choose candle intervals from settings, including 5m, 15m, 1h, and 4h.

Chart cards may include:

- Token or pair name.
- Timeframe label.
- Price or market cap scale.
- Current value marker.
- Entry and exit overlays when tracked trade data is available.

## PnL Cards

PnL cards summarize BRO-ker tracked trades for a token. They can represent open or closed positions.

Common fields include:

| Metric | Meaning |
| --- | --- |
| Total buys | SOL spent through tracked BRO-ker buys. |
| Total sells | SOL received through tracked BRO-ker sells. |
| Current value | Estimated value of remaining balance. |
| PnL | Realized plus estimated unrealized result. |
| PnL after price impact | Estimate that accounts for a live exit quote when available. |

## Entry And Exit Markers

When BRO-ker has tracked executions, chart cards can overlay entry and exit markers. These markers are scaled to the chart pair and should be treated as visual aids, not a guarantee of exact fill comparison across venues.

## Market Cap Vs Price

Some views use price; others can use market cap. Market cap depends on token supply data and live pricing. If supply or price is unreliable, market cap targets or chart labels may be unavailable.

## Time Windows

BRO-ker uses multiple time windows depending on context:

| Window | Where it appears |
| --- | --- |
| 24h | Admin and referral operational metrics. |
| 7d | Admin and referral operational metrics. |
| 1mo | Admin and referral operational metrics. |
| Full | Lifetime admin and referral summaries. |
| 5m, 15m, 1h, 4h candles | User chart settings. |

## How To Interpret Metrics

Analytics are informational. They can lag during provider outages, depend on successful metadata lookup, and are based on BRO-ker tracked executions. Always verify important decisions with independent sources and current on-chain data.

