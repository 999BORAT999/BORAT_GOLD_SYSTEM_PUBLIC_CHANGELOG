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



### Detailed change record

**Release identity and scope**
- This is the first recorded CP58 R2 package revision for system V1.1.118, Radar V1.0.120, AutoTrader V1.0.26, and Research 1.0.70. R2 identifies the package revision; it does not claim a new strategy version.
- The handoff included the defined installation payload, prepared application binaries, Research components, project-history and provenance material, and test/guard evidence. Brain Office was not included.
- The package described 82 Research X variants, 13 additional AutoTrader records, and 24 AutoTrader slots. The 13 new entries defaulted to SHADOW; private dependencies were not represented as newly created strategies.

**Installation and state-protection work**
- The installer was designed to check the package identity before copying only the declared deployment tree, create a backup of program files, and leave an installation receipt.
- The documented installation flow distinguished copying files from attaching/restarting an Expert in the terminal. The installer did not change account configuration, risk/lot stores, user result databases, Algo Trading, or ARM.
- Prepared binaries were included so normal use did not require a source rebuild; the separate guard/audit workflow had its own runtime requirement.

**Evidence and limits**
- The delivery record reported 32/32 release-build checks and 10/10 installer-contract checks; additional recorded evidence included 47 MQL fixtures, 22 Python contract tests, 24 local database checks, SQLite integrity, and export scenarios.
- WIN/LOSS/FLAT labels in fixtures were synthetic test cases, not real trading outcomes.
- No owner terminal deployment, complete historical market replay, broker fill/reject campaign, long-duration performance campaign, or profitability evidence was established.

**Status:** archived DEMO handoff; not LIVE authorization or a profit claim.

## 2026-10-26 — CP58 R3 package revision

R3 republished the full CP58 handoff with stronger package-level consistency checks. It is a package revision, not a separate strategy release.

- Preserved the approved 141-file deployment payload and confirmed that its recorded file digests matched the prior accepted package contents.
- Retained the application, research, project-history, guard, and verification material needed to reproduce the handoff; no new trading algorithm change is claimed for R3.
- Recorded 48/48 package checks and a successful installer run in a temporary test target. The test target was isolated; the owner's MT5 installation was not changed.
- Earlier integration receipts remained reference evidence rather than a new R3 live-market test.
- Live installation, broker order scenarios, long-duration load, and strategy profitability remained unverified.



**R3 — package consistency revision**
- Retained the V1.1.118 CP58 component identities and the same approved 141-file installation payload; R3 was explicitly a packaging/integrity revision, not an algorithm update.
- Preserved the application source and binaries, Research material, project records, guards, and verification evidence. The 141 installation files were compared to the accepted package by recorded digests.
- Recorded 48/48 package checks and a successful installer run against a temporary target. Earlier integration receipts were reference evidence rather than a new R3 live-market run.
- The temporary target did not change the owner's terminal. Market replay, broker execution, and long-duration performance were not established.

**Status:** package-integrity revision only; not a live acceptance.

## 2026-10-26 — CP58 R4 recovery hotfix

R4 addressed a narrowly defined recovery case in which a valid empty initial state could be rejected and leave selected research modules waiting. The underlying origin of the original empty-state record was not established.

- Allowed recovery only for the specifically validated empty-start condition; other empty, malformed, or conflicting state remains blocked rather than being accepted broadly.
- Preserved the original state record for audit and avoided replacing it with a synthetic timestamp or overwriting prior evidence.
- Improved diagnostics for storage failures while preserving the distinction between an actual open position and an unavailable or uncertain state.
- Left strategy entry/exit rules, filters, identities, risk settings, and default shadow behavior unchanged.
- R4 changed a small, defined portion of the deployment payload; the remaining files were checked against the prior package. Targeted evidence included 57 contract tests, 27 isolated MQL checks, successful host/popup compilation, and an independent focused review with no critical or major findings.
- Testing used isolated local data. No live account, broker order, full market replay, or long-running performance acceptance was performed.



**R4 — narrowly scoped empty-state recovery fix**
- Addressed a recovery failure in which a specifically valid empty initial checkpoint could cause selected Research modules to remain waiting. The underlying origin of the original empty checkpoint was not proven.
- Limited the exception to a precisely validated initial-empty case, including schema/content checks and the absence of relevant position/order/entry state. This was not a general permission to accept zero timestamps or damaged state.
- Preserved the original checkpoint as audit evidence; did not synthesize a replacement time or overwrite historical evidence. A subsequent genuine market update followed the normal checkpoint path.
- Improved storage-failure reporting and retained the distinction between an actual open position and uncertain/unavailable state. Other established modules and strategy rules were left unchanged.
- Targeted evidence included 57 contract tests, 27 isolated MQL checks, successful host/popup compilation, and a focused independent review without critical or major findings.
- Tests used isolated local data; no live account, broker order, full market replay, long-duration load test, or owner-terminal installation was part of R4 acceptance.

**Status:** targeted recovery correction; not a LIVE or profitability certification.

## 2026-10-28 — CP58 R5 infrastructure update

R5 concentrated on operator settings, durable risk and order records, research data handling, export reliability, and safer installation/rollback. The release notes state that the established strategy entry/exit logic was retained, with persistent risk accounting identified as the intentional behavior change.

- Updated the settings interface with clearer global/per-module views, draft/apply/reset handling, and bounded display controls.
- Made peak/drawdown and emergency blocks persist across restart. When required risk state cannot be trusted, new entries remain blocked until the owner initializes or verifies the reference; apply, restart, or arm actions do not silently clear the block.
- Improved order/event bookkeeping and recovery so records are tied to the corresponding position evidence. Uncertain historical order outcomes remain uncertain instead of being reconstructed as facts.
- Added provenance-aware research storage and a separate export workflow using a consistent database snapshot, with explicit partial-versus-complete export status.
- Strengthened package verification, backups, rollback checks, and recognized-installation handling without modifying retained user databases or terminal profiles.
- Evidence recorded 116 automated test cases and 229 native fixture checks, along with compilation and focused infrastructure review. The live terminal deployment status remained not installed; long-duration performance, full market replay, and broker order scenarios remained open.



### Detailed change record

**Settings and safety state**
- Added clearer global-versus-module settings presentation, AUTO/FIXED selection, draft/apply/reset behavior, and bounded display scaling/scrolling.
- Persisted peak/drawdown and emergency blocks across restart. If a valid risk reference or durable accounting state cannot be established, new entries remain blocked; applying settings, restarting, or arming does not silently clear the block.
- Kept the protected execution rules and module identities stable; the release identifies persistent risk accounting as the intentional behavior change rather than a strategy formula rewrite.

**Order and Research data handling**
- Improved execution journaling, event queues, CSV recovery, and position-history audit linkage so records can be reconciled to position identity.
- Left unclear historical order attempts and rejects unresolved; R5 does not invent an OrderSend outcome or claim to reconstruct missing broker facts.
- Added provenance-aware Research storage and indexing/recovery tools. Large exports use a consistent database/WAL snapshot and distinguish PARTIAL from COMPLETE; COMPLETE applies only to that particular export slice.

**Installer, backup, and operational boundary**
- Added package manifest/SHA checks, pre-install backups, recognized legacy-program archiving, and rollback verification.
- The installer was designed not to alter user Research databases, Common/Files results, or MT5 profiles.
- Included helper/export workflow guidance; helper execution was not a Windows service and required its own launch/configuration.

**Evidence and limits**
- The package recorded 116 automated test cases and 229 native fixture checks, plus build receipts and focused infrastructure review.
- At release time the owner's terminal was marked NOT_INSTALLED. Long-duration performance, full market replay, new-bot broker order scenarios, complete historical backfill, and profitability were not established.
- Known data-volume, historical RAW/WAL gaps, unfinished backfill, and a possible delayed overlay-seed concern remained disclosed follow-up work.

**Status:** infrastructure and workflow update; not LIVE authorization or a profitability claim.

## 2026-11-02 — CP58 R6 DEMO package (owner-exception status)

R6 expanded research integration and state restoration while documenting where original strategy behavior, virtual research, and broker execution must remain distinct.

- Expanded the catalogue of research and shadow integrations and improved precision and decoding for selected persisted states, caches, and profiles.
- Restored selected original modules and added separate research-cycle handling; where pricing, quantity, fees, feed, or native parity evidence was missing, the result remained explicitly unknown or not run.
- Kept signal studies and virtual exit analysis separate from confirmed broker trades; a research signal is not described as an order fill.
- Improved durable exit-analysis/database handling and persistence checks, including restart-related fixtures, while leaving broader history-route and whole-host acceptance as separate gates.
- Added two infrastructure hotfix iterations to reduce repeated encoding work and correct selected routing behavior without changing the recorded file format or integrity checks.
- Package integrity was checked against its internal manifest. The release decision retained an owner-exception status, and important gates remained open: native parity, complete market replay, recovery under real terminal restarts, performance/canary monitoring, migration rollback, and final clean-install acceptance.



### R6 — integration, state restoration, and Research boundaries

- Expanded the catalogue to document 54 NEW BOTS integrations, 69 Research copies, and 80 of 82 eligible original-work integrations (203 integration records in total, including state-only records). The remaining named work was explicitly deferred; it was not counted as an R6 feature.
- Corrected 14 typed-state formats to retain IEEE-754 64-bit precision and reviewed identity mapping across original, hybrid, and S-source families.
- Corrected cache/profile decoding for 20 original cache fields across seven adapter families and clarified why selected STATE/PROFILE records are generated. Strategy formulas and the documented persistence format remained unchanged.
- Restored selected original sources and attached separate H1/PAPER research cycles. For selected modules, unit, quantity, fee, data-feed, and native-parity assumptions stayed UNKNOWN/NOT_RUN where evidence was unavailable.
- Added separate source-study and exit-analysis paths: selected original indicator signals and class-0 exit research were not treated as native orders or broker fills; original direction/reversal behavior was retained where applicable.
- Preserved explicit limitations for studies derived from completed bars: incomplete OHLC/volume, missing bars, timing, and feed evidence were not converted to proven live parity.
- Added EXIT Lab class-0/class-2 and selected D5 persistence work, with isolated SQLite compare-and-set, acknowledgement, default-off, and close/reopen read-back checks. Full host/restart and private cold-history route acceptance remained open.
- R6.1 routed selected D5 work to its actual database path and deferred live signal-hypothesis routing to limit load; journal evidence remained, but Research presentation could be delayed.
- R6.2 changed large state-packet HEX encoding to reuse a preallocated buffer while retaining file format and digest checks. Slow Research stages were still to be measured.
- Preserved parent/history copies and append-only records; the sole deployment tree remained defined and release integrity was checked against a manifest.
- The release decision was OWNER_EXCEPTION, not unconditional acceptance. Native runtime parity, full market replay, recovery under real terminal restarts, performance/canary monitoring, migration rollback, all source-order requirements, and clean-install acceptance remained open.

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



### R7 — separate trading authority from Research processing

- Kept Radar, UI, AutoTrader mode, native entries/exits, risk controls, order handling, and operational checkpoints with the primary execution owner; Research and EXIT Lab ran in a separate worker without broker-order authority.
- Split database ownership: the primary component used a small owner-bound operational database and read legacy Research history read-only; the Research worker remained the sole writer for its designated Research database.
- Added durable transport for broker facts: source-side persistence, owner/generation/hash validation, destination transaction, receipt, then acknowledgement. Unacknowledged facts remain queued; they are not deleted, renumbered, or acknowledged before destination commit.
- Kept Radar context and broker facts on distinct channels and added deduplication, leases, worker bootstrap retry, duplicate-worker policy, and restart recovery checks.
- Restored and checked 78 unique module checkpoints and the recorded 18 ACTIVE / 60 SHADOW mode snapshot without bulk-clearing individual HALTs.
- Defined downtime as a Research GAP; affected virtual cycles and EXIT windows are marked unreliable with NULL outcomes. AutoTrader broker cycles are not converted into Research gap losses.
- Corrected bounded UTF-8 read-back validation for the handoff path. A recovery test delivered 9,379 rows and reconciled both databases through the same confirmed cursor.
- Recorded acceptance was 136 PASS out of 141 entries, with five prior architecture checks marked obsolete/not applicable; both components compiled with zero errors/warnings.
- The 200 ms tick and 250 ms timer goals were not met; one-hour queue observation was cancelled. No physical second-worker acceptance, full live order campaign, ARM-enabled trade, or complete live performance acceptance was established.

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



### CP58 R8 — execution safeguards, Research evidence, and operations

**Execution and risk handling**
- Added bounded retry and recovery for selected transient I/O failures without allowing a diagnostic event to erase a genuine HALT. Exposure-related recovery remains blocked until position/order identity is reconciled.
- Strengthened EMERGENCY behavior so ARM is disabled and pending entries are cancelled even when no position is currently open; the existing position-close path remains responsible for exposure reduction.
- Reconciled stale pending orders only after checking broker evidence; a found trade is adopted and remains risk-accounted rather than being treated as absent.
- Included open-to-stop and reserved exposure in daily/weekly loss budgeting, and validated the intended ordering of total risk, daily loss, and weekly loss limits.
- Distinguished manual/operator close from emergency close; manual close does not silently change a module's ACTIVE/SHADOW mode.
- Added weekend close handling for long session gaps while avoiding an ordinary daily market break being mistaken for a weekend. Existing Radar NoCarry behavior was not changed.
- Kept unknown account positions/order risk fail-closed and preserved position ownership checks.

**Research, timestamps, and EXIT Lab**
- Added UTC quality markers for new Research timestamps. If server-to-UTC mapping could not be verified, the timestamp was marked uncertified instead of labeling server time as UTC; old records were not rewritten.
- Added modeled costs/net points to eligible new exit records, but left historical cost fields NULL where spread, fee, time, or other evidence was missing.
- Investigated 28 similar MQ exit variants and documented why many outputs matched under shared stop/target rules; policy regrouping and additional warm-up/replay fixes were deferred to R8.1 rather than claimed as R8 changes.
- Kept GAP_UNRELIABLE and NOT_EVALUABLE states explicit. An observed low sample or absent history was not treated as proof that the underlying strategy was broken or fixed.
- Left the Research bar-event evaluation engine OFF where parity had not passed; added health/readiness reasons instead of enabling unvalidated evaluation.
- Added selected module health summaries for counts, signals, entries, NOT_EVALUABLE reasons, and last signal, without changing mode or membership automatically.

**Data sources, helpers, and operator feedback**
- Added selected calendar/news and macro-data status paths, exact-session/time mapping and DST checks, plus stale-data warnings. External endpoints and scheduled refresh still required owner setup and live confirmation.
- Added helper heartbeat/WORKER_OFF/PARTIAL export reporting, database backup/recovery guidance, storage/capacity and path-length checks, duplicate-message limits, and clearer environment/build readiness.
- Added operator notification modes, quiet-hour handling, and Telegram status/command scaffolding with PIN-protected owner actions. Tokens were not bundled; a real connection and delivery cycle remained untested.
- Clarified module-count, readiness, reason, and version displays. Retired or superseded modules retained identity/history; unknown data lineage was not guessed.
- Documented freeze and single-writer rules to keep AutoTrader execution ownership separate from Research persistence.

**Release evidence and deferred work**
- The package audit recorded 560 deployment files and preserved frozen strategy/source hashes. Compilation, ZIP integrity, manifest, and selected offline regressions were checked.
- Live startup/timer spikes, full UTC-day health, Research gap frequency, warm-up behavior, helper autostart, Telegram end-to-end delivery, ARM-enabled broker scenarios, and full performance limits remained open.
- R8 did not establish profitability or a live deployment. Several evaluation, exit-policy, and installer tasks were intentionally assigned to R8.1.

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



**R8 Hotfix 1 — HALT, close reasons, risk, and installer verification**

- Added a versioned HALT sidecar with backward reading of prior state. The first HALT cause remains immutable for recovery decisions; a newer diagnostic reason cannot mask it. If sidecar/core state conflicts after restart or persistence fails, the system stays blocked.
- Persisted OPERATOR_CLOSE and weekend-close reasons before sending, preserving the original cause across send failure, retry, and restart.
- Changed a missing/unreadable broker ticket from silent exclusion to explicit unknown-position/order risk that blocks new entries. The documented exception for known external positions without stop protection remained separate.
- Tightened health-summary timestamp/freshness checks and removed selected retired entries from active coverage warnings. The audit identified a remaining freshness-threshold concern for quiet modules; this was disclosed rather than claimed solved.
- Hardened installer target identity and reparse-point checks, package/verifier matching, backup selection, rollback receipts, and partial-seed failure reporting. A rollback is not called successful if restoration is incomplete.
- Targeted offline validation included 58 functional regressions, 107 safety checks, health and messaging fixtures, isolated installer/verifier scenarios, and parser/static checks. Seven compiled targets reported zero errors/warnings; no external network delivery or broker execution was proven.
- A later NULL-versus-empty health queue fix was a distinct follow-up, not part of this Hotfix 1 archive.

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



### Detailed change record

**Execution, HYBRID, and multi-part positions**
- Warmed selected Research inputs from terminal history after worker start and used bounded time ranges for delayed events, addressing cold-buffer NOT_EVALUABLE cases without changing the historical evaluation timestamp. The live restart target remained unverified.
- Prioritized native order and stop-protection work ahead of shadow processing, with duplicate-dispatch protections. A documented dispatch latency target remained for live measurement.
- Reduced redundant EXIT Lab evaluation by retiring 24 near-duplicate policy entries and keeping four distinct indicator variants; added three longer gold-oriented horizons, for nine active MQ policies. Historical records were retained and live load reduction was not yet measured.
- Extended weekend close and recovery to all legs and pending orders; release of an exposure halt still required broker position/order evidence. UI warnings described multi-position exposure; a dedicated live multi-leg acceptance was not performed.

**Research accuracy, costs, and readiness**
- Added cautious virtual cost/net-point handling for new and selected historical Research records. Missing lot, spread, fee, UTC, or FX evidence remained NULL/unknown; nominal research currency remained separate from broker-account currency.
- Synchronized selected GAP_UNRELIABLE state changes with corresponding overlays without rewriting or deleting old history.
- Restored a selected time-window evaluation and added explicit readiness/quiet/missing-data/dependency states for selected modules, without changing their signal formulas.
- Added a rolling performance window and clearer EXIT result labels. These diagnostics did not by themselves establish a terminal-wide latency target.
- Added selected news/macro data handling and stale-data notices. Market endpoints remained dependent on owner configuration and actual broker data; unvalidated/missing inputs were not replaced by stale data.
- Classified 11 of 15 selected alert-only modules as Research/EXIT Lab signals without enabling orders or fabricating historical entries; unsupported raw-input paths remained excluded.

**Installation, operations, and preservation**
- Added fresh-install/upgrade/repair identification, safer plan-only checks, bounded directory handling, backups/retention, generated catalogue cards, and explicit handling for state and database identity.
- Kept existing module identities and protected core sources where required; default fresh-install state remained shadow/off rather than active trading.
- Added a plan-only deployment report that described file changes and retained user data without modifying the target. It was not a deployment receipt.
- Preserved project history and documented a known mismatch between some embedded package documents; the archive itself was not silently rewritten to conceal that mismatch.

**Verification and limits**
- Recorded 8/8 compilation targets with zero errors/warnings and extensive offline/source/package checks, including installer plan-only and bounded worker tests.
- Not performed: clean-machine runtime acceptance, installation into the owner terminal, one-hour event/acknowledgement run, full-day health coverage, live calendar/macro retrieval, broker multi-leg/SLTP test, full Research parity, complete performance campaign, or full DEMO week.
- TOP/EXIT numerical parity remained unvalidated; unavailable costs and historical gaps stayed unknown. This was not a profitability or LIVE certificate.

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



### Detailed change record

**Architecture and catalogue growth**
- Introduced Brain Office as a separate user interface/data component alongside the primary AutoTrader owner and a non-trading Research worker. Compatibility identities and existing database/IPC contracts were retained for the transition.
- Added a catalogue/slot layer with identity/version tracking, default shadow state, deduplication, risk/ARM checks, facts, and durable outbox handling. Unsupported adapters return an explicit blocked/unsupported reason rather than appearing fully executable.
- Expanded adapter coverage in audited stages: 163/314 initially, 193 after the first implementation pass, 195 after a narrow source correction, 309 during grouped integration, and 316/316 catalogue identities in the final package. This is catalogue/adapter coverage, not 316 live-approved or active strategies.
- Final classification documented 314 potential active-capable adapter paths after parity and risk guards and 35 original active paths. These counts do not represent live enabled strategies or broker trades. Current activation still depends on locked exit policy, sufficient Research parity, fresh source/model state, risk/exposure checks, and owner-controlled ARM.
- Added exact variant/source identity checks tying version and source digest to the selected adapter; multi-part records distinguish Research trade IDs from broker-position IDs and reserve risk across legs.
- Added explicit parity thresholds and pending states for insufficient samples. Empty evidence does not grant parity; selected module families remain intentionally unsupported or blocked until their required context exists.

**Initial audit fixes and staged adapter work**
- Refactored supported Brain Office entry requests through the shared AutoTrader dispatch path, retaining the existing order checks, ARM, slot switch, price, and risk gates. Owner intent/facts are recorded around execution and reconciled with the result.
- Added bounded timing for Research evaluation and 16 named EA1 timer stages so slow work can be attributed rather than reported as one undifferentiated delay. This instrumentation does not make synchronous work asynchronous.
- Corrected a narrow source-extrema calculation for four owner-approved profiles using prior completed bars and sufficient history, while leaving other profiles and identity records unchanged. Isolated tests exercised 2,000 OHLC sequences; live restart/first-signal behavior remained open.
- Added slot-state codecs, exact source/version variant tables, and restart-time identity validation before restore/reconciliation.
- Added multi-leg books with separate trade/position/exit identities and reserved-risk checks before each leg. Selected partial-exit paths require a locked exit policy.
- Added model/source publication with digest checks and stale-state blocks. A stale model or incompatible restored state cannot silently authorize an active entry.
- Added bounded work and per-tick scan limits; the 100-slot timer/tick budget was left for live measurement.
- Completed selected S-family counterfactual capture, Quantum handoff, and a B033x adapter while retaining exact source context and refusing malformed linkages. These produce research/evidence records, not automatic broker orders.

**Data ownership, feed, and analysis**
- Added separate Brain Office feed, open-state, inbox, version, and acknowledgement records with a single-writer rule per database. Research data and seed inputs are read-only to Brain Office; mismatched database identity is rejected.
- Added catalogue cards, filters, period selection, comparisons, curves, sessions/heat views, and CSV export. Open exposure and cross-currency totals are shown only when supported by evidence.
- Added incremental TOP and EXIT Lab jobs, paired-exit evidence checks, and active-policy gates. Numerical outputs remained explicitly unvalidated pending real Research parity.
- Added cautious virtual-currency estimates. Without verified stop, position size, FX, or fee inputs, the monetary result remains NULL/unknown and is never represented as broker-account profit.
- Added durable owner-command and acknowledgement handling; Brain Office can request supported actions but is not itself a broker-order executor.
- Added feed triggers/revisions and replay separation; Brain Office reads the Research source rather than becoming a second writer to the Research database.

**Risk, lifecycle, history, and operator controls**
- Added state capture/restore, identity checks, restart handling, multi-leg risk reservation, and safeguards for stale model or source state. An unsupported or stale path blocks rather than authorizes an entry.
- Added status/health alerts and explicit reasons for blocked or unsupported paths. Dashboard READY and catalogue eligibility are not execution authorization.
- Added database backup/temporary-file retention and generated catalogue documentation. A plan-only installer mode describes expected changes without applying them.
- Preserved owner-supplied provenance and project history. The distribution was prepared as a separate redacted copy where needed; this public note does not reproduce any private values or archive detail.

**Verification and limits**
- Recorded 8/8 compilation targets with zero errors/warnings and extensive isolated source, database, adapter, and package checks. A stress fixture tested 20,000 feed writes; it is not a live-terminal performance benchmark.
- A large seed rehearsal processed an 812 MB fixture; 38 of 39 recorded checks passed, with the remaining exception explicitly tracked for final seed-time validation. The canonical seed itself was not generated as part of live installation.
- A plan-only deployment report was generated against the existing target and confirmed that the target was not modified; this was not an installation receipt.
- Catalogue counts and isolated adapter tests do not establish strategy parity or profitability. TOP/EXIT remained unvalidated; missing historical inputs and unsupported adapters remained blocked.
- The package was not installed into MT5. Seed takeover, clean-machine startup, terminal UI behavior, broker order handling, multi-leg recovery, full-day health, 100-slot latency targets, and a complete DEMO week remained unverified.

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



### Detailed change record

**Lifecycle, state, and execution safety**
- Made selected popup mode/status parsing tolerant of additional health fields so newer metadata does not break existing mode detection.
- If a module's required counters cannot be read, temporarily block its new entries and retry after readiness; persistent failure gets a distinct HALT reason. When verified data recovers, the associated halt marker is archived rather than silently removed.
- Enforced the required chart context and reset selected startup lifecycle markers on initialization. Added a narrow entry guard while preserving the existing execution core and multi-control behavior.
- Kept the existing database, IPC, state, and identity contracts so this handoff could continue from the prior CP59 package.

**Operator interface and catalogue**
- Improved display of multi-leg position/risk details, versions, module groups, market state, and module status.
- Allowed operator close only when broker-position ownership can be verified; separated a normal market veto from a technical failure and preserved identity during manual close.
- Expanded Brain Office catalogue cards with concise identity/version information and a detail view for module/result context.
- Corrected selected date-period response and source-switch reload behavior; added the additional source choice to the UI contract.
- Made technical-card responses appear in the card and made CSV export feedback identify the output result and row count.
- In a database query fixture, a selected curve query changed from 0.223 s to 0.027 s after an index addition; this isolated measurement does not establish live dashboard performance. Demo UI/DB fixtures also exercised analytics, EXIT, settings, and persisted star state across reload.

**Installer and provenance**
- Reused the same writable-target preflight in plan-only and install modes and avoided applying deployment-file length constraints to retained databases.
- Made optional helper autostart non-blocking when elevated permissions are unavailable; the skipped action is recorded in the plan.
- Preserved owner-source provenance and used a separately prepared redacted distribution copy where required; sensitive values are not repeated in this public summary.

**Build and remaining acceptance**
- Recorded 8/8 compilation targets with zero errors and warnings; selected popup contracts and read-only database checks passed.
- The package was not installed. Source switching, interactive close/deactivate on a valid demo position, all chart transitions, new index behavior in the live terminal, broker execution, and complete DEMO acceptance remained open.
- ARM and installation authorization remained separate owner decisions; this handoff was not LIVE authorization or profitability evidence.

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



### Additional cumulative history detail

The release also carries forward a long CP59.1 hotfix history. These are historical work areas, not a claim that every earlier item was newly changed or live-accepted by HF12:

- **Early HF1–HF2:** expanded Brain Office catalogue/analysis/coverage and CSV flows; refined EA1/EA2 status and timing, RAW-storage repair guidance, and PIN/ARM confirmation UX. Restoring evidence gaps did not fabricate historical trades or outcomes.
- **HF3:** improved catalogue/shadow result distinctions, durable paper-entry/close linkage for selected modules, and Research source/version identity. Some historical lineage and one EXIT Lab input contract remained limited.
- **HF4:** tightened one selected shadow-to-order path's symbol, execution-price, stop, lot, and risk checks; separated an AutoTrader close from a virtual Research cycle. Broader natural-cycle acceptance remained a live test.
- **HF5/HF5.1:** refined Radar readiness, paged shadow history, retained table headings during scrolling, aligned OPEN/CLOSE message wording, and improved observer restart and one-time warning behavior. Desktop Telegram, autostart, and new broker-cycle tests were still outstanding.
- **HF6:** strengthened daily summary validation and quiet-time messaging, improved macro-history recovery, introduced a separately identified shadow prototype, and added selected Research identity, indicator-refresh, market-pause, and readiness states. Prototype output was not treated as a broker result.
- **HF7:** improved multi-version catalogue search, paged historical reads, and explicit PAPER/WAITING versus unverified-data states. An isolated database recovery restored 64 selected states while labeling cache-recovered records distinctly; this was not a live-terminal recovery campaign.
- **HF8–HF11:** expanded replay identity/checkpoint handling for selected historical evaluations; continued classifying UNKNOWN/STALE/WAITING-FOR-BAR and dependency states; added delivery and scheduled-worker recovery checks. Some replay/checkpoint reconciliation and long-term readiness work remained open at HF12.

### HF12 acceptance details

- The archived package and deployment manifest were checked for integrity; the report recorded 692 deployment files matching the inspected terminal installation. This is a package/file comparison, not proof of post-update trading acceptance.
- Recorded builds showed zero errors/warnings for the popup and selected core targets; the Research build had one sign-mismatch warning. The release is therefore not described as an all-target 0/0 compile.
- A broker-history export was recorded as complete for a historical snapshot, but its results are not attributed to HF12 and are deliberately not used here as a weekly profitability claim.
- The audit retained unresolved multi-second work stages, a performance target shortfall, replay/history items, post-update UI scenarios, external-message receipt, and a fresh broker OPEN/CLOSE cycle. These remain acceptance items, not completed features.

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



### Detailed change record

**Telegram alert identity and delivery uncertainty**
- Refined HEALTH_ALERT change detection so semantic health changes are distinguished from routine packet revisions; equivalent notifications are less likely to repeat unnecessarily.
- Kept delivery states explicit: an attempt without a confirmed receipt remains UNCERTAIN, neither delivered nor safely retryable. Recovery checks occur before an old state is finalized.
- Prevented a later recipient-configuration change from silently retargeting a previously attempted message. An uncertain old message is not blindly sent again to a different destination.

**S8/Lab continuity and health fairness**
- Improved GAP aggregation and restart reconciliation to avoid duplicating continuity facts while retaining gaps whose original evidence is missing.
- Added fairer handling of raw-data frontiers so one not-yet-mature row does not indefinitely block other eligible channels.
- Added source/owner attribution for newly verified rows. Historical rows with missing provenance are not backfilled with guessed identity.
- Preserved event time, cursor, and historical decision windows; did not clear a cursor or widen an acceptance window merely to make coverage appear complete.
- Kept Research SIGNALs distinct from other system decision counts and preserved GAP/UNKNOWN markers.

**Radar outbox, IPC, and history access**
- Strengthened durable Radar outbox behavior: persist exact event identity/content, commit before acknowledging, and reconcile a newer revision of the same event without creating a duplicate event.
- Added multi-phase IPC acknowledgements and durable cursor checks tied to a specific event and source identity.
- Separated read-only history retrieval from trading actions. History retrieval does not gain order or position-management authority.
- Kept bounded failure reporting and explicit uncertainty when persistence or acknowledgement cannot be verified; a limited in-memory queue is not claimed to survive every disk failure.

**Brain Office, macro data, and diagnostics**
- Made selected TOP/Catalog/Feed work more incremental and bounded, with clearer stage/ownership timing to isolate slow work.
- Improved exact-bar macro diagnostics and retry behavior. Missing or stale endpoints remain UNKNOWN instead of being replaced with an older bar.
- Corrected a narrow telemetry condition where an uninitialized string slot could be confused with overflow; targeted native RED/GREEN fixtures and source review covered this behavior only.
- Preserved existing historical gaps and did not relabel incomplete records as fully covered.

**Measured acceptance status**
- The recorded whole-DEMO window was NOT_PASS: EA1 copy maximum 144.417 ms, EA1 timer maximum 2,555.612 ms, EA2 p95 upper 215–230 ms, EA2 maximum 946.537–958.288 ms, and full TOP work 843,250 ms. These exceeded the documented gates.
- Targeted offline regressions and later repair fixtures do not erase the failed whole-window result or establish a full UTC-day health pass.
- Some historical data gaps and a missing exact macro endpoint remained unresolved. No weekly P/L or profitability claim is made.

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



### Detailed change record

**B001x cost provenance and non-fabricated outcomes**
- Kept a specific historical cycle CLOSED with its recorded gross points, but retained modeled net monetary outcome as UNKNOWN because confirmed size, FX, commission, swap, and fee evidence was incomplete.
- Required stable cycle identity, an approved model identity, complete cycle inputs, matching content digests, and a durable proof/host receipt before accepting a modeled cost result.
- Conflicting content for an existing cycle is rejected; an identical repeat is idempotent. Missing inputs do not cause the system to invent a new model or monetary result.
- Native fixtures covered incomplete/foreign evidence, conflicts, restart, and a synthetic negative cooldown case. Synthetic points are test data, not market performance or a weekly P/L.

**B033x derived GAP/OPEN projection recovery**
- Addressed a crash window where a database projection could commit before its companion runtime checkpoint advanced, potentially leaving an orphaned OPEN state after restart.
- Reconciliation now binds owner, module/version/source identity, old/new run, native lifecycle event, GAP content, checkpoint and digest evidence; transaction-level uniqueness/revision/content checks run again before commit.
- Recovery can retire only the exact prior projection supported by matching evidence. Missing, mismatched, partial, or conflicting proof stays RECOVERY_PENDING instead of being overwritten or accepted.
- If a native close is proven but its full observation is not, the state is explicitly NATIVE_CLOSED_UNOBSERVED; unknown exit, points, excursions, win/loss, and costs remain NULL.
- The recorded native matrix included first-process, ordinary restart, and controlled process interruption between database commit and checkpoint update, plus close/replacement, rollback, false evidence, HALT, and exposure conflicts. These are targeted crash/recovery fixtures, not a live-market acceptance.

**Current ARM explanation and macro history**
- Separated the dashboard's current blocking reason from retained historical ARM_NOT_READY text. This changes presentation only; it does not arm trading, change risk limits, reset emergency state, or alter orders.
- Improved macro worker history with bounded trace records, owner/path/content validation, and explicit recovery/failure transitions.
- Required the exact closed market bar for READY. A missing, stale, or approximate endpoint remains UNKNOWN; the system does not substitute the last available bar.
- Deterministic fixtures reproduced and then covered incorrect READY history, stale targets, synchronization/copy failures, restart, and multi-symbol fairness. Actual broker endpoint timing was not established.

**EA1 serialization and timing**
- Reduced repeated serialization only when the complete fixed-format source state, sequence, signal context, and run identity were byte-identical. Dynamic broker guards, actual entry, and changing close state are still regenerated.
- Preserved per-leg state while reusing only the common group journal for a narrowly defined multi-call path.
- In a 3,072-call fixture, the recorded ENTRY/CLOSE/revision decisions and unchanged-state count were preserved; a separate 8,000-packet comparison and restart trace were also checked.
- Isolated T043/T038 microbenchmarks reduced repeated serialization work, but are not whole-terminal tick/timer SLA evidence. Added callback/timer stage measurements for bot processing, history reads, source journals, packet comparison, and duration.

**EA2 persistence, PAPER_COST fairness, and scanner semantics**
- For a verified identical persisted payload, checked the exact existing bytes before retrying instead of repeating hashing/temp-write/flush/rename. The first durable write and commit-before-ACK rule remain mandatory; changed or damaged content returns to full persistence.
- Fairer PAPER_COST service separates new records from historical backfill and tracks eligible, covered, waiting-model, unprovable-pair, and unprovable-cost work independently.
- Preserved COMMISSION_UNKNOWN/NULL when no approved fee model exists. Slow history/database calls remain synchronous and can exceed cooperative deadlines.
- Distinguished successful empty directory scans from missing paths, iterator errors, closed handles, and incomplete scans. Partial inventories are discarded; retries produce sorted complete results.
- Missing ready files can be reconciled only against matching durable completion and commit acknowledgement; a present but corrupt ready file is not bypassed through a fallback.
- Targeted scanner fixtures reported 11/11 and 9/9 green after their respective red baselines, plus a final 12/12 iterator check. The original cause of a large set of older scan errors remains unknown.

**Exit Lab adapter and replay evidence**
- Restricted one replay adapter to an exact source/run/symbol/quote/time/sequence identity match; it is not a general permission to execute all replay work.
- A frozen fixture prepared one selected policy as PREPARED_NOT_EXECUTED and matched its decision, exit time/price, and excursion evidence in 10/10 cases. No live inbox was published.
- All-policy owner-database execution and full parity remained unproven. Dispatch-keyed acknowledgements and recovery fixtures addressed interleaving and restart identity.

**Brain Office catalogue and release validation**
- Improved TOP/catalog progress safeguards and separated status/reason counts; a yellow status is not automatically a confirmed software defect.
- Strengthened build/release evidence checks so malformed receipts, misleading success prefixes, or a passing nested fixture cannot override a failing aggregate result.
- Corrected target-count validation for the 13-program certificate; five affected targets were rebuilt and eight unchanged binaries were checked against their parent receipts.
- The distribution copy had an additional archive-only redaction process; no credential-shaped values, private paths, or redaction specifics are included in this public changelog.

**Acceptance status**
- The package was not installed and was not deployment-authorized; release_ready=false, runtime validation pending, ARM disabled.
- One-hour post-install acceptance, live EA1/EA2 performance limits, full TOP sweep, all-policy EXIT Lab parity, endpoint delivery, full-day health, and a broker statement were not established.
- No profitability, weekly P/L, or LIVE authorization is claimed.

**Status:** private DEMO package candidate only; not LIVE authorization.
