# AiXPurpose Standalone — Donations & Finance — BRD Goals

> **Document ID:** AIXP-DF-GOALS  
> **Version:** 1.1 — UPDATED | 28 October 2026  
> **Status:** Approved functional scope baseline; implementation open items explicitly marked  
> **User:** Admin only (all Admins can access all native functionality)  
> **Purpose:** Enhance existing AiXPurpose for additional tenant clients; **not** a new application.  
> **Companion documents:** [Goals](Donations_Finance_BRD_Goals.md) · [Workflow](Donations_Finance_BRD_Workflow.md) · [Feature Catalogue](Donations_Finance_BRD_Feature_Catalogue.md)

**Scope:** Donations, Pledges, Receipt Management, Bank Reconciliation and shared record-source behaviour.

## Source-of-truth and classification convention

- **As-Is:** currently visible or user-confirmed working behaviour. Visible controls may be disabled or backend-incomplete.
- **Existing Jira development baseline:** configured Donations and Pledges four-card KPI changes already approved and under development; classify under baseline per Product Owner convention, never claim production readiness without QA.
- **To-Be:** additions/fixes necessary to support native AiXPurpose transaction and pledge creation and multi-tenant operation.
- **Future:** selected or discussed possibilities; not committed to the current delivery.
- **Admin-only:** all signed-in application users are Admins; no additional roles, approvals, or permissions matrix.
- **Origin:** external integrated source records are strictly read-only to Admins; native AiXPurpose records may be edited where financial state and transaction integrity permit. Source synchronisation can refresh imported records.
- **Data:** do not fabricate gateway status, receipt numbers, matched transactions, donor identifiers or campaign allocations not supported by sources.

## 1. Business problem and goals

AiXPurpose currently presents donor and finance data largely received from connected source systems. Existing Add/Create/Edit controls appear in screens but native workflows may be disabled or undefined. The standalone enhancement enables Admins of each tenant to create native financial records through the existing interface while preserving external data provenance. Financially sensitive operations must remain reliable, traceable and clearly differentiated by record origin.

**Goals:** (G-01) Retain useful existing finance UI and confirmed individual receipt/pledge interactions; (G-02) enable payment gateway-backed native donations; (G-03) support native pledge persistence and installments; (G-04) issue traceable native receipts and enable batch PDF/email; (G-05) enable statement import and source-aware financial transaction review; (G-06) enforce read-only imported records and Admin-only tenant isolation; (G-07) retain existing Jira-approved KPI catalog without modifying formulas.

## 2. Functional scope summary

| Status | Included | Explicit exclusions |
|---|---|---|
| As-Is | Existing Donations, Pledges, Receipt Management and Reconciliation pages; search, details, history and status UI; individual receipt PDF/email confirmed working; existing pledge interactions reported working for integration-based views | Native Add/Edit functionality **not** confirmed working merely because buttons exist |
| Existing Jira development baseline | Independent configurable four-card KPI behavior for Donations and Pledges per the supplied approved specification | Not represented as QA-verified production |
| To-Be | Native Add Donation via payment gateway; eligible native edits; native pledge and installment mapping; receipt identity/format; batch PDFs and batch emails; bank statement import and transaction **review only**; per-page Source dropdown; tenant/source enforcement | No current manual or automatic bank matching; no refunds implementation |
| Future Scope | DF-F01 auto matching; DF-F02 advanced matching/exceptions; DF-F03 source-aware refunds (candidate, not previously selected); DF-F04 receipt customization; DF-F05 pledge reminders; DF-F06 financial export; DF-F07 multi-donor pledges (candidate pending rules) | No automatic commitment to implement future scope |

## 3. Key business requirements

| Goal | Business requirement | Related features |
|---|---|---|
| G-01 | Preserve working interfaces, existing donor/member mapping and approved KPI catalog. | DF-001–008, DF-021 |
| G-02 | Native Add Donation initiates actual payment and records one donation only after verified gateway success. | DF-009–010 |
| G-03 | Native pledge creation and installment updates appear consistently in current UI without rewriting imported records. | DF-011 |
| G-04 | Generate numbered native receipts; enable existing batch controls for PDF and email. | DF-012–014 |
| G-05 | Import statement, show bank line counts/details and source-filtered donation/pledge transaction details; no matching in current To-Be. | DF-015–017 |
| G-06 | All Sources (default), AiXPurpose, External Sources (All), individual applicable source, with tenant isolation and strict external read-only. | DF-018–020 |
| G-07 | Follow already-approved Jira KPI specification; verify data availability and implementation separately. | DF-001, DF-007, DF-021 |

## 4. Existing approved KPI reference

The authoritative **AiXPurpose_Donations_Pledges_Configurable_KPI.docx** states: each page has exactly four selected and ordered KPI cards and its own catalog; Donations initial four cards are Total Donation Amount, Donations This Month, Average Gift Size, Total Gift Transactions; Pledges initial four cards are Total Pledges, Active Pledges, Fulfilled Pledges, Partially Fulfilled Pledges. Fields and readiness must follow that specification; transaction summaries must not be confused with a gift-by-gift ledger. No new design is proposed.

## 5. Approval boundaries and acceptance themes

- Every listed record carries origin and tenant context; imported records can be viewed but not manually altered.
- Source dropdown is in existing list Filters, scoped per page; does not change global settings or underlying records.
- For native payment collection, a successful confirmed gateway result establishes the donation; a failed/cancelled result does not.
- Receipt number issuance applies to native receipts; missing third-party receipt numbers are not invented.
- Bank Reconciliation To-Be is **import and review**; no manual match, auto match, Unmatch or match-rate promises.
- All financial operations need clear validation and error states, and may not cross tenant boundaries.

## 6. Risks and dependencies

| Risk/dependency | Handling |
|---|---|
| Integrated sources vary in transaction depth | Show only available fields; do not present iWave research as payment records |
| Payment gateway is not selected | Record provider and notification mechanism as open dependency |
| Imported receipt numbers may be missing | Preserve source values; generate native receipt numbers only for native receipts |
| Bank matching UI is visible but workflow is deferred | Do not fabricate matched/unmatched KPI outcomes |
| Native pledge paid installments may overlap donation ledgers | Define transaction linkage and reconcile approved KPI calculations |
| Batch operations may partially fail | Return per-item results and avoid duplicates |

## 7. Open decisions register

| ID | Decision required | Owner |
|---|---|---|
| OD-01 | Payment gateway provider, confirmation/webhook, settlement and failure semantics | Development / Finance |
| OD-02 | Native receipt number pattern, uniqueness boundary, legal/organisation fields | Product / Finance / Development |
| OD-03 | Bank import file format, field mapping, statement-level duplicate detection | Development |
| OD-04 | Exact eligible transaction sources including whether each connector supplies transaction-level donation/pledge data | Development / Data mapping |
| OD-05 | Batch send limits, duplicate-send treatment and recipient error recovery | Development / Product |
| OD-06 | Native pledge and installment schema, payment linkage and no double counting | Development / Finance |
| OD-07 | Refund provider and source-system workflow | Future discussion |
| OD-08 | Multi-donor pledge ownership/allocation/payment responsibility | Future discussion |
| OD-09 | Existing reconciliation matching KPI meaning and whether unsupported cards should be hidden/qualified | Product / Development |
| OD-10 | Existing disabled Create/Edit actions and QA checklist for each Donations & Finance screen | QA / Development |

## Screenshot references — original application captures

The following images are extracted without editing from **donation and finance module.docx**, in document image order. Screenshots establish interface presence, not server-side functionality.

| Figure | Source screenshot |
|---|---|
| 1 | ![Original Donations and Finance screenshot 1](screenshots/donation_finance_01.png) |
| 2 | ![Original Donations and Finance screenshot 2](screenshots/donation_finance_02.png) |
| 3 | ![Original Donations and Finance screenshot 3](screenshots/donation_finance_03.png) |
| 4 | ![Original Donations and Finance screenshot 4](screenshots/donation_finance_04.png) |
| 5 | ![Original Donations and Finance screenshot 5](screenshots/donation_finance_05.png) |
| 6 | ![Original Donations and Finance screenshot 6](screenshots/donation_finance_06.png) |
| 7 | ![Original Donations and Finance screenshot 7](screenshots/donation_finance_07.png) |
| 8 | ![Original Donations and Finance screenshot 8](screenshots/donation_finance_08.png) |
| 9 | ![Original Donations and Finance screenshot 9](screenshots/donation_finance_09.png) |
| 10 | ![Original Donations and Finance screenshot 10](screenshots/donation_finance_10.png) |



## UPDATED v1.1 — Donations and Pledges native template imports

**Change IDs DF-029–DF-031 | To-Be, Admin only.** Provide separate approved download/upload import templates on the **Donations** and **Pledges** pages. For every upload, validate the template, match against tenant-owned **AiXPurpose native records**, preview the proposed update, allow confirmed updates of eligible native fields, create eligible unmatched native records, and report invalid, unresolved, duplicate and external-only matches with row-level details. Refresh source-filtered lists, details and KPI values according to approved source-backed calculations.

**Critical finance safeguard:** A donation/pledge file import is not an online payment instruction. A file upload never initiates a gateway charge, marks payments successfully captured, issues duplicate receipts, or marks pledges paid without independently validated evidence. Externally synced financial records are not updated. Exact transaction matching keys, import file schemas and permitted financial field updates remain technical/business confirmation points. See [shared import standard](SHARED_IMPORT_MATCH_UPDATE_STANDARD_UPDATED.md).
