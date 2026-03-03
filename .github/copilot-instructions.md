# Copilot Instructions

## Repository Overview

This repository contains **Pine Script v6** indicator scripts for TradingView:

- **Gamma SPX** – A structure & retracement engine that tracks key gamma levels (support, resistance, zero-gamma pivot) for SPX and generates trade recommendations via an on-chart dashboard.
- **SUPER INDIBOT** – A multi-feature indicator combining an EMA ribbon, ATR-based stop-loss/take-profit management, a trend analysis dashboard, and a multi-symbol screener.

## Language & Platform

- All scripts are written in **Pine Script version 6** (`//@version=6`).
- Scripts run inside **TradingView** as `indicator()` overlays.
- There is no build system, package manager, or test runner — validation is done by loading scripts in TradingView.

## Coding Conventions

- Use `//` line comments and `/* */` block comments for documentation.
- Group related `input.*` calls under named `group` strings (e.g., `group = 'MODEL SETTINGS'`).
- Name constants with `UPPER_SNAKE_CASE` and functions with the `f_` prefix (e.g., `f_send_alert()`).
- Prefer named constants over magic numbers (e.g., `FIB_618 = 0.618` rather than the bare literal).
- Add JSDoc-style headers to all `f_*` utility functions describing parameters and return values.
- Keep `request.security()` calls deduplicated and use `lookahead = barmerge.lookahead_on` only on confirmed bars to prevent repainting.
- Use `var` for variables that should persist across bars; avoid unnecessary re-initialisation on every tick.

## Style Guidelines

- Align related assignments with spaces for readability (columnar style).
- Use Unicode emoji prefixes in input labels and indicator titles to aid visual scanning.
- Organise code into clearly delimited sections with box-drawing comment headers:
  ```
  // ╔═══════════════╗
  // ║  SECTION NAME ║
  // ╚═══════════════╝
  ```
- Keep line length reasonable (≤ 120 characters where practical).

## Common Patterns

- Dashboard tables are built with `table.new()` / `table.cell()` and updated only when values change (change-detection guard).
- Alerts are sent via a dedicated `f_send_alert()` helper that centralises message formatting.
- Profile modes (`'Conservative'`, `'Balanced'`, `'Aggressive'`) gate signal thresholds via score constants.

## What Copilot Should Do

- When adding new features, follow the existing input grouping and naming conventions.
- When fixing bugs, add a CHANGELOG entry in the script header describing the fix.
- Do not introduce `request.security()` calls with `lookahead_on` on unconfirmed bars.
- Prefer extending existing helper functions (`f_*`) rather than writing inline logic.
