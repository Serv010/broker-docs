# Security

This documentation project is public-safe by design. It describes behavior and architecture without exposing private source code, live credentials, production data, or exploit-ready internals.

## Secret Handling

Use placeholders only:

- `TELEGRAM_BOT_TOKEN`
- `DATABASE_URL`
- `HELIUS_API_KEY`
- `JUPITER_API_KEY`
- `ENCRYPTION_SECRET`
- `ADMIN_TELEGRAM_IDS`

Never place real values in Markdown, screenshots, examples, issue comments, or GitHub Actions logs.

## Environment Files

Do not commit:

- `.env`
- `.env.*`
- Production config files.
- Mounted secret files.
- Database dumps.
- Wallet exports.

The docs `.gitignore` blocks common secret and source-code patterns, but operators must still review every commit.

## GitHub Upload Safety

This repository should contain only:

- Markdown docs.
- MkDocs config.
- Mermaid diagrams.
- Docs assets.
- GitHub Pages workflow.
- Docs dependency file.

It should not contain bot source files, Python scripts, databases, keys, production Docker overrides, or private infrastructure notes.

## Private Key Principles

Wallet private keys and seed phrases are never documentation content. Public docs should describe custody concepts only. Do not include example seed phrases, real encrypted wallet rows, or screenshots of wallet backup messages.

## Database Access

Database URLs, usernames, passwords, hostnames, private IPs, and dumps are private. Public docs may describe database responsibilities at a high level but should not publish schema exports or production migration commands with real targets.

## Webhook Security

Webhook paths, webhook secrets, provider auth headers, and Telegram secret tokens must be treated as credentials. Public docs may mention that webhook secrets exist, but must not disclose values or full production endpoints.

## Provider API Keys

Provider keys for RPC, transaction sending, quotes, or market data must be stored in a secret manager or environment system. Avoid logging full URLs because RPC URLs can include keys.

## Admin Permission Model

Admin access is limited to configured admin users. Admin controls should be private-chat only for sensitive actions. Admin actions should be logged and rate-limited.

## Rate Limiting And Abuse Protection

The reviewed implementation includes user and admin rate-limit concepts, private-chat checks, whitelist mode, payload size limits, and deduplication for queued events. Deployment operators should tune limits for their community size and threat model.

## What Is Intentionally Not Published

This docs site does not publish:

- Full source files.
- Private routes or route-building internals.
- Raw database schema dumps.
- Production environment values.
- Real admin IDs.
- Provider keys.
- Wallet keys or seed phrases.
- Private VPS IPs or server names.
- Webhook secrets.

## Before Publishing Docs

- [ ] No `.py` files are present.
- [ ] No `.env` or `.env.*` files are present.
- [ ] No database files or dumps are present.
- [ ] No private keys, seed phrases, mnemonics, or wallet exports are present.
- [ ] No Telegram bot tokens are present.
- [ ] No provider API keys or RPC URLs with keys are present.
- [ ] No production hostnames, private IPs, or admin IDs are present.
- [ ] No full bot source files are copied.
- [ ] Screenshots, if added later, are redacted.
- [ ] GitHub Pages workflow logs do not print secrets.

