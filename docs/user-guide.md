# User Guide

BRO-ker is organized around a Telegram dashboard and token sheets. Most actions happen through inline buttons so users can move quickly without memorizing commands.

## Dashboard

The dashboard is the starting point for wallet setup, portfolio checks, trading settings, referrals, copytrading, limit orders, and admin access when applicable.

Common buttons include:

| Button | Purpose |
| --- | --- |
| Wallets or Set Up Wallet | Create or manage trading wallets. |
| Portfolio | View live balances and jump back into held tokens. |
| Limit Dash | Review active limit orders across tokens. |
| Copy Trade | Add source wallets and manage copytrade settings. |
| Referrals | View referral link, attribution, rewards, and claims. |
| Settings | Adjust quick buttons, slippage, confirmation, PnL display, and chart interval. |
| Refresh | Reload the current view. |

## Wallet Screen

The wallet screen shows the active trading wallet, SOL balance, and wallet management actions. BRO-ker also supports multiwallet management, including adding wallets, renaming wallets, selecting the main wallet, exporting backups when enabled, and deleting inactive wallets after confirmation.

Withdrawal flows are handled in private chat. Users can withdraw SOL, withdraw a custom SOL amount, or withdraw a token by mint address.

## Token Sheet

Paste a Solana mint address to open a token sheet. Depending on whether the wallet already holds the token, the sheet shows buy controls, sell controls, or both.

Token sheets may include:

- Price and market cap.
- Wallet SOL balance.
- Current token holding and estimated value.
- Open limit orders for the token.
- PnL information from tracked executions.
- Links to chart, PnL card, Solscan, or external market pages.

## Buy Flow

1. Open a token sheet.
2. Select a preset buy amount or custom amount.
3. Review the quote, slippage, price impact, expected output, and warnings.
4. Confirm the trade when required.
5. Review the final result message.

## Sell Flow

1. Open a token already held by the active wallet.
2. Choose a preset sell percentage, custom sell amount, or Sell Initial if available.
3. Review the live quote.
4. Confirm when required.
5. Refresh the token sheet or portfolio after completion.

## Positions And Portfolio

The portfolio screen summarizes the active wallet, available SOL, tracked token balances, and links back to token sheets. Position data combines on-chain balances, token metadata, and BRO-ker tracked executions.

## PnL And Analytics

PnL cards are based on BRO-ker tracked buys and sells. For open positions, live exit quote data may be used to estimate the value after price impact. Chart cards can show price or market cap, with entry and exit markers when tracked trade data is available.

## Copytrade Area

Copytrade lets a user add source wallets to watch. Each watched wallet can use global settings or custom overrides. Users can enable or disable each source wallet, rename it, and adjust trade sizing, risk limits, execution settings, token filters, and notifications.

## Referral Area

The referral dashboard shows a user's referral code, link, total earned rewards, claimable rewards, paid rewards, attribution counts, qualified referrals, and tracked referred trades.

## Support Flow

The reviewed bot implementation includes a help flow and admin announcements. A dedicated in-bot ticket system was not observed. Public deployments should publish the official support channel separately and remind users that support will never request private keys or seed phrases.

