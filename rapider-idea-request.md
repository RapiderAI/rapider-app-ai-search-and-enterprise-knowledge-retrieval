<!-- Rapider Official App SOW & Specification | App #121: AI Search & Enterprise Knowledge Retrieval (ai-search-and-enterprise-knowledge-retrieval) | Domain: AIA -->

# #121 AI Search & Enterprise Knowledge Retrieval (`ai-search-and-enterprise-knowledge-retrieval`) — Scope of Work (SOW)

- **App Number & Name:** `#121` — AI Search & Enterprise Knowledge Retrieval
- **Proposed Rapider App Key:** `ai-search-and-enterprise-knowledge-retrieval`
- **Suite / Domain & Model Prefix:** `AIA` (`Aia*`)
- **Function Category:** 12. AI & Intelligent Automation
- **Representative Benchmark (`P1`):** Glean
- **Combined Feature Set Reference:** [../combined-features/121-ai-search-and-enterprise-knowledge-retrieval-features.md](../combined-features/121-ai-search-and-enterprise-knowledge-retrieval-features.md)

---

## 1. Executive Outcome & Target Audience

Rapider **AI Search & Enterprise Knowledge Retrieval (`ai-search-and-enterprise-knowledge-retrieval`)** serves as the workspace-wide Enterprise Graph, hybrid lexical-semantic search bar, and strict permission-trimmed Retrieval-Augmented Generation (RAG) engine across all built Rapider Suites (`CRM`, `FIN`, `HR`, `APM`, `MKT`, `SUP`, `OPS`, `MFG`, `COM`, `LRN`), `support` Knowledge Base (`SupKnowledgeArticle`), `#092` Internal Wiki, `#091` Drive (`ColDocumentRecord`), and `projectChannelMessage` threads. It eliminates information silos, repeated Slack/chat interruptions, ungrounded AI hallucinations, and unauthorized document exposure.

- **SME Fast-Path Defaults:** Zero-config automatic indexing of all native Rapider Suites + `#091` Drive + `#092` Wiki + `SUP` KB + permitted `projectChannelMessage` channels, instant `<300 ms` hybrid search with rich Suite Genius Cards, `go/` Links (`go/benefits`, `go/roadmap`), and cited conversational answers that cleanly abstain when sources do not exist.
- **Enterprise Progressive Disclosure:** Pre-retrieval RBAC + `#091` Shield (`RESTRICTED` / `aiAgentReadAllowed`) security trimming, multi-hop Deep Research sessions, SME-verified Q&A & Acronym Glossary cards with `30`/`90`/`180`-day expiration timers via Home `WorkItem`s, `<rapider-kanban>` Knowledge Gap & Policy Contradiction boards, ML synonym/boost relevance pipelines, Admin ACL Oversharing Simulators, and immutable `Decimal128` retrieval audit logs.
- **Measurable Outcomes:** Cut employee time spent hunting across apps for policies, customer context, and engineering specs by 65%, deflect 40%+ of repetitive internal IT/HR/Support tickets, and guarantee **0%** unauthorized record/snippet leakage across all search and RAG queries.
- **Top 6 Global Benchmarks Synthesized:** `P1` Glean, `P2` Microsoft Copilot Search & M365 Semantic Index, `P3` Atlassian Rovo (`Teamwork Graph`), `P4` ServiceNow AI Search & Now Assist, `P5` Coveo Relevance Cloud, and `P6` Guru Enterprise Knowledge Network.

---

## 2. In-Scope, Out-of-Scope & Suite Ownership Boundaries

### In-Scope
- Event-driven federated indexing (`AiaSearchConnectorSource`, `AiaSearchIndexDocument`) across native Rapider Suites, `SupKnowledgeArticle`, `#092` Wiki, `#091` `ColDocumentRecord` OCR versions, permitted `projectChannelMessage` streams, and governed external read-only SaaS connectors.
- Pre-query RBAC & Shield-trimmed hybrid BM25 + vector + cross-encoder search, inline-cited RAG answers, multi-hop Deep Research threads, and internal SME/Expert discovery.
- Memorable `AiaSearchGoLink` shortcuts, time-verified `AiaSearchVerifiedAnswer` & acronym cards, `<rapider-kanban>` `AiaSearchKnowledgeGap` & policy-contradiction workflows, `AiaSearchRelevanceRule` tuning, and `AiaSearchSessionLog` audit/cost ledgers.

### Out-of-Scope
- Authoring or storing canonical wiki handbooks (owned by `#092 Internal Wiki & Knowledge Management`), binary files/PDF versions (owned by `#091 Document Management & File Sharing` + Platform Files), or customer support KB articles (owned by `SUP` `support`).
- Creating shadow copies of `CrmAccount`, `FinInvoice`, `HrEmployee`, `ApmIssue`, or `SupTicket` rows (only lightweight chunk pointers and ACL hashes are indexed).
- Managing external OAuth secret vaults and bi-directional webhook ETL syncs (owned by `#044 API Integration & iPaaS`, consumed here for read-only external connectors).
- Executing autonomous destructive mutations in target suites from search bars (handoffs open pre-filled drafts or require explicit user confirmation).

### Cross-Suite Ownership & Integration Contract

| Domain / App | Owns | Integration Contract with `ai-search-and-enterprise-knowledge-retrieval` (`#121`) |
| :--- | :--- | :--- |
| **Platform Identity / RBAC** | User roles, department scopes & record ACL grants | Pre-retrieval query filter injects live caller principal & group grants **before** top-K retrieval or LLM synthesis. |
| **Platform `projectChannelMessage`** | Team chat channels, record chatter & RAG research threads | Indexes permitted channels/threads strictly by membership; persists multi-turn Deep Research conversations as `projectChannelMessage` threads. |
| **Platform Home `WorkItem`** | SME re-verification reminders, Knowledge Gap assignments & contradiction alerts | Expired `AiaSearchVerifiedAnswer`s and assigned `AiaSearchKnowledgeGap`s create and resolve canonical Home `WorkItem`s. |
| **`COL` `#091` (`documents`) & `#092` (`wiki`)** | `ColDocumentRecord`, `ColDocumentVersion`, Wiki Spaces/Pages | Honors `ColDocumentRecord.classification == RESTRICTED` and `aiAgentReadAllowed == false`; routes Knowledge Gaps into `#092` Wiki drafts. |
| **`SUP` (`support`) & `HR` (`employees`, `hrs`)** | `SupKnowledgeArticle`, `SupTicket`, `HrEmployee`, `HrCase` | Surfaces `SupKnowledgeArticle`s for deflection, resolves SME profiles from `HrEmployee`, and escalates unresolved queries to pre-filled `SupTicket`/`HrCase` drafts. |
| **`CRM` / `FIN` / `APM` / `OPS` / `MFG` / `COM` / `LRN`** | Canonical operational & financial suite records | Renders field-ACL-aware Genius Cards in search results; tracks `Decimal128` RAG token/rerank spend against `FinBudget`. |

---

## 3. Primary Web Pages & Sidebar Navigation Architecture

Every visible sidebar section strictly contains **3 or more visible items** (`displayOnMenu: true`), while deep-research views, connector inspectors, and configuration drawers set `displayOnMenu: false`.

| # | Route | Page Title | Sidebar Section | Menu Visible | Key Components & UX |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | `enterprise-search` | Unified Search & Deep Research | `Search & Knowledge` | `true` | Instant hybrid search + RAG/Deep Research mode toggle (`findSWR`/`countSWR` recent sessions), Suite/Type/Date filter pills, `#activeFilterTagsBar` with `Clear all`, Genius Cards, SME Finder, clickable session -> `research-session-detail`. |
| 2 | `verified-answers-glossary` | Verified Answers & Acronyms | `Search & Knowledge` | `true` | Table of `AiaSearchVerifiedAnswer` Q&A cards and Acronym/Codename definitions, verification expiry badges, icon+text Edit and icon-only Delete. |
| 3 | `go-links-directory` | `go/` Links & Shortcuts | `Search & Knowledge` | `true` | Searchable registry of `AiaSearchGoLink` shortcuts (`go/benefits`, `go/incident-sop`), owner `HrEmployee`, redirect counts, and `+ New go/ Link` button. |
| 4 | `knowledge-gaps-board` | Knowledge Gaps & Hygiene | `Search & Knowledge` | `true` | `<rapider-kanban>` board (`DETECTED_GAP` -> `SME_ASSIGNED` -> `DRAFTING_IN_SUITE` -> `VERIFIED_PINNED` -> `RESOLVED`) + list toggle for unanswered clusters & policy contradictions. |
| 5 | `connector-sources` | Suite & External Connectors | `Indexing & Governance` | `true` | Health table of `AiaSearchConnectorSource` native Rapider Suite indexers and external connectors, sync lag, indexed chunk counts, clickable name -> `connector-source-detail`. |
| 6 | `relevance-rules` | Synonyms & Ranking Rules | `Indexing & Governance` | `true` | Registry of `AiaSearchRelevanceRule` synonym rings, authority weights, and recency decay policies with inline ranking preview. |
| 7 | `acl-retrieval-audit` | ACL Simulator & Audit Log | `Indexing & Governance` | `true` | Role/Department ACL Oversharing Simulator (metadata envelope check) + `AiaSearchSessionLog` latency, faithfulness, deflection rate, and `Decimal128` cost telemetry. |
| 8 | `research-session-detail` | Grounded Answer & Citations | *(Hidden)* | `false` | Full `projectChannelMessage` Deep Research thread, clickable passage-highlighted citations (`[Doc v2, p.4]`), NLI faithfulness badges, 1-click Escalate to `SupTicket`/`HrCase`, and `#btnGoBack`. |
| 9 | `connector-source-detail` | Connector Sync & ACL Inspector | *(Hidden)* | `false` | Incremental CDC cursor status, ACL group sync diagnostics, Shield `RESTRICTED` exclusion counters, manual re-index trigger, and `#btnGoBack`. |
| 10 | `verified-answer-drawer` | Verified Card & Acronym Drawer | *(Hidden)* | `false` | Author/edit `AiaSearchVerifiedAnswer` markdown, cited source bindings, `verifyIntervalDays`, SME on-call phone (`<rapider-phone-input>`), and `try/catch/finally` auto-close. |
| 11 | `go-link-rule-drawer` | `go/` Link & Synonym Drawer | *(Hidden)* | `false` | Create/edit `go/{slug}` mappings or `AiaSearchRelevanceRule` synonym/boost entries with `try/catch/finally` auto-close. |

**Rapider UI Standards Enforced Across All Pages:**
- All initial data loads invoke `findSWR` and `countSWR` with zero manual `isDeleted` filter clauses, paired with defensive client-side `item.isDeleted !== true` filtering and immediate cache invalidation.
- Tables contain **zero** standalone `View` buttons in `Actions`; primary identifiers navigate directly to detail routes; `Edit` uses icon+text; `Delete` uses icon-only backed by `#rapiderConfirmOkBtn` modal confirmation and zero `window.alert`/`confirm`/`prompt`.
- `<rapider-kanban>` powers `knowledge-gaps-board`, `<rapider-phone-input>` captures SME escalation contact numbers in `verified-answer-drawer`, and primary/danger buttons enforce `#ffffff !important` white text.

---

## 4. Canonical Data Models (`Aia*`)

All models omit `projectId`, use platform UUIDs (`00000000-xxxx-xxxx-xxxx-xxxxxxxxxxxx` in seed fixtures), represent weights/scores/costs in `Decimal128`, and maintain optimistic `version` counters.

| Model Name | Key Fields & Types | Relationships & External Refs | Invariants & Lifecycle |
| :--- | :--- | :--- | :--- |
| **`AiaSearchConnectorSource`** | `id` (UUID), `connectorKey` (string, unique), `name` (string), `sourceCategory` (`RAPIDER_SUITE_NATIVE` \| `COL_DRIVE_091` \| `COL_WIKI_092` \| `SUP_KB` \| `PLATFORM_CHANNEL_MSG` \| `EXTERNAL_SAAS`), `syncMode` (`REALTIME_CDC` \| `INCREMENTAL_POLL`), `cursorToken` (string), `indexedDocCount` (int), `aclSyncHealthy` (boolean), `lastSyncedAt` (datetime), `status` (`ACTIVE` \| `PAUSED` \| `DEGRADED_ACL_HOLD`), `version` (int) | `ipaasConnectionId` -> `#044` Connection (nullable for native suites); `ownerUserId` -> Platform User | **Fail-Closed ACL Invariant:** If `aclSyncHealthy == false` (`DEGRADED_ACL_HOLD`), newly ingested external documents remain non-retrievable until ACL group sync recovers. |
| **`AiaSearchIndexDocument`** | `id` (UUID), `docPointerKey` (string, unique), `sourceSuite` (string), `sourceModel` (string), `sourceRecordId` (UUID), `title` (string), `deepLinkRoute` (string), `classification` (`PUBLIC` \| `INTERNAL` \| `CONFIDENTIAL` \| `RESTRICTED`), `aiAgentReadAllowed` (boolean), `aclPrincipalsHash` (string), `chunkCount` (int), `sourceUpdatedAt` (datetime), `lastIndexedAt` (datetime), `version` (int) | `connectorId` -> `AiaSearchConnectorSource`; `authorEmployeeId` -> `HrEmployee` (`HR`) | Stores zero shadow copies of mutable financial/HR fields; when `aiAgentReadAllowed == false` or `classification == RESTRICTED`, chunks are excluded from general RAG synthesis. |
| **`AiaSearchGoLink`** | `id` (UUID), `slug` (string, unique, lowercase `[a-z0-9-]`), `title` (string), `targetUrlOrRoute` (string), `description` (string), `redirectCount` (int), `isVerifiedCorporate` (boolean), `status` (`ACTIVE` \| `DEPRECATED`), `version` (int) | `ownerEmployeeId` -> `HrEmployee` (`HR`); `departmentId` -> `HrDepartment` (`HR`) | `slug` is workspace-unique; redirecting never bypasses target route/document RBAC checks. |
| **`AiaSearchVerifiedAnswer`** | `id` (UUID), `cardCode` (string, unique), `cardKind` (`VERIFIED_QA` \| `ACRONYM_GLOSSARY` \| `PINNED_ANNOUNCEMENT`), `termOrQuestion` (string), `triggerQueriesJson` (json), `answerMarkdown` (string), `citationsJson` (json: recordId, version, page), `verifierOnCallPhone` (string), `verifyIntervalDays` (int), `lastVerifiedAt` (datetime), `nextVerifyDueAt` (datetime), `verificationStatus` (`VERIFIED_FRESH` \| `DUE_REVERIFICATION` \| `EXPIRED_DEMOTED`), `version` (int) | `verifierEmployeeId` -> `HrEmployee` (`HR`); `reverifyWorkItemId` -> Home `WorkItem` | Cards must include `>= 1` canonical citation; when `now > nextVerifyDueAt`, status flips to `EXPIRED_DEMOTED` (removing top-pin boost) and opens a Home `WorkItem`. |
| **`AiaSearchKnowledgeGap`** | `id` (UUID), `gapNumber` (string, unique), `gapKind` (`ZERO_RESULT_CLUSTER` \| `LOW_CONFIDENCE_RAG` \| `POLICY_CONTRADICTION` \| `DUPLICATE_OVERLAP`), `topicClusterTitle` (string), `sampleAnonymizedQueriesJson` (json), `occurrenceCount` (int), `conflictingDocIdsJson` (json), `kanbanStage` (`DETECTED_GAP` \| `SME_ASSIGNED` \| `DRAFTING_IN_SUITE` \| `VERIFIED_PINNED` \| `RESOLVED`), `version` (int) | `assignedSmeEmployeeId` -> `HrEmployee` (`HR`); `remediationWorkItemId` -> Home `WorkItem`; `resolvedTargetSuite` / `resolvedTargetRecordId` -> `#092` Wiki / `SupKnowledgeArticle` / `AiaSearchVerifiedAnswer` | Cannot transition to `RESOLVED` without linking a published `#092` Wiki page, `SupKnowledgeArticle`, or `VERIFIED_FRESH` `AiaSearchVerifiedAnswer`. |
| **`AiaSearchRelevanceRule`** | `id` (UUID), `ruleCode` (string, unique), `name` (string), `ruleType` (`SYNONYM_RING` \| `SOURCE_AUTHORITY_BOOST` \| `RECENCY_DECAY` \| `QUERY_PIN_BURY`), `synonymsJson` (json), `targetSourceCategory` (string), `boostWeight` (Decimal128), `status` (`ACTIVE` \| `INACTIVE`), `version` (int) | `createdByUserId` -> Platform User | Relevance rules only reorder documents already permitted by pre-retrieval ACL trimming (can never surface unauthorized records). |
| **`AiaSearchSessionLog`** | `id` (UUID), `sessionRef` (string, unique), `queryMode` (`INSTANT_HYBRID` \| `GROUNDED_RAG` \| `DEEP_RESEARCH`), `aclPrincipalSnapshotHash` (string), `retrievedAuthorizedCount` (int), `excludedRestrictedCount` (int), `abstainedNoSource` (boolean), `faithfulnessScore` (Decimal128), `latencyMs` (int), `userFeedback` (`NONE` \| `HELPFUL` \| `NOT_HELPFUL`), `deflectedTicket` (boolean), `tokenCostAmount` (Decimal128), `currencyCode` (string), `executedAt` (datetime), `version` (int) | `userId` -> Platform User; `departmentId` -> `HrDepartment` (`HR`); `budgetId` -> `FinBudget` (`FIN`); `researchThreadId` -> `projectChannelMessage`; `escalatedTicketId` -> `SupTicket` / `HrCase` | Strictly append-only audit and cost record; raw query strings containing detected PII secrets are scrubbed prior to analytical clustering. |

---

## 5. Core End-to-End User Journeys

1. **SME Instant Permission-Trimmed RAG & Ticket Deflection:**
   - A Sales Rep asks `#/enterprise-search` *"What is our SLA credit cap for Enterprise tier and who owns security questionnaires?"* Pre-retrieval ACL trimming queries `#092` Wiki, `SupKnowledgeArticle`, and `#091` `ColDocumentRecord` (automatically excluding `RESTRICTED` board files), returning an inline-cited answer (`[1] Enterprise MSA Playbook v3, p.7`, `[2] KB-204`) plus an SME Genius Card for the Security Lead (`HrEmployee`), recording a self-service ticket deflection.
2. **Multi-Hop Customer 360 Deep Research (`CRM` + `SUP` + `APM` + `projectChannelMessage`):**
   - Before an executive renewal call, an Account Executive runs `DEEP_RESEARCH` for *"Summarize Northwind's open P1 support tickets, blocking engineering issues, and contract renewal terms"*. The engine decomposes the query across `CrmAccount`, `CrmContract`, `SupTicket`, `ApmIssue`, and `#090`/`projectChannelMessage` notes authorized for that AE, persisting a fully cited briefing in `#/research-session-detail`.
3. **Policy Contradiction & Knowledge Gap Remediation on `<rapider-kanban>`:**
   - Nightly hygiene analysis detects 38 unanswered queries for *"EU parental leave carryover"* plus a contradiction between an outdated `#091` PDF and `#092` Wiki, creating two `AiaSearchKnowledgeGap` cards on `#/knowledge-gaps-board` (`<rapider-kanban>`) and assigning Home `WorkItem`s to an HR Knowledge Steward. The Steward clicks **Create `#092` Wiki Draft**, publishes the harmonized policy, pins a `VERIFIED_FRESH` answer, and moves the card to `RESOLVED`.
4. **SME Verification Timer Expiry & On-Call Alert:**
   - A `90`-day `AiaSearchVerifiedAnswer` for `SOC2-Bridge-Letter` reaches `nextVerifyDueAt`, automatically flipping to `EXPIRED_DEMOTED`, opening a Home `WorkItem` for the Compliance SME (configured with `<rapider-phone-input>` on-call contact in `#/verified-answer-drawer`), and restoring top-pin ranking immediately once re-verified.
5. **Security Admin ACL Oversharing Simulation & `RESTRICTED` Guardrail Check:**
   - On `#/acl-retrieval-audit`, a Security Admin runs the ACL Simulator for role `Contractor - Marketing` against sensitive keywords (`"M&A"`, `"Payroll"`), verifying via metadata envelopes that zero `RESTRICTED` `#091` documents or `HrPayrollRun` records are retrievable.
6. **Search Session Click-Through, Faceted Filter Tags & Back Restoration:**
   - On `#/enterprise-search`, a Product Manager filters by `Suite: "APM"` and `Verified Only: "true"` (`#activeFilterTagsBar` shows `Suite: "APM" ✕` and `Verified Only: "true" ✕`), clicks a research session row -> `#/research-session-detail`, inspects highlighted source passages, and clicks `#btnGoBack` — restoring exact filter state and scroll offset.

---

## 6. Consolidated Feature Priorities & Work Packages

### `P0` Foundation Work Packages
- **WP-P0-1 Federated Multi-Suite, KB, Wiki, Drive & Chat Indexing (`SRCH-001`–`SRCH-003`):** Deliver `AiaSearchConnectorSource` and `AiaSearchIndexDocument` real-time CDC indexing across all Rapider Suites, `SupKnowledgeArticle`, `#092` Wiki, `#091` Drive OCR, and permitted `projectChannelMessage` threads with SME Expert Graph resolution.
- **WP-P0-2 Pre-Retrieval ACL/Shield Trimming, Hybrid Reranking & Cited RAG (`SRCH-005`–`SRCH-008`, `SRCH-015`, `SRCH-021`, `SRCH-022`):** Enforce fail-closed pre-query RBAC + `#091` `RESTRICTED` filtering, `<300 ms` BM25 + vector + cross-encoder search, inline passage-highlighted citations with hallucination abstention, Suite Genius Cards, and `#activeFilterTagsBar` faceted filtering.
- **WP-P0-3 `go/` Links, Verified Answers/Acronyms, Knowledge Gap `<rapider-kanban>` & Audit Ledger (`SRCH-011`, `SRCH-012`, `SRCH-017`, `SRCH-018`):** Ship `AiaSearchGoLink` resolution, `AiaSearchVerifiedAnswer` Q&A/glossary cards, `<rapider-kanban>` `AiaSearchKnowledgeGap` board, and append-only `Decimal128` `AiaSearchSessionLog`.

### `P1` Scale & Enterprise Governance Work Packages
- **WP-P1-1 External SaaS Connectors, Deep Research & Prompt-Injection Defense (`SRCH-004`, `SRCH-009`, `SRCH-010`):** Add external read-only connectors with fail-closed ACL group sync, multi-hop Deep Research in `projectChannelMessage`, and indirect prompt-injection sanitization.
- **WP-P1-2 SME Expiry `WorkItem`s, Relevance Rules, Deflection Handoffs & ACL Simulator (`SRCH-013`, `SRCH-014`, `SRCH-016`, `SRCH-019`, `SRCH-020`):** Deliver scheduled SME re-verification Home `WorkItem`s (`<rapider-phone-input>`), `AiaSearchRelevanceRule` synonyms/boosts, 1-click `SupTicket`/`HrCase` escalation, `#092`/`SUP` draft creation, and Admin ACL Oversharing Simulator.

### `P2` Adjacent & Grounded AI Work Packages
- **WP-P2-1 Policy Contradiction Detection, Deduplication, Thread Distillation & NLI Check (`SRCH-023`–`SRCH-028`):** Build cross-repository contradiction alerts, >88% duplicate consolidation recommendations, public `projectChannelMessage` to Verified Card distillation, role-aware `HrDepartment` onboarding digests, acronym harvesting, and `Decimal128` NLI sentence-faithfulness verification.

---

## 7. Roles, Permissions & Field-Level Governance

| Role | Permitted Actions | Restricted / Field-Level Boundaries |
| :--- | :--- | :--- |
| **Workspace Member** | Execute hybrid search, RAG, and Deep Research strictly over records permitted by their own RBAC grants; resolve `go/` Links; escalate unresolved queries to `SupTicket`/`HrCase`. | Zero visibility into unauthorized suite rows, private `projectChannelMessage` threads, or `RESTRICTED` `#091` files; cannot pin corporate Verified Answers. |
| **Subject Matter Expert (`SME`)** | Author and re-verify assigned `AiaSearchVerifiedAnswer`s and Acronym cards, resolve `AiaSearchKnowledgeGap`s via Home `WorkItem`, create team `go/` Links. | Cannot alter `AiaSearchConnectorSource` ACL mappings or view other users' search histories. |
| **Knowledge & Search Steward** | Manage workspace `go/` Links, `AiaSearchRelevanceRule` synonyms/boosts, triage `<rapider-kanban>` Knowledge Gaps and Policy Contradictions. | Cannot bypass source-suite RBAC or read private documents via admin dashboards. |
| **Security & AI Governance Admin** | Configure `AiaSearchConnectorSource`s, pause degraded ACL connectors, run metadata-only ACL Oversharing Simulations, audit `AiaSearchSessionLog` cost/telemetry (e.g., `\$1,200.00`/month budget). | Cannot disable pre-retrieval ACL trimming, override `#091` `RESTRICTED` AI blocks without a `#091` Security `WorkItem`, or mutate `AiaSearchSessionLog`. |

---

## 8. Technical APIs, Guarded Commands, Events & `requiredWorkflows`

### Guarded Command Contracts
All commands require `{ idempotencyKey: string, correlationId: string, expectedVersion: number }`:
- `aia.search.query.executeGroundedRag` — Resolves caller RBAC + `#091` Shield predicates, executes pre-trimmed hybrid retrieval + cross-encoder rerank, sanitizes prompt injections, runs NLI faithfulness check, and appends `AiaSearchSessionLog`.
- `aia.search.verifiedAnswer.verifyOrPublish` — Validates non-empty canonical citations, sets `nextVerifyDueAt`, resolves linked `reverifyWorkItemId`, and updates ranking cache.
- `aia.search.gap.dispatchDraftToSuite` — Creates a linked draft `#092` Wiki page or `SupKnowledgeArticle` and advances `AiaSearchKnowledgeGap.kanbanStage` to `DRAFTING_IN_SUITE`.
- `aia.search.connector.enforceAclHold` — Transitions `AiaSearchConnectorSource` to `DEGRADED_ACL_HOLD` automatically if external ACL sync fails.

### Domain Events (Kafka) & `requiredWorkflows`
- **Published Events:** `aia.search.gap_detected`, `aia.search.verified_answer_expired`, `aia.search.contradiction_flagged`, `aia.search.ticket_deflected`, `aia.search.connector_acl_degraded`.
- **Consumed Events:** CDC domain events across `crm.*`, `fin.*`, `hr.*`, `apm.*`, `sup.*`, `col.document.*` (including immediate ACL/classification updates), `col.wiki.*`, `platform.channel_message.created`, `platform.workitem.resolved`.
- **`requiredWorkflows` in `app.manifest.json`:** `aiaSearchRealtimeCdcAndChunkEmbedWf`, `aiaSearchVerificationExpiryMonitorWf`, `aiaSearchKnowledgeGapAndContradictionScanWf`, `aiaSearchExternalConnectorAclSyncWf`.

### Grounded Rapider AI Contract
- Every RAG and Deep Research turn strictly executes **pre-retrieval ACL & Shield trimming**, attaches clickable `[RecordID, Version/Page]` citations for every claim, abstains (`abstainedNoSource = true`) when authorized evidence is absent, strips indirect prompt-injection instructions from untrusted content, and never mutates any suite record (`SupTicket`, `HrCase`, `#092` Wiki) without explicit human confirmation.

---

## 9. Security, Privacy, Compliance & Non-Functional Requirements

- **Zero-Trust Retrieval Security (SOC 2 Type II, ISO 27001, GDPR Right-to-Erasure, HIPAA):** Pre-retrieval ACL enforcement guarantees zero existence/snippet side-channel leakage; soft-deleting or revoking access on a source `#091` document, `SupTicket`, or `projectChannelMessage` purges/updates its index entry via CDC in `<5 seconds`; query telemetry scrubs PII before Knowledge Gap clustering.
- **Exact Financial & Scoring Precision:** Token/rerank costs (e.g., `\$0.0042`/query), `boostWeight`, and `faithfulnessScore` (`0.00`–`1.00`) use `Decimal128`.
- **Latency & Scale:** Hybrid lexical+vector retrieval returns in `<300 ms` (`P95`); initial UI views load in `<200 ms` via `findSWR`/`countSWR`.
- **Accessibility & Responsive UX:** WCAG 2.2 AA compliant keyboard combobox/facet navigation, screen-reader citation announcements, `#ffffff !important` white text on primary/danger buttons, and responsive layouts across `390px`, `768px`, and `1440px`.

---

## 10. Deterministic Acceptance Criteria

1. **Sidebar 3+ Grouping Standard:** `Search & Knowledge` contains 4 visible items and `Indexing & Governance` contains 3 visible items (`>= 3` per group); `research-session-detail`, `connector-source-detail`, `verified-answer-drawer`, and `go-link-rule-drawer` set `displayOnMenu: false`.
2. **SWR Reads & Clean Soft-Delete Queries:** All page reads invoke `findSWR` / `countSWR` with zero manual `isDeleted` filter clauses and filter `item.isDeleted !== true` in client memory.
3. **Table Actions & Native Dialog Ban:** Tables omit standalone `View` buttons; primary identifiers (`sessionRef`, `cardCode`, `slug`, `connectorKey`, `ruleCode`) navigate to detail views or drawers; `Edit` uses icon+text; `Delete` uses icon-only with `#rapiderConfirmOkBtn` confirmation and zero `window.alert`/`confirm`/`prompt`.
4. **Rapider Custom Elements Adoption:** `knowledge-gaps-board` renders stages via `<rapider-kanban>` and `verified-answer-drawer` captures SME escalation phones via `<rapider-phone-input>`.
5. **Search, `#activeFilterTagsBar` & `Clear all`:** Applying Suite, Content Type, or Verification filters displays `#activeFilterTagsBar` with escaped dismissible chips and synchronous `Clear all` restoration across list and `<rapider-kanban>` views.
6. **Drawer Lifecycle & `finally` Button Reset:** Saving or cancelling `verified-answer-drawer` or `go-link-rule-drawer` closes the drawer, invalidates SWR cache, broadcasts updates, and resets button state inside a `finally` block.
7. **Pre-Retrieval ACL Zero-Leakage Invariant:** Querying for exact unique keywords inside an unauthorized `CrmContract`, private `projectChannelMessage`, or `RESTRICTED` (`aiAgentReadAllowed = false`) `#091` `ColDocumentRecord` returns zero citations, zero snippets, and `abstainedNoSource = true`.
8. **Fail-Closed Connector ACL Hold:** When an `AiaSearchConnectorSource` enters `DEGRADED_ACL_HOLD` (`aclSyncHealthy = false`), newly synced chunks are deterministically excluded from retrieval until ACL health recovers.
9. **Citation Mandatory & Verification Expiry Demotion:** Publishing an `AiaSearchVerifiedAnswer` with zero citations fails validation; passing `nextVerifyDueAt` transitions status to `EXPIRED_DEMOTED` and opens a canonical Home `WorkItem`.
10. **Knowledge Gap Resolution Gate:** Moving an `AiaSearchKnowledgeGap` to `RESOLVED` fails unless linked to a published `#092` Wiki page, `SupKnowledgeArticle`, or `VERIFIED_FRESH` `AiaSearchVerifiedAnswer`.
11. **Immutable `Decimal128` Session Audit Log:** `AiaSearchSessionLog` records exact `Decimal128` `faithfulnessScore` and `tokenCostAmount` values and rejects update/delete mutations.
12. **Click-Through Navigation & Theme Validation:** Real click-through `#/enterprise-search` -> `#/research-session-detail` -> `#btnGoBack` preserves active filter chips without `<base href>` URL traps, and all 11 routes pass dark/light `validate_theme` with `#ffffff !important` primary/danger button contrast.
13. **Prompt-Injection Sanitization & Abstention Guardrail:** Untrusted indexed passages containing embedded instruction overrides cannot alter system prompts or bypass `ColDocumentRecord.classification == RESTRICTED` exclusions.
14. **Optimistic Mutation, SWR Invalidation & 6-Pillar E2E Coverage:** Editing/deleting `go/` Links, Verified Answers, or Knowledge Gaps updates list and `<rapider-kanban>` views optimistically with SWR cache invalidation, and `e2e/expectations.json` covers all 6 mandatory E2E pillars across all 11 routes.
15. **CDC Access-Revocation Propagation:** Revoking folder ACLs or soft-deleting a `#091` `ColDocumentRecord`, `SupTicket`, or `projectChannelMessage` immediately suppresses its chunks from subsequent retrieval queries.
