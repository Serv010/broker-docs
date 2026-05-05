# Troubleshooting

This guide is practical and public-safe. It avoids private endpoints, keys, and internal production data.

## Bot Does Not Start

Check:

- Required environment variables are present.
- Dependency installation completed.
- Database is reachable.
- The selected `APP_ROLE` is valid.
- The Telegram bot token is valid.
- The process has access to its configured port.

## Missing Environment Variable

The bot validates required configuration at startup. If startup reports a missing variable, add it through the deployment secret manager or local environment file. Do not paste real secrets into logs, GitHub issues, or screenshots.

## Database Connection Error

Check:

- `DATABASE_URL` points to the intended database.
- Network access from the bot runtime to the database is allowed.
- Credentials are valid.
- Migrations have run.
- The database is not at its connection limit.

## Telegram Command Not Responding

Check:

- The bot process is running.
- Webhook mode is correctly configured, or polling mode is active for local development.
- The user has accepted terms if required.
- Whitelist mode is not blocking the user.
- User or admin rate limits are not being hit.
- Admin-only commands are sent by an admin in private chat.

## Trade Quote Failed

Common causes:

- Provider outage or rate limit.
- Invalid token mint.
- No route available.
- Trade size is too small.
- Price impact exceeds configured limits.
- Token metadata or liquidity is unavailable.

Try refreshing the token sheet, reducing trade size, or waiting for provider recovery.

## Transaction Failed

Common causes:

- Quote expired.
- Price moved beyond slippage.
- Wallet has insufficient SOL for amount plus fees.
- Wallet token balance changed before execution.
- Route became unavailable.
- Network confirmation timed out.

Refresh the quote before retrying.

## Provider Rate Limit

Provider rate limits can affect token lookup, quote fetching, copytrade ingestion, chart data, and transaction confirmation.

Operators should tune concurrency settings, retry limits, and provider plans. Users should wait and retry if the provider is temporarily unavailable.

## Copytrade Event Skipped

Expected skip reasons include:

- Source wallet disabled.
- Copy buys or sells disabled.
- Daily cap reached.
- Loss cap reached.
- Max open positions reached.
- Source trade size outside configured range.
- No user wallet exists.
- No quote route available.
- Token filters rejected the asset.
- Dry run mode is enabled.

Review copytrade settings and skipped-trade notifications.

## Limit Order Did Not Trigger

Possible reasons:

- The target was not reached by fresh market data.
- Cached price appeared close, but a live route could not satisfy the target output.
- The wallet balance was insufficient at trigger time.
- The wallet that created the order is no longer active.
- Provider data was temporarily unavailable.
- The order was cancelled or marked for review.

Limit orders only execute when a live executable quote satisfies the saved target.

## Chart Failed To Render

Common causes:

- No valid price bars are available.
- Market data provider is unavailable.
- Token pair could not be resolved.
- The chart interval has insufficient history.
- The image renderer could not load required assets.

Try a different interval or refresh later.

