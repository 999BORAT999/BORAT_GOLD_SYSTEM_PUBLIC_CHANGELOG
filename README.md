# BORAT GOLD SYSTEM — public changelog

This repository publishes curated, high-level summaries of project updates. The source code and release packages are kept in a separate private repository and are not published here.

This public changelog does not contain source files, downloadable builds, credentials, account identifiers, broker records, or private repository links. Each entry is reviewed and written specifically for public sharing; private release notes are not copied here verbatim.

## 2026-10-25 — CP58 R2 package candidate

CP58 R2 established the first complete versioned handoff for the V1.1.118 / CP58 line. This was a package and integration milestone, not a new strategy-performance certification.

- Bundled application sources and prepared binaries with a canonical deployment payload, research modules, project documentation, provenance records, and test evidence.
- Added a group of new AutoTrader records in a non-executing shadow state by default; the package also documented the existing research variants and capacity model. Brain Office was not part of this release.
- Included integrity and installer checks designed to validate the package before copying the defined deployment files and to retain a recovery copy.
- Recorded 32/32 release-build checks and 10/10 installer-contract checks. Separate evidence included 47 MQL fixture checks, 22 Python contract checks, and 24 local database checks.
- Those checks were performed in controlled environments. The package was not installed into the owner's live terminal; full market replay, broker fill/reject coverage, long-duration performance, and profitability were not established.

**Status:** archived DEMO handoff; not LIVE authorization or a profit claim.

## 2026-10-26 — CP58 R3 package revision

R3 republished the full CP58 handoff with stronger package-level consistency checks. It is a package revision, not a separate strategy release.

- Preserved the approved 141-file deployment payload and confirmed that its recorded file digests matched the prior accepted package contents.
- Retained the application, research, project-history, guard, and verification material needed to reproduce the handoff; no new trading algorithm change is claimed for R3.
- Recorded 48/48 package checks and a successful installer run in a temporary test target. The test target was isolated; the owner's MT5 installation was not changed.
- Earlier integration receipts remained reference evidence rather than a new R3 live-market test.
- Live installation, broker order scenarios, long-duration load, and strategy profitability remained unverified.

**Status:** package-integrity revision only; not a live acceptance.

## 2026-10-26 — CP58 R4 recovery hotfix

R4 addressed a narrowly defined recovery case in which a valid empty initial state could be rejected and leave selected research modules waiting. The underlying origin of the original empty-state record was not established.

- Allowed recovery only for the specifically validated empty-start condition; other empty, malformed, or conflicting state remains blocked rather than being accepted broadly.
- Preserved the original state record for audit and avoided replacing it with a synthetic timestamp or overwriting prior evidence.
- Improved diagnostics for storage failures while preserving the distinction between an actual open position and an unavailable or uncertain state.
- Left strategy entry/exit rules, filters, identities, risk settings, and default shadow behavior unchanged.
- R4 changed a small, defined portion of the deployment payload; the remaining files were checked against the prior package. Targeted evidence included 57 contract tests, 27 isolated MQL checks, successful host/popup compilation, and an independent focused review with no critical or major findings.
- Testing used isolated local data. No live account, broker order, full market replay, or long-running performance acceptance was performed.

**Status:** targeted recovery correction; not a LIVE or profitability certification.

## 2026-10-28 — CP58 R5 infrastructure update

R5 concentrated on operator settings, durable risk and order records, research data handling, export reliability, and safer installation/rollback. The release notes state that the established strategy entry/exit logic was retained, with persistent risk accounting identified as the intentional behavior change.

- Updated the settings interface with clearer global/per-module views, draft/apply/reset handling, and bounded display controls.
- Made peak/drawdown and emergency blocks persist across restart. When required risk state cannot be trusted, new entries remain blocked until the owner initializes or verifies the reference; apply, restart, or arm actions do not silently clear the block.
- Improved order/event bookkeeping and recovery so records are tied to the corresponding position evidence. Uncertain historical order outcomes remain uncertain instead of being reconstructed as facts.
- Added provenance-aware research storage and a separate export workflow using a consistent database snapshot, with explicit partial-versus-complete export status.
- Strengthened package verification, backups, rollback checks, and recognized-installation handling without modifying retained user databases or terminal profiles.
- Evidence recorded 116 automated test cases and 229 native fixture checks, along with compilation and focused infrastructure review. The live terminal deployment status remained not installed; long-duration performance, full market replay, and broker order scenarios remained open.

**Status:** infrastructure and workflow update; not LIVE authorization or a profitability claim.

## 2026-11-02 — CP58 R6 DEMO package (owner-exception status)

R6 expanded research integration and state restoration while documenting where original strategy behavior, virtual research, and broker execution must remain distinct.

- Expanded the catalogue of research and shadow integrations and improved precision and decoding for selected persisted states, caches, and profiles.
- Restored selected original modules and added separate research-cycle handling; where pricing, quantity, fees, feed, or native parity evidence was missing, the result remained explicitly unknown or not run.
- Kept signal studies and virtual exit analysis separate from confirmed broker trades; a research signal is not described as an order fill.
- Improved durable exit-analysis/database handling and persistence checks, including restart-related fixtures, while leaving broader history-route and whole-host acceptance as separate gates.
- Added two infrastructure hotfix iterations to reduce repeated encoding work and correct selected routing behavior without changing the recorded file format or integrity checks.
- Package integrity was checked against its internal manifest. The release decision retained an owner-exception status, and important gates remained open: native parity, complete market replay, recovery under real terminal restarts, performance/canary monitoring, migration rollback, and final clean-install acceptance.

**Status:** constrained DEMO package with explicit owner exceptions; no live-performance or profitability claim.

## 2026-11-05 — CP58 R7 execution separation

R7 introduced a clearer separation between the component responsible for AutoTrader/Radar operation and a separate non-trading research worker.

- Kept trading decisions, order handling, risk protections, and operational checkpoints in the primary execution component; research and exit-analysis work ran in a separate worker without broker-order authority.
- Separated database responsibilities and used a durable event handoff with identity checks and acknowledgement only after the receiving side recorded the event.
- Preserved pending events across interruption and avoided renumbering or discarding unacknowledged facts.
- Recorded downtime as an explicit research coverage gap; cycles crossing a gap were marked unreliable instead of being filled in with invented outcomes or counted as ordinary wins/losses.
- Restored and checked module identities and operating modes, while keeping existing halt conditions intact. A recovery test delivered 9,379 queued records and reconciled both sides through the same confirmed cursor.
- The acceptance record showed 136 passing checks out of 141 recorded; five earlier architecture tests were explicitly obsolete, not counted as passes. Both components compiled with zero errors/warnings in the recorded builds.
- The 200 ms tick and 250 ms timer targets were not met, and the one-hour queue observation was cancelled. ARM remained off for the final test; no broker trade or full live acceptance is claimed.

**Status:** execution/data-boundary update; key latency and live acceptance gates remained open.

## 2026-11-06 — CP58 R8 DEMO candidate

R8 combined execution safeguards, research-data quality work, health reporting, and runtime diagnostics. Its release notes distinguish implemented code from work explicitly deferred to R8.1.

- Improved recovery and halt handling so selected temporary I/O failures could be retried without erasing a genuine safety halt; added checks before releasing uncertain exposure states.
- Strengthened emergency behavior, pending-order reconciliation, and daily/weekly risk accounting. Uncertain positions remain a blocking condition rather than being omitted from risk review.
- Added clearer operator-close and weekend-close reasons while retaining the existing strategy and order-management boundaries.
- Added cost fields for new virtual exit records while leaving unsupported historical costs unknown. Missing spread, time, or fee evidence is not reconstructed as a verified result.
- Improved research timestamps, health summaries, selected module readiness explanations, macro/news data status, and bounded notification behavior. Missing or stale inputs remain visible as missing/stale rather than being silently substituted.
- Added helper and backup diagnostics, capacity/path safeguards, and clearer environment checks. Some automation and external-service connections still required owner setup and had not been live-tested.
- Compiled and audited package contents, but live installation, a full DEMO week, enabled-order scenarios, complete health coverage, and external-message acceptance remained open. Several startup/timer spikes and research warm-up gaps were specifically left for further observation or R8.1.

**Status:** DEMO candidate; package and targeted checks are not equivalent to full runtime acceptance.

## 2026-11-06 — CP58 R8 Hotfix 1

This hotfix focused on state recovery, explicit risk handling, health freshness, and installer/verifier safeguards. It did not introduce new strategy rules.

- Preserved the first safety-halt reason separately from later diagnostic messages, so a restart or recovery decision could not accidentally conceal a serious original block.
- Persisted operator-close and weekend-close reasons before attempting the close, retaining the original reason through retries and restarts.
- Changed unreadable position/order identity from a silent omission into an explicit unknown-risk block for new entries.
- Improved health-summary time checks and excluded selected retired items from active coverage warnings while keeping uncertain data visibly uncertain.
- Hardened installer and package verification around target identity, backup/recovery evidence, partial rollback, and files that must not be overwritten or removed blindly.
- Targeted offline validation included 58 functional regressions, 107 safety checks, health and messaging fixtures, and isolated installer/verifier scenarios. Seven compiled targets reported zero errors and warnings; these are scoped tests, not live broker or network delivery proof.
- A later health-queue follow-up was documented separately and is not represented here as included in this hotfix archive.

**Status:** narrow reliability hotfix; live installation, full-day health, external messaging, and broker acceptance remained outstanding.

## 2026-11-07 — CP58 R8.1 package

R8.1 extended R8/Hotfix1 across execution scheduling, research/exit analysis, data readiness, installation, and documentation. It retained the frozen core strategy and compatibility identity; the release was not a live-terminal acceptance.

- Warmed selected research inputs from available historical ticks after worker startup and used time-bounded history for delayed evaluations, addressing cases where a cold in-memory buffer caused an evaluation to be unavailable. The live restart acceptance target remained open.
- Reduced redundant exit-analysis work by consolidating an over-sized set of near-duplicate policies into a smaller documented set and adding a few distinct horizons; live load reduction was still to be measured.
- Improved multi-part position visibility and close/recovery safeguards, requiring exposure evidence before releasing a block. Separate live multi-part order acceptance was not performed.
- Reordered execution work so confirmed order and stop-protection tasks are handled ahead of non-executing shadow analysis; timing targets were documented but not established in a live market run.
- Added cautious virtual-cost estimation and GAP synchronization. Missing lot, fee, time, or price evidence remains unknown rather than being treated as net profit.
- Improved readiness explanations for selected modules, macro/news data status, time mapping, and health/latency monitoring. Historical records were not rewritten to manufacture missing coverage.
- Added safer fresh-install/upgrade planning, retention and backup rules, generated module documentation, and clearer version identity while preserving existing state.
- The recorded offline evidence included 8/8 compilation targets with zero errors/warnings and extensive source/package checks. The package was not installed; clean-machine startup, full-day acceptance, live broker handling, and a full DEMO week remained pending.

**Status:** final R8.1 package handoff, not proof of live acceptance, profitability, or LIVE authorization.

## 2026-11-07 — CP59 BO1.0 / V1.2.0 Brain Office foundation

CP59 introduced the first Brain Office component and a broad catalogue/analytics foundation while preserving compatibility with the prior execution and research state. The headline catalogue coverage is not a count of strategies proven profitable or approved for live execution.

- Added a separate Brain Office interface and data layer for module catalogue, status, analysis, comparison, and export. The design distinguishes verified broker facts from virtual research and incomplete evidence.
- Built the catalogue and adapter framework in stages. The final package described 316 catalogue identities with supported integration paths; this did not mean all entries were active or had passed live parity.
- Added guarded paths for adding modules, risk/exposure checks, state restoration, and identity/version validation. Incomplete adapters remain blocked or explicitly unsupported rather than being presented as ready.
- Added research-feed, open-state, version, and acknowledgement records with separate write responsibilities. Read-only research sources and identity-checked seed handling were used to avoid silently accepting mismatched historical data.
- Added dashboard periods, filters, summaries, comparison views, and export support, plus incremental TOP/exit-analysis work. TOP/exit numerical outputs were explicitly marked unvalidated pending real data and parity evidence.
- Added safeguards for event cost and nominal-currency calculations: where verified stop, size, exchange-rate, or fee inputs were unavailable, monetary outcomes remained unknown. Virtual figures were not conflated with broker-account results.
- Added multi-part execution safeguards, parity thresholds, bounded processing, backup/temporary-file retention, catalogue documentation, and an installation plan mode that described changes without applying them.
- The release recorded 8/8 compiled targets with zero errors/warnings and extensive isolated/source/package audits. It was not installed into a live terminal; seed import, market behavior, broker acceptance, performance targets, full demo week, and profitability remained unverified.

**Status:** Brain Office DEMO foundation; not 316 live-approved strategies, not LIVE authorization, and not a profitability claim.

## 2026-11-09 — CP59.1 V1.2.1 / Brain Office V1.0.1

V1.2.1 was an updated DEMO handoff that refined state recovery, user feedback, catalogue inspection, and installer preflight while preserving the prior release's database and component identity.

- Made selected interface and mode readers tolerant of additional health metadata so an added status field would not interrupt mode interpretation.
- When a module's counters could not be read, blocked its new entries temporarily, retried after readiness, and recorded a distinct halt reason if the read remained unavailable. Recovery evidence was retained rather than silently discarded.
- Added chart/context checks and startup-state handling; preserved the existing execution core and added a narrowly scoped entry guard.
- Improved display of multi-part exposure and risk, clarified normal market vetoes versus technical errors, and enabled operator close only when ownership could be verified.
- Expanded catalogue cards with concise identity/version information and a detail view. Installer plan-only and deployment paths now share write-target checks; optional helper startup can be skipped with its result recorded when permission is unavailable.
- Preserved provenance for owner-supplied records and used a separately redacted distribution copy where historical sensitive values were found; public changelog contains no such values or source archive.
- The package recorded 8/8 build targets with zero errors/warnings and targeted interface/database checks. It was not installed into a terminal; interactive close/deactivate, source switching, full chart behavior, and live broker acceptance remained unverified.

**Status:** DEMO handoff only; ARM and installation authorization remain separate owner decisions.
## 2026-11-13 — CP59.1 Hotfix 12 DEMO candidate

Hotfix 12 focused on Brain Office health-queue recovery, Research event identity and evidence checks, execution-stage diagnostics, clearer counts, and status messaging. It retained the CP59.1 component version labels; the accompanying audit explicitly notes that version-label policy still needed follow-up.

### Changes documented for HF12

- **Health queue fairness:** separated current-day and prior-day processing cursors so one stalled item can be retried without preventing other eligible records from progressing. A read-only fixture processed 432 eligible keys, including work after a previously stalled item; historical replay-required cases were not automatically repaired.
- **Research identity and input evidence:** aligned selected module identifiers with their versioned registry records and checked that a source tick had already been durably recorded before accepting its research event. Quote and associated context-time checks were retained.
- **Performance diagnostics:** added stage-level measurements for selected research, signal, and exit-processing work, making bottlenecks easier to isolate. The audit still recorded multi-second stages in some cases, so the intended latency target was not demonstrated.
- **Pending-event handling:** tied selected repeated-event recognition to a durable receipt and indexed pending work in order, reducing ambiguous replay behavior without inventing fills.
- **Interface counts and status:** separated primary AutoTrader counts from additional Brain Office slots and clarified period labels. Unavailable or unverified history/health is shown as unknown or unconfirmed, not as a misleading zero-result summary.
- **PIN/session messaging:** clarified timeout, invalid-entry, and temporary-block messages. This is presentation and workflow feedback, not a change to trading authorization.
- **Cumulative history:** the release also included a change-history document covering earlier CP59.1 and HF1–HF11 work. Planned, implemented, isolated-tested, and live-accepted items remain distinct; the cumulative document is not evidence that every earlier item passed live acceptance.

### Evidence and acceptance limits

- Package integrity and deployment-file matching were checked for the distributed copy. The recorded build receipts show zero errors for the targeted core builds; the Research build retained one compiler warning, so the release is not represented as an all-target zero-warning build.
- Offline regressions covered health processing, event identity/data boundaries, selected presentation cases, and isolated message-workflow behavior. Test recipients and fixtures do not prove external network delivery.
- The audit retained unresolved version/manifest inconsistencies and performance shortfalls, as well as history/replay, interactive UI, and end-to-end message/trade acceptance work.
- No new live broker cycle or complete post-update acceptance was established by the HF12 package. Any historical demo summary is not attributed to this hotfix and is not a forecast or guarantee.

**Status:** DEMO candidate only. Not a complete acceptance, LIVE authorization, or profitability claim.
## Publishing policy

Each published private release tag is represented by its own reviewed, text-only public entry. These entries summarize change areas, scoped evidence, and known limits; they are not copies of private audit reports. This repository does not publish source code, package archives, credentials, account identifiers, broker records, private repository links, or claims that exceed the supporting evidence.
Future entries will be added as reviewed, summary-only commits. No private source code, package archives, credentials, account or broker identifiers, or verbatim private audit logs should be published in this repository.

## 2026-11-21 — CP59.1 V1.2.23 DEMO candidate

V1.2.23 is a broad reliability and observability update. It targets bounded startup work, durable event processing, more consistent market-input delivery, accurate research evidence, and clearer operational status. The changes are intended to preserve existing strategy decisions and risk controls while making slow or incomplete work easier to detect and recover.

### Startup work and EA1 processing

- Split selected startup preparation into smaller timer-driven steps instead of doing all warm-up work on the first market tick.
- Prepared selected indicator/history inputs incrementally and separated large history restoration from unrelated parity checks.
- Restored long-running history in bounded pages; a partially restored state is not exposed as complete before its identity and contents are checked.
- Limited checkpoint preparation to a small amount of work per timer step, reducing the chance that startup housekeeping accumulates into one long callback.
- Added stage-level timing so source reads, history restoration, checkpointing, and selected bot work can be distinguished in later diagnostics.
- Added a narrowly scoped same-bar reuse path for repeated calculations. It applies only when the bar, revision, quote, and restored context match; changed or pending inputs still take the normal evaluation path.
- In a fixed 900-tick / 90-ack fixture, repeated history requests fell from 899 to 181 while the complete event and state trace remained identical. This is a controlled regression result, not a live-terminal latency guarantee.

### Durable HYBRID event processing

- Moved selected shadow/research event persistence out of repeated synchronous tick-path database commits and into a durable queue for later ordered processing.
- Retained full durability requirements: events are not acknowledged or exposed as committed until the database transaction has completed and the stored state has been checked.
- Preserved FIFO event ordering, cursor progression, compare-and-set identity checks, rollback behavior, and restart recovery across the queue-to-database boundary.
- Kept the active execution path's existing paper-before-execution ordering; the queue change does not add trading permissions or change order-routing rules.
- In a fixed comparison, 1,800 event commits were reduced to 600 grouped commits with matching table digests. A separate 6,406-input fixture recorded a tick maximum of 201.588 ms before and 5.059 ms after for the tested path, with matching event/checkpoint evidence.
- A dense synthetic workload drained its queued events after a forced timer pause, but the timer maximum was 294.879 ms and one physical commit reached 226.254 ms. Synchronous operating-system and database I/O can still produce long tails; strict maximum-latency acceptance was not demonstrated.

### EXIT analysis and health reporting

- Consolidated selected exit overlay, adapter, price, and event writes into an atomic transaction so related results are either committed together or rolled back together.
- Prioritized exact known policy identity over broad scans and divided deferred analytical work into bounded pages.
- Kept queue acknowledgement, dirty revision, and published facts consistent within their transaction; injected write/commit failures must not falsely advance the queue.
- Changed selected health-history collection to copy rows in bounded pages using a cycle-start boundary, so rows arriving during a report do not silently alter that report's input set.
- In fixed fixtures, 384 overlay cases completed with a worst control-step time of 29.344 ms versus 10.085 seconds in the baseline fixture; all compared result, price, and fact records matched. A separate health test processed 48,295 input rows in 382 pages, with matching compared output fields.
- These are isolated database fixtures, not a complete live acceptance test. They do not prove a hard upper bound for database locks, disk flushes, or broker-history calls.

### Original market-input delivery and S-source continuity

- Added a dedicated ordered input channel for eight selected research sources so each original quote and its associated Radar/micro context can be delivered without relying only on a latest-value snapshot.
- Kept the database writer ownership unchanged and tied persisted source heads, evaluation events, exit-lab state, and completion receipts to a single durable commit before acknowledgement.
- Preserved sequence gaps as explicit GAP/unreliable states rather than inventing a missing entry or backfilling an unobserved quote.
- Added restart, wrong-owner/configuration, out-of-order sequence, read/write failure, and acknowledgement-boundary cases to the regression set.
- A controlled 1,000-quote fixture completed with 8,008 source events and all 72 exercised policies consuming the same input sequence. The source step p95 was 78.762 ms; the full callback p95 was 148.763 ms and maximum 190.599 ms, with 10 of 200 callbacks above 150 ms.
- The queue ended empty in the exercised run. The measured maximum and callbacks above 150 ms remain important limits; physical disk behavior and live broker delivery were not proven by this fixture.

### Research evidence: completed negative decisions versus missing evidence

- Added narrowly scoped evidence for genuine completed negative evaluations, preserving the quote/context and source identity used at the time of the decision.
- Kept a real completed “do not enter” decision distinct from missing history, incomplete warm-up, unavailable inputs, failed writes, or an unfinished evaluation.
- Extended selected legacy and historical evaluation paths only after their actual evaluation predicate completed; a successful scan or an empty result alone is not treated as proof of a negative decision.
- Left entry/exit rules, strategy parameters, risk limits, and broker actions unchanged in these evidence-only paths.
- In tested fixtures, existing positive-signal counts and full strategy traces remained unchanged while negative-evaluation evidence was added. One historical-source fixture recorded 92 durable negative records from 94 attempts, with two deliberately injected writer failures and a restart check.
- Historical NO_EVAL/GAP coverage is not automatically repaired by these changes; post-install evidence is still needed.

### Historical-input coverage, readiness, and safety presentation

- Expanded the historical input supplied to one selected evaluation observer while leaving its decision kernel, provider, codec, and formulas unchanged; regression comparison reported 204 assertions, with 121 baseline mismatches and zero candidate mismatches in that fixture.
- Clarified selected readiness states, including waiting for the first required higher-timeframe bar, without changing entry gates.
- Separated the historical ARM_NOT_READY rejection explanation from technical errors in the dashboard. This is presentation-only: it does not turn ARM on, change a risk limit, or bypass a rejection.
- Kept HALT, open-position, pending-order, and other blocking conditions higher priority than the informational ARM message.

### File handoff, Telegram polling diagnostics, and resource cleanup

- Added a short read gate for selected status/proof files so a helper does not consume a file while it is being moved or replaced; a failed move does not replace a prior complete file with partial content.
- Added safe Telegram polling failure categories and relevant transport status/time diagnostics without recording tokens or message contents. This helps distinguish rate limiting, timeout, DNS/TLS, and general network errors.
- Added idempotent cleanup for a selected runtime database handle after its users finish, without changing the protected legacy source component.
- These changes improve file/diagnostic reliability; they do not prove delivery to an external Telegram recipient or end-to-end broker execution.

### Build and acceptance status

- The package recorded 12 program build/equivalence receipts: seven affected programs were rebuilt and five unchanged binaries were checked against their prior receipts; the aggregate report showed zero errors and zero warnings.
- The overall package still records `release_ready=false` and `PUPRIME_DEMO_PENDING`. Required live gates include a one-hour DEMO run, a full UTC-day health check, clean-machine helper startup, and end-to-end message acknowledgement.
- A dense HYBRID fixture still reached 294.879 ms timer maximum; the S-source fixture had a 190.599 ms callback maximum and 10/200 callbacks above 150 ms. Those results are not hidden by functional regression PASS results.
- The package's deployment/publication flags are not equivalent to a completed runtime acceptance. ARM remains off/manual; this is not LIVE authorization.
- No primary broker statement for the reviewed week was available in the analysis, so no weekly trade count or P/L is asserted. Offline fixtures are not real trading results.

**Status:** DEMO candidate only. Targeted offline regressions provide evidence for specific paths; full live acceptance, performance thresholds, and weekly profitability are not claimed.
## 2026-11-22 — CP59.1 V1.2.24 DEMO candidate

V1.2.24 continues the CP59.1 work with a focus on reliable S8 input recovery, exact health-packet publication, bounded EA1/EA2 maintenance, and clearer readiness diagnostics. It is a DEMO candidate, not an accepted live release: targeted native tests cover specific cases, while the full live acceptance gates remain open.

### S8 input reconciliation and file-race handling

- Addressed a race in which an input filename discovered during directory enumeration could disappear or change before the corresponding read/move operation completed.
- A missing ready-file state is reconciled only when the canonical retired packet, exact prior acknowledgement, and durable database receipt all agree. A present but corrupt ready packet is not bypassed by silently reading a fallback file.
- Missing, conflicting, or incomplete evidence remains blocked for recovery rather than being treated as an acknowledged event.
- Preserved the existing age/GAP behavior; the change does not create retrospective entries, alter event times, or broaden the input time window.
- Isolated native MT5 regressions recorded 187 race checks, 10 cold-start preparation checks, and 269 recovery checks passing.
- A separate S8 load test did not pass: it processed 133 of 150 planned inputs, reached a queue peak of 20, recorded p95 of 152.595 ms and maximum of 160.328 ms, and missed three load criteria. Functional race/recovery passes do not erase this throughput result.
- The post-install one-hour live test of all eight clocks remains outstanding.

### Health packet publication: exact UTF-8 bytes

- Corrected a mismatch between character counts and bytes written when line endings are converted from LF to CRLF. Previously, a one-byte discrepancy could prevent a temporary health packet from being validated and published.
- Routed full-alert and summary packet publication through a shared byte-accurate path that checks the actual UTF-8 bytes before and after the final file operation.
- In the documented comparison, the baseline published 0 of 4 packets while the candidate published 4 of 4 ASCII/UTF-8 fixtures. The native reader also accepted a packet after checking its owner, digest, timestamp, and complete alert list.
- This fixes packet-file publication; it does not add Telegram alert throttling or establish external message delivery.

### EA1 timing coverage and narrow checkpoint optimization

- Added stage/callback timing for selected restored bots, hybrid work, shadow observation, checkpoints, and Radar stages so future slow intervals can be attributed to specific work.
- Kept canonical state generation and the persist/flush/read-back/rename/error sequence in place; reuse is permitted only for an identical verified path and canonical payload, with bounded cache size.
- In a fixed 200-state fixture, repeated SHA calls fell from 400 to zero while canonical states were still generated 200 times in both versions. A checkpoint fixture's SHA count fell from 427 to 9, and 96 exercised T038 branches retained their event order and state.
- Two small 200-call timing samples were 37.884 ms and 30.948 ms. They are fixture measurements, not a production benchmark or proof of a live speed-up.
- Live EA1 tick/timer/copies54 limits were not revalidated. The stated copies, timer, and callback targets remain acceptance gates, not achieved results.

### EA2 paper-cost maintenance, Brain Office retry, and Legacy-S paging

- Split selected paper-cost work into bounded stages for row discovery, close matching, quote/history resolution, and result/cursor publication.
- Persisted progress only for fully decoded eligible rows; a true read failure must not advance the durable cursor. Slow history requests receive a bounded retry delay without changing selection order.
- Retried a prepared Brain Office publication using its original immutable bytes and quote/time context, with a limited retry rate. A changed owner, run, database, or generation invalidates stale pending content; partial packets are not published.
- Changed selected Legacy-S directory inventory work to process at most 128 names per slice while retaining a complete sorted inventory. Incomplete inventories are discarded, and empty-directory results are distinguished from scan errors.
- The native fixture read 300 names in bounded pages and checked empty/error distinctions, deadline behavior, restart, and cursor/commit failure handling. Targeted builds recorded zero errors and warnings.
- Synchronous history/database operations can still exceed a cooperative deadline while inside the operating-system call. EA2 p95, maximum, and OnTick service targets were not established by these fixtures.

### Readiness and diagnostics

- Clarified the selected waiting-for-first-H1 status and exercised first-bar, stale-quote, missing-history, pending-order, no-signal, and closed-market cases without changing strategy gates.
- Distinguished an empty S inventory from a directory/search failure, reducing the risk that a diagnostic “nothing found” is confused with a successful scan.
- Improved Telegram polling diagnostics with safe failure category, transport status where available, and timestamp. Tokens and message contents are not written into the diagnostic record.
- These telemetry changes do not implement a HEALTH_ALERT rate limit. A later review identified requested alert-throttling and more precise risk-rejection labels as follow-up work; those items are not V1.2.24 fixes.

### Build evidence and remaining gates

- The build record covers 12 program targets: four affected programs were rebuilt and eight unchanged binaries were checked against the prior version's receipts. The reported aggregate is zero errors and zero warnings; it does not mean all 12 were rebuilt.
- The package remains `release_ready=false`, `runtime_validation=PUPRIME_DEMO_PENDING`, and `trading_arm_enabled=false`; deployment authorization is also false.
- No post-install live one-hour S8 acceptance, live quarter-hour EA1 measurement, or EA2 timer/OnTick acceptance is claimed.
- The independent S8 load test missed three criteria. Full performance thresholds, day-long health coverage, helper startup, and external-message acceptance remain unverified.
- No broker statement was available for a validated weekly profit calculation. No weekly P/L or profitability claim is made.

**Status:** DEMO candidate only; offline regressions cover targeted cases, not full live acceptance or LIVE authorization.
## 2026-11-22 — CP59.1 V1.2.25 DEMO candidate

This update focuses on durable event handling, health visibility, and bounded maintenance:

- Refined HEALTH_ALERT change handling and recovery checks so routine packet changes are less likely to create repeated equivalent notifications.
- Preserved explicit uncertainty for sends without a confirmed receipt; uncertain items are not treated as delivered or blindly retried.
- Improved S8/Lab GAP aggregation and restart reconciliation to reduce duplicate continuity facts while retaining historical gaps that cannot be proven.
- Added fairer health processing around the raw-data frontier so one not-yet-mature row does not indefinitely block other eligible channels.
- Added source attribution for newly verified rows without inventing provenance for historical rows that lack it.
- Strengthened Radar's durable outbox and same-event revision repair, with commit-before-ACK ordering and bounded failure reporting.
- Added multi-phase IPC acknowledgement and durable cursor checks tied to a specific event and source identity.
- Separated read-only history retrieval work from trading actions.
- Made selected Brain Office TOP, Catalog, and Feed work more incremental and bounded.
- Improved macro-endpoint diagnostics and retry behavior; missing exact market data remains UNKNOWN instead of being replaced with stale data.
- Corrected a Brain Office telemetry check that could classify uninitialized string slots as overflow; targeted native regressions and source review cover this narrow fix.
- Expanded stage-level timing and ownership diagnostics to make slow work easier to isolate.

The package contains targeted offline regressions and a later repair set, but the recorded whole-DEMO window was **NOT_PASS**: EA1 copies peaked at 144.417 ms, EA1 timer at 2,555.612 ms, EA2 p95 upper at 215–230 ms, EA2 maximum at 946.537–958.288 ms, and the full TOP work at 843,250 ms. These exceeded the documented acceptance thresholds. Some old data gaps and a missing exact macro endpoint remain unresolved.

**Status:** private DEMO candidate only; `release_ready=false`, live acceptance remains pending, ARM stays manual/off, and this is not LIVE authorization. No profitability claim is made.

## 2026-11-22 — CP59.1 V1.2.26 DEMO package candidate

This update focuses on recovery correctness, bounded processing, and stronger evidence handling:

- Added crash/restart reconciliation for a derived GAP projection that may have committed before its companion runtime checkpoint was updated.
- Required owner, run, source hash, checkpoint, and lifecycle evidence before retiring or adopting a projected OPEN state.
- Kept unobserved exits, points, excursions, and trading costs UNKNOWN instead of synthesizing historical outcomes.
- Separated the dashboard's current ARM-blocking explanation from older readiness messages; the presentation change does not arm trading or reset risk controls.
- Improved macro worker history for exact-bar recovery and failure transitions, while keeping missing market endpoints explicitly UNKNOWN.
- Reduced repeated EA1 journal/checkpoint serialization only when the complete serialized source state is byte-identical.
- Added EA1 callback/timer stage diagnostics; isolated microbenchmark improvements are not presented as whole-terminal latency acceptance.
- Avoided repeated EA2 persistence writes for an already verified identical payload while retaining mandatory first-write, durable commit, and ACK ordering.
- Added fairer paper-cost queue servicing and separate counts for eligible, covered, waiting-model, and unprovable work.
- Preserved explicit UNKNOWN commission/cost states when no approved model or complete cycle evidence exists.
- Distinguished empty, missing, and failed S-scanner reads; missing ready packets require matching durable completion and commit evidence.
- Restricted one LIVE-to-shadow replay adapter to exact source/run/symbol/quote identity and validated one policy against a frozen native fixture; all-policy parity remains open.
- Added dispatch-keyed replay acknowledgements and recovery across restart/interleaving cases.
- Added TOP/catalog progress safeguards and clearer catalog status accounting; yellow statuses are not counts of confirmed software defects.
- Strengthened release-guard evidence checks and corrected target-count validation for the 13-program certificate.

**Acceptance limits:** the package was not installed, deployment authorization remains false, and no post-install one-hour live acceptance was recorded. Whole-system EA1/EA2 performance limits and the full TOP sweep target remain unproven. Historical gross points are not validated net monetary profit, and no weekly profitability claim is made.

**Status:** private DEMO package candidate only; not LIVE authorization.
