# Frontline Escalated - Signal Dashboard

Daily signal dashboard for Frontline Escalated Support (TMS + SSA). Surfaces early warning signals, upcoming launches, queue health, and operational risks - designed for a 2-minute morning scan.

**Live site:** https://frontline-escalated-signal-dashboard.quick.shopify.io/

## What it shows

- **Today's Signals** - categorized by type (routing, tooling, training, launch gap, etc.) with priority levels and recommended actions
- **Queue Health** - daily Zendesk snapshot for TMS and SSA queues (backlog, unassigned, volume trend, age distribution)
- **Horizon** - launches shipping in the next 14 days from Birdwatcher, plus relevant calendar events
- **History** - past signal check results and risk level trends

## How it works

A scheduled automation runs each weekday morning (7:30am EST), scanning Slack channels, Birdwatcher, GitHub, Vault, BigQuery, and Calendar. Results are written to `signals.json` and deployed to Quick.

## Data sources

- Slack (channel scans + workspace keyword searches)
- Zendesk via BigQuery (queue metrics)
- Birdwatcher (upcoming launches)
- GitHub project board #13430
- Vault (internal docs and posts)
- Google Calendar

## Deploying

```bash
quick deploy . frontline-escalated-signal-dashboard
```

## Scope

TMS and SSA (Group 1) only. Shipping and Markets (Group 2) are excluded.

## Owner

Katie McConnell - Operations Multifecta, Frontline Escalated Support
