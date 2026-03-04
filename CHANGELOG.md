# Changelog

All notable changes to Elliott Wave + Fibonacci Professional Indicator are documented here.

---

## [v2.0] – 2026-03-04

### Added
- **Named constants** for all Fibonacci ratios (FIB_236 through FIB_4236) replacing magic numbers
- **`validateElliotRules()` function** – validates 8 core Elliott Wave rules and returns:
  - `complianceScore` (0-100%)
  - `violationCount` (0-8)
- **Corrective Wave Detection (`detectCorrectiveWaves()`)**:
  - Detects bearish and bullish ABC patterns from 4-pivot sequences
  - Classifies patterns as **Zigzag** (B retraces 50-78.6% of A) or **Flat** (B retraces 80-100% of A)
  - Configurable `correctionTolerance` (default 10%)
  - Draws purple dashed lines for A, B, C waves
  - Labels (A), (B), (C) at wave endpoints with pattern type annotation
- **Sub-Wave Labeling (`labelSubWaves()`)**:
  - Optional sub-wave pivot detection using a configurable finer lookback (`subZigzagLen`)
  - Labels primary waves 1, 3, 5 with internal pivots: (1a), (1b)…(3a), (3b)…(5a)…(5e)
  - Gray/tiny labels to distinguish from primary wave labels
- **Advanced Fibonacci projections**:
  - Extended ratios: 127.2%, 200%, 261.8%, 423.6% (toggleable)
  - Wave 4 retracement levels from Wave 3 (23.6%, 38.2%, 50%)
  - Uses named FIB_* constants throughout
- **Confluence Zone Detection**:
  - Checks if Wave 1 retracement levels cluster with Wave 4 retracement levels
  - Draws yellow highlight boxes around confluence zones
  - Labels confluences with "Confluence: X% W1 / Y% W3"
  - Configurable `confluenceTolerance` width
- **New input groups**:
  - `Corrective Wave Detection` (4 settings)
  - `Sub-Wave Analysis` (3 settings)
  - `Validation Settings` (4 settings)
  - `Advanced Fibonacci` (5 settings)
- **Enhanced dashboard** (2 x 14 table):
  - Compliance score display with color coding (green/yellow/red)
  - Wave ratios: W3/W1, W5/W1, W4/W3 (toggleable)
  - Correction type (Zigzag / Flat, direction)
  - All existing rows preserved
- **New alert conditions**:
  - `ABC Correction Detected` – fires when a new correction pattern is found
  - `Rule Violation Detected` – fires when a full pattern has rule violations
- **`patternVisible` gate** – suppresses wave drawing when Strict Mode is on and compliance is too low
- **New data window plots**:
  - `Compliance Score %` (for use in strategies/alerts)
  - `Correction Found` (0 or 1)
- **Documentation files**:
  - `DOCUMENTATION.md` – comprehensive user guide (pre-existing, enhanced)
  - `RULES_REFERENCE.md` – detailed 8-rule reference
  - `EXAMPLES.md` – annotated visual examples and case studies
  - `CHANGELOG.md` – this file
  - `CONFIGURATION_GUIDE.md` – timeframe/asset settings recommendations

### Changed
- Indicator title updated: `"Elliott Wave + Fibonacci Pro v2"` (was `"Elliott Wave + Fibonacci Pro"`)
- `maxPivots` constant renamed `MAX_PIVOTS` for consistency with naming conventions
- `w2RetIdeal` input retained (was already present in v1) – no breaking change
- Signal generation now respects `patternVisible` flag
- Dashboard rows expanded from 10 to 14
- Fibonacci projection now uses `projectionLookahead` input (default 30 bars) instead of fixed 15
- All Fibonacci level drawing uses named constants (FIB_618 etc.) instead of hardcoded floats

### Fixed
- `w2Ref` for extension targets correctly uses `w2Price` when available (was always using `w0Price` equivalent)
- Wave 4 / Wave 5 retracement levels now drawn from correct anchor bar (`w3Bar`, not `w1Bar`)

### Performance
- No additional `request.security()` calls
- Sub-wave pivot buffer only populated when `enableSubWaveLabeling = true`
- Confluence detection is O(3) (constant – checks only 3 fixed level pairs)
- Smart array cleanup on every new pattern/partial detection

---

## [v1.0] – Original Release

### Added
- 5-wave Elliott impulse detection (bullish and bearish)
- Partial wave detection (waves 1-2-3 in progress)
- Fibonacci retracement/extension lines (Wave 2, Wave 3, Wave 4 levels)
- HTF trend filter (EMA/SMA/WMA/HMA on configurable higher timeframe)
- Trade signals at Wave 2 and Wave 4 completions
- Stop-loss and take-profit level lines
- Info table with wave progress, Fibonacci validation [v]/[x], entry/SL/TP, Risk:Reward
- Alert conditions for wave entries and pattern completions
- Data window plots for wave prices, entry, SL, TP
