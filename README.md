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

This update focuses on reliability, processing efficiency, and clearer diagnostics:

- Split selected startup, history-recovery, and analysis work into bounded steps.
- Improved durable handling and recovery of queued analysis events.
- Reduced repeated database work in exit-analysis and health-reporting paths.
- Preserved the ordering and context of incoming market-data events for analysis.
- Improved evidence for completed negative research evaluations without changing trading rules.
- Clarified selected readiness and file-publication status handling.

The package includes offline regression and failure-recovery test evidence. These checks do not constitute full live-environment acceptance. Live DEMO timing, day-long health, and end-to-end helper acceptance remain outstanding.

**Status:** DEMO candidate only; not a LIVE authorization or a claim of full acceptance. No performance or profitability claim is made in this entry.
## 2026-11-22 — CP59.1 V1.2.24 DEMO candidate

This update focuses on reliability and diagnostics:

- Improved S8 input reconciliation around file-enumeration and rename races, with isolated restart and recovery regression coverage.
- Corrected health-packet byte validation and verified publication of both full and summary packets in native fixtures.
- Added EA1/EA2 stage-level timing and narrowly scoped checkpoint, maintenance, and retry improvements while preserving tested ordering.
- Clarified readiness, empty-versus-error reporting, and Telegram polling failure diagnostics.

Offline native regressions cover targeted cases only. One S8 journal-load test processed 133 of 150 planned inputs and missed three load criteria. Live DEMO acceptance and performance thresholds remain pending.

**Status:** DEMO candidate only; not a LIVE authorization. No profitability claim is made.

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
