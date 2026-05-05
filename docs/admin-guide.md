# Admin Guide

Admin functionality is restricted to configured admin users and is designed for private chat operation.

!!! warning "Operational safety"
    Do not publish admin Telegram IDs, private links, production screenshots with user data, webhook secrets, payout wallets, or fee account addresses.

## Admin Dashboard

The admin dashboard provides an operations snapshot for users, wallets, trading, limits, referral links, referral network activity, reward ledgers, and platform fee metrics.

Observed dashboard controls include:

| Area | Actions |
| --- | --- |
| Referral links | Create user links, create KOL links, list active links, view code stats, disable links. |
| Referral analysis | Lookup by code, username, or Telegram ID; check custom time ranges. |
| Reward tiers | Enable configured 15% or 30% referral tiers. |
| Platform fees | Sweep fees now, toggle autosweep, review fee windows. |
| Access | Add or remove whitelist users through admin commands. |
| Announcements | Broadcast an HTML-formatted message to users. |

## Referral And KOL Management

Admins can create referral links for normal users and KOLs. A KOL link is a partner or creator attribution link that still maps to an owner for rewards.

Recommended practice:

- Confirm the owner account before creating a link.
- Use clear code naming conventions.
- Disable old or compromised links instead of reusing them.
- Review time-window metrics before making payout or campaign decisions.

## Platform Fee Metrics

Admin fee views can summarize confirmed trades, referred trades, tracked volume, rewarded fee base, referral rewards, and estimated retained fees over selectable windows.

Fee sweeps should be treated as a privileged financial operation. Confirm treasury configuration and wallet ownership before enabling autosweep.

## Whitelist Mode

If whitelist-only mode is enabled, non-admin users need to be explicitly added before they can use the bot. Admins can add or remove Telegram IDs through admin commands.

## Announcements

Announcements can broadcast to all known users. Keep them short, avoid sensitive data, and preview formatting before sending. Do not include links that ask users to provide private keys or seed phrases.

## Support Practices

The reviewed implementation includes help and announcement flows but no dedicated ticketing system. Operators should maintain an official public support channel and a private escalation process for admins.

Support staff should never request:

- Seed phrases.
- Private keys.
- Telegram login codes.
- Production database records.
- User wallet backup screenshots.

