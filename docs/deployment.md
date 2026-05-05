# Deployment

This page covers the docs deployment and a high-level bot deployment model. It intentionally does not include private server addresses, production secrets, database credentials, or source code.

## Local Docs Preview

Run these commands from the docs repository root:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements-docs.txt
mkdocs serve
```

MkDocs prints a local preview URL, usually:

```text
http://127.0.0.1:8000
```

## Build The Docs

```bash
source .venv/bin/activate
mkdocs build
```

The generated static site is written to `site/`.

## GitHub Upload

```bash
git init
git add README.md mkdocs.yml requirements-docs.txt .gitignore .github docs
git commit -m "Add BRO-ker public docs"
git branch -M main
git remote add origin https://github.com/OWNER/BROKER_DOCS.git
git push -u origin main
```

Replace `OWNER` and `BROKER_DOCS` with the public docs repository owner and name.

## GitHub Pages

The included workflow uses the official GitHub Pages Actions pattern:

1. Check out the repository.
2. Set up Python.
3. Install docs requirements.
4. Run `mkdocs build --strict`.
5. Upload the Pages artifact.
6. Deploy to GitHub Pages.

In GitHub repository settings, configure Pages to use GitHub Actions as the source.

## Bot Deployment Concept

The private bot can be deployed as an ASGI application with role-based workers:

| Role | Purpose |
| --- | --- |
| `ingress` | Accepts Telegram webhook updates and copytrade events. |
| `bot-worker` | Processes Telegram UI and conversation jobs. |
| `trade-worker` | Executes trades, withdrawals, wallet exports, referral payouts, fee sweeps, and copytrade jobs. |
| `scheduler-worker` | Schedules recurring work such as limit-order scans. |
| `all` | Local development mode. |

Production deployments should use managed secrets, TLS termination, private database networking, monitoring, and log redaction.

## Docker And Process Managers

If Docker is used, run separate containers per role and inject secrets through the platform secret manager. If systemd or another process manager is used, keep each role in its own service unit with limited permissions, restart policies, centralized logs, and no secrets in unit files committed to Git.

## Developer Note

Material for MkDocs is stable and suitable for this public docs site. The dependencies are pinned in `requirements-docs.txt` for repeatable builds.

