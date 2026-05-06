# Standards & API Reference

> Project: Deal Intelligence Platform · Generated: 2026-05-06

## Industry Standards & Specifications

### ISO Standards

**ISO/IEC 27001:2022 — Information Security Management Systems**
URL: https://www.iso.org/standard/27001
The primary information security management standard for SaaS vendors. Any deal intelligence platform that ingests call recordings, email threads, and CRM data must demonstrate ISO 27001 compliance to satisfy enterprise procurement requirements. Defines controls for data access, encryption at rest and in transit, and incident response.

**ISO/IEC 27701:2019 — Privacy Information Management**
URL: https://www.iso.org/standard/71670.html
Extension to ISO 27001 specifically for privacy; directly relevant to platforms processing call recordings and personal communications data. Provides the control framework that maps to GDPR Article 5 (data processing principles) and can be audited alongside ISO 27001.

**ISO/IEC 25012:2008 — Data Quality Model**
URL: https://www.iso.org/standard/35736.html
Defines a data quality model with 15 characteristics (accuracy, completeness, consistency, currentness, etc.). Directly relevant to the integrity of signals feeding ML-based deal health scoring models; low-quality CRM data is a documented cause of poor deal scoring accuracy in the revenue intelligence category.

**ISO/IEC 23053:2022 — Framework for Artificial Intelligence Systems Using Machine Learning**
URL: https://www.iso.org/standard/74438.html
Provides a framework for describing ML systems, including lifecycle stages, performance measurement, and uncertainty quantification. Applicable to the design of deal health scoring and forecast accuracy models, where model uncertainty should be communicated to end users rather than presented as deterministic predictions.

---

### W3C & IETF Standards

**RFC 6749 — The OAuth 2.0 Authorization Framework**
URL: https://www.rfc-editor.org/rfc/rfc6749
The foundational authorization framework for all major CRM and communication platform integrations (Salesforce, HubSpot, Zoom, Gong). Any deal intelligence platform must implement OAuth 2.0 client flows to integrate with these upstream sources. The Authorization Code with PKCE flow (RFC 7636) is the 2026 recommended pattern for all client types.

**RFC 6750 — The OAuth 2.0 Authorization Framework: Bearer Token Usage**
URL: https://www.ietf.org/rfc/rfc6750.txt
Defines how Bearer tokens are transmitted in HTTP requests (Authorization header, form-encoded body). All REST API integrations in the deal intelligence ecosystem rely on Bearer token authorization.

**RFC 7636 — Proof Key for Code Exchange (PKCE)**
URL: https://datatracker.ietf.org/doc/html/rfc7636
Extension to OAuth 2.0 that prevents authorization code interception attacks; required for public clients (SPAs, mobile apps) and recommended for all new OAuth 2.0 implementations. Salesforce, HubSpot, and Zoom APIs all support PKCE.

**OpenID Connect Core 1.0**
URL: https://openid.net/specs/openid-connect-core-1_0.html
Authentication identity layer built on OAuth 2.0. Relevant for SSO integration in enterprise deployments; enterprise buyers expect SAML 2.0 or OIDC-based SSO as table stakes for a deal intelligence platform deployed to 50+ seat sales teams.

**W3C WebRTC — Web Real-Time Communication**
URL: https://w3c.github.io/webrtc-pc/
W3C specification defining peer-to-peer audio and video communication in browsers. Underpins the call capture capabilities of Zoom, Google Meet, and Teams; any browser-based call recording or live whisper coaching feature must conform to WebRTC APIs. MediaRecorder API (W3C) handles the recording layer.

**RFC 7159 / ECMA-404 — JSON Data Interchange Format**
URL: https://datatracker.ietf.org/doc/html/rfc7159
The universal wire format for all REST APIs in the revenue intelligence ecosystem. All CRM, transcription, and engagement platform APIs return JSON responses.

**JSON:API v1.1**
URL: https://jsonapi.org/format/
A specification for structuring JSON API request/response payloads with standardised resource objects, relationships, and links. Reduces client-side complexity when working with related resources (opportunities, contacts, accounts, activities) — relevant for the data model layer of a deal intelligence platform's own REST API surface.

---

### Data Model & API Specifications

**OpenAPI Specification v3.1.0**
URL: https://spec.openapis.org/oas/v3.1.0.html
The de facto standard for describing RESTful APIs. All major products in the deal intelligence ecosystem (Gong, Clari, HubSpot, Salesforce, Salesloft) publish or accept OpenAPI/Swagger specifications for their APIs. Any open-source deal intelligence platform should publish an OpenAPI 3.1 specification to enable third-party integrators.

**JSON Schema (Draft 2020-12)**
URL: https://json-schema.org/draft/2020-12/schema
Used within OpenAPI 3.1 for defining request/response object schemas. Relevant for defining deal objects, risk signal payloads, and qualification framework score structures (MEDDIC/BANT/SPICED field schemas).

**GraphQL (June 2018 Specification)**
URL: https://spec.graphql.org/June2018/
Query language for APIs used by some revenue intelligence platforms for flexible data retrieval. Clari's developer portal exposes a GraphQL playground. Worth evaluating for the platform's own query interface given the complex relational nature of deal data (opportunities → contacts → activities → signals).

**Protocol Buffers (proto3)**
URL: https://protobuf.dev/programming-guides/proto3/
Binary serialisation format used in high-throughput signal ingestion pipelines. Relevant if the platform needs to process high-volume activity event streams (email open events, call event metadata) at sub-millisecond latency.

---

### Security & Authentication Standards

**GDPR Article 22 — Automated Decision-Making and Profiling**
URL: https://gdpr-info.eu/art-22-gdpr/
Individuals have the right not to be subject to solely automated decisions that produce significant legal or similarly significant effects. Deal health scores that directly influence rep performance reviews, compensation, or termination decisions in EU-context deployments may trigger Article 22 obligations, requiring human review mechanisms and explainability of scoring logic. Platforms should document their scoring methodology and provide a human-in-the-loop review pathway.

**GDPR Article 5 — Principles Relating to Processing of Personal Data**
URL: https://gdpr-info.eu/art-5-gdpr/
Lawfulness, fairness, transparency, purpose limitation, data minimisation, accuracy, storage limitation, and integrity/confidentiality. Call recordings and email content processed by a deal intelligence platform are personal data; data retention schedules, purpose-limiting policies, and deletion workflows must be designed to comply with these principles.

**CCPA / CPRA — California Consumer Privacy Act / Rights Act**
URL: https://oag.ca.gov/privacy/ccpa
California's comprehensive privacy law with rights parallel to GDPR. Deal intelligence platforms processing data about California residents must provide opt-out of sale/sharing, deletion rights, and data access rights. Call recording consent requirements under California Penal Code 632 (two-party consent) must also be addressed for any call capture feature serving California users.

**US State Two-Party Consent Laws**
Multiple US states (California, Florida, Illinois, Maryland, Pennsylvania, Washington) require all parties to consent to call recording. A deal intelligence platform's call capture feature must implement geographic consent workflows that detect jurisdiction and apply the appropriate consent prompt before recording begins. Illinois BIPA (Biometric Information Privacy Act) is also relevant if voiceprint or facial recognition features are used.

**OWASP API Security Top 10 (2023)**
URL: https://owasp.org/API-Security/editions/2023/en/0x11-t10/
The reference checklist for API security design. Directly applicable to the platform's own API surface: API1 (Broken Object Level Authorization) is particularly critical for multi-tenant deal intelligence platforms where one tenant must not be able to access another tenant's deal data or call recordings.

**SOC 2 Type II**
URL: https://www.aicpa-cima.com/topic/audit-assurance/audit-and-assurance-greater-than-soc-2
Not an ISO standard but the dominant enterprise SaaS compliance attestation in North America. Enterprise buyers (financial services, healthcare, government) require SOC 2 Type II reports before procurement approval. Platform design must account for the trust service criteria (security, availability, processing integrity, confidentiality, privacy) from the outset.

---

### MCP Server Specifications

**Model Context Protocol (MCP) — Specification 2025-11-25**
URL: https://modelcontextprotocol.io/specification/2025-11-25
Anthropic's open standard for connecting LLM applications with external data sources and tools. Uses JSON-RPC 2.0 transport. As of 2026, Klue has launched an MCP server for its competitive intelligence platform, and MCP adoption in the sales tech ecosystem is accelerating rapidly. A deal intelligence platform that exposes an MCP server would enable AI sales agents to pull real-time deal health scores, risk signals, and qualification gaps directly into agent workflows without custom integration work. MCP tools, resources, and prompts primitives map well to the deal intelligence domain (deal score resources, risk alert tools, MEDDIC field prompts).

---

## Similar Products — Developer Documentation & APIs

### Gong
- **Description:** Market-leading revenue intelligence platform; records, transcribes, and analyses sales calls to surface deal health scores, risk alerts, and coaching recommendations across 4,000+ customers.
- **API Documentation:** https://help.gong.io/docs/what-the-gong-api-provides
- **Base URL:** https://api.gong.io/v2/
- **Authentication:** HTTP Basic Auth (Access Key + Access Key Secret); admin-level credentials required.
- **SDKs/Libraries:** No official SDK; community Python wrapper available via dltHub (https://dlthub.com/context/source/gong); Postman collection at https://www.postman.com/growment/gong-meetup/collection/yuikwaq/gong-api-beginners-guide
- **Developer Guide:** https://help.gong.io/docs/receive-access-to-the-api
- **Key Endpoints:** Calls (GET /calls, GET /calls/{id}/transcript), Users (GET /users), CRM data (GET /crm/entities), Scorecards (GET /scorecards)
- **Standards:** REST/JSON; no public OpenAPI spec
- **Rate Limits:** ~1,000 requests/hour for most endpoints
- **Notes:** Two distinct APIs — Standard API (call data extraction) and Engage API (outreach automation). Call transcript data is the primary integration target for a deal intelligence platform.

---

### Clari
- **Description:** Revenue orchestration platform combining pipeline forecasting, deal execution, and conversation intelligence (Clari Copilot). Merged with Salesloft in December 2025.
- **API Documentation:** https://developer.clari.com/documentation/external_spec
- **Copilot API Documentation:** https://api-doc.copilot.clari.com/
- **Base URL:** https://api.clari.com/v2
- **Authentication:** API Token in `apikey` header; partner APIs additionally require `partnerkey` header; Copilot uses `X-Api-Key` and `X-Api-Password` headers.
- **SDKs/Libraries:** Python connector available via dltHub (https://dlthub.com/context/source/clari)
- **Developer Guide:** https://community.clari.com/product-q-a-6/clari-api-all-you-need-to-know-556
- **Standards:** REST/JSON; GraphQL playground available in developer portal; OpenAPI/Swagger specs available
- **Notes:** Developer portal includes OAuth playground, sandbox environment, and Postman/Insomnia collections. Webhook management API enables event-driven integration.

---

### Salesloft (merged with Clari)
- **Description:** Sales engagement platform covering cadences, email sequencing, dialler, and (post-merger) revenue intelligence. Acquired Clari's Copilot conversation intelligence in December 2025.
- **API Documentation:** https://developers.salesloft.com/api.html
- **Swagger Spec:** https://api.salesloft.com/swagger/index.html
- **Authentication:** OAuth 2.0; Bearer token in Authorization header.
- **SDKs/Libraries:** GitHub examples at https://github.com/SalesLoft/api-example; API guide at https://github.com/SalesLoft/api-guide
- **Developer Guide:** https://developers.salesloft.com/
- **Standards:** REST/JSON; Swagger/OpenAPI documented
- **Notes:** Person and Cadence are the core resource objects. Integration with Clari's forecasting and conversation intelligence endpoints is in progress post-merger (as of May 2026).

---

### Salesforce CRM
- **Description:** Dominant enterprise CRM; Opportunity object is the canonical deal record that all deal intelligence platforms write scores and risk flags back to.
- **API Documentation:** https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/resources_list.htm
- **Object Reference (Opportunity):** https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_objects_opportunity.htm
- **Authentication:** OAuth 2.0 via Connected App; supports Authorization Code, Client Credentials, and JWT Bearer flows.
- **SDKs/Libraries:** Salesforce DX CLI; official Node.js, Python, Java SDKs; `simple-salesforce` (Python community); `jsforce` (Node.js community)
- **Developer Guide:** https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/intro_oauth_and_connected_apps.htm
- **Standards:** REST/JSON; SOAP API also available; Bulk API 2.0 for large dataset operations; Streaming API for real-time event subscriptions (Platform Events)
- **Current Version:** Spring '26 (v66.0) — https://resources.docs.salesforce.com/latest/latest/en-us/sfdc/pdf/api_rest.pdf
- **Notes:** Deal intelligence platforms must write custom fields to Opportunity records (deal health score, risk flag, MEDDIC scores). Managed Packages or unlocked packages are the recommended deployment pattern for Salesforce-native integrations.

---

### HubSpot CRM
- **Description:** Leading mid-market CRM; Deals object is the equivalent of Salesforce Opportunities. Growing enterprise adoption; second most common CRM in the revenue intelligence ecosystem after Salesforce.
- **API Documentation:** https://developers.hubspot.com/docs/api-reference/crm-deals-v3/guide
- **Pipeline API:** https://developers.hubspot.com/docs/reference/api/crm/pipelines
- **Authentication:** OAuth 2.0 (preferred for integrations); Private App tokens for single-account integrations.
- **SDKs/Libraries:** Official Python, Node.js, PHP, Ruby, Java, Go SDKs at https://developers.hubspot.com/docs/cms/developer-reference
- **Developer Guide:** https://developers.hubspot.com/blog/a-developers-guide-to-hubspot-crm-objects-deals-object
- **Standards:** REST/JSON; API v3; OpenAPI 3.0 specs available
- **Notes:** Deal properties (dealname, dealstage, pipeline, closedate, amount) are the primary write targets. Custom properties must be created before writing deal health scores. Last updated March 2026.

---

### Zoom (Cloud Recording & Transcription)
- **Description:** Primary video conferencing platform for B2B sales calls; provides cloud recording, automated transcription, and real-time media stream APIs critical for conversation intelligence features.
- **API Documentation:** https://developers.zoom.us/docs/api/
- **Scribe Transcription API:** https://www.zoom.com/en/products/ai-services/scribe-api/
- **Live Transcription (Video SDK):** https://developers.zoom.us/docs/video-sdk/web/transcription-translation/
- **Authentication:** OAuth 2.0 Server-to-Server (recommended for server integrations); OAuth 2.0 Authorization Code for user-authorized access.
- **SDKs/Libraries:** Official Node.js, Python, Java, Go SDKs; Video SDK (JavaScript, React Native, iOS, Android)
- **Standards:** REST/JSON; WebSocket-based Real-Time Media Streams (RTMS) for live audio/transcript access
- **Notes:** `recording.transcript_completed` webhook event triggers when a cloud recording transcript is ready. Real-Time Media Streams (RTMS) API provides live transcript access during the meeting — essential for whisper coaching features. Zoom Scribe API offers synchronous low-latency transcription for pre-recorded audio files.

---

### OpenAI Whisper (Open-Source Transcription)
- **Description:** Open-source automatic speech recognition (ASR) model trained on 680,000 hours of multilingual audio; the primary open-source transcription engine for self-hosted deal intelligence deployments that cannot send recordings to cloud services.
- **API Documentation (Hosted):** https://developers.openai.com/api/docs/guides/speech-to-text
- **Model Card:** https://openai.com/index/whisper/
- **GitHub (Open Source):** https://github.com/openai/whisper
- **HuggingFace:** https://huggingface.co/openai/whisper-large-v3
- **Authentication (Hosted API):** Bearer token (OpenAI API key)
- **SDKs/Libraries:** `openai` Python package; `openai` Node.js package; `faster-whisper` (CTranslate2-optimised community library) for high-throughput local deployment
- **Supported Formats:** mp3, mp4, mpeg, mpga, m4a, wav, webm
- **Output Formats:** json, text, srt, verbose_json, vtt
- **Notes:** whisper-1 model available via OpenAI hosted API (25 MB file limit). For self-hosted regulated-industry deployments: `whisper-large-v3` on HuggingFace is the recommended base model; `faster-whisper` library provides 4× speedup via CTranslate2. Supports multilingual recognition, language identification, and word-level timestamps.

---

### People.ai
- **Description:** AI-driven activity capture platform that maps all communication signals (email, calendar, calls, LinkedIn) to CRM opportunities automatically, including dark funnel contact discovery.
- **API Documentation:** https://setup.people.ai/
- **API Tracker Reference:** https://apitracker.io/a/peopleai
- **Authentication:** API key-based; OAuth 2.0 for Salesforce integration via managed package.
- **SDKs/Libraries:** Community Python library `peopleai-api` on PyPI; GitHub: https://github.com/maxzheng/peopleai-api
- **Standards:** REST/JSON; Salesforce managed package for native CRM integration
- **Notes:** Primary integration is via Salesforce Managed Package (custom fields, triggers, components, reports). REST API provides activity download and reporting access. Documentation is gated behind the setup portal for enterprise customers.

---

### Klue (Competitive Intelligence)
- **Description:** Combined competitive intelligence and win/loss analysis platform; tracks competitor signals, generates battlecards, and synthesises win/loss interview themes. Launched an MCP server in 2026.
- **API Documentation:** https://apitracker.io/a/klue (gated; full docs in Klue Apps & Integrations portal)
- **MCP Server:** https://klue.com/blog/introducing-klue-mcp-server
- **Authentication:** API Key (for Content API); integration-specific keys for Gong, Salesforce, Slack connectors.
- **SDKs/Libraries:** No official SDK; MCP server enables LLM agent access without custom integration.
- **Standards:** REST/JSON; MCP (JSON-RPC 2.0 transport) for AI agent integration
- **Integrations:** Salesforce, HubSpot, Gong, Chorus, Slack, Microsoft Teams, Highspot, Seismic, Guru, Google Drive, SharePoint, ChatGPT, Microsoft Dynamics
- **Notes:** Content API allows filtering and retrieval of battlecards by competitor, tag, or date range. MCP server enables AI agents to retrieve competitive intelligence without hallucination — directly relevant for competitive context surfacing during calls.

---

## Notes

**Emerging standard: Agent-to-Agent (A2A) Protocol**
Google's Agent-to-Agent protocol (in draft as of mid-2026) is an emerging complement to MCP, designed for agent-to-agent task delegation in multi-agent systems. A deal intelligence platform that orchestrates multiple AI agents (transcription agent, scoring agent, coaching agent, win/loss synthesis agent) may benefit from A2A for inter-agent communication as the standard matures.

**Call recording consent: geographic complexity**
No single global standard governs call recording consent. A deal intelligence platform must implement jurisdiction-aware consent workflows covering at minimum: GDPR (EU/EEA), UK GDPR, CCPA/CPRA (California), Illinois BIPA, and US state two-party consent laws (CA, FL, IL, MD, PA, WA). The 2026 practitioner consensus is to default to all-party consent prompts globally and allow per-jurisdiction overrides configured by the enterprise admin.

**CRM data quality as a foundational dependency**
Deal health scoring accuracy is fundamentally constrained by CRM data quality. ISO/IEC 25012 data quality dimensions (completeness, currentness, consistency) should inform the platform's data validation layer; an open-source deal intelligence platform should surface CRM data quality warnings alongside deal scores to prevent false-confidence in scoring outputs derived from stale or incomplete opportunity records.
