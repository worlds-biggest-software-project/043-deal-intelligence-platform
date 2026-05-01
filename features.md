# Deal Intelligence Platform — Feature & Functionality Survey

> Candidate #43 · Researched: 2026-05-01

## Solutions Analysed

| Tool | Type | Licence / Model | URL |
|------|------|-----------------|-----|
| Gong | Commercial SaaS | Proprietary; $1,400–$2,000/seat/yr | https://gong.io |
| Clari | Commercial SaaS | Proprietary; est. $60–$100/user/mo | https://clari.com |
| People.ai | Commercial SaaS | Proprietary; enterprise custom | https://people.ai |
| BoostUp | Commercial SaaS | Proprietary; est. $50–$80/user/mo | https://boostup.ai |
| Klue | Commercial SaaS | Proprietary; est. $15–$25k/yr flat | https://klue.com |
| Crayon | Commercial SaaS | Proprietary; from ~$15k/yr flat | https://crayon.co |
| Revenue.io | Commercial SaaS | Proprietary; est. $50–$80/user/mo | https://revenue.io |
| Oliv.ai | Commercial SaaS | Proprietary; from ~$50/user/mo | https://oliv.ai |
| Tellius | Commercial SaaS | Proprietary; enterprise custom | https://tellius.com |

## Feature Analysis by Solution

### Gong

**Core features**
- Records, transcribes, and analyses every sales call across Zoom, Teams, and telephony platforms
- Deal boards: customisable views combining CRM data with AI risk assessments, engagement timelines, and qualification scores
- Deal likelihood scoring: 50% weighted on conversation intelligence signals, 50% on activity, contacts, timing, and historical patterns
- Risk alerts: automated warnings for single-threaded relationships, ghosting post-proposal, pricing objection patterns, and stalled deals
- Win/loss analytics: win rate calculations across key deal characteristics (rep, segment, deal size, competitive scenario)

**Differentiating features**
- Gold standard for conversation intelligence depth; analyses 100+ signals per deal including talk-time ratios, question frequency, competitor mentions, and next-step clarity
- AI risk detection described by practitioners as identifying at-risk deals 3+ weeks earlier than manual pipeline reviews
- Coaching moment identification: surfaces specific call moments for manager review and rep coaching
- Deals Intelligence module connects conversation patterns to revenue outcomes at the cohort level

**UX patterns**
- Deal board as primary interface: visual pipeline with AI risk badges overlaid on each opportunity
- Call library: searchable transcript repository with topic filters and sentiment timeline
- Manager coaching dashboard: rep-level performance metrics with comparative benchmarks

**Integration points**
- Native: Salesforce, HubSpot, Microsoft Dynamics
- Zoom, Teams, Google Meet, Dialpad, RingCentral for call capture
- Slack for deal alert notifications
- REST API for data export

**Known gaps**
- Very expensive ($1,400–$2,000/seat/year plus platform fee); ROI difficult to demonstrate for sub-50-seat teams
- Win/loss analysis requires manual interview programs for the qualitative narrative layer; automated synthesis is limited
- Competitive intelligence requires separate Klue or Crayon integration; not native
- Coaching recommendations are pattern-matched, not personalised to individual rep development stage

**Licence / IP notes**
- Fully proprietary

---

### Clari

**Core features**
- Revenue orchestration: combines forecasting, pipeline management, deal execution, and conversation intelligence
- Deal scoring: models evaluate engagement frequency, stakeholder involvement, and progression velocity against historical closed-won patterns
- Forecast rollup: bottom-up pipeline roll-up with manager override workflow and AI-adjusted confidence ranges
- Activity capture: aggregates data from CRM, email, calendar, and call recordings to surface revenue health indicators
- Clari Copilot (formerly Wingman): conversation intelligence module with real-time whisper coaching during live calls (merged with Salesloft December 2025)

**Differentiating features**
- Best-in-class revenue forecasting accuracy; uses AI to adjust manager-submitted forecasts against historical bias patterns
- Clari Align: digital sales room for buyer-seller collaboration on shared deal timelines
- Merged with Salesloft (December 2025): combined platform now covers engagement, intelligence, and forecasting in a single stack
- Bottom-up forecasting transparency: each rep sees how their deals roll into team and regional numbers

**UX patterns**
- Forecast grid: spreadsheet-style roll-up where managers drill from total to individual deals
- Pipeline inspection: list view with risk indicators, engagement scores, and missing qualification fields highlighted
- Executive view: revenue health summary across segments with trend indicators

**Integration points**
- Native: Salesforce (primary), HubSpot
- Zoom, Teams, Gong (for conversation data)
- Slack for alert delivery
- REST API

**Known gaps**
- Conversational intelligence weaker than Gong in head-to-head comparisons
- Expensive for teams not at scale ($60–$100/user/mo; full stack including Copilot $200–$310/user/mo)
- Complex configuration; requires dedicated RevOps resource to maintain forecast settings

**Licence / IP notes**
- Fully proprietary

---

### People.ai

**Core features**
- Activity capture from all communication channels: email, calendar, calls, and LinkedIn mapped automatically to CRM opportunities
- Dark funnel contact discovery: identifies contacts engaging with deals who are not yet in CRM
- Deal health scoring based on captured activity depth and relationship coverage
- CRM auto-update: writes captured signals back to Salesforce/HubSpot fields without rep action

**Differentiating features**
- Deepest activity capture depth in the category; captures signals that reps would never manually log
- Dark funnel visibility: discovers buying committee members who are engaged but invisible in CRM
- Revenue attribution from activity data; shows which engagement patterns are leading indicators of close

**UX patterns**
- Opportunity intelligence panel embedded within Salesforce (via managed package)
- Activity timeline showing all stakeholder engagement across the deal lifecycle

**Integration points**
- Salesforce (primary; native managed package)
- HubSpot
- Gmail, Outlook, Zoom, Teams
- LinkedIn (via integration)

**Known gaps**
- Requires significant implementation effort; not self-serve
- Limited self-hosted or privacy-preserving deployment options
- Enterprise-only pricing; SMB teams priced out entirely

**Licence / IP notes**
- Fully proprietary

---

### BoostUp

**Core features**
- Deal-level risk scoring using signals from emails, calls, and CRM activity at the individual opportunity level
- Forecasting: AI-adjusted commit and best-case predictions with rep-level accuracy tracking
- Deal coaching recommendations surfaced within the deal view
- Works with both Salesforce and HubSpot (broader CRM compatibility than some competitors)

**Differentiating features**
- Bottom-up risk scoring surfaced at the individual deal level rather than only in aggregate
- CRM flexibility: one of few revenue intelligence tools with genuine HubSpot support alongside Salesforce
- Actionable deal coaching embedded in deal view; not just analytics dashboards

**UX patterns**
- Deal list with risk badges and recommended actions per deal
- Forecast manager: drill-down from total to segment to rep to individual opportunity

**Integration points**
- Salesforce, HubSpot
- Zoom, Teams for call capture
- Slack for notifications

**Known gaps**
- Smaller AI model training dataset than Gong; accuracy of deal scoring less validated at scale
- Smaller ecosystem and partner network than Gong/Clari

**Licence / IP notes**
- Fully proprietary

---

### Klue

**Core features**
- Competitive intelligence tracking: monitors competitor websites, review sites (G2, Capterra), job postings, and news for signal changes
- Battlecard generation and distribution to sales reps via Slack/email/CRM
- Win/loss interview management: structured template capture and qualitative theme analysis
- Win/loss reporting: win rate by competitor, deal size, segment, and time period

**Differentiating features**
- Best combined competitive intelligence + win/loss analysis platform in the market
- AI-generated battlecard summaries from competitor tracking signals
- Win/loss interview theme synthesis across multiple interviews using NLP

**UX patterns**
- Competitive intelligence dashboard: real-time competitor signal feed organised by topic
- Battlecard editor with collaborative editing and version history
- Win/loss interview builder with guided question templates

**Integration points**
- Slack (battlecard delivery during live calls)
- Salesforce, HubSpot (win/loss tagging)
- Gong (call transcript analysis for competitor mentions)

**Known gaps**
- Win/loss data relies on manual interview entry unless integrated with conversation intelligence
- Deal-level risk scoring absent; Klue is CI-focused, not deal health-focused
- Not a forecasting tool; requires Gong/Clari for deal intelligence depth

**Licence / IP notes**
- Fully proprietary

---

### Oliv.ai

**Core features**
- AI-native deal intelligence built on an agentic architecture
- Auto-scores MEDDIC, BANT, and SPICED qualification frameworks from call transcripts without manual rep input
- Real-time deal coaching: surfaces recommendations during live calls (whisper mode)
- CRM field auto-population: writes MEDDIC scores, next steps, and deal summary to Salesforce/HubSpot fields
- Deal risk flags surfaced from communication pattern analysis

**Differentiating features**
- Purpose-built AI-first architecture (not a legacy platform with AI bolted on)
- Methodology auto-scoring (MEDDIC/BANT/SPICED) from conversation is more automated than Gong's equivalent
- Real-time whisper coaching during calls; Gong is primarily post-call
- Modular pricing from ~$50/user/mo; more accessible than Gong for growth-stage companies

**UX patterns**
- Deal workspace: per-deal view combining methodology scores, activity timeline, and AI recommendations
- Live call coaching overlay with contextual suggestions triggered by conversation events

**Integration points**
- Salesforce, HubSpot
- Zoom, Teams, Google Meet
- Slack for deal alerts

**Known gaps**
- Newer entrant; unproven at enterprise scale (500+ seat deployments)
- Smaller training dataset than Gong; deal scoring model less battle-tested

**Licence / IP notes**
- Fully proprietary

---

### Tellius

**Core features**
- Natural-language query layer for revenue analytics: "why did we miss Q3 quota in EMEA?" returns AI-generated root cause analysis
- Multi-source data connection: CRM, conversation intelligence, and financial data in one analytical model
- Automated insight detection: proactively surfaces anomalies and drivers without requiring a specific query
- Revenue analytics for RevOps: segment-level performance drill-down with AI-generated commentary

**Differentiating features**
- Best analytical depth for complex multi-source revenue queries; not a pipeline management tool
- Natural-language interface eliminates the need for SQL or BI expertise for RevOps analysis
- Automated insight alerts: notifies RevOps when unexpected patterns emerge in revenue data

**UX patterns**
- Chat-like query interface for natural-language analysis
- Dashboard canvas for standard KPI monitoring alongside conversational analytics

**Integration points**
- Salesforce, HubSpot, Marketo
- Gong, Chorus (conversation data)
- Snowflake, Redshift, BigQuery (data warehouse)

**Known gaps**
- Not a deal management or forecasting tool; purely analytical
- Requires data infrastructure (data warehouse) for full value; not a standalone deployment
- Enterprise pricing and implementation complexity

**Licence / IP notes**
- Fully proprietary

---

## Cross-Cutting Feature Themes

### Table-Stakes Features
- Deal health scoring using multi-signal analysis (CRM data, email activity, call patterns)
- Risk alerts surfacing deals at risk of stalling, ghosting, or single-threaded engagement
- Pipeline visibility: deal list view with health indicators, stage age, and next-step status
- CRM integration for bi-directional data sync (Salesforce primary; HubSpot secondary)
- Call transcript ingestion for conversation signal extraction
- Win rate reporting by key dimensions (rep, segment, deal size, competitive scenario)

### Differentiating Features
- Sales methodology auto-scoring (MEDDIC/MEDDPICC, BANT, SPICED) from conversation transcripts without manual rep input
- Real-time whisper coaching during live calls (Clari Copilot, Oliv.ai model)
- Dark funnel contact discovery: finding buying committee members invisible in CRM
- Automated win/loss synthesis from call transcripts and email threads (replacing quarterly manual interview programs)
- Longitudinal rep coaching: personalised development recommendations based on rep's deal outcome history
- Competitive intelligence integration: real-time battlecard surfacing during calls based on transcript content
- Natural-language revenue analytics: "why did we miss quota?" answerable without SQL or BI expertise
- Predictive early-warning: detecting deal risk 3+ weeks before ghosting or disengagement becomes obvious

### Underserved Areas / Opportunities
- **No viable open-source option**: Building deal intelligence on Whisper (transcription) + local LLM + CRM data is technically feasible but has not been productised; self-hosted deal intelligence would serve regulated industries (financial services, healthcare, defence) that cannot send recordings to Gong's cloud
- **Continuous win/loss analysis**: Current tools deliver quarterly snapshots from interview programs; automated continuous synthesis from call transcripts and email threads remains largely unbuilt
- **Personalised coaching at the individual rep level**: Current tools benchmark reps against team averages; a longitudinal model of each rep's strengths and development trajectory would be meaningfully more actionable
- **Competitive intelligence embedded in deal view**: Klue and Crayon are separate tools; no deal intelligence platform surfaces competitive context inline from the live transcript

### AI-Augmentation Candidates
- Deal health scoring: manually inspected pipeline reviews → ML model scoring 100+ engagement, qualification, and timing signals
- Win/loss analysis: quarterly interview programs → continuous LLM synthesis from closed deal transcripts, emails, and CRM notes
- Forecast submission: rep-estimated commit figures → AI-adjusted predictions correcting for individual rep historical bias
- Methodology scoring: manual rep-entered MEDDIC field updates → automatic extraction from call transcripts
- Coaching recommendations: aggregate talk-time benchmarks → personalised rep development path from longitudinal call pattern analysis

## Legal & IP Summary

No credible open-source deal intelligence platform was identified; the entire category is proprietary. All major commercial platforms (Gong, Clari, People.ai, BoostUp, Klue, Crayon, Revenue.io, Oliv.ai, Tellius) are fully proprietary with no code reuse permitted. GDPR Article 22 (automated decision-making) may apply to deal risk scoring where scores influence hiring or performance management decisions affecting EU-based employees; transparency obligations would apply. Call recording consent requirements under GDPR, CCPA, and US state two-party consent laws must be addressed for any call intelligence feature; geographic consent workflows are necessary. Gong holds patents related to aspects of its conversation intelligence methodology; specific patent numbers were not identified in the research, but any implementation of similar techniques should conduct a freedom-to-operate review. No patent concerns were identified for statistical deal scoring methods.

## Recommended Feature Scope

**Must-have (MVP)**:
- Deal health scoring using CRM activity data, email engagement signals, and call transcript analysis
- Risk alert engine: automated flags for single-threaded deals, no recent activity, stalled stage progression, and unanswered proposals
- Pipeline view with health indicators, stage age, and qualification gap identification (MEDDIC/BANT fields)
- CRM bi-directional sync: automatic population of deal health scores and risk flags to Salesforce/HubSpot opportunity records
- Win rate reporting by rep, segment, deal size, and close quarter with trend comparison

**Should-have (v1.1)**:
- Sales methodology auto-scoring: extract MEDDIC/BANT/SPICED field values from call transcripts and write to CRM automatically
- Automated win/loss synthesis: LLM analysis of closed deal transcripts and email threads surfacing primary win and loss reasons by cohort
- Dark funnel contact discovery: identify stakeholders engaging with deals who are absent from CRM contacts
- Forecast roll-up with AI-adjusted confidence ranges correcting for rep historical optimism/pessimism bias

**Nice-to-have (backlog)**:
- Real-time whisper coaching during live calls with qualification framework prompts
- Competitive intelligence integration: surface relevant battlecard content during calls based on competitor mentions in the live transcript
- Personalised rep coaching paths based on longitudinal deal outcome and conversation pattern analysis
- Natural-language revenue analytics interface for RevOps ("why did Q2 miss in EMEA?")
- Self-hosted deployment option with on-premises transcription (Whisper) for regulated industry use
