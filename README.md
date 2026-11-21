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