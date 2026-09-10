# SION Semiconductors — Management Dashboard

Live operating dashboard for SION Semiconductors (India + UAE, 6 business units).

## Files
- **`index.html`** — root landing page (byte-identical copy of `dashboard.html`, for GitHub Pages / default serving).
- **`dashboard.html`** — canonical dashboard source (single self-contained HTML file: inline CSS + JS + injected model data).
- **`*.json`** — computed model ground-truth (workforce, per-BU cash, group cash, org projection). Regenerated in the Genspark session from `Sionsemi-Employees.xlsx` and inlined into the HTML on each build; kept in the repo for auditability.

## Deploy pipeline
Changes are authored in the Genspark chat session. On every user-visible update, the Genspark bot verifies the changed files, commits them with a descriptive message, and pushes to `main`.

Guardrails:
- Only this repository, only `main`.
- No force-push, no history rewrites, no branch deletes.
- Only files explicitly changed in a turn are staged — never a blanket `git add .`.
- Pre-commit scan blocks credentials / tokens.
- Every push is reported back in chat with: changed files · commit SHA · push result.
