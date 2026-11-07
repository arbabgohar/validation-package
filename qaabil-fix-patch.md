# Qaabil fix patch (instructions and exact text for Codex)

This file is a working instruction file, not a controlled document. Do not import it into the validation package and do not commit it. Apply each item exactly. If the "old" text of a replacement is not found exactly, do not guess: skip the item and list it under "Not applied" in your report.

Document IDs: the traceability matrix is TM-001. The old desktop file name RTM-001 is a legacy name only.

---

## A. validation/SRS-001.md

A1. Front matter: set `status: draft`. Make sure the first lines of the body read, in this form: `SRS-001, Rev A (draft), October 2026.` If the byline is absent or different, add or correct it without touching other text.

A2. Purpose section: if it says "Qaabil version A", change it to "Qaabil version 1".

A3. Purpose section, the sentence listing what v1 covers: it must read "...CAPA, reportability rule sets, email intake, the triage agent, ..." and must say "for English-language use". Insert only the missing words.

A4. ESG-001 requirement text, replace with:

> The system shall require the signer to re-authenticate immediately before signing, and the re-authentication shall remain valid for no more than 5 minutes.

A5. CMP-002 requirement text, replace with:

> The system shall record the receipt date and time automatically. The awareness date shall default to that time and, for emailed complaints, shall be confirmed by a person under EML-008. Any change shall require a reason and shall be audited.

A6. Insert this whole section immediately before the heading "Nonconformance reports (NCR)":

```
## Email intake (EML)

| ID | Requirement | R | V |
|---|---|---|---|
| EML-001 | The system shall give each company a unique inbound email address containing a random token that cannot be guessed, and shall let an administrator replace it. | M | T |
| EML-002 | The system shall store every accepted email and its attachments unchanged, and shall never alter or delete the stored original. | H | T |
| EML-003 | The system shall scan received attachments for malicious content and shall quarantine any that fail. | M | T |
| EML-004 | The system shall enforce a size limit and rate limits on inbound email. | L | T |
| EML-005 | The system shall ignore an email it has already received, identified by its message identifier, and shall record the duplicate. | L | T |
| EML-006 | The system shall create a draft complaint in an inbox from each accepted email, holding the sender, subject, body, attachments, and the original date from the message headers. | M | T |
| EML-007 | The system shall run the language check, the urgent-term check, and the triage agent on a draft complaint without waiting for a person. | H | T |
| EML-008 | The system shall record both the time of receipt and the original date from the headers, and shall require a person to confirm the awareness date, with a reason if it differs from the time of receipt. | H | T |
| EML-009 | A person shall confirm or discard each draft with a reason. Discards shall be audited and the draft preserved. | H | T |
| EML-010 | The system shall show the age of each unconfirmed draft and shall alert administrators when a draft stays unconfirmed longer than [period]. | H | T |
```

A7. Audit trail table: add this row after AUD-006:

`| AUD-007 | The system shall link audit entries in a cryptographic chain for each company and shall verify the chain on a schedule, alerting an administrator and the vendor if it breaks. | H | T |`

A8. Security table: add these rows after SEC-007:

`| SEC-008 | The system shall enforce a credential policy through the identity provider, including minimum strength, periodic revision where a company configures it, and prompt deactivation of lost or compromised credentials. | M | T |`
`| SEC-009 | The system shall alert company administrators and the vendor when repeated failed sign-ins suggest attempted unauthorized use. | M | T |`

A9. Add the approval block (section E) with roles Author, Independent reviewer, Regulatory advisor.

Expected result: 102 requirements in total (ACC 8, ACS 5, ESG 5, AUD 7, CMP 11, EML 10, NCR 4, CAPA 8, PRD 2, RUL 2, AGT 14, LIB 3, ENT 3, EXP 3, LNG 2, SEC 9, OPS 6).

---

## B. validation/RA-001.md

B1. Spelling: change "teesting" to "testing".

B2. Set the Controls cell of every risk to exactly the following (keep all other cells as they are):

| Risk | Controls |
|---|---|
| RSK-001 | CMP-010, AGT-002, AGT-005, AGT-006, AGT-013 |
| RSK-002 | AGT-005, AGT-006, CMP-006, AGT-013 |
| RSK-003 | AGT-003, AGT-004, AGT-012, AGT-013 |
| RSK-004 | AGT-001, AGT-007, AGT-011 |
| RSK-005 | AGT-009, AGT-013, AUD-006, change control in the validation plan |
| RSK-006 | AGT-010, SEC-001, supplier assessment in the validation plan |
| RSK-007 | AGT-008, LIB-002, LIB-003 |
| RSK-008 | ACC-001, ACS-001, ACS-002, ACS-003 |
| RSK-009 | ACS-005, AUD-001 |
| RSK-010 | ACC-006, ACC-008, ESG-001 |
| RSK-011 | ESG-002, ESG-003, ESG-004, AUD-001, AUD-003 |
| RSK-012 | AUD-001, AUD-002, AUD-003, AUD-004, AUD-005, AUD-007 |
| RSK-013 | CMP-002, CMP-007, OPS-003, RUL-001 |
| RSK-014 | CMP-005, CAPA-006, CAPA-007 |
| RSK-015 | CAPA-005, CAPA-007 |
| RSK-016 | AUD-004, EML-002, OPS-001, OPS-002, OPS-005, OPS-006 |
| RSK-017 | ENT-001, ENT-002, ENT-003 |
| RSK-018 | OPS-003, CMP-002 |
| RSK-019 | ACC-007, ACS-004, AUD-001 |
| RSK-020 | EXP-001, EXP-003, ESG-005 |
| RSK-021 | ACC-002, ACC-003, ACC-004, ACC-005 |
| RSK-022 | SEC-001 to SEC-009 |
| RSK-023 | CMP-007, PRD-002, RUL-001, RUL-002 |
| RSK-024 | CMP-006, CMP-010, AGT-005, AGT-014, LNG-001, LNG-002 |
| RSK-025 | EML-006, EML-008, CMP-002, CMP-007 |
| RSK-026 | EML-007, EML-009, EML-010, CMP-010 |
| RSK-027 | EML-001, EML-003, EML-004, EML-005 |
| RSK-028 | CMP-001, CMP-003, CMP-004, CMP-008, CMP-009, CMP-011, NCR-001 to NCR-004, CAPA-001 to CAPA-004, CAPA-008, PRD-001, LIB-001, EXP-002, OPS-004 |

B3. If the risk register lacks them, append these rows at the end of the register table (columns: ID, failure mode and effect, S, O, D, Initial, Controls, Residual):

```
| RSK-025 | The awareness date of an emailed complaint is set to the forwarding time instead of the original receipt, causing a late report | 5 | 3 | 3 | High (45) | EML-006, EML-008, CMP-002, CMP-007 | Medium (20) |
| RSK-026 | Draft complaints sit unconfirmed in the inbox while the reporting clock runs | 5 | 3 | 3 | High (45) | EML-007, EML-009, EML-010, CMP-010 | Medium (20) |
| RSK-027 | A malicious or oversized email or attachment reaches the system through the inbound address | 4 | 3 | 3 | Medium (36) | EML-001, EML-003, EML-004, EML-005 | Low (8) |
| RSK-028 | A core record-keeping function (numbering, required fields, links, search, export, version display) behaves incorrectly, producing incomplete or inaccurate quality records | 3 | 3 | 3 | Medium (27) | CMP-001, CMP-003, CMP-004, CMP-008, CMP-009, CMP-011, NCR-001 to NCR-004, CAPA-001 to CAPA-004, CAPA-008, PRD-001, LIB-001, EXP-002, OPS-004 | Low (12) |
```

B4. The paragraph after the risk register (it begins "Residual scores assume the controls work as specified") must end with this sentence: "Three risks (RSK-025 to RSK-027) were added when email intake was designed, together with requirements EML-001 to EML-010, SEC-008, and SEC-009. RSK-028 and several added control links were created while building the traceability matrix (TM-001), so that every requirement traces to at least one risk."

B5. Open items: remove these two bullets if present: "Add RUL-001, RUL-002, and AGT-014 to the requirements specification and update ENT-002" and "Decide which languages the agent and keyword check support in v1".

B6. Add the approval block (section E) only if the document has none. Roles: Author, Independent reviewer, Regulatory advisor.

---

## C. validation/TC-001.md

C1. In "Common preconditions", change "Rule sets loaded for the US and one other test market, with known deadlines" to "Rule sets loaded for the US and one synthetic second test market, used only to test multi-market logic, with known deadlines".

C2. The imported file ends after the Email intake table. Append everything between the lines START and END below, directly after that table. It already contains the review and approval table and the open items, so do not add section E to this file. If the file already contains any of these headings, stop and report instead of duplicating.

START

## Nonconformance reports

| ID | Req | Risk | Steps | Expected result |
|---|---|---|---|---|
| T-NCR-01 | NCR-001 | RSK-014 | Create an NCR with every field, then with required fields missing. | Valid data is saved and missing data is refused. |
| T-NCR-02 | NCR-002 | RSK-014 | Record a disposition without a rationale or signature, then with both. | The first is refused and the second is saved with an approval signature. |
| T-NCR-03 | NCR-003 | RSK-014 | Link an NCR to a complaint and a CAPA. | Links show from both sides. |
| T-NCR-04 | NCR-004 | RSK-014 | Create NCRs from two users at once and step through each status. | Numbers are unique, and invalid status changes are refused. |

## CAPA

| ID | Req | Risk | Steps | Expected result |
|---|---|---|---|---|
| T-CAPA-01 | CAPA-001, CAPA-002 | RSK-015 | Create a CAPA with problem statement, source, scope, root cause, and method, then with items missing. | Complete CAPAs are saved and incomplete ones are refused where required. |
| T-CAPA-02 | CAPA-003 | RSK-015 | Add corrective and preventive actions with owners, due dates, and statuses. | Actions are saved, and the two types are distinguishable. |
| T-CAPA-03 | CAPA-004 | RSK-015 | Use a controlled clock to move to before, on, and after an action's due date. | Upcoming and overdue notices go to the owner at the right times. |
| T-CAPA-04 | CAPA-005 | RSK-015 | Try to close without effectiveness criteria, then with criteria but no result, then with both. | Closure is blocked until criteria are defined and a result is recorded. |
| T-CAPA-05 | CAPA-006 | RSK-014 | Try to close a CAPA with one action open, then with all actions complete. | Closure is blocked while any action is open. |
| T-CAPA-06 | CAPA-007 | RSK-014, RSK-015 | Try to close as a contributor, then as an approver with a signature. | Only an approver with a signature can close. |
| T-CAPA-07 | CAPA-008 | RSK-014 | Link a CAPA to a complaint and an NCR. | Each shows the other, and the reverse. |

## Product records and rule sets

| ID | Req | Risk | Steps | Expected result |
|---|---|---|---|---|
| T-PRD-01 | PRD-001 | RSK-023 | Create a product with name, version, UDI, intended use, markets, and classification. | The record is saved and every field is retrievable. |
| T-PRD-02 | PRD-002 | RSK-023 | For a product authorized in two markets, enter a complaint from a third market, then from each authorized one. | Only applicable rule sets are evaluated, and each decision records the rule set used. |
| T-RUL-01 | RUL-001 | RSK-013, RSK-023 | Decide a complaint, publish a new rule set version, then decide another. | Each decision shows the version in force at its time, and the earlier decision is unchanged. |
| T-RUL-02 | RUL-002 | RSK-023 | Change a rule set as a contributor and as an administrator without and with an approver's signature. | The change takes effect only after a signed approval, and every step is audited. |

## Reference library and entitlements

| ID | Req | Risk | Steps | Expected result |
|---|---|---|---|---|
| T-LIB-01 | LIB-001 | RSK-007 | Upload a document with title, version, effective date, and status. | The document is stored with its details. Agent use is tested in TC-002. |
| T-ENT-01 | ENT-001 | RSK-017 | Set different plans for companies A and B. | Each company sees the features of its own plan. |
| T-ENT-02 | ENT-002 | RSK-017 | For a company without an add-on, try the screen, a direct address, the API, and an export. Then grant and revoke the entitlement. | All routes are refused without it, work when granted, and stop again when revoked. Data is retained. |
| T-ENT-03 | ENT-003 | RSK-017 | Change an entitlement. | An audit entry records who changed it and the old and new states. |

## Export and language

| ID | Req | Risk | Steps | Expected result |
|---|---|---|---|---|
| T-EXP-01 | EXP-001 | RSK-020 | Export a signed record with an audit trail as a PDF. | The PDF holds the record, all signatures, and the full audit trail. |
| T-EXP-02 | EXP-002 | RSK-020 | Export a filtered list as CSV. | The CSV matches the filtered on-screen list. |
| T-EXP-03 | EXP-003 | RSK-020 | Compare exports with on-screen records field by field, including long text, large records, and special characters. | Exports are complete and accurate. |
| T-LNG-01 | LNG-001 | RSK-024 | Inspect the interface, notifications, and exported documents. | All text is in English. |

## Security

| ID | Req | Risk | Steps | Expected result |
|---|---|---|---|---|
| T-SEC-01 | SEC-001 | RSK-022 | Scan all endpoints for protocol and cipher support and try an unencrypted request. | Only encrypted connections work, and unencrypted requests are refused or redirected. |
| T-SEC-02 | SEC-002 | RSK-022 | Inspect the encryption settings of the database, file storage, and backups. | Encryption at rest is enabled for all. |
| T-SEC-03 | SEC-003 | RSK-010 | Leave a session idle just under and just over the configured period. | The session persists below the period and ends above it. |
| T-SEC-04 | SEC-004 | RSK-022 | Inspect the database and logs for stored credentials. | No credentials are stored or logged by Qaabil. |
| T-SEC-05 | SEC-005 | RSK-022 | Enter wrong credentials repeatedly. | Each attempt is logged and repeated failures are throttled. |
| T-SEC-06 | SEC-006 | RSK-022 | Scan the source code and configuration for secrets. | No secrets are found. |
| T-SEC-07 | SEC-007 | RSK-022 | Run the dependency scan on the release candidate. | No unresolved critical or high findings [criteria to be set]. |
| T-SEC-08 | SEC-008 | RSK-010 | Set a weak password. Configure periodic revision and advance the clock. Report a credential as lost. | The weak password is refused, revision is enforced when configured, and the lost credential is deactivated within [time]. |
| T-SEC-09 | SEC-009 | RSK-022 | Trigger repeated failed sign-ins. | Administrators and the vendor receive an alert. |

## Operations

| ID | Req | Risk | Steps | Expected result |
|---|---|---|---|---|
| T-OPS-01 | OPS-001 | RSK-016 | Inspect the backup schedule and logs, check retention, and perform a restore test. | Daily backups exist for the retention period and the restore succeeds. |
| T-OPS-02 | OPS-002 | RSK-016, RSK-012 | Restore to a separate environment and run chain verification. | Records and the complete audit trail return, and verification passes. |
| T-OPS-03 | OPS-003 | RSK-018 | View the same records as users in different time zones, including dates around a daylight saving change. | Times are stored in UTC and shown correctly in each user's zone. |
| T-OPS-04 | OPS-004 | RSK-017 | Inspect the interface for the software version. | The version is visible and matches the release. |
| T-OPS-05 | OPS-005 | RSK-016 | Try to remove records inside and just outside the retention period. | Records inside the period cannot be removed. |
| T-OPS-06 | OPS-006 | RSK-016 | Analyze availability over the test period and run a load test at [expected load]. | Availability meets [value] and the load test completes within [thresholds]. |

## Execution record

For each run, the execution copy records: software version, environment, tester, date, result for every case, evidence references, and defects raised. Test case results feed TR-001, and evidence links feed TM-001.

## Review and approval

| Role | Name | Signature | Date |
|---|---|---|---|
| Author | [name] | [signature] | [date] |
| Independent reviewer | [name] | [signature] | [date] |

## Open items

- Set the bracketed times, tolerances, and thresholds
- Review expected results with the independent reviewer
- Confirm that every requirement in SRS-001 appears in at least one test case, including any added after this revision

END

Expected result: TC-001 contains 83 test cases (ACC 8, ACS 5, ESG 5, AUD 6, CMP 11, EML 10, NCR 4, CAPA 7, PRD 2, RUL 2, LIB 1, ENT 3, EXP 3, LNG 1, SEC 9, OPS 6).

---

## D. compliance/P11-001.md

D1. Replace "[Change control procedure to be written]" with "CC-001 (drafted)".

D2. Replace the bullet text "Procedures to write: vendor training and qualification records for 11.10(i), and a change control procedure for 11.10(k)." with "Procedures: a vendor training and qualification procedure is still to be written for 11.10(i). The change control procedure for 11.10(k) is drafted as CC-001 and needs review."

D3. Replace the open item "Write the vendor training and change control procedures" with "Write the vendor training procedure and review CC-001".

D4. In the 11.10(k) row only, change the status "Procedure needed" to "Procedure drafted". Leave the 11.10(i) row as "Procedure needed".

---

## E. Approval block (add to documents that lack one)

Documents that need it: validation/ADS-001.md, validation/DS-001.md, validation/SRS-001.md, validation/TP-001.md, validation/VP-001.md. (TC-001 gets its block from section C.)

Place it as a section headed "Review and approval", immediately before the "Open items" section, or at the end of the document if there is no "Open items" section.

Roles: ADS-001, SRS-001, TP-001, and VP-001 use Author, Independent reviewer, and Regulatory advisor. DS-001 uses Author and Independent reviewer.

```
## Review and approval

| Role | Name | Signature | Date |
|---|---|---|---|
| Author | [name] | [signature] | [date] |
| Independent reviewer | [name] | [signature] | [date] |
| Regulatory advisor | [name] | [signature] | [date] |
```

---

## F. Decision: version 1 reportability rule sets

The decision is that version 1 ships with the US reportability rule set only. The EU rule set is a later phase. The second market in test data is synthetic and exists only to test multi-market logic.

F1. validation/ADS-001.md, open questions: replace the item "Which rule sets ship in v1: US only, or EU as well?" with "Decided: version 1 ships with the US rule set only. The EU rule set is a later phase."

F2. validation/VP-001.md, Intended use section: after the sentence "Version 1 supports English-language content only." add: "Version 1 includes the US reportability rule set only."

(The TC-001 change for this decision is in C1.)

---

## G. planning/

G1. planning/MVP.md: directly under the title, add this line: "Note: this is an uncontrolled planning document. The hosting region, technology stack, identity provider, and job queue it lists as open were decided in DS-001."

G2. Create planning/complaint-handling.md with the following content, adding front matter with `id: planning-complaint-handling`, `status: uncontrolled`, and no other change:

```
# Complaint handling: what happens and what the agent needs

Rev A (draft), October 2026. Reportability criteria and timelines must be verified by a qualified regulatory affairs professional.

## What happens when a complaint arrives

1. **Receive and log.** Anyone can receive one (sales, support, a distributor, email). It must reach the complaint unit quickly, and the reporting clock starts when the company becomes aware.
2. **Initial assessment.** Is it a real complaint, meaning an allegation that a released device fell short on quality, safety, reliability, or performance? Is the device involved, and can it be returned? Was there a death or serious injury?
3. **Reportability decision.** Does it meet the criteria for a US medical device report, an EU vigilance report, or a field action? The decision is documented even when the answer is no.
4. **Investigation.** Look up the lot or serial number, the device history record, the software version, similar past complaints, the risk file, and the labeling, then analyze any returned device. Decide whether it was a device problem, user error, or something else.
5. **Outcome.** Close with justification, open an NCR or CAPA, update the risk file, or start a field action.
6. **Respond and close.** Tell the complainant where required, and a reviewer approves closure.
7. **Feed trending and post-market surveillance.** Complaint data goes into trend reports, post-market surveillance, and management review.

## What the agent needs to see

### About the device

- Intended use, indications, and IFU or labeling
- Device description, models, versions, and UDI
- Software release notes and known anomalies, for software devices

### Risk

- The risk management file: hazard analysis, design and process FMEA, and the risk-benefit conclusion
- This is the key link. The agent can map a complaint to an existing hazard or failure mode, and flag when it reveals one that is not in the file or happens more often than assumed.

### Manufacturing

- Device history records and lot records
- Past NCRs, process validations, and supplier information by lot

### Quality history

- Past complaints and their outcomes
- CAPAs, NCRs, field actions, and recalls
- Existing trend reports

### Procedures

- The complaint handling SOP and the reportability decision criteria
- MDR and vigilance procedures, and the CAPA procedure

### Post-market and regulatory

- Post-market surveillance plan and reports (PSUR for the EU) and the PMCF plan
- Clinical evaluation report and relevant literature
- Searches of public adverse event databases
- The basis for clearance or approval, and the technical file

## What to load first

More documents do not automatically mean better answers. For version 1, load:

1. IFU and intended use
2. The risk file's hazard list or FMEA
3. The complaint and reportability SOPs
4. Past complaints and CAPAs
5. Lot lookup or software release notes

Everything else can come later.

## Two rules that matter more than volume

- Only current approved versions count as sources, never drafts or obsolete documents.
- The agent must cite where each statement came from, and say so when nothing in the documents supports an answer.
```

---

## H. Not to change

Leave these findings unfixed and only record them in the report: L-01 (table styling), L-02 (running headers and footers), L-03 (MVP PDF layout), L-06 (core title wording), and M-02 (record in register.md that the legacy desktop file name for TM-001 was "RTM-001 Rev A Draft.docx").
