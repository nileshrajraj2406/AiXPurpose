# AiXPurpose Standalone — Campaigns & Communications — BRD Goals

> **Document ID:** AIXP-CC-GOALS  
> **Version:** UPDATED 1.1 — 28 October 2026  
> **Status:** Working baseline for Product / BA / Development / QA review; open decisions are not approved features  
> **Application users:** Admin only; all Admins have access to native functionality  
> **Document set:** [Goals](Campaigns_Communications_BRD_Goals.md) · [Workflow](Campaigns_Communications_BRD_Workflow.md) · [Feature Catalogue](Campaigns_Communications_BRD_Feature_Catalogue.md)

## Scope and classification conventions

- **As-Is:** functionality confirmed by the Admin or visible in the provided references. Screenshots establish UI presence, not necessarily backend execution.
- **Standalone baseline enhancement — QA verification:** provided change requirements intended for the standalone baseline; implementation remains to be confirmed and must not be asserted as working As-Is without verification.
- **To-Be:** approved work for the standalone implementation.
- **Future candidate:** discussion only, not approved for implementation.
- **Open decision:** formula, technical handoff, provider or feature behavior not decided; do not invent details.
- **Source ownership:** all externally synchronized business records are read-only to Admin users within AiXPurpose; externally initiated API synchronisation may refresh them. Native AiXPurpose records are editable by Admins. There is currently no differentiated native role-permission model.
- **Source filter:** a per-page dropdown within the existing Filters area, not a global Settings switch. Its choices are All Sources (default), AiXPurpose, External Sources (All), plus applicable tenant-connected source applications. It changes _listing visibility_, not record origins, stored data or reporting formulas.

## 1. Executive summary

The Campaigns & Communications module allows Admins to create and manage native fundraising campaigns, view mapped campaign giving and performance, build and send communications, manage templates and configure automations. The standalone version must preserve the confirmed working email and campaign workflows while introducing source-aware safe record editing, SMS/WhatsApp delivery, basic automation execution and document upload to editable email template.

## 2. Business goals

| ID   | Goal                                 | Measurable acceptance direction                                                          |
| ---- | ------------------------------------ | ---------------------------------------------------------------------------------------- |
| G-01 | Preserve established workflows       | Native campaign creation and email Send Now/Schedule continue working without regression |
| G-02 | Make record origin unmistakable      | Admin distinguishes native editable records from external read-only records              |
| G-03 | Prevent integrated-source corruption | UI and backend reject manual integrated-record updates                                   |
| G-04 | Support channel expansion            | SMS and WhatsApp work only when tenant service configuration is valid                    |
| G-05 | Reuse existing scheduling            | Scheduled content editable before sending; sent content locked                           |
| G-06 | Activate basic drip workflows        | Approved trigger → Wait → Email/SMS execution operates under verified technical rules    |
| G-07 | Simplify template creation           | Document uploaded, converted to editable draft, reviewed and explicitly saved            |
| G-08 | Preserve data fidelity               | Campaign metrics and communication statistics use verified mapping and formulas          |

## 3. In-scope capability map

| Area                | Feature coverage                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Campaigns           | CC-001 Campaign list and four KPI cards, CC-002 Campaign search, filters and statuses, CC-003 Four-step native campaign creation, CC-004 AI Campaign Generator control and fallback, CC-005 Campaign detail tabs, CC-006 Campaign editing and source protection, CC-007 Campaign donations and donor linkage, CC-008 Campaign audience communication, CC-009 Campaign performance and calculation integrity                                                                                                                  |
| Communications      | CC-010 Communication KPIs and list, CC-011 Communication list search and filtering, CC-012 Four-step communication creation, CC-013 Email Send Now, CC-014 Email schedule and schedule management, CC-015 Communication details overview and delivery KPIs, CC-016 Recipient audience status list and export, CC-017 Message preview and code view, CC-018 Communication content editing lifecycle, CC-019 SMS operational delivery, CC-020 WhatsApp operational delivery, CC-021 Audience resolution and tenant consistency |
| Templates           | CC-022 Template list, search and type filters, CC-023 Native template creation and editing, CC-024 Variables and Use in Communication, CC-025 Document upload to editable email template                                                                                                                                                                                                                                                                                                                                     |
| Automations & Drips | CC-026 Automation listing and builder, CC-027 Basic automation execution                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Shared              | CC-028 Source dropdown and origin-aware record listing, CC-029 Tenant isolation and source ownership, CC-030 Export behavior consistency                                                                                                                                                                                                                                                                                                                                                                                     |

## 4. Feature classification register

| ID     | Area                | Feature                                          | Current classification                            |
| ------ | ------------------- | ------------------------------------------------ | ------------------------------------------------- |
| CC-001 | Campaigns           | Campaign list and four KPI cards                 | As-Is                                             |
| CC-002 | Campaigns           | Campaign search, filters and statuses            | As-Is                                             |
| CC-003 | Campaigns           | Four-step native campaign creation               | As-Is                                             |
| CC-004 | Campaigns           | AI Campaign Generator control and fallback       | Existing UI gap / decision pending                |
| CC-005 | Campaigns           | Campaign detail tabs                             | As-Is                                             |
| CC-006 | Campaigns           | Campaign editing and source protection           | As-Is business rule / To-Be enforcement           |
| CC-007 | Campaigns           | Campaign donations and donor linkage             | Standalone baseline enhancement – QA verification |
| CC-008 | Campaigns           | Campaign audience communication                  | Standalone baseline enhancement – QA verification |
| CC-009 | Campaigns           | Campaign performance and calculation integrity   | As-Is UI / open calculation decision              |
| CC-010 | Communications      | Communication KPIs and list                      | As-Is                                             |
| CC-011 | Communications      | Communication list search and filtering          | As-Is                                             |
| CC-012 | Communications      | Four-step communication creation                 | As-Is                                             |
| CC-013 | Communications      | Email Send Now                                   | As-Is confirmed functional                        |
| CC-014 | Communications      | Email schedule and schedule management           | As-Is confirmed functional                        |
| CC-015 | Communications      | Communication details overview and delivery KPIs | As-Is / QA verification                           |
| CC-016 | Communications      | Recipient audience status list and export        | As-Is / QA verification                           |
| CC-017 | Communications      | Message preview and code view                    | As-Is                                             |
| CC-018 | Communications      | Communication content editing lifecycle          | As-Is rule / QA verification                      |
| CC-019 | Communications      | SMS operational delivery                         | To-Be                                             |
| CC-020 | Communications      | WhatsApp operational delivery                    | To-Be                                             |
| CC-021 | Communications      | Audience resolution and tenant consistency       | To-Be shared rule                                 |
| CC-022 | Templates           | Template list, search and type filters           | As-Is                                             |
| CC-023 | Templates           | Native template creation and editing             | As-Is                                             |
| CC-024 | Templates           | Variables and Use in Communication               | As-Is / QA verification                           |
| CC-025 | Templates           | Document upload to editable email template       | To-Be approved                                    |
| CC-026 | Automations & Drips | Automation listing and builder                   | As-Is UI                                          |
| CC-027 | Automations & Drips | Basic automation execution                       | To-Be approved                                    |
| CC-028 | Shared              | Source dropdown and origin-aware record listing  | To-Be approved shared enhancement                 |
| CC-029 | Shared              | Tenant isolation and source ownership            | To-Be standalone rule / verification              |
| CC-030 | Shared              | Export behavior consistency                      | Standalone baseline enhancement – QA verification |

## 5. Approved non-negotiable business rules

1. AiXPurpose currently exposes **only Admin accounts**; every Admin has access to native create/edit features. Do not add unapproved role-level restrictions.
2. Records from external systems remain **read-only within AiXPurpose**, regardless of who views them; protect on both front end and backend.
3. Native campaigns and templates are editable by Admin; scheduled communications editable before dispatch; sent communications immutable.
4. The four-step campaign builder remains, but the **AI Generator itself does not work** and is not to be described as functional.
5. Email sending and enhanced scheduling management already exist; they are As-Is, not future enhancements.
6. SMS and WhatsApp operational delivery, and basic automation execution, are To-Be.
7. Document upload → editable email template draft is To-Be; AI-assisted authoring is only a future _candidate_.
8. Reportable data remain tenant-scoped. Campaign-performance formulas, provider event semantics and source joins require separate verification.
9. Source dropdown filters only eligible record-list data; All Sources is default and selecting a source never changes source ownership or automatically recalculates unrelated KPI cards.
10. Audience and giving information must use validated campaign/member/donor mappings; every donor is a member, but not every member is a donor.

## 6. Dependencies and exclusions

Dependencies: configured tenant channel services, campaign/member/gift mappings, enabled application integrations, existing communication scheduler, approved document import formats, and backend origin enforcement.

Excluded until approved: rebuilding working campaign/email flows; new role matrix; AI Campaign Generator implementation; additional analytics formulas; advanced targeting and extra automation triggers; execution-history or cross-campaign performance comparison features.

## 7. Future candidates — not approved

| Candidate ID | Name                          | Description                                                                          |
| ------------ | ----------------------------- | ------------------------------------------------------------------------------------ |
| CC-F01       | Advanced audience targeting   | Optional audience-rule expansion beyond current campaign/segment selection.          |
| CC-F03       | Advanced automation triggers  | Additional event triggers beyond the verified existing set.                          |
| CC-F07       | AI-assisted template creation | AI-assisted template authoring or conversion beyond approved non-AI document upload. |

## 8. Open decisions and verification log

| ID    | Area                                            | Pending clarification                                                                                                                   |
| ----- | ----------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| OD-01 | AI Campaign Generator disposition               | Existing UI is nonfunctional. Decide repair as To-Be, hide action, or defer; not silently approved.                                     |
| OD-02 | Campaign performance formulas                   | Audience, conversion, goal progress, donation attribution and source of goals need Product/Development approval.                        |
| OD-03 | Template document upload                        | Confirm permitted document formats, limits, attachments/assets treatment, sanitisation and conversion engine.                           |
| OD-04 | Automation execution rules                      | Confirm triggers, wait timing, error/retry/idempotency and schedule semantics.                                                          |
| OD-05 | SMS and WhatsApp integrations                   | Confirm enabled providers, supported message/template requirements, recipient consent and delivery events.                              |
| OD-06 | Template variables and communications analytics | QA validate variable mappings, audience statuses, opens, clicks and exports.                                                            |
| OD-07 | Existing standalone change requests             | Confirm release/QA status of campaign-specific donor/audience, global export and navigation enhancements.                               |
| OD-08 | Source dropdown eligible pages                  | Confirm supported record lists and handling of composite unified constituent profiles; native origin must not unlock integrated fields. |
| OD-09 | Future selection                                | CC-F01, CC-F03 and CC-F07 remain unapproved candidates pending explicit user selection.                                                 |

## 9. Traceability and release readiness

Goals G-01 to G-08 map to features CC-001 through CC-030 in the [Feature Catalogue](Campaigns_Communications_BRD_Feature_Catalogue.md) and corresponding [Workflow BRD](Campaigns_Communications_BRD_Workflow.md). Product approval establishes scope; successful QA, provider integration and data reconciliation establish production readiness.

## Source materials and screenshots

1. `campaign and comunication.docx`, supplied Campaigns & Communications module, screenshots and summary spanning 20 pages; original embedded images are preserved in [`screenshots/`](screenshots/).
2. Three additional Communication Details screenshots supplied in the conversation: [Overview](screenshots/communication_detail_01.png), [Audience](screenshots/communication_detail_02.png), [Messages](screenshots/communication_detail_03.png).
3. `AiXPurpose_changes.docx`, particularly campaign status, campaign-linked donations and communication enhancements, and cross-module export / messaging work.
4. Approved Q1–Q8 answers and subsequent corrections: Admin-only, AI Generator not working, email send/schedule functional, SMS/WhatsApp To-Be, scheduled editable but sent immutable, document-to-template To-Be, automation execution To-Be, scheduling management already As-Is.

Screenshots document reference UI, not validated runtime behavior.

## UPDATED v1.1 — Native Campaign and Template Import (approved To-Be)

> **Source evidence and classification:** The Campaigns and Communication Templates screenshots show existing creation/list/detail interfaces. They do **not** establish an operational bulk-import button, template download, or upload/matching backend. These are **To-Be additions**, integrated into the existing pages rather than a new application/module. The Communication Templates page's existing **New Template** action remains As-Is; bulk upload is a separate action to implement. The previously approved **document upload → editable email template** (CC-025) is a different single-template authoring feature, not this structured multi-record import.

| ID     | Area                    | To-Be capability                                                                                                                               | Ownership and safety                                                                                                                       |
| ------ | ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| CC-031 | Campaigns               | Download Campaign import template; populate, upload, validate, preview create/update, confirm, refresh                                         | Verified native campaign matches may be updated; external source matches are read-only and reported; no silent editing of external records |
| CC-032 | Communication Templates | Download bulk Template import template; upload multiple Email/SMS/WhatsApp template records; validate, preview create/update, confirm, refresh | Only native template matches updated; preserve content/variables and prevent overwriting source-managed templates                          |
| CC-033 | Shared Imports          | Match/update classification, row results, errors and safe refresh across Campaigns/Templates                                                   | Native-only upsert; no automatic external API writeback; tenant scope; admin-only; idempotent retries                                      |

### Required Admin import behaviour

1. Existing pages expose **Import** alongside Create Campaign / New Template, where the function is supported; select a downloadable **module-specific structured import template**. This does **not** replace the document-to-email-template authoring feature.
2. Admin uploads a completed file; system validates tenant, template/schema version, required fields, permitted Campaign or Template fields, formats, duplicate file rows and relevant references. Exact columns, file extensions, sizes and authoritative matching keys require Development confirmation.
3. Match uploaded rows against tenant-specific **native AiXPurpose records**, and separately check for externally integrated source collisions. A name/title-only similarity is **not** enough to overwrite records; ambiguous rows are flagged for review.
4. Preview each proposed **Matched Native — Update**, **New Native — Create**, **Unchanged — Skip**, **External Source Match — Read-only / Reject Update**, **Invalid / Duplicate — Reject**, or **Unresolved Reference — Review**; show before/after changes for updates.
5. Admin explicitly confirms eligible creations/updates. Commit only native mutations; retries must not create duplicate campaigns or templates; reject unsupported protected fields and cross-tenant links.
6. Show counts plus row-specific outcomes and correction guidance; refresh Campaign/Template lists, details, relevant filters and supported dashboard views without modifying source-origin metadata or silently recalculating undefined business KPIs.
7. Campaign imports must **not** invent donation transactions, campaign conversion, audience membership, sent communications or campaign success status. Template imports must **not** send messages, schedule communications, or auto-approve/activate unsupported provider templates. Importing a template is not equivalent to transmitting a communication.
8. A native AiXPurpose record created via template upload is editable by Admin; integration-synced data remains strictly read-only, both UI and backend. Where data reference links involve integrated member/donor records, linking must not mutate those external records.

**Open Development confirmations:** File formats and import column catalogs; native matching keys; whether blank values clear existing fields; permissible campaign status/goal updates; template variables/HTML validation and supported WhatsApp provider approval constraints; partial or atomic commit; bulk size/error thresholds; treatment of imported campaign audience references. Do not silently assume any unresolved policy.

### UPDATED scope traceability

- **CC-031, CC-032, CC-033:** individual Jira stories and acceptance criteria: [Feature Catalogue](Campaigns_Communications_BRD_Feature_Catalogue.md#cc-031--bulk-campaign-template-import-native-match-and-update).
- **WF-31, WF-32, WF-33:** Mermaid workflows: [Workflow](Campaigns_Communications_BRD_Workflow.md#wf-31--campaign-import-create-or-update).
- **Screenshots:** original `screenshots/` captures document existing Campaign and Template pages; import UI is To-Be and has no fabricated screenshot.
