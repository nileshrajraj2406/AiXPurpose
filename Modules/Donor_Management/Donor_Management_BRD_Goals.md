# AiXPurpose Standalone — Donor Management — BRD Goals

> **Document control:** Version 1.6 — UPDATED | Status: Scope approved; technical verification open | Product: existing AiXPurpose enhanced for additional clients | Module: Donor Management | User: Admin only | Format: Markdown / GitHub

**Companion documents:** [BRD Goals](Donor_Management_BRD_Goals.md) · [BRD Workflow](Donor_Management_BRD_Workflow.md) · [BRD Feature Catalogue](Donor_Management_BRD_Feature_Catalogue.md)

**Source of truth:** `donor managemt.docx` screenshots; previously approved Members and Donors BRDs; `AiXPurpose_Configurable_KPI.docx`; `AiXPurpose_Members_Donors_Field_Mapping(1).docx`; `AiXPurpose_changes.docx`; decisions agreed in the product discussions. **This is not a rebuild of AiXPurpose.**

## Document purpose and module boundaries

One module-level BRD covering **Members, Donors, Segments, Prospecting and the shared Unified Constituent Profile**. Earlier standalone page-level Members and Donors BRDs remain supporting references; this replaces fragmented page-only scope with one coherent module view.

## Business objectives

| Goal ID | Goal                                                             | Evidence of success                                                                                                   |
| ------- | ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| DM-G01  | Preserve working Members/Donors/Segment/Prospecting UI and flows | Regression checks pass with no unjustified redesign                                                                   |
| DM-G02  | Make existing native Add/Create/Edit controls operational        | Admin creates/updates native members and linked donors                                                                |
| DM-G03  | Enforce source integrity                                         | All external member/donor values remain read-only                                                                     |
| DM-G04  | Support multi-client operation                                   | Tenant-restricted data, native configuration and segmentation                                                         |
| DM-G05  | Support practical segmentation                                   | Multiple AND/OR conditions and Admin manual include/remove actions                                                    |
| DM-G06  | Retain previously approved Jira improvements                     | KPI/column/profile/search work trace to original specifications                                                       |
| DM-G07  | Keep prospect scoring transparent                                | Preserve mapped score display; defer unapproved native score model                                                    |
| DM-G08  | Support template-based native Member/Donor/Segment imports       | Eligible imported records are editable AiXPurpose data, with validation, previews, accurate outcomes and list refresh |

## Scope classification

| Feature ID | Capability                                                              | Classification                                  |
| ---------- | ----------------------------------------------------------------------- | ----------------------------------------------- |
| DM-A01     | Module navigation and Admin access                                      | As-Is                                           |
| DM-A02     | Members listing, search and pagination                                  | As-Is                                           |
| DM-A03     | Donors listing, search and pagination                                   | As-Is                                           |
| DM-A04     | Members KPI configuration – approved Jira baseline                      | Existing Jira baseline (As-Is convention)       |
| DM-A05     | Donors KPI configuration – approved Jira baseline                       | Existing Jira baseline (As-Is convention)       |
| DM-A06     | Members advanced column selection – approved Jira baseline              | Existing Jira baseline (As-Is convention)       |
| DM-A07     | Donors advanced column selection – approved Jira baseline               | Existing Jira baseline (As-Is convention)       |
| DM-A08     | Unified Constituent Profile – approved Jira baseline                    | Existing Jira baseline (As-Is convention)       |
| DM-A09     | Global Search navigation – approved Jira baseline                       | Existing Jira baseline (As-Is convention)       |
| DM-A10     | Segment listing and type filters                                        | As-Is – working                                 |
| DM-A11     | Create and manage basic segments                                        | As-Is – working                                 |
| DM-A12     | Segment email, send communication and export                            | As-Is – working                                 |
| DM-A13     | Dynamic/static segment behaviour                                        | As-Is – verification pending                    |
| DM-A14     | Prospecting list and categories                                         | As-Is – source/logic verification pending       |
| DM-A15     | Prospect to unified profile navigation                                  | As-Is                                           |
| DM-T01     | Enable native Member creation                                           | To-Be                                           |
| DM-T02     | Enable native Member editing                                            | To-Be                                           |
| DM-T03     | Enable native Donor creation linked to Member                           | To-Be                                           |
| DM-T04     | Enable native Donor editing                                             | To-Be                                           |
| DM-T05     | Shared Source dropdown for eligible lists                               | To-Be                                           |
| DM-T06     | Backend source ownership enforcement                                    | To-Be                                           |
| DM-T07     | Multi-tenant isolation across donor management                          | To-Be shared invariant                          |
| DM-T08     | Multiple segment conditions and AND/OR                                  | To-Be                                           |
| DM-T09     | Manual include/remove members in segments                               | To-Be                                           |
| DM-T10     | Native Member template import                                           | To-Be — native template-based import            |
| DM-T11     | Native Donor template import and member resolution                      | To-Be — native template-based import            |
| DM-T12     | Segment membership template import                                      | To-Be — native template-based import            |
| DM-T13     | Import status, refresh and ownership controls                           | To-Be — native template-based import            |
| DM-T14     | Native template import matching, updates and unmatched record reporting | To-Be — UPDATED v1.6                            |
| DM-F06     | Prospect / Donor Strength scoring framework                             | Future Scope – separate dedicated specification |

## To-Be: native template import baseline and ownership

The earlier Member and Donor page-level BRDs already define import entry points, downloadable versioned Excel/CSV templates, file/row validation, duplicate and identity review, confirmation, result summaries and list/KPI refresh (Members MEM-F-025–032; Donors DON-F-032–034 and DON-F-043–050). These requirements are consolidated here, **not invented as a replacement**. The existing module-level BRD previously omitted them.

| Import target | Purpose                                                                                                         | Resulting ownership                                                                 | Key dependencies                                                                                            |
| ------------- | --------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Members       | Download approved template, validate/upload, create/update eligible native members                              | `AiXPurpose`; Admin editable                                                        | Existing identity matching, fields and duplicate resolution; never overwrite CORE source records            |
| Donors        | Download approved template, resolve each donor to a Member, validate incoming donor/giving rows                 | `AiXPurpose` for successfully committed native records; Admin editable              | No donor without member; imported historical giving does not charge gateway; prevent duplicate transactions |
| Segments      | Download target-segment membership template; upload existing-member references and intended inclusion/exclusion | Native segment membership editable, even if referenced member is externally sourced | Exact template columns and dynamic recalculation interaction pending Development                            |
| All imports   | Preview/confirm, accurate result counts, errors and refresh                                                     | Source selector treats newly imported native records as AiXPurpose                  | Tenant isolation, no writeback to integration systems, correct KPI eligibility                              |

**Open decisions:** member/donor duplicate-update precedence and partial processing remain subject to the approved earlier BRD policy/technical confirmation; the supported segment import template layout, missing-member handling and dynamic segment override precedence are not approved. Avoid silently changing these rules.

## Approved cross-module rules

- **Admin only:** currently all Admin users can access all product features. Do not introduce distinct roles or additional access-approval steps.
- **Native versus integrated:** native AiXPurpose records may be edited by Admins, while external records (CORE, DonorPerfect, iWave, other connected applications) are strictly read-only via both UI and backend.
- **Source filters:** page-local dropdown (All Sources / AiXPurpose / External Sources (All) / individual eligible apps). This must not silently affect unrelated pages or metrics.
- **Member/donor relationship:** donor maps to member; no separate iWave-only profile. A member may never have donated.
- **Segment definitions:** editable native segment configuration can reference read-only integrated members without modifying source records.
- **Tenant isolation:** records, segment definitions, exports, suggestions, and communications must be scoped to the active client.
- **Existing Jira changes:** KPI catalogs, advanced columns, unified profile and Global Search are included in As-Is baseline _by project convention_, but their delivery and QA status must be verified; avoid creating duplicate Jira stories.
- **Prospecting:** existing source-supplied scores/display retained; native donor scoring model is **Future Scope** and not assumed to exist.

## Existing Jira development baseline — not a new implementation request

- Members: nine allowed CORE-derived KPI candidates, exactly four selected at a time.
- Donors: ten approved mapped DonorPerfect/iWave KPI candidates, exactly four selected at a time.
- Distinct KPI configurations per page, with Save, Reset and four-card order.
- Members advanced columns restricted to CORE; Donors columns use CORE + mapped DonorPerfect/iWave.
- The control titled **Advanced Filter** in the field-mapping specification manages _columns_, not row criteria. The new **Source** dropdown is a separate list filter.
- The same Unified Constituent Profile opens from Members, Donors and Prospecting. Only mapped/available information should render.
- Global Search must resolve matching records and navigate to the same unified Member/Donor profile; use original approved Jira specification.

## Source-backed KPI catalogs

### Members: nine catalog options (approved reference)

| KPI (UI label)                      | Definition and calculation                                                         | Exact source mapping               | Conditions / validation                                                                   |
| ----------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------- | ----------------------------------------------------------------------------------------- |
| Total Members                       | COUNT(DISTINCT m_ID) across included CORE member records.                          | CORE: m_ID                         | Count unique IDs; exclude null IDs/duplicate synced rows. DEFAULT                         |
| New Member Records This Month       | Count unique m_ID where m_Created falls in the current calendar month.             | CORE: m_ID, m_Created              | Record-created metric, NOT confirmed membership joins. DEFAULT                            |
| New Member Records This Year        | Count unique m_ID created since Jan 1 of the current year.                         | CORE: m_ID, m_Created              | Record-created metric. Clearly label as new records.                                      |
| Members With Email                  | Count distinct m_ID with usable nonblank mi_Email.                                 | CORE: m_ID, mi_Email               | Ignore empty, null, NONE, and whitespace; no validation/verification claim. DEFAULT       |
| Members With Phone                  | Count distinct m_ID with usable nonblank mi_PrimaryPhone.                          | CORE: m_ID, mi_PrimaryPhone        | Phone present, NOT verified. DEFAULT                                                      |
| Membership-Eligible Members         | Count distinct m_ID where mt_CountsForMembership = Yes (normalize boolean/string). | CORE: m_ID, mt_CountsForMembership | Not an Active Members metric.                                                             |
| Members in Selected Branch          | Count distinct m_ID with u_HomeBranch = administrator-selected existing branch.    | CORE: m_ID, u_HomeBranch           | Requires branch selection parameter; do not create a separate static KPI for each branch. |
| Members in Selected Membership Type | Count distinct m_ID with mt_Name = selected existing membership type.              | CORE: m_ID, mt_Name                | Requires type selection parameter.                                                        |
| Members in Selected State           | Count distinct m_ID where normalized mi_HomeState matches selected state.          | CORE: m_ID, mi_HomeState           | Requires state parameter; distinguish blank from unknown.                                 |

### Donors: ten catalog options (approved reference)

| KPI (UI label)                         | Definition and calculation                                                                                                | Exact source mapping                                                    | Conditions / validation                                                                       |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Total Donors                           | Count DISTINCT mapped member IDs with genuine DonorPerfect giving relationship (gifts > 0 or validated gift_total > 0).   | CORE: m_ID; DonorPerfect: donor_id, gifts, gift_total; existing mapping | DEFAULT. Never count duplicate source rows; must be subset of members.                        |
| Active Donors (Trailing 12 Months)     | Count distinct donors whose last_contrib_date is on/after the beginning of the prior 12-month window, through as-of date. | DonorPerfect: donor_id, last_contrib_date; CORE mapping                 | DEFAULT. Proposed business definition, not native donor status. Exclude future/invalid dates. |
| Inactive Donors (No Gift in 12 Months) | Count donors with a known last_contrib_date older than 12 months.                                                         | DonorPerfect: donor_id, last_contrib_date                               | Unknown dates separately categorized, not assumed inactive.                                   |
| Lifetime Giving                        | SUM(gift_total) across distinct linked donors, with canonical source totals.                                              | DonorPerfect: donor_id, gift_total                                      | DEFAULT. Currency unit and refund/adjustment rules should be confirmed.                       |
| Total Gifts                            | SUM(gifts) across distinct linked donors.                                                                                 | DonorPerfect: donor_id, gifts                                           | Count number of gifts, not number of donors.                                                  |
| Average Gift Amount                    | SUM(gift_total) / SUM(gifts) over donor population where denominator > 0.                                                 | DonorPerfect: gift_total, gifts                                         | Weighted across gifts; do NOT AVG(avg_amt). Display N/A when no gifts.                        |
| Donors Who Gave This Calendar Year     | COUNT DISTINCT donor_id where cytd > 0 for currently active reporting calendar.                                           | DonorPerfect: donor_id, cytd                                            | Requires confirmation the cytd field is refreshed for current year.                           |
| Repeat Donors                          | COUNT DISTINCT donor_id where gifts > 1.                                                                                  | DonorPerfect: donor_id, gifts                                           | Two or more gifts historically; not year-over-year retention.                                 |
| High-Capacity Donors                   | Count donors with mapped iWave capacityValue >= admin-set currency threshold.                                             | iWave: mostRecentScore.scoreDetails.capacityValue; existing mapping     | Optional enrichment KPI. Requires threshold, currency harmonization and score freshness.      |
| Donors With iWave Score                | Count distinct donors with a valid mapped mostRecentScore.score.                                                          | iWave: mostRecentScore.score; CORE/DP mapping                           | Counts coverage, not predicted donation likelihood.                                           |

## Dependencies and decisions still open

| ID       | Open decision / verification                                                       | Treatment                                                     |
| -------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| DM-OD-01 | Dynamic segment refresh and update schedule                                        | Verify with Development; retain observed behavior             |
| DM-OD-02 | Static segment actual membership semantics                                         | QA verification, no presumed algorithm                        |
| DM-OD-03 | Manual additions/exclusions versus dynamic recomputation precedence                | Explicitly OPEN; not assumed persistent or overwritten        |
| DM-OD-04 | Prospect list eligibility, source linkage and category thresholds                  | Development verification; no scoring changes now              |
| DM-OD-05 | iWave propensity/affinity/capacity source fields, quality and freshness            | Source-backed only; new scoring deferred                      |
| DM-OD-06 | Existing Jira deployment and QA status for KPI, columns, profile and Global Search | Track against current tickets                                 |
| DM-OD-07 | Native Donor creation qualification and de-duplication                             | Development confirmation; must link to Member                 |
| DM-OD-08 | Supported segment AND/OR fields, operator matrix and possible nested groups        | Confirm feasible initial builder; do not assume nested groups |

## Screenshots — original application references

![Original Donor Management screen 01](screenshots/donor_management_01.png)
![Original Donor Management screen 02](screenshots/donor_management_02.png)
![Original Donor Management screen 03](screenshots/donor_management_03.png)
![Original Donor Management screen 04](screenshots/donor_management_04.png)
![Original Donor Management screen 05](screenshots/donor_management_05.png)
![Original Donor Management screen 06](screenshots/donor_management_06.png)
![Original Donor Management screen 07](screenshots/donor_management_07.png)

## Traceability

All feature IDs above map to same-named sections in [Feature Catalogue](Donor_Management_BRD_Feature_Catalogue.md) and corresponding Mermaid flows in [Workflow](Donor_Management_BRD_Workflow.md). The original KPI and mapping documents govern exact field semantics; any mismatches require Product clarification, not silent reinterpretation.

## UPDATED v1.6 — Native import match-and-update rule

**Change ID: DM-IMP-UPD-01 | Classification: To-Be | Actor: Admin.** This amendment expands DM-T10–DM-T13. Admins upload approved Member, Donor and Segment templates and the application checks the uploaded rows against the tenant's **existing AiXPurpose records**. Matched, unambiguously identified native records can be **updated** after preview/confirmation; eligible unmatched independent records are **created** as new native entries, while unresolved mandatory links, ambiguous matches, invalid rows and collisions with read-only integration records must be **reported with reasons**. Changes immediately refresh eligible lists, unified profiles, segments and supported KPIs. Importing never updates a third-party source record.

For Segment templates, an imported membership link to an externally synchronized Member is allowed without editing the source member profile. Whether a template also creates Segment definitions rather than only memberships is an open template-type decision. Existing Dynamic Segment override precedence remains OPEN for Development confirmation. See [shared import standard](SHARED_IMPORT_MATCH_UPDATE_STANDARD_UPDATED.md) and Feature Catalogue **DM-T14**.
