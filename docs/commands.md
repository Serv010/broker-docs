# Commands

The commands below were observed from the bot command registration. Availability can still depend on deployment settings, terms acceptance, private chat requirements, whitelist mode, and admin permissions.

## User Commands

| Command | Who can use it | Purpose | Notes |
| --- | --- | --- | --- |
| `/start` | Users | Open the dashboard and process referral or deep-link payloads. | Main entry point. |
| `/wallet` | Users | Open the wallet screen. | Wallet actions that expose secrets require private chat. |
| `/portfolio` | Users | View portfolio and tracked holdings. | Requires a wallet for full functionality. |
| `/limits` | Users | View active limit orders. | Opens Limit Dash. |
| `/copytrade` | Users | Open copytrade management. | Requires copytrade to be enabled in deployment. |
| `/referrals` | Users | Open referral dashboard. | Requires referrals to be enabled in deployment. |
| `/my_ref_link` | Users | Show personal referral link. | Link format depends on bot username. |
| `/ref_stats` | Users | Show referral stats. | Admins may be able to query a specific code. |
| `/settings` | Users | Open trade settings. | Includes quick buttons, slippage, confirmation, PnL, chart settings, and limit target mode. |
| `/help` | Users | Explain the basic BRO-ker workflow. | Good first stop for new users. |

## Admin Commands

| Command | Who can use it | Purpose | Notes |
| --- | --- | --- | --- |
| `/admin` | Admins | Open admin dashboard. | Private chat only. |
| `/refcodes` | Admins | List active referral codes. | Verify exact output in bot implementation. |
| `/newref` | Admins | Create a user referral link. | Requires an owner user. |
| `/newkol` | Admins | Create a KOL referral link. | Requires an owner user. |
| `/ref15` | Admins | Set a user's referral reward tier to 15%. | Uses configured referral policy. |
| `/ref30` | Admins | Set a user's referral reward tier to 30%. | Uses configured referral policy. |
| `/reflookup` | Admins | Look up a referral tree by code, username, or Telegram ID. | Also available through admin dashboard buttons. |
| `/refrange` | Admins | Check referral stats for a custom time range. | Time-window entry is interactive. |
| `/disable_ref` | Admins | Disable a referral code. | Records an admin action. |
| `/addwl` | Admins | Add a Telegram user to the whitelist. | Relevant only when whitelist mode is enabled. |
| `/removewl` | Admins | Remove a Telegram user from the whitelist. | Relevant only when whitelist mode is enabled. |
| `/announce` | Admins | Broadcast a message to users. | Private chat only; use carefully. |

## Development And Test Commands

| Command | Who can use it | Purpose | Notes |
| --- | --- | --- | --- |
| `/drypnl` | Verify in bot implementation | Render a dry-run PnL card scenario. | Appears intended for internal testing. Do not document as a normal user feature unless intentionally exposed. |
| `/drypnl1` | Verify in bot implementation | Render a dry-run PnL card scenario. | Appears intended for internal testing. Do not document as a normal user feature unless intentionally exposed. |

