# Configuration

This page is a safe environment variable reference. It lists variable names and placeholder examples only. Do not publish real values.

## Core Runtime

| Variable | Required? | Purpose | Example placeholder |
| --- | --- | --- | --- |
| `APP_ENV` | Recommended | Runtime environment name. | `production` |
| `APP_ROLE` | Required | Selects `all`, `ingress`, `bot-worker`, `trade-worker`, or `scheduler-worker`. | `bot-worker` |
| `BIND_HOST` | Deployment-specific | Host for the ASGI service. | `0.0.0.0` |
| `PORT` | Deployment-specific | Port for the ASGI service. | `PORT_NUMBER` |
| `APP_BASE_URL` | Required for webhooks | Public base URL used for webhook registration. | `https://BOT_DOMAIN` |
| `DATABASE_URL` | Required | Database connection string. | `DATABASE_URL` |
| `REDIS_URL` | Optional | Redis URL if used by deployment infrastructure. | `redis://HOST:PORT/DB` |
| `WHITELIST_ONLY_ENABLE` | Optional | Restricts bot use to whitelisted users when enabled. | `true` |

## Telegram

| Variable | Required? | Purpose | Example placeholder |
| --- | --- | --- | --- |
| `TELEGRAM_BOT_TOKEN` | Required | Telegram bot token from BotFather. | `TELEGRAM_BOT_TOKEN` |
| `TELEGRAM_BOT_USERNAME` | Recommended | Public bot username for referral and deep links. | `BOT_USERNAME` |
| `TELEGRAM_WEBHOOK_SECRET` | Required for webhooks | Secret used in Telegram webhook path and header validation. | `TELEGRAM_WEBHOOK_SECRET` |
| `TELEGRAM_ADMIN_IDS` | Required for admins | Comma-separated admin Telegram user IDs. | `ADMIN_TELEGRAM_IDS` |

## Secrets And Custody

| Variable | Required? | Purpose | Example placeholder |
| --- | --- | --- | --- |
| `ENCRYPTION_SECRET` | Required | Master secret used to encrypt wallet material. | `LONG_RANDOM_ENCRYPTION_SECRET` |
| `ENCRYPTION_SECRET_PREVIOUS` | Rotation-only | Previous encryption secrets during rotation. | `OLD_ENCRYPTION_SECRET` |
| `WALLET_EXPORT_ENABLE` | Optional | Enables or disables wallet backup export. | `false` |
| `WALLET_EXPORT_COOLDOWN_SECONDS` | Optional | Cooldown between wallet exports. | `SECONDS` |
| `AUDIT_LOG_RETENTION_DAYS` | Optional | Retention window for audit events. | `DAYS` |

## Providers

| Variable | Required? | Purpose | Example placeholder |
| --- | --- | --- | --- |
| `HELIUS_API_KEY` | Required | Chain data and transaction provider key. | `HELIUS_API_KEY` |
| `HELIUS_RPC_URL` | Optional | Override RPC endpoint. | `https://RPC_PROVIDER_URL` |
| `HELIUS_WS_URL` | Optional | Override websocket endpoint. | `wss://RPC_PROVIDER_WS_URL` |
| `HELIUS_SENDER_URL` | Optional | Override transaction sender endpoint. | `https://SENDER_PROVIDER_URL` |
| `USE_HELIUS_GATEKEEPER` | Optional | Selects alternate provider gatekeeper behavior when enabled. | `false` |
| `JUPITER_API_KEY` | Required | Quote and swap provider key. | `JUPITER_API_KEY` |
| `JUPITER_SWAP_BASE_URL` | Required | Swap API base URL. | `https://JUPITER_PROVIDER_URL` |
| `HELIUS_MAX_CONCURRENCY` | Optional | Provider concurrency limit. | `NUMBER` |
| `JUPITER_MAX_CONCURRENCY` | Optional | Quote provider concurrency limit. | `NUMBER` |
| `PROVIDER_RETRY_MAX_ATTEMPTS` | Optional | Retry attempt limit. | `NUMBER` |
| `PROVIDER_CIRCUIT_BREAKER_THRESHOLD` | Optional | Circuit breaker threshold. | `NUMBER` |
| `HELIUS_SENDER_RETRY_ATTEMPTS` | Optional | Sender retry attempts. | `NUMBER` |
| `HELIUS_SENDER_FALLBACK_RPC` | Optional | Enables fallback send path when configured. | `false` |

## Trading

| Variable | Required? | Purpose | Example placeholder |
| --- | --- | --- | --- |
| `DEFAULT_SLIPPAGE_BPS` | Optional | Default slippage in basis points. | `BPS` |
| `MAX_SLIPPAGE_BPS` | Optional | Maximum user slippage in basis points. | `BPS` |
| `PLATFORM_FEE_BPS` | Required if fees enabled | Platform fee in basis points. | `BPS` |
| `PLATFORM_FEE_WSOL_ACCOUNT` | Required | Platform fee WSOL token account. | `PLATFORM_FEE_WSOL_ACCOUNT` |
| `TRADE_SOL_BUFFER_LAMPORTS` | Optional | SOL reserve buffer for trading. | `LAMPORTS` |
| `SENDER_TIP_LAMPORTS` | Optional | Sender or priority tip amount. | `LAMPORTS` |
| `SENDER_REBROADCAST_MS` | Optional | Broadcast retry timing. | `MILLISECONDS` |
| `QUOTE_TTL_SECONDS` | Optional | Quote lifetime. | `SECONDS` |
| `METADATA_TTL_SECONDS` | Optional | Metadata cache lifetime. | `SECONDS` |
| `LIMIT_ORDER_SCAN_INTERVAL_SECONDS` | Optional | Limit-order scan cadence. | `SECONDS` |

## Workers And Jobs

| Variable | Required? | Purpose | Example placeholder |
| --- | --- | --- | --- |
| `JOB_POLL_INTERVAL_SECONDS` | Optional | Worker polling interval. | `SECONDS` |
| `BOT_WORKER_CONCURRENCY` | Optional | Bot worker concurrency. | `NUMBER` |
| `TRADE_WORKER_CONCURRENCY` | Optional | Trade worker concurrency. | `NUMBER` |

## Copytrade

| Variable | Required? | Purpose | Example placeholder |
| --- | --- | --- | --- |
| `COPYTRADE_ENABLE` | Optional | Enables copytrade features. | `true` |
| `COPYTRADE_WEBHOOK_SECRET` | Webhook mode | Secret for copytrade webhook path. | `COPYTRADE_WEBHOOK_SECRET` |
| `COPYTRADE_HELIUS_WEBHOOK_ID` | Webhook mode | Provider webhook ID. | `COPYTRADE_HELIUS_WEBHOOK_ID` |
| `COPYTRADE_HELIUS_AUTH_HEADER` | Webhook mode | Provider auth header value. | `COPYTRADE_HELIUS_AUTH_HEADER` |
| `COPYTRADE_WORKER_CONCURRENCY` | Optional | Copytrade worker concurrency. | `NUMBER` |
| `COPYTRADE_LASERSTREAM_ENABLE` | Optional | Enables streaming ingress mode. | `false` |
| `COPYTRADE_LASERSTREAM_ENDPOINT` | Streaming mode | Streaming provider endpoint. | `https://STREAM_PROVIDER_URL` |
| `COPYTRADE_LASERSTREAM_COMMITMENT` | Optional | Chain commitment level. | `confirmed` |
| `COPYTRADE_LASERSTREAM_FROM_SLOT` | Optional | Starting slot for stream mode. | `SLOT_NUMBER` |
| `COPYTRADE_LASERSTREAM_REFRESH_SECONDS` | Optional | Stream address refresh interval. | `SECONDS` |
| `COPYTRADE_LASERSTREAM_RETRY_MIN_SECONDS` | Optional | Minimum retry delay. | `SECONDS` |
| `COPYTRADE_LASERSTREAM_RETRY_MAX_SECONDS` | Optional | Maximum retry delay. | `SECONDS` |
| `COPYTRADE_LASERSTREAM_MAX_MESSAGE_BYTES` | Optional | Maximum stream message size. | `BYTES` |
| `COPYTRADE_LOGSUBSCRIBE_ENABLE` | Optional | Enables Solana log subscription ingress. | `true` |
| `COPYTRADE_LOGSUBSCRIBE_COMMITMENT` | Optional | Chain commitment level. | `confirmed` |
| `COPYTRADE_LOGSUBSCRIBE_REFRESH_SECONDS` | Optional | Subscription refresh interval. | `SECONDS` |
| `COPYTRADE_LOGSUBSCRIBE_RETRY_MIN_SECONDS` | Optional | Minimum retry delay. | `SECONDS` |
| `COPYTRADE_LOGSUBSCRIBE_RETRY_MAX_SECONDS` | Optional | Maximum retry delay. | `SECONDS` |
| `COPYTRADE_LOGSUBSCRIBE_TRANSACTION_RETRY_ATTEMPTS` | Optional | Transaction fetch retry attempts. | `NUMBER` |
| `COPYTRADE_LOGSUBSCRIBE_TRANSACTION_RETRY_DELAY_SECONDS` | Optional | Delay between transaction fetch attempts. | `SECONDS` |
| `COPYTRADE_LOGSUBSCRIBE_SUBSCRIBE_TIMEOUT_SECONDS` | Optional | Subscription timeout. | `SECONDS` |
| `COPYTRADE_LOGSUBSCRIBE_PREFETCH_FILTER_ENABLE` | Optional | Enables prefetch filtering. | `true` |
| `COPYTRADE_LOGSUBSCRIBE_TRADE_PROGRAM_IDS` | Optional | Additional program IDs to treat as trade sources. | `PROGRAM_ID_LIST` |
| `COPYTRADE_LOGSUBSCRIBE_TRADE_LOG_KEYWORDS` | Optional | Additional log phrases to treat as trade signals. | `LOG_KEYWORD_LIST` |
| `COPYTRADE_POLLING_FALLBACK_ENABLE` | Optional | Enables polling fallback. | `false` |
| `COPYTRADE_POLLING_FALLBACK_INTERVAL_SECONDS` | Optional | Polling interval. | `SECONDS` |
| `COPYTRADE_POLLING_FALLBACK_BATCH_SIZE` | Optional | Polling batch size. | `NUMBER` |
| `COPYTRADE_POLLING_FALLBACK_SEEN_CACHE_SIZE` | Optional | Signature cache size. | `NUMBER` |

## Referrals And Fees

| Variable | Required? | Purpose | Example placeholder |
| --- | --- | --- | --- |
| `REFERRAL_ENABLE` | Optional | Enables referral system. | `true` |
| `NORMAL_REFERRAL_BPS` | Optional | Normal referral reward share. | `BPS` |
| `KOL_REFERRAL_BPS` | Optional | KOL referral reward share. | `BPS` |
| `REFERRAL_FIRST_REFERRER_WINS` | Optional | Keeps first valid attribution. | `true` |
| `REFERRAL_REQUIRE_FIRST_TRADE` | Optional | Requires initial trade before qualification. | `true` |
| `REFERRAL_MIN_QUALIFY_TRADES` | Optional | Minimum trades for qualification. | `NUMBER` |
| `REFERRAL_MIN_QUALIFY_VOLUME_USD` | Optional | Minimum volume for qualification. | `USD_AMOUNT` |
| `REFERRAL_CODE_PREFIX` | Optional | Prefix for user referral codes. | `REF_PREFIX` |
| `KOL_REFERRAL_CODE_PREFIX` | Optional | Prefix for KOL referral codes. | `KOL_PREFIX` |
| `REFERRAL_DEFAULT_CODE_LENGTH` | Optional | Generated code length. | `NUMBER` |
| `REFERRAL_CLAIM_ENABLE` | Optional | Enables user reward claims. | `true` |
| `REFERRAL_CLAIM_MIN_LAMPORTS` | Optional | Minimum claim size. | `LAMPORTS` |
| `REFERRAL_PAYOUT_WALLET_PRIVATE_KEY` | Sensitive | Payout wallet private key. Prefer secret manager. | `REFERRAL_PAYOUT_WALLET_PRIVATE_KEY` |
| `REFERRAL_PAYOUT_WALLET_PRIVATE_KEY_ENCRYPTED` | Sensitive | Encrypted payout wallet key. | `ENCRYPTED_REFERRAL_PAYOUT_KEY` |
| `REFERRAL_PAYOUT_BUFFER_LAMPORTS` | Optional | SOL reserve buffer for payouts. | `LAMPORTS` |
| `PLATFORM_FEE_SWEEP_ENABLE` | Optional | Enables platform fee autosweep. | `false` |
| `PLATFORM_FEE_SWEEP_INTERVAL_SECONDS` | Optional | Autosweep interval. | `SECONDS` |
| `PLATFORM_FEE_SWEEP_MIN_LAMPORTS` | Optional | Minimum sweep size. | `LAMPORTS` |

## Admin And Abuse Controls

| Variable | Required? | Purpose | Example placeholder |
| --- | --- | --- | --- |
| `ADMIN_ALERT_WEBHOOK` | Optional | Alert destination for privileged events. | `ADMIN_ALERT_WEBHOOK` |
| `USER_RATE_LIMIT_WINDOW_SECONDS` | Optional | User rate-limit window. | `SECONDS` |
| `USER_RATE_LIMIT_MAX_ACTIONS` | Optional | User action limit per window. | `NUMBER` |
| `ADMIN_RATE_LIMIT_WINDOW_SECONDS` | Optional | Admin rate-limit window. | `SECONDS` |
| `ADMIN_RATE_LIMIT_MAX_ACTIONS` | Optional | Admin action limit per window. | `NUMBER` |
| `TERMS_VERSION` | Optional | Terms acceptance version. | `TERMS_VERSION` |
| `APP_NAME` | Optional | Display name. | `BRO-ker` |

## Native Route Settings

| Variable | Required? | Purpose | Example placeholder |
| --- | --- | --- | --- |
| `ENABLE_NATIVE_PUMP_ROUTE` | Optional | Enables native route support for selected tokens. | `true` |
| `PUMPFUN_PROGRAM_ID` | Optional | Program ID override. | `PROGRAM_ID` |
| `PUMPSWAP_PROGRAM_ID` | Optional | Program ID override. | `PROGRAM_ID` |
| `PUMP_ROUTE_MAX_RETRIES` | Optional | Route retry count. | `NUMBER` |
| `PUMP_ROUTE_RETRY_DELAY_MS` | Optional | Retry delay. | `MILLISECONDS` |
| `PUMP_ROUTE_DEFAULT_SLIPPAGE_BPS` | Optional | Default slippage for native route. | `BPS` |
| `PUMP_ROUTE_MAX_SLIPPAGE_BPS` | Optional | Max slippage for native route. | `BPS` |
| `PUMP_ROUTE_CREATE_ATA` | Optional | Creates token account when needed. | `true` |
| `PUMP_ROUTE_PRIORITY_FEE_MODE` | Optional | Native route priority mode. | `MODE_NAME` |
| `NATIVE_PUMP_PLATFORM_FEE_ENABLED` | Optional | Enables native route platform fee behavior when supported. | `false` |
| `NATIVE_PUMP_PLATFORM_FEE_BPS` | Optional | Native route fee basis points. | `BPS` |
