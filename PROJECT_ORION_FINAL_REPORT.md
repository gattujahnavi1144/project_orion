# Project ORION: Presentation Report

## Executive summary

Project ORION's customer demo is confirmed for **24 November 2026 at 11:00 AM IST**. The dashboard and searchable ticket list are confirmed for the demonstration. Live CSV export remains conditional on resolving an open staging timeout.

The latest recorded QA result is **23 of 24 tests passing**. Authentication was fixed and verified; the remaining failure relates to CSV export. The dashboard uses **14,130 valid tickets** after 370 records without ticket IDs were excluded. Data-quality signoff and several production decisions remain open.

**Reporting basis:** This report summarizes the existing [Project ORION Delivery Brief](./PROJECT_ORION_BRIEF.md), which cites the four source documents. The `.docx` files are not currently in the workspace, so their contents and any subsequent updates could not be independently rechecked. Dates and statuses below are historical source findings, not a live project-status verification.

## 1. Delivery milestones and scope

| Item | Finding | Status |
|---|---|---|
| Customer demo | 24 November 2026, 11:00 AM IST; customer approval recorded on 18 November | Confirmed |
| Dashboard and searchable ticket list | Planned for the demo | Confirmed |
| Live CSV export | Show only if the staging timeout is fixed | Conditional |
| Production launch | Earlier notes mention 28 November, 30 November and 2 December; PMO confirmation follows QA | Unconfirmed |
| Dark mode and multi-language filters | Deferred or described as Phase 2 | Outside current demo |
| AI chatbot and sentiment widget | Not in Phase 1; sentiment widget is not approved | Excluded from Phase 1 |

**Presentation takeaway:** The demo date is agreed, but it should not be presented as an approved production launch date.

## 2. Quality and technical readiness

| Area | Finding | Status |
|---|---|---|
| QA | On 13 November, 23 of 24 tests passed; the remaining failure was CSV export | One failure recorded |
| Authentication, INC-4810 | Patch deployed on 12 November; QA verified the fix on 13 November | Fixed |
| Export service, INC-4871 | Staging export timed out after 65 seconds; last recorded update on 17 November | Open in latest source |
| Export workaround | Export in batches of 1,000 rows | Available workaround |
| Export fix | Backend owner had a target of 20 November | Completion not confirmed |

Earlier QA results showed 18 of 24 tests passing, with six authentication failures. The later written result reflects the authentication fix, but does **not** support saying all tests were green.

## 3. Data quality and risk

| Measure | Finding |
|---|---:|
| Source dataset | 14,500 rows |
| Rows missing ticket IDs | 370 |
| Valid tickets displayed | 14,130 |

The 370 invalid rows were quarantined or excluded. Risk **R-04** was rated high because missing IDs could distort the volume chart. The mitigation is to exclude the invalid records and report the excluded count; business or stakeholder approval and data-quality signoff remained pending, with a target of 22 November.

The demo requires an anonymized dataset with no real customer personally identifiable information. The source brief does not confirm whether anonymization was completed.

## 4. Commercial and production considerations

| Item | Finding | Decision status |
|---|---|---|
| CloudMetrics setup | Revised quote: ₹39,000 plus 18% GST; valid until 25 November. Onboarding takes five days after a purchase order. | Unapproved; no PO recorded |
| AuditTrail logging add-on | ₹42,000 plus 18% GST annually | Optional quote, unapproved |
| Cloud budget estimate | An estimate of 68,000 is mentioned, but its currency is unspecified | Unsupported and unapproved |
| Production audit logging | Security review may determine it is mandatory for production; it is not a customer-demo gate | Decision pending |

Quotes and estimates are **not approved expenditure**. No production date or budget should be communicated as committed based on these records.

## 5. Priority actions and decisions

| Priority | Action or decision | Responsible role | Target or dependency |
|---|---|---|---|
| 1 | Resolve and retest the export timeout; decide whether to demonstrate live CSV export | Backend and QA | Fix was targeted for 20 November; demo on 24 November |
| 2 | Complete data-quality and stakeholder signoff, including acknowledgement of the 370 excluded rows | Data owner and stakeholders | Due 22 November |
| 3 | Verify that demo data is anonymized and contains no real customer PII | Data owner / project team | Before the demo; completion not stated |
| 4 | Confirm the production launch date after QA | PMO | Date not confirmed |
| 5 | Decide whether audit logging is required for production | Security | Security review pending |
| 6 | Review vendor quotes and issue a PO if approved | Procurement / Finance | CloudMetrics quote valid until 25 November |

## 6. Suggested closing message

> The customer demo is scheduled and the core dashboard and search capabilities are in scope. Authentication has been verified, while export and data-quality signoff are the key remaining readiness items. Production timing, audit logging, and procurement approvals require separate decisions.

## Source traceability

The existing delivery brief attributes its findings to:

1. **01_Messy_Project_Notes.docx** — project notes, scope, QA and data risk.
2. **02_Email_Thread_And_Chat.docx** — demo confirmation, engineering updates, ownership and signoff.
3. **03_Vendor_And_Budget_Notes.docx** — vendor quotes, scope dependencies and production uncertainty.
4. **04_Service_Desk_Incident_Notes.docx** — incident status and dataset counts.

For the cited headings and supporting excerpts, see the [Project ORION Delivery Brief](./PROJECT_ORION_BRIEF.md). Unrelated service-desk items are excluded.
