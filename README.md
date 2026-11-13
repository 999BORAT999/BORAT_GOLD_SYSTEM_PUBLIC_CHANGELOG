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

**Status:** DEMO candidate only. This update is not a LIVE authorization or a claim of full acceptance. Performance targets and several interactive terminal, replay, and end-to-end demo acceptance checks remain outstanding. Historical demo results are not a guarantee of future performance.

## Publishing policy

Future entries will be added as reviewed, summary-only commits. No private source code, package archives, credentials, account or broker identifiers, or verbatim private audit logs should be published in this repository.
