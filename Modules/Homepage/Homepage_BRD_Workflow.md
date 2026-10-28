# BRD Workflow — Homepage / Analytics Command Center

**Scope:** Existing page enhancement, not a new application. **User:** Admin only. **Baseline:** approved 28 October 2026. **Status:** Requirements for review, not evidence of QA completion.

## Overview
The page is retained. Mermaid diagrams below are native code for GitHub rendering; they describe approved UI behaviour, not implementation evidence.

### HP-WF-01 — Open Homepage and use existing dashboard filters (As-Is)
```mermaid
flowchart TD
 A[Admin opens Homepage] --> B[Load tenant dashboard]
 B --> C[Show KPI cards and existing analyses]
 C --> D{Date, Campaign or Location changed?}
 D -->|No| E[Keep current dashboard view]
 D -->|Yes| F[Apply supported existing filter behaviour]
 F --> G[Refresh applicable dashboard sections]
```
**Notes:** Keep Solicitation, General Ledger, Donation Trend, Donor Segments, Conversion Funnel, Top Donors and AI Insights UI; do not claim AI Insights works. Metric eligibility and blank states remain verification items.

### HP-WF-02 — Configurable KPI cards (existing Jira baseline)
```mermaid
flowchart TD
 A[Admin opens Customize KPIs] --> B[Show approved 12-option catalog]
 B --> C[Select exactly four distinct KPI options]
 C --> D[Reorder the four cards]
 D --> E{Save or Reset?}
 E -->|Save| F[Apply saved card selection and order]
 E -->|Reset| G[Restore approved default four]
 F --> H[Show dashboard with four cards]
 G --> H
```
**Notes:** Reuse `AiXPurpose_Homepage_Configurable_KPI.docx`; this is previously raised Jira work. Data availability and KPI filter scope remain governed by that specification.

### HP-WF-03 — Top Donors single-select metric (HP-TB-01)
```mermaid
flowchart TD
 A[Admin views Top Donors] --> B[Default Top Donors Total Giving]
 B --> C[Admin opens Select Metric]
 C --> D{Choose exactly one metric}
 D -->|Total Giving| E[Rank by verified lifetime total giving]
 D -->|Largest Gift| F[Rank by verified largest single gift]
 D -->|Last Gift| G[Rank by most recent gift date]
 D -->|iWave Score| H[Rank by mapped available iWave score]
 E --> I[Replace Top Donors list with selected view]
 F --> I
 G --> I
 H --> I
 I --> J[Keep existing search and row navigation]
```
**Notes:** Only one active choice at any moment; do not combine multiple ranking metrics. Missing score/date data is not fabricated.

### HP-WF-04 — Top Donors source filter (HP-TB-02)
```mermaid
flowchart TD
 A[Admin opens Source inside Top Donors] --> B{Select a source}
 B -->|All Sources| C[Eligible records from all tenant sources]
 B -->|AiXPurpose| D[Native AiXPurpose records only]
 B -->|External Sources All| E[External synced records only]
 B -->|Specific application| F[Records mapped to selected configured source]
 C --> G[Update Top Donors list only]
 D --> G
 E --> G
 F --> G
 G --> H[Retain selected single ranking metric]
 H --> I[Do not modify Homepage KPI cards or other charts]
```
**Notes:** Source options only from configured eligible applications. Each source retains its provenance; this is a display filter, not a record edit or integration disconnect.

### HP-WF-05 — AI Insights future candidate (HP-F01)
```mermaid
flowchart TD
 A[Existing AI Insights UI nonfunctional] --> B[Future Product approval]
 B --> C[Define supported data, generation and actions]
 C --> D[Define validation and QA criteria]
 D --> E[Future implementation only if approved]
```
**Notes:** Conceptual, not a To-Be commitment. Existing UI remains visible per As-Is screenshot.

## Source screenshots

- ![Homepage upper dashboard, filters, KPIs, Solicitation Analysis and AI Insights](screenshots/homepage_source_01.png)
- ![Homepage charts: General Ledger, Donation Trend, Donor Segments and Conversion Funnel](screenshots/homepage_source_02.png)
- ![Homepage Top Donors section](screenshots/homepage_source_03.png)
- ![Homepage Top Donors table rows](screenshots/homepage_source_04.png)

> The images above are extracted unchanged from `homepage.docx`; no proposed UI mockups are presented as original screenshots.
