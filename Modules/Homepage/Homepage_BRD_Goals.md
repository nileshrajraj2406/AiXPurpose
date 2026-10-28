# BRD Goals — Homepage / Analytics Command Center

**Scope:** Existing page enhancement, not a new application. **User:** Admin only. **Baseline:** approved 28 October 2026. **Status:** Requirements for review, not evidence of QA completion.

## 1. Objective
Retain the single existing Homepage dashboard and provide simple, unambiguous Top Donors metric selection and source filtering without changing the existing charts or introducing new modules.

## 2. As-Is / existing Jira development baseline
| ID | Function | Classification / note |
|---|---|---|
| HP-AS-01 | Existing four-card dashboard and overall layout | As-Is UI; retain |
| HP-AS-02 | Date, Campaign and Location selectors | As-Is; retain; verify effectiveness |
| HP-AS-03 | Solicitation Analysis | As-Is; retain |
| HP-AS-04 | General Ledger Analysis and Donation Trend | As-Is; retain |
| HP-AS-05 | Donor Segments and Conversion Funnel | As-Is; retain; conversion formula pending verification |
| HP-AS-06 | Top Donors table, search, row actions and member/donor profile navigation | As-Is; retain |
| HP-AS-07 | AI Insights cards/actions | Existing UI **not working**; not an operational As-Is capability |
| HP-JIRA-01 | Exactly four configurable KPI cards, one selection per card, from approved **12-option** catalog; reorder, Save/Apply and Reset | Previously raised in Jira; **implementation status not assumed**; independent of other pages |
| HP-JIRA-02 | Functional Global Search | Existing Jira development baseline; not new Homepage feature |
| HP-JIRA-03 | Remove Homepage-only Export CSV and Export PDF buttons | Existing Jira development baseline; preserve exports elsewhere |

**KPI authority:** `AiXPurpose_Homepage_Configurable_KPI.docx` governs catalog, default selection, validation prerequisites and filter-specific metric behaviour. Do not substitute the visual screenshot card labels for the catalog. The source spec warns that Active Users cannot be treated as verified activity merely because it matches Total Members.

## 3. Approved To-Be
| ID | Requirement | Acceptance outcome |
|---|---|---|
| HP-TB-01 | **Single-select Top Donors metric view** | Admin selects exactly one of **Top Donors / Total Giving**, **Largest Gift**, **Last Gift (most recent gift date)** or **iWave Score**. Selection changes displayed ranked list and selected metric; no multi-select or simultaneous competing ranking. Verified score only; unavailable values are not invented. |
| HP-TB-02 | **Top Donors-only Source dropdown** | All Sources (default), AiXPurpose, External Sources (All), and each configured eligible connected application. The dropdown affects **Top Donors only**; it must not silently change Homepage KPIs, charts or global Date/Campaign/Location filters. |

**Default metric:** Top Donors / Total Giving, subject to established eligible giving data. Rank most recent first for Last Gift; higher values first for amount/score, and do not substitute score estimates for giving. Eligible source mappings and ties should be verified with Development.

## 4. Future Scope
**HP-F01 — Operational AI Insights:** Existing cards are nonfunctional. AI generation logic, live-data grounding, output/action outcomes and activation require separate future approval. Do not describe the feature as working or approved for immediate implementation.

## 5. Shared business rules
1. Only Admin users currently access AiXPurpose; no additional role matrix.
2. All external integration records remain read-only; native AiXPurpose records are editable in their owning modules. Homepage rankings do not edit records.
3. Source provenance must remain clear when member/donor information is unified; select an eligible donor source without creating duplicate unified profiles.
4. The Top Donors Source selection has a **local-only scope**; no Homepage-wide source dropdown.
5. Existing page layout, search, dashboard analysis and established Jira KPI changes are preserved.
6. Tenant-specific results only; user-provided/verified iWave scores only.

## 6. Open QA / Development decisions
| Ref | Outstanding verification |
|---|---|
| HP-OD-01 | Existing missing/empty/error states; do not add an unapproved To-Be empty-state feature. |
| HP-OD-02 | Conversion Funnel, growth badges and other displayed analytics: source lineage and calculations. |
| HP-OD-03 | Precise eligible fields and deduplication semantics for Top Donors by selected source; iWave score absence/freshness. |
| HP-OD-04 | Jira rollout and QA state for KPI customisation, Global Search, Homepage export-button removal. |
| HP-OD-05 | Handling of ties and last-gift dates absent from available mapped source records. |

## 7. Traceability
HP-TB-01 → HP-WF-03 → HP-FC-10; HP-TB-02 → HP-WF-04 → HP-FC-11; HP-F01 → HP-WF-05 → HP-FC-12.

## Source screenshots

- ![Homepage upper dashboard, filters, KPIs, Solicitation Analysis and AI Insights](screenshots/homepage_source_01.png)
- ![Homepage charts: General Ledger, Donation Trend, Donor Segments and Conversion Funnel](screenshots/homepage_source_02.png)
- ![Homepage Top Donors section](screenshots/homepage_source_03.png)
- ![Homepage Top Donors table rows](screenshots/homepage_source_04.png)

> The images above are extracted unchanged from `homepage.docx`; no proposed UI mockups are presented as original screenshots.
