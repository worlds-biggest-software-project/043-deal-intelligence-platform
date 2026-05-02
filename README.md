# Deal Intelligence Platform

A revenue intelligence platform that surfaces deal-level risk signals, win/loss patterns, and coaching opportunities from multi-source signals (conversations, CRM activity, email/calendar), with built-in win/loss analysis and competitive intelligence.

## Problem Statement

Revenue intelligence is dominated by expensive, siloed solutions:
- **Gong** ($1,400–$2,000/seat/year) excels at conversation intelligence but lacks integrated forecasting and win/loss analysis
- **Clari** ($60–$100/user/month) offers best-in-class forecasting but weaker on deal-level coaching signals
- **No credible open-source option** exists; existing CRM analytics require significant custom engineering
- **Win/loss analysis** remains manual and subjective; 87% of enterprises missed revenue targets in 2025 despite record AI investment (Clari Labs 2026)

## Key Differentiators

### Deal-Level Risk Detection (3+ Weeks Earlier)
- Automated alerts for single-threaded relationships, ghosting post-proposal, pricing objection patterns, stalled deals
- 100+ conversation signals analyzed per deal: talk-time ratios, question frequency, competitor mentions, next-step clarity
- Practitioners report risk identification 3+ weeks earlier than manual pipeline reviews

### Multi-Source Signal Aggregation
- Activity capture from all channels: email, calendar, calls, CRM, and LinkedIn automatically mapped to opportunities
- Dark funnel contact discovery: identifies deals with hidden stakeholders not in CRM
- Bottom-up forecasting transparency: reps see how their deals roll into team/regional numbers

### Win/Loss Analysis Engine
- Automated synthesis of closed deal communication patterns and notes
- Identifies win factors by segment, rep, deal size, and competitive scenario
- Benchmarking across cohorts to surface patterns invisible to manual review

### Conversation Intelligence Depth
- Records and transcribes sales calls across Zoom, Teams, phone
- AI coaching moment identification surfaces specific call moments for manager review
- Qualification scoring against MEDDIC/SPICED frameworks auto-detected from transcripts

## Market Context

- **Market size**: Revenue intelligence estimated at $3–5B in 2025, growing 15–20% CAGR through 2030
- **Key players**: Gong ($7.25B peak valuation, $580M raised), Clari ($2.6B valuation, $510M raised)
- **Positioning**: Open-source alternative to Gong for SMB/mid-market teams needing deal intelligence without enterprise pricing

## Recommended MVP Scope

- Call recording/transcription across Zoom, Teams, and telephony
- Deal scoring combining conversation signals (50%) with activity/contacts/timing (50%)
- Risk alerts: ghosting, single-threading, stalled deals, reduced engagement
- Win/loss analysis dashboard: rate calculations by segment, rep, deal size
- CRM bi-directional sync (Salesforce, HubSpot native)
- Manager coaching dashboard with rep-level benchmarking

## Resources

**Research Materials**: [research.md](research.md) | **Feature Analysis**: [features.md](features.md)

## Target Users

- VP of Sales/CRO at B2B SaaS companies (100–2,000 employees) needing forecast accuracy
- Sales enablement leaders responsible for rep coaching and onboarding acceleration
- RevOps managers building deal health dashboards and pipeline governance
- Competitive intelligence teams that need win/loss data to inform GTM strategy
