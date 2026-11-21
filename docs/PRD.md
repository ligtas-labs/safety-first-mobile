# Safety First Android simulation PRD

The game is the student practice client for O1 (first-person, touch-based construction cases), O2 (changed conditions and reassessment), and O3 (scored decisions, debrief and distinct corrective replay). The Godot 4.7 Compatibility scaffold configures an icon. It contains no playable main scene, GDScript workflow, SQLite extension or Android export preset.

## Sources and delivery status

Paper 33 is *OSH CASPTONE RESEARCH PAPER (33).pdf*, Chapters 1–3. Page numbers below refer to printed pages. C4 identifies the separate *Chapter 4 FOR PLANNING.pdf* draft. Paper 33 §1.3.2 defines O1 (repeatable 3D practice before OJT), O2 (reassessment after changing conditions) and O3 (expert-reviewed feedback and distinct corrective attempts). Chapter 2 §§2.1.6–8 and 2.4 inform the learning design. Paper 33 §3.8 reports needs-validation evidence. The draft user stories give implementation examples and the draft Gantt gives sequencing.

Safety First supplements Civil Engineering instruction and supervised practice. Simulation scores confer no certification or evidence of real-site competence. Rows are proposed backlog requirements unless marked implemented. Signed approvals and completed product evaluation were not verified. Appendix A–I entries appear in the Paper 33 contents but their bodies are absent from the available copy.

## Users and responsibilities

Civil Engineering students authenticate online, obtain reviewed packages, play downloaded cases offline, review local feedback, and later synchronize or submit to an assignment. No teacher dashboard or content editing runs on Android. Teacher review happens in web after explicit eligible submission.

## Requirements and acceptance

### Learning, evidence and progression

| ID | Capability and source | Acceptance criteria for this repo |
| --- | --- | --- |
| SF-01 | Touch exploration of reviewed fictional workplaces and inspection of objects, records and routes. 33 §1.7, §3.3 item 1 (printed p. 35); C4 §4.3.1. | Use touch movement and inspect stable targets in a downloaded reviewed case in airplane mode. A missing or partial package prompts download without discarding saved progress. |
| SF-02 | Search reviewed hazard entries and open linked practice. 33 §3.3 item 2 (pp. 35–36); C4 §4.3.2. | Search reviewed descriptions by hazard or keyword, inspect source, exposed people and controls, and open linked practice offline. No match shows an empty state; unavailable content can be downloaded online. |
| SF-03 | Complete choice-based HIRAC including exposed people, likelihood, severity, priority, control, rationale and residual risk. 33 §3.3 item 3 (pp. 36–37); C4 §4.6.2. | Capture selected hazard, people, likelihood, severity, priority, control, rationale and residual risk in order. Missing prerequisites remain visible; a later valid action updates the draft. |
| SF-04 | Respond to reviewed changes and resource constraints across planning, emergency preparedness and documentation. 33 §1.3.2, §3.3 items 3–4 (pp. 36–38); C4 §4.5.8. | Trigger a reviewed change to work, equipment, route or resources and require reassessment. Record revised planning, emergency and documentation decisions and show the predefined consequence. Unavailable resource choices remain observable. |
| SF-05 | Sequence tutorial, work at height and temporary works with provisional offline unlock and confirmed credit. 33 §3.3 item 5 (pp. 38–39); C4 §4.5.5, §4.7.2. | Open the tutorial (basic hazard inspection and emergency reporting), work-at-height/pre-work case, and temporary-works sequencing case in order. A reviewed local pass can unlock a downloaded case provisionally. If the API rejects the prerequisite, retain the original attempt and show the difference from confirmed status. |
| SF-06 | Version reviewed rubrics and assess initial, corrective and independent attempts separately. 33 §3.3 items 6–7, Tables 6–7 (pp. 39–41); C4 §4.5.5, §4.5.7. | Score against the same pinned reviewed fixtures as API. Corrective practice creates a new ID linked to the original. Independent checks use a distinct reviewed situation and record guidance status. Exact applicability and thresholds require approval against Paper 33 Tables 6–7 and C4 Table 14. |
| SF-07 | Explain criterion-level results, omissions and corrective practice. 33 §3.3 items 7–8 (pp. 41–42); C4 §4.3.7–8. | Show provisional per-area counts, ratings, essential misses and explanations with corrective action. On server discrepancy retain and label the original and show the confirmed result separately. |
| SF-08 | Show learner-owned progress, separated attempt types and practice recommendations. 33 §3.3 item 8 (p. 42), §3.6; C4 §4.4.1. | Show the student's own attempt history, attempt kind and suggested practice with pending and confirmed state. Refresh when online without overwriting local evidence. |

### Access, classroom and synchronization

| ID | Capability and source | Acceptance criteria for this repo |
| --- | --- | --- |
| SF-09 | Authenticate students and provision teachers operationally; scope first deployment to one school with multiple classes. 33 §1.7, §3.6; C4 §4.1, §4.5.6. | Require connectivity for initial sign-in. Expired credentials pause uploads until reauthentication; existing saved evidence remains intact. Offline session expiry policy remains open. |
| SF-10 | Manage classes and approve enrollment requests from class codes. 33 §3.3 item 9 (p. 42); C4 §4.6.4, §4.7.1. | Honor approved class membership on online refresh. A code or pending request grants no class access. |
| SF-11 | Assign published activities and show eligible work and status. 33 §3.3 item 9 (p. 42), §3.6; C4 §4.6.4. | Retrieve the student's eligible assignments when online and label missing local content. Recover after download; treat revoked access according to the approved offline policy. |
| SF-12 | Durably save and synchronize attempt evidence with repeat-safe server acceptance. 33 §1.7.2, §3.6.I (printed pp. 47–48); C4 §4.5.6, §4.7.2–3. | Save the current attempt and pending state durably in SQLite before upload. Test airplane mode, process termination, same-ID retry after a lost response, expired authentication and invalid evidence. An acknowledgment persists the confirmed ID/result; a conflicting response remains flagged. |
| SF-13 | Explicitly submit an eligible confirmed attempt and restrict teacher review to that class. 33 §3.3 item 9 (p. 42); C4 §4.5.6, §4.7.4. | Let the student explicitly submit an API-confirmed eligible attempt. On failure show the reason and retain the attempt. Treat a submission as visible to the teacher only after API acceptance. |
| SF-15 | Control account/record access and retain historical versions and finalized evidence. 33 §3.6; C4 §4.3.11, §4.5.4, §4.5.6. | Resume using the save's pinned content/rubric references. Keep finalized evidence intact across updates and disallow cross-account reads. Test migrations once a SQLite schema exists. |

### Quality, research and operations

| ID | Capability and source | Acceptance criteria for this repo |
| --- | --- | --- |
| SF-16 | Verify product quality, accessibility to intended devices and operational behavior. 33 §1.7, §3.1–2, §3.8.5; C4 §4.5.3. | Run editor/CI import and device tests for touch, readability, loading, frame time, export, and kill/restart recovery. Device matrix, FPS, package size and minimum Android version await approval. |
| SF-17 | Keep approved study procedures and records separate from classroom use. 33 §3.2, §3.10–11. | Use synthetic accounts and content fixtures in engineering sessions. The research team controls pilot instruments, approved evidence capture and any study-data export. |

## Cross-app workflow

Mobile pins the content and rubric versions and saves an attempt ID, attempt kind, relevant parent attempt ID, and ordered evidence locally before upload. On reconnection it retries pending evidence under the same learner and client attempt ID. API validates ownership, content compatibility and evidence, persists results, and returns the existing confirmation on a matching repeat. A changed payload for the same ID produces a conflict. Mobile holds on timeout, pauses for renewed authentication, and retains rejected or discrepant evidence with its reason. Only server acknowledgment establishes confirmed credit.

Synchronization and classroom submission are distinct. Confirmed practice remains private. An explicit submission identifies the assignment and a confirmed attempt. API checks learner ownership, current enrollment and assignment eligibility before linking it. Web shows the result to the authorized teacher after the submission succeeds and the view refreshes. Teacher comments are separate records. The study protocol controls access to research instruments and outcomes separately.

This is the proposed behavior from Chapter 4 §§4.5.4–7 and 4.7.1–4. Endpoint names, payload shape and canonical comparison, auth mechanism, retry timing, offline session expiry, deadline/resubmission policies, and archive/recovery semantics require a shared decision.

## Data and access

Planned local SQLite stores scoped learner references, content and rubric versions, attempt state, ordered events, provisional result, sync marker and confirmed result reference. Downloaded packages and hazard entries remain available offline. Upload only contract-approved evidence over HTTPS. Device key/session storage, app-data retention, account switching, version migration and supported SQLite extension require decisions.

## Verification evidence

Record engine, build/APK, physical Android model and version, case and rubric IDs, touch task outcomes, and offline/restart/duplicate traces. CI can prove import. A device export and user study need separately recorded evidence.

## Study evidence and open decisions

Use synthetic accounts and reviewed fixture data for development. Paper 33 §§3.2 and 3.10–11 describe content/functional verification, a rubric-based pilot, pretest, post-test and usability assessment. These are distinct from the needs survey and ordinary classroom scoring. Study participation is voluntary with informed consent and confidential withdrawal handling. Coded individual study records are limited to the research team and adviser, with aggregate reporting. The paper's August 2027 disposal date concerns the specified survey/interview materials. Confirm the applicable retention and disposal rules for platform and pilot records before collection.

Confirm approved pilot instruments, eligibility and participant counts, consent and withdrawal handling, linkage/retention, reviewer authorization, and the current ethics/panel/adviser approval records. Leave evaluation outcomes open until measured. Confirm reviewed criterion applicability, essential items, accepted alternatives, guidance rules, weights or rounding, and golden fixtures before releasing assessment logic.
