# Referrals

BRO-ker includes a referral system for user links, KOL links, attribution, qualification, reward accrual, and reward claiming when enabled.

## Referral Codes

Each referral link carries a code in the Telegram start payload. When a new user starts the bot through a referral link, BRO-ker can attribute that user to the code owner.

Example public pattern:

```text
https://t.me/BOT_USERNAME?start=REFERRAL_CODE
```

Use placeholders in public docs and screenshots. Do not publish real production links unless they are intended for public use.

## Referral Dashboard

The user dashboard can show:

- Referral code.
- Referral link.
- Lifetime earned rewards.
- Rewards ready to claim.
- Rewards already paid.
- Processing payouts.
- Attributions.
- Qualified referrals.
- Tracked referred trades.
- Reward rate.
- Claim destination.

## Who Referred Who

The reviewed implementation supports first-valid-referrer behavior and prevents self-referrals. A referred user may need to complete qualification requirements before rewards begin accruing.

## Fee And Reward Attribution

At a high level:

1. A referred user completes a qualifying trade.
2. BRO-ker records the trade and fee base.
3. The referral service computes the reward share using configured reward basis points.
4. Rewards become claimable when they meet payout rules.
5. Claims settle to the user's main wallet when enabled and properly funded.

## Admin And KOL Concepts

Admins can create user links and KOL links, inspect referral stats, disable codes, set reward tiers, review referral trees, and check custom time ranges.

KOL links are referral links intended for partner or creator attribution. They still need a payout owner.

## Time-Window Metrics

Admin views include time windows such as 24h, 7d, 1mo, and full history for selected platform fee and referral metrics. These are operational summaries, not financial statements.

