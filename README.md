# BRO-ker Bot Documentation

This repository contains public documentation for BRO-ker Bot.

It is a docs-only project. The private Telegram bot source code, production configuration, database files, wallet material, and infrastructure credentials are not included.

## Preview Locally

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements-docs.txt
mkdocs serve
```

Open the local URL printed by MkDocs, usually `http://127.0.0.1:8000`.

## Build

```bash
source .venv/bin/activate
mkdocs build
```

The static site is written to `site/`.

## Publish With GitHub Pages

1. Create a new public GitHub repository for the docs.
2. Push this docs project to the repository root.
3. In GitHub, open Settings -> Pages.
4. Set the source to GitHub Actions.
5. Push to the `main` branch.
6. The workflow in `.github/workflows/deploy-docs.yml` builds and deploys the site.

## Security Reminder

Never upload private bot source files, `.env` files, private keys, wallet seed phrases, Telegram bot tokens, RPC URLs with API keys, database dumps, production config, server IPs, admin IDs, or credentials to this repository.

