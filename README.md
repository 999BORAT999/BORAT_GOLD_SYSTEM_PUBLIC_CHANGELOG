# BORAT GOLD SYSTEM — public changelog

This repository publishes curated, high-level summaries of project updates. The source code and release packages are kept in a separate private repository and are not published here.

This public changelog does not contain source files, downloadable builds, credentials, account identifiers, broker records, or private repository links. Each entry is reviewed and written specifically for public sharing; private release notes are not copied here verbatim.

## 2026-11-13 — CP59.1 Hotfix 12 DEMO candidate

The latest demo-candidate update focuses on reliability and diagnostics:

- Improved recovery behavior for Brain Office health processing so a stalled item does not prevent other eligible items from being processed.
- Strengthened Research event identity reconciliation and validation of source data before accepting events.
- Added more detailed timing diagnostics around Research and exit-processing stages to help investigate latency.
- Improved handling of pending paper events and their ordering.
- Clarified AutoTrader and Brain Office counts in the interface.
- Refined Telegram PIN timeout handling and period/status messages.

**Historical DEMO result (reported in the audit snapshot):** the weekly summary showed **+166.88 EUR**. The report did not specify the exact week boundaries. This is a historical demo-account figure, is not attributed to Hotfix 12, and is not a forecast or guarantee of future results.

**Status:** DEMO candidate only. This update is not a LIVE authorization or a claim of full acceptance. Performance targets and several interactive terminal, replay, and end-to-end demo acceptance checks remain outstanding. Historical demo results are not a guarantee of future performance.

## Publishing policy

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
