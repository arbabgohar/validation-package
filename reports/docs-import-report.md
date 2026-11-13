<img src="../assets/sigiltrace-header.png" alt="SigilTrace — Trace every complaint to its source" width="320">

# Qaabil document import and consistency audit

Audit date: 2026-11-06

Source: `/Users/arbabgohar/Desktop/Qaabil` (read-only)

## Summary

- Controlled documents imported: 14
- Uncontrolled planning documents imported: 1
- Expected controlled documents missing: 0
- Duplicate document formats: 0
- Sensitive-data screen: no credential, email-address, phone-number, or SSN patterns detected
- Findings: 4 High, 9 Medium, 6 Low

Severity definitions used in this report:

- **High:** the package makes an assurance or traceability claim that the supplied records do not support.
- **Medium:** a controlled-record inconsistency or unresolved item could affect review, approval, or validation scope.
- **Low:** a formatting, metadata, editorial, or uncontrolled-note inconsistency does not by itself invalidate traceability.

No document wording was corrected or completed during import.

## Source inventory

| Source file | Format | Size (bytes) | Modified | Detected ID | Detected title | Disposition |
|----|----|----:|----|----|----|----|
| `.DS_Store` | macOS metadata | 6,148 | 2026-11-02 14:19:26 -0600 | — | — | Not imported |
| `ADS-001 Agent Triage Rev A DRAFT.docx` | docx | 21,386 | 2026-10-24 15:50:39 -0500 | ADS-001 | Qaabil triage agent specification v1 | `validation/ADS-001.md` |
| `BR-001 REV A.docx` | docx | 6,338 | 2026-11-06 20:28:29 -0600 | BR-001 | Qaabil backup and restore procedure | `procedures/BR-001.md` |
| `CC-001 Change Control Rev A DRAFT.docx` | docx | 20,389 | 2026-10-28 10:31:47 -0500 | CC-001 | Qaabil change control procedure | `procedures/CC-001.md` |
| `DS-001 Rev. A DRAFT.docx` | docx | 27,177 | 2026-10-24 13:39:14 -0500 | DS-001 | Qaabil design specification v1 | `validation/DS-001.md` |
| `INC-001 REV A .docx` | docx | 6,605 | 2026-11-06 20:27:30 -0600 | INC-001 | Qaabil incident management procedure | `procedures/INC-001.md` |
| `MVP.pdf` | pdf | 95,901 | 2026-10-22 00:13:53 -0500 | — | MVP scope: agent-assisted complaints and CAPA | `planning/MVP.md` |
| `P11-001 Rev A DRAFT.docx` | docx | 25,542 | 2026-10-26 18:00:18 -0500 | P11-001 | Qaabil Part 11 control matrix | `compliance/P11-001.md` |
| `RA-001 Rev A DRAFT.docx` | docx | 26,214 | 2026-10-24 12:53:44 -0500 | RA-001 | Qaabil risk assessment v1 | `validation/RA-001.md` |
| `RTM-001 Rev A Draft.docx` | docx | 30,409 | 2026-10-27 23:17:17 -0500 | TM-001 in byline; RTM-001 in file name and running header | Qaabil traceability matrix v1 | `validation/TM-001.md` |
| `SA-001 REV A DRAFT.docx` | docx | 6,699 | 2026-11-06 20:28:03 -0600 | SA-001 | Qaabil supplier assessment procedure | `procedures/SA-001.md` |
| `SRS-001 Rev. A .docx` | docx | 32,954 | 2026-10-24 12:31:32 -0500 | SRS-001 | Software requirements specification v1 platform | `validation/SRS-001.md` |
| `TC-001 Test Cases DRAFT Rev A.docx` | docx | 26,190 | 2026-10-27 23:08:40 -0500 | TC-001 | Qaabil test cases core platform | `validation/TC-001.md` |
| `TC-002 Test Cases Rev A DRAFT.docx` | docx | 23,682 | 2026-10-27 23:10:07 -0500 | TC-002 | Qaabil test cases triage agent | `validation/TC-002.md` |
| `TP-001 Rev A DRAFT.docx` | docx | 24,360 | 2026-10-26 18:15:22 -0500 | TP-001 | Qaabil test plan v1 | `validation/TP-001.md` |
| `VP-001 Validation Plan DRAFT.docx` | docx | 22,042 | 2026-10-24 14:23:16 -0500 | VP-001 | Qaabil validation plan v1 (complaints, CAPA, NCR, triage agent) | `validation/VP-001.md` |

No document was present in more than one supported format, so no alternate-format precedence decision was required.

## High findings

### H-01 — TM-001 claims 102 SRS requirements, but SRS-001 contains 89

TM-001 states that SRS-001 contains 102 requirements and that all 102 are traced. Thirteen TM-001 requirement rows are absent from SRS-001: AUD-007, EML-001 through EML-010, SEC-008, and SEC-009. SRS-001 has no requirement missing from TM-001.

### H-02 — TM-001 claims 83 core test cases, but TC-001 contains 45

TC-001 ends after the email-intake cases even though its purpose says it covers NCR, CAPA, products, rule sets, the reference library, entitlements, export, language, security, and operations. TM-001 references 38 core test cases that are not present in TC-001: T-CAPA-01 through T-CAPA-07; T-ENT-01 through T-ENT-03; T-EXP-01 through T-EXP-03; T-LIB-01; T-LNG-01; T-NCR-01 through T-NCR-04; T-OPS-01 through T-OPS-06; T-PRD-01 through T-PRD-02; T-RUL-01 through T-RUL-02; and T-SEC-01 through T-SEC-09. TC-002 contains the 19 cases claimed by TM-001.

### H-03 — TM-001 and TC-001 cite risk IDs absent from RA-001

RA-001 contains RSK-001 through RSK-024. TM-001 cites RSK-025 through RSK-028, and TC-001 cites RSK-025 through RSK-027. TM-001 nevertheless states that all 102 requirements are linked to at least one risk after RA-001 was updated.

### H-04 — P11-001 marks controls addressed using requirements absent from SRS-001

P11-001 cites AUD-007 for audit-chain controls and EML-001, EML-003, and EML-005 for inbound-email controls. Those requirements do not exist in SRS-001, although the corresponding Part 11 rows are marked addressed in design or addressed for email.

## Medium findings

### M-01 — The five-minute e-signature window is not specified in SRS-001

DS-001, P11-001, TP-001, and TC-001 specify or test a five-minute re-authentication window. SRS-001 ESG-001 requires re-authentication at signing but contains no five-minute threshold.

### M-02 — The traceability document has conflicting IDs

The source file name and running header say RTM-001. The document byline and core title identify it as TM-001. The imported path and front matter use TM-001 because the document body is the controlling source.

### M-03 — SRS-001 has no draft status

The SRS metadata table records revision A but no status, and its source file name does not say draft. Its imported front matter and register therefore record `status: unspecified`; it was not assumed to be draft.

### M-04 — SRS-001 calls the product “version A”

The SRS purpose states, “Qaabil version A,” while the remainder of the package consistently describes product version 1 and uses A as the document revision.

### M-05 — P11-001 says the change-control procedure remains to be written

P11-001 lists `[Change control procedure to be written]` and marks the control “Procedure needed,” but CC-001 is present in the same source set.

### M-06 — The v1 reportability-rule geography remains inconsistent or unresolved

ADS-001 and the MVP notes leave US-only versus EU rules open. TC-001 requires the US and one other test market, while SRS-001 PRD-002 requires evaluation for every authorized market. The controlled records do not state which rule sets ship in v1.

### M-07 — Open placeholders remain throughout the controlled package

There are 113 bracketed items across 13 controlled documents. They include names, signatures, dates, recovery targets, retention periods, the AWS region, acceptance thresholds, and other approval inputs. ADS-001 has no bracketed placeholders but has an open-questions section.

### M-08 — Six controlled documents lack a formal signature block

ADS-001, DS-001, SRS-001, TC-001, TP-001, and VP-001 do not contain the role/name/signature/date approval block found in the other controlled records.

### M-09 — The expected complaint-handling planning notes were not found

The source folder contains the uncontrolled MVP scope PDF but no separate complaint-handling notes in a supported format.

## Low findings

### L-01 — Pandoc produced HTML tables for SRS-001

Pandoc emitted HTML for the metadata table and the LNG requirement table because the Word cells are styled as Heading 2 paragraphs. Both were mechanically represented as GitHub-flavored pipe tables without changing their text. The loss of heading semantics inside those cells is a conversion limitation. All 17 source tables remain present.

### L-02 — Running headers and footers are not represented in the Markdown body

Pandoc does not import Word running headers or page-number footers. This affects ADS-001, CC-001, DS-001, P11-001, RA-001, TM-001, SRS-001, TC-001, TC-002, TP-001, and VP-001. Their IDs and titles are retained in front matter, and all body-content tokens were independently matched to the source.

### L-03 — MVP PDF pagination artifacts were omitted, and page 2 has a source-layout defect

The repeated running title and “Page n of 3” footers were not copied into `planning/MVP.md`. Visual review found the page 2 footer overlapping the final build-order line in the source PDF; the line itself remains readable and was preserved.

### L-04 — The uncontrolled MVP notes retain a stale hosting decision

The MVP notes list the hosting region and technology stack as open. Later controlled documents specify AWS in a US region, Auth0, FastAPI/Python, PostgreSQL, and a PostgreSQL-backed job queue. The planning note was not revised.

### L-05 — RA-001 contains an uncorrected spelling error

RA-001 says “teesting” in its purpose. It is retained verbatim.

### L-06 — Several core titles differ from their running-header titles

ADS-001, DS-001, and SRS-001 use different wording between the Word core-title metadata and their running headers. The front matter uses the core-title metadata exactly; the variants are not reconciled.

## Conversion verification

- DOCX conversion used Pandoc 3.13 with `-f docx -t gfm --wrap=none`.
- The source DOCX files contain no embedded media.
- Source and imported body-content tokens match for all 14 controlled documents.
- Source and imported table counts match for all 14 controlled documents.
- No HTML tables remain in the repository.
- The three-page MVP PDF was rendered and visually inspected before conversion.
- Headings, lists, bracketed placeholders, and signature blocks present in the source bodies were retained.
- The source folder was not modified.

## Referenced future records not included in this import

TR-001 (test report) and a validation summary report are referenced as records to be created after test execution. They were not listed among the expected source documents and were not present in the source folder.
