# Qaabil Markdown fix report 2

## Changes made

Each line gives the file, section, and before and after state.

- reports | Repository root | absent → folder created
- _scratch | Repository root | absent → folder created
- .gitignore | Repository root | absent → ignore .DS_Store, _scratch/ and *.swp
- .DS_Store | Repository root | present → removed
- reports/docs-import-report.md | Repository root | docs-import-report.md → reports/docs-import-report.md
- reports/docs-fix-report.md | Repository root | docs-fix-report.md → reports/docs-fix-report.md
- reports/decision-log.md | Repository root | decision-log.md → reports/decision-log.md
- _scratch/qaabil-fix-patch.md | Repository root | qaabil-fix-patch.md → _scratch/qaabil-fix-patch.md
- README.md | Folder list | no reports/ or _scratch/ entries → added requested folder notes
- README.md | Source inventory link | docs-import-report.md → reports/docs-import-report.md
- validation/SRS-001.md | Purpose | ## This document defines what Qaabil version 1 shall do, so that each function can be designed, risk-assessed, and tested against a numbered requirement. In this document, "the system" means Qaabil. → This document defines what Qaabil version 1 shall do, so that each function can be designed, risk-assessed, and tested against a numbered requirement. In this document, "the system" means Qaabil.
- validation/SRS-001.md | Purpose | ## It covers only the functions released in v1, for English-language use: accounts and access, electronic signatures, audit trail, complaints, NCRs, CAPA, reportability rule sets, email intake, the triage agent, the reference library, and the controls around them. Later phases will be specified in their own documents. → It covers only the functions released in v1, for English-language use: accounts and access, electronic signatures, audit trail, complaints, NCRs, CAPA, reportability rule sets, email intake, the triage agent, the reference library, and the controls around them. Later phases will be specified in their own documents.
- validation/SRS-001.md | Purpose | ## Version 1 supports English-language content only → Version 1 supports English-language content only
- validation/SRS-001.md | Reference library | ## Reference Library (LIB) → ## Reference library (LIB)
- validation/SRS-001.md | Requirements | EML-006: M → H
- validation/SRS-001.md | Requirements | OPS-003: M → H
- validation/SRS-001.md | Open items | - Confirm risk levels after the risk assessment → - Review the risk levels with the independent reviewer
- validation/SRS-001.md | Open items | - Define the configured urgent terms and the rule sets included in v1 → - Define the configured urgent terms. Version 1 includes the US rule set only.
- validation/DS-001.md | Scope | reportability rule sets, the triage agent, → reportability rule sets, email intake, the triage agent,
- validation/DS-001.md | Data model | The diagram shared earlier is the starting point. These are the v1 entities. → These are the v1 entities. [The architecture and data model diagrams are to be added in the next revision.]
- validation/DS-001.md | Complaint and CAPA workflow | The awareness time is set by the server at receipt and any later change needs a reason. → The server records the receipt time. The awareness date defaults to that time and, for emailed complaints, is confirmed by a person as described under Email intake. Any later change needs a reason.
- validation/DS-001.md | Requirements coverage | no insertion → inserted Front end and Availability sections
- validation/DS-001.md | Requirements coverage | CMP, NCR, CAPA: Complaint and CAPA workflow; Data model → Complaint and CAPA workflow; Email intake; Front end; Data model
- validation/DS-001.md | Requirements coverage | CMP, NCR, CAPA: CMP, NCR, CAPA → CMP, EML, NCR, CAPA
- validation/DS-001.md | Requirements coverage | OPS: Backup and recovery; Audit trail (time handling); Environments and release → Backup and recovery; Audit trail (time handling); Environments and release; Availability
- validation/RA-001.md | Findings | Three gaps need new requirements: → Three gaps were found and have been added to SRS-001 as new requirements:
- validation/RA-001.md | Findings | Two existing ratings should change. ENT-002 moves from High to Medium, since a feature leak harms the validated state but not a safety report. Every requirement tied to a High initial risk above keeps its high rating. → ENT-002 was moved from High to Medium in SRS-001, since a feature leak harms the validated state but not a safety report. After the traceability review, EML-006 and OPS-003 were raised to High because they control High initial risks (RSK-025 and RSK-013). AUD-005, LNG-001, and OPS-006 keep their lower ratings because they support a High-risk control without performing it: viewing and exporting the audit trail, the English-language interface, and the availability target.
- validation/TM-001.md | Matrix | EML-006: M → H
- validation/TM-001.md | Matrix | OPS-003: M → H
- validation/TM-001.md | Matrix | CMP-011: Tech → Front end
- validation/TM-001.md | Matrix | OPS-006: Tech → Availability
- validation/TM-001.md | Design short-name key | 13 mappings → added Front end and Availability mappings
- validation/TM-001.md | Findings | - **Thin design coverage.** CMP-011 (search and saved views) and OPS-006 (availability) map only to the technology and hosting choices, because DS-001 has no front end section and no availability section. Both should be added to DS-001. → removed
- validation/TM-001.md | Open items | - Add a front end section and an availability section to DS-001 → removed
- validation/TC-001.md | Email intake | T-EML-06: EML-006 → CMP-001, EML-006
- validation/VP-001.md | Scope | scope list ends at Export to PDF and CSV → added email intake, US reportability rules, product records and entitlements, and English-language use
- validation/VP-001.md | Scope | Out of scope for v1: document control, risk management and FMEA, monitoring, change control, supplier management, traceability integrations, and regulatory report submission. → Out of scope for v1, as product features: document control, risk management and FMEA, monitoring, change control, supplier management, traceability integrations, and regulatory report submission. Qaabil's own change control and supplier assessment follow CC-001 and SA-001.
- validation/VP-001.md | Test strategy | no insertion → added document numbers and operating procedures after the Deliverables table
- validation/VP-001.md | Release criteria | no insertion → added controlling TC-002 criteria statement after starting targets
- validation/TP-001.md | Test data | at least 100 synthetic complaints → at least 111 synthetic complaints (minimum composition in TC-002)
- validation/ADS-001.md | Validation plan for the tool itself | Test set: at least 100 de-identified or synthetic complaints → Test set: at least 111 de-identified or synthetic complaints (minimum composition in TC-002)
- validation/ADS-001.md | Workflow | Complaint arrives and the system stores it with an awareness timestamp. → Complaint arrives and the system stores it with a receipt timestamp. The awareness date defaults to that time and, for emailed complaints, a person confirms it.
- validation/ADS-001.md | Inputs | (for example US medical device reporting, EU vigilance requirements) → (version 1 includes the US rule set only; EU is a later phase)
- compliance/P11-001.md | After front matter | no level-1 heading → # Qaabil Part 11 control matrix
- compliance/P11-001.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- procedures/BR-001.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- procedures/CC-001.md | After front matter | no level-1 heading → # Qaabil change control procedure
- procedures/CC-001.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- procedures/INC-001.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- procedures/SA-001.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- validation/ADS-001.md | After front matter | no level-1 heading → # Qaabil triage agent specification v1
- validation/ADS-001.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- validation/DS-001.md | After front matter | no level-1 heading → # Qaabil design specification v1
- validation/DS-001.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- validation/DS-001.md | Data model | [The architecture and data model diagrams are to be added in the next revision.] → \[The architecture and data model diagrams are to be added in the next revision.\]
- validation/DS-001.md | Availability | [value to be set] → \[value to be set\]
- validation/RA-001.md | After front matter | no level-1 heading → # Qaabil risk assessment v1
- validation/RA-001.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- validation/SRS-001.md | After front matter | no level-1 heading → # Software requirements specification v1 platform
- validation/SRS-001.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- validation/SRS-001.md | Email intake (EML) | [period] → \[period\]
- validation/TC-001.md | After front matter | no level-1 heading → # Qaabil test cases core platform
- validation/TC-001.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- validation/TC-001.md | Security | [criteria to be set] → \[criteria to be set\]
- validation/TC-001.md | Security | [time] → \[time\]
- validation/TC-001.md | Operations | [expected load] → \[expected load\]
- validation/TC-001.md | Operations | [value] → \[value\]
- validation/TC-001.md | Operations | [thresholds] → \[thresholds\]
- validation/TC-002.md | After front matter | no level-1 heading → # Qaabil test cases triage agent
- validation/TC-002.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- validation/TM-001.md | After front matter | no level-1 heading → # Qaabil traceability matrix v1
- validation/TM-001.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- validation/TP-001.md | After front matter | no level-1 heading → # Qaabil test plan v1
- validation/TP-001.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- validation/VP-001.md | After front matter | no level-1 heading → # Qaabil validation plan v1 (complaints, CAPA, NCR, triage agent)
- validation/VP-001.md | Review and approval | no insertion → inserted Revision history with Rev A, October 2026, First draft
- reports/decision-log.md | All controlled documents | prior placeholder inventory → 168 placeholder occurrences grouped by document and section with current line numbers

- register.md | Register | no paths changed → retained as-is

## Not applied

- validation/ADS-001.md | Review and approval | line 190 | [name], [signature], [date] (signature row preserved)
- validation/ADS-001.md | Review and approval | line 191 | [name], [signature], [date] (signature row preserved)
- validation/ADS-001.md | Review and approval | line 192 | [name], [signature], [date] (signature row preserved)
- validation/DS-001.md | Review and approval | line 257 | [name], [signature], [date] (signature row preserved)
- validation/DS-001.md | Review and approval | line 258 | [name], [signature], [date] (signature row preserved)
- validation/SRS-001.md | Review and approval | line 249 | [name], [signature], [date] (signature row preserved)
- validation/SRS-001.md | Review and approval | line 250 | [name], [signature], [date] (signature row preserved)
- validation/SRS-001.md | Review and approval | line 251 | [name], [signature], [date] (signature row preserved)
- validation/TC-001.md | Review and approval | line 198 | [name], [signature], [date] (signature row preserved)
- validation/TC-001.md | Review and approval | line 199 | [name], [signature], [date] (signature row preserved)
- validation/TP-001.md | Review and approval | line 185 | [name], [signature], [date] (signature row preserved)
- validation/TP-001.md | Review and approval | line 186 | [name], [signature], [date] (signature row preserved)
- validation/TP-001.md | Review and approval | line 187 | [name], [signature], [date] (signature row preserved)
- validation/VP-001.md | Review and approval | line 178 | [name], [signature], [date] (signature row preserved)
- validation/VP-001.md | Review and approval | line 179 | [name], [signature], [date] (signature row preserved)
- validation/VP-001.md | Review and approval | line 180 | [name], [signature], [date] (signature row preserved)

## Verification

1. **PASS**. ID inventory: 102 requirements across 17 groups, 28 risks, 83 TC-001 cases and 19 TC-002 cases.
2. **PASS**. Risk ratings: EML-006 is H/H and OPS-003 is H/H (SRS/TM). Mismatches: none.
3. **PASS**. Bidirectional test coverage: 111 requirement/test links. Missing tests: none. TM-only links: none. TC-only links: none. SRS/TM ID differences: none.
4. **PASS**. Design key: 15 entries checked against DS-001. Unmatched: none.
5. **PASS**. Markdown table widths: all checked tables have consistent cell counts.
6. **PASS**. Five prohibited strings: none.
7. **PASS**. Level-2 headings ending in a period: none.
8. **PASS**. Level-1 heading and revision history across 14 controlled documents. Exceptions: none.
9. **PASS**. Root inventory and ignore rules. Extra entries: none. Missing entries: none. The existing uncontrolled planning/ document folder is counted as a document folder, and .git is repository metadata.

The RA-001 risk register and all approval table rows were checked against the original text and preserved.

## Needs a decision

- ACC-006, P11-001 11.200(a), T-ACC-06, and T-ESG-01: decide whether every signer must use multi-factor authentication.
- RA-001 and TM-001: retain the Author name, initials, and dates pending any authorized decision.
- Specify the urgent term list, urgent routing, role matrix, workflow state tables, rule set, and model provider.
- ESG-006: decide whether to require signature acknowledgement.

## Other observations

- The SRS-001 Purpose section contains no heading beginning “It is written for.” The three paragraph headings present were restored, including “It covers only the functions released in v1”.
- The moved qaabil-fix-patch.md was tracked at the root. Its new copy is under ignored _scratch/, so the working-tree change for the tracked path is a deletion.
- VP-001 lists TR-001, RN-001, VSR-001, and CVP-001. Those documents are absent from the current controlled folders and register.
- ADS-001 still mentions “awareness timestamp” in Suggested build order. The requested receipt-time replacement applied to Workflow step 1.
