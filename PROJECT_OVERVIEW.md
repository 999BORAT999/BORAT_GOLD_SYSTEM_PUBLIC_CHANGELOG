# BORAT GOLD SYSTEM — development overview

This page explains the engineering effort recorded in the public release history. It is based on the project's release descriptions and scoped audit summaries. It is a retrospective documentation view, not a new source-code audit or a claim of completed runtime acceptance.

## What the project contains

BORAT GOLD SYSTEM brings together Radar, AutoTrader, Research Bot Centrum and, from CP59, Brain Office. The recorded work covers execution, non-executing research, operator tools, analytical views, deployment and evidence handling. Keeping these responsibilities explicit is a recurring part of the project: a research observation is not automatically a broker trade, a catalogue identity is not automatically an active strategy, and an isolated PASS is not a live acceptance certificate.

The development record includes integration of existing and owner-supplied material as well as new implementation and repair work. Retaining source provenance is part of the work; this overview does not claim sole original authorship of every included strategy or historical dependency.

## How the work developed

| Phase | Engineering direction | Why it mattered |
|---|---|---|
| CP58 R2–R3 | Complete package handoff, declared deployment payload, manifests, installer contracts and package-consistency checks. | Made delivery reproducible and distinguished deployment files from the larger retained history/evidence package. |
| CP58 R4 | Narrow recovery correction for a validated empty initial state. | Avoided turning a specific recovery exception into blanket acceptance of missing or damaged state. |
| CP58 R5 | Operator settings, persistent peak/drawdown/emergency state, order journals, consistent Research export and safer rollback. | Extended the work beyond signal logic into durable risk accounting and recoverable operations. |
| CP58 R6 | Research integration, precise typed-state/cache decoding, native/virtual boundaries and EXIT persistence. | Preserved source behavior and uncertainty while expanding integration; owner exceptions remained documented. |
| CP58 R7 | Separation of trading authority and Research work, single-writer responsibilities and durable event transfer. | Reduced ambiguity about which component can trade, which can write a database and when a fact is acknowledged. |
| CP58 R8–R8.1 | Risk/recovery safeguards, health and UTC quality, execution priorities, history warm-up, EXIT consolidation and deployment planning. | Made operational readiness and retained historical gaps more visible while addressing scheduling and recovery issues. |
| CP59 / V1.2.0 | Brain Office catalogue, adapters, analytics, TOP/EXIT, comparisons/export and guarded data ownership. | Added an operator/research analysis layer; catalogue scale was not presented as proven strategy profitability. |
| CP59.1 / V1.2.1 and HF12 | Lifecycle and interface fixes, shared preflight, catalogue detail, health fairness, versioned identity and timing diagnostics. | Improved operator feedback and evidence continuity; version/manifest and performance follow-up remained explicit. |
| V1.2.23–V1.2.26 | Incremental processing, durable queues, exact-input evidence, file-race recovery, checkpoint reuse and stronger release validation. | Targeted repeated work, data loss/duplication windows and misleading diagnostics without inventing missing historical results. |

The public changelog contains a separate entry for each of the 16 published private releases. The gaps between published version numbers are not filled with invented milestones.

## Reliability work that is easy to miss in a feature list

### Persistence and interruption recovery

The project records durable event handoff, source/run/content identity checks, acknowledgement after the relevant database commit, retained pending work and restart reconciliation. These mechanisms are intended to avoid acknowledging work that has not actually been recorded or accepting an unrelated state after restart.

Later work addresses a more specific interruption window: a derived projection may already exist in the database while its companion runtime checkpoint has not advanced. Recovery must bind the previous and current state to matching evidence. An unobserved close remains unobserved; its price, excursions and costs are not synthesized.

This is state-management and evidence work, not a new profitability claim.

### Historical data quality and costs

The release history distinguishes a genuine completed negative evaluation from a missing input, unfinished warm-up, failed write or incomplete evaluation. GAP, UNKNOWN, NOT_EVALUABLE and unverified provenance remain visible rather than being converted into ordinary wins, losses or coverage.

Cost accounting similarly requires verified inputs and an approved model. A recorded gross point result does not establish net money when size, FX, commission, swap or fees are missing. Source-study, paper/shadow and broker outcomes remain different evidence categories.

### Operator tools and delivery

The work also includes catalogue/detail views, source and period selection, clearer ARM/HALT explanations, export feedback, health queues, Telegram diagnostics, installer preflight, recognized-installation handling, backups and rollback receipts.

A presentation fix does not change trading permission. A successful file comparison does not prove the interface was exercised in a live terminal. An installer plan describes intended changes; it is not a receipt showing those changes were applied.

## Concrete examples of recorded verification

The figures below retain their original scenario boundaries. They are not added together into a total test count because fixtures, checks and reports can overlap.

| Release / work item | Recorded evidence | Practical limit |
|---|---|---|
| CP58 R2 | 32/32 release-build checks, 10/10 installer-contract checks; additional MQL, Python and local-database fixtures. | Controlled package/integration evidence; no full owner-terminal or broker acceptance. |
| CP58 R3 | 48/48 package checks and an installer run against a temporary target. | No change to the owner's terminal and no new live-market certification. |
| CP58 R4 | 57 contract tests and 27 isolated MQL checks, plus targeted compilation/review. | Narrow recovery scenario, not full replay or long-duration acceptance. |
| CP58 R5 | 116 automated cases and 229 native fixture checks recorded. | Package remained not installed in the stated acceptance record. |
| CP58 R7 | Recovery delivered 9,379 queued records; 136 PASS of 141 recorded checks, with five obsolete architecture checks. | Obsolete checks are not passes; tick/timer targets were not met. |
| CP59.1 | A selected database-query fixture changed from 0.223 s to 0.027 s after an index. | Isolated query measurement; live dashboard performance was not established. |
| V1.2.23 | One fixed comparison reduced 1,800 event commits to 600 grouped commits with matching compared digests. | Synchronous I/O still produced long tails in other fixtures. |
| V1.2.24 | Health publication changed from 0/4 to 4/4 fixtures; 187 race checks and separate 10/269 cold-start/recovery checks recorded. | The separate S8 load run failed three criteria and is retained as a failure. |
| V1.2.26 | A 3,072-call fixture retained ENTRY/CLOSE/revision behavior; separate 8,000-packet and restart comparisons recorded. | Exact-path regressions do not establish whole-terminal latency. |
| V1.2.26 | One frozen EXIT policy matched decision, exit time/price and excursions in 10/10 cases. | One policy only; all-policy owner-database execution remained unproven. |

RED/GREEN means the documented regression reproduced a failure against the relevant baseline and passed after the targeted change. Focused reviews also identified problems requiring another repair cycle, including release-receipt parsing, acknowledgement identity, shared handoff races and a combined crash/restart recovery case. These repairs are part of the recorded effort; a later scoped PASS does not erase an earlier failed integrated run.

## Latest package: V1.2.26

V1.2.26 continues V1.2.25 across recovery correctness, cost provenance, repeated serialization, Research persistence, queue service, scanner behavior, macro history and release evidence.

The private release comparison records **127 added / 62 changed / 0 removed files** across the full package, and **8 added / 33 changed / 0 removed files** in the deployment tree. The deployment payload contains **757 files**. These figures describe package contents, including evidence and history; they are not counts of unique features or newly written source files.

The recorded component labels are AutoTrader **1.1.20**, Research **1.2.20** and Radar **1.0.133**. The 13-program certificate consists of five rebuilt targets and eight unchanged targets checked against parent receipts. It does not mean all 13 were freshly compiled.

Additional recorded work includes:

- Exact projection recovery after interruption, with conflicting or incomplete proof retained as pending.
- Explicit unknown economic outcomes when complete size/cost evidence is unavailable.
- Current ARM-blocking explanation separated from retained historical messages.
- Serialization reuse only for a complete byte-identical source state; dynamic execution data is still regenerated.
- Verified identical-payload retry reuse while preserving the mandatory first durable write.
- Fairer new-versus-historical paper-cost service and separate waiting/unprovable/covered counts.
- Empty-versus-missing-versus-failed scanner results and exact durable evidence before reconciling missing ready packets.
- Dispatch-keyed replay acknowledgement and stronger release-receipt/aggregate-result checks.

See the [full V1.2.26 record](README.md#release-v1-2-26-cp59-1-demo-candidate) for the detailed change history and remaining gates.

## What remains unproven

The latest package is a DEMO candidate. Its recorded state is release_ready=false, deployment_authorized=false and trading_arm_enabled=false. One-hour post-install acceptance, whole-system performance, full TOP sweep, complete EXIT parity and full-day health are not established by the release record.

The V1.2.25 integrated observation was NOT_PASS. EA1 copy maximum was 144.417 ms, EA1 timer maximum 2,555.612 ms, EA2 p95 upper 215–230 ms, EA2 maximum 946.537–958.288 ms, and TOP work 843,250 ms. Subsequent targeted repairs do not retroactively turn that observation into a pass.

The work is documented as software engineering and controlled verification. No verified weekly profitability, guaranteed trading return, completed LIVE authorization, invented working-hour total or inferred personal commit authorship is claimed.

## Independent archive check — 2026-11-22

The review was extended from the latest package to **all 16 recommended archived release ZIPs**. Every downloaded canonical archive matched its GitHub SHA-256 and size, and every ZIP CRC check passed. Checksum sidecars were compared where available. Fifteen full-package manifests passed. CP58 R2 uses a separate deployment manifest: all 141 deployment files passed; its other 1,570 archive files are outside that manifest's coverage, with the outer ZIP digest and CRC still verified.

| Release | Archive bytes | Manifest scope | Verified manifest entries |
|---|---:|---|---:|
| v1.2.26-cp59.1-demo-candidate | 461519154 | Full package | 28346 |
| v1.2.25-cp59.1-demo-candidate | 460993790 | Full package | 28219 |
| v1.2.24-cp59.1-demo-candidate | 459705291 | Full package | 27809 |
| v1.2.23-cp59.1-demo-candidate | 459470721 | Full package | 27748 |
| v1.2.1-cp59.1-hf12 | 425054565 | Full package | 25918 |
| v1.2.1-cp59.1 | 424286543 | Full package | 25808 |
| v1.2.0-cp59-bo1.0 | 396000568 | Full package | 25718 |
| v1.1.118-cp58-r8.1 | 325734732 | Full package | 24461 |
| v1.1.118-cp58-r8-hotfix1 | 147249203 | Full package | 22407 |
| v1.1.118-cp58-r8 | 145517004 | Full package | 22192 |
| v1.1.118-cp58-r7 | 132487368 | Full package | 20801 |
| v1.1.118-cp58-r6 | 136185769 | Full package | 20562 |
| v1.1.118-cp58-r5 | 68103810 | Full package | 6405 |
| v1.1.118-cp58-r4 | 60105267 | Full package | 6153 |
| v1.1.118-cp58-r3 | 53315423 | Full package | 6076 |
| v1.1.118-cp58-r2 | 32281537 | Deployment only | 141 |

These are per-archive verification records. Historical material can be repeated across packages; the figures are not counts of unique new source files, features, development hours or functional tests.

### A packaging defect detected and corrected

The initial CP59 / V1.2.0 distribution passed its outer digest and CRC checks but failed 13 root-manifest size/hash rows. Its release record documented an earlier privacy redaction of 13 historical documents; their manifest metadata had not followed those changes.

A separately named corrected distribution updates only MANIFEST.json. All **25,718 non-manifest file contents**, including all **675 deployment files**, are byte-identical to the previous redacted copy. The corrected ZIP and its checksum pass validation. The original redacted distribution remains private and unchanged, and the release index now explicitly distinguishes the recommended canonical ZIP from retained earlier copies. No component version, strategy code or acceptance state was changed.

The failed original audit and its correction evidence remain recorded. This is an example of verification identifying and fixing delivery metadata, rather than relabeling a failing result as a pass.

### Current source baseline and verification limits

A private Git baseline preserves **694 unchanged MQL5 source files** from the verified V1.2.26 deployment tree. This creates a current point for subsequent code comparison; it does not reconstruct missing historical commits or publish project code.

No package programs or installers were run for the archive checks. Historical compilation and MT5 acceptance tests were not rerun. Nested historical ZIPs were not independently expanded or executed, unavailable original unredacted archives were not newly compared, and the audit is not a guarantee that every possible secret has been detected.

## Public documentation policy

The public record intentionally includes substantial technical detail about development, changes, recovery and measured behavior. Project source code, binaries, ZIP packages, credentials, account identifiers, private paths and raw private logs remain excluded.

Descriptions are curated from release evidence. An old public revision can remain accessible in Git history even after the current wording changes; the current documentation does not claim that an edit erases prior disclosure. Historical DEMO figures must not be treated as a validated current-week performance statement.

This overview and the detailed changelog describe the currently documented releases. Future completeness requires that each new package receives its own evidence-backed private and public update.

[Return to all release entries](README.md#version-and-release-navigation).
