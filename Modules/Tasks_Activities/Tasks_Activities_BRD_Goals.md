# AiXPurpose Standalone – Tasks & Activities – BRD Goals

> **Document type:** Business Requirements Document – Goals

## Document Control

| Field                | Details                                                                                                    |
| -------------------- | ---------------------------------------------------------------------------------------------------------- |
| Product              | AiXPurpose Standalone                                                                                      |
| Module               | Tasks & Activities                                                                                         |
| Document             | BRD Goals                                                                                                  |
| Version              | 1.0                                                                                                        |
| Status               | Draft for Business and Development Review                                                                  |
| Scope classification | **To-Be only**. No As-Is functionality implemented and no future enhancement scope.                        |
| Source               | Provided `TASK AND ANALYTICS MODULE.docx` screenshots and approved decisions Q1–Q4                         |
| Related documents    | Tasks_Activities_BRD_Goals.md, Tasks_Activities_BRD_Workflow.md, Tasks_Activities_BRD_Feature_Catalogue.md |

## Overview

This document defines the **proposed, not yet implemented** Tasks & Activities scope. The screenshots illustrate target interfaces only. Unspecified behaviour is listed as an open decision, not filled in as fact.

## Contents

1. Purpose and Scope
2. To-Be Business Context and Objectives
3. To-Be Functional Areas
4. Business Rules and Dependencies
5. Success Criteria
6. Open Decisions
7. Goals–Workflow–Feature Traceability
8. Screenshot References

## 1. Purpose and Scope

Implement the five UI-defined pages within Tasks & Activities. **As-Is: none implemented. Future Scope: none included.** Do not add functionality not represented in the source or confirmed by the user.

## 2. To-Be Business Context and Objectives

| Goal ID   | Business Goal                                                                                   |
| --------- | ----------------------------------------------------------------------------------------------- |
| TA-GO-001 | Record, find, edit, delete and complete tasks related to supported records.                     |
| TA-GO-002 | Enter and import donation batches with visible validation counts and approved saving outcomes.  |
| TA-GO-003 | Create events, manage attendees and send invitations by configured email.                       |
| TA-GO-004 | Register and monitor monthly giving plans and their states without assuming payment collection. |
| TA-GO-005 | Maintain the five-stage donor moves pipeline with notes and related tasks.                      |

## 3. To-Be Functional Areas

### Tasks

- **TA-F-001:** Tasks workspace, list and search
- **TA-F-002:** Create a task
- **TA-F-003:** View, edit, delete and complete task

### Batch Gift Entry

- **TA-F-004:** Batch gift entry grid
- **TA-F-005:** Batch CSV import and validation summary
- **TA-F-006:** Save batch donations

### Event Management

- **TA-F-007:** Event list, details and create event
- **TA-F-008:** Event attendees and email invitations

### Monthly Giving

- **TA-F-009:** Monthly giving plans and list
- **TA-F-010:** Monthly giving plan status and KPIs

### Moves Management

- **TA-F-011:** Moves pipeline and stage counts
- **TA-F-012:** Add donor to pipeline
- **TA-F-013:** Pipeline note
- **TA-F-014:** Pipeline follow-up task

## 4. Business Rules and Dependencies

| Rule ID   | Business Rule                                                                                                                                |
| --------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| TA-BR-001 | This module is entirely To-Be; existing screenshots are not evidence of working implementation.                                              |
| TA-BR-002 | Related task record options are limited to supplied UI and require Development confirmation.                                                 |
| TA-BR-003 | Batch donations reference eligible existing donor/member and campaign records under existing related BRDs.                                   |
| TA-BR-004 | Batch invalid-row rules and save/partial-save outcome remain unapproved.                                                                     |
| TA-BR-005 | Event invitations use the organisation's configured email communication service.                                                             |
| TA-BR-006 | Recurring giving plan creation does not establish automatic payment collection; processing requires confirmation.                            |
| TA-BR-007 | Moves pipeline uses Identified, Contacted, Engaged, Committed, Donated stages.                                                               |
| TA-BR-008 | Task creation from a Moves donor must refer to the same Tasks capability.                                                                    |
| TA-BR-009 | Access to records and actions must follow the existing AiXPurpose identity/tenant permission boundaries; no new role names are defined here. |

## 5. Success Criteria

- Each of the five pages supports the pictured core actions and saves/retrieves valid records.
- Related entities and summary KPIs reflect committed records under approved definitions.
- Event invitations use configured email and do not falsely report delivery.
- QA can distinguish approved To-Be behaviour from unresolved definitions.

## 6. Open Decisions

| ID        | Clarification required                                                           |
| --------- | -------------------------------------------------------------------------------- |
| TA-OD-001 | Exact task Related To options and supported relationships.                       |
| TA-OD-002 | Batch CSV schema, validation, invalid-row and partial-save/all-or-nothing rules. |
| TA-OD-003 | Monthly giving: payment tracking versus payment-gateway recurring collection.    |
| TA-OD-004 | Event attendee selection, invitation message and delivery confirmation.          |
| TA-OD-005 | KPI formulas for giving, event and pipeline totals, beyond UI labels.            |
| TA-OD-006 | Pipeline duplicate entries and permissible stage transition actions.             |

## 7. Goals–Workflow–Feature Traceability

| Goal      | Workflow | Features     |
| --------- | -------- | ------------ |
| TA-GO-001 | TA-WF-01 | TA-F-001–003 |
| TA-GO-002 | TA-WF-02 | TA-F-004–006 |
| TA-GO-003 | TA-WF-03 | TA-F-007–008 |
| TA-GO-004 | TA-WF-04 | TA-F-009–010 |
| TA-GO-005 | TA-WF-05 | TA-F-011–014 |

## 8. Original Screenshot References

All 16 source images are included in `screenshots/`; the relevant screens are referenced below.

- **1**: ![1](screenshots/01_source.png)
- **2**: ![2](screenshots/02_source.png)
- **3**: ![3](screenshots/03_source.png)
- **4**: ![4](screenshots/04_source.png)
- **5**: ![5](screenshots/05_source.png)
- **6**: ![6](screenshots/06_source.png)
- **7**: ![7](screenshots/07_source.png)
- **8**: ![8](screenshots/08_source.png)
- **9**: ![9](screenshots/09_source.png)
- **10**: ![10](screenshots/10_source.png)
- **11**: ![11](screenshots/11_source.png)
- **12**: ![12](screenshots/12_source.png)
- **13**: ![13](screenshots/13_source.png)
- **14**: ![14](screenshots/14_source.png)
- **15**: ![15](screenshots/15_source.png)
- **16**: ![16](screenshots/16_source.png)
