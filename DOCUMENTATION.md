# Elliott Wave + Fibonacci Professional Indicator v2.0
## Comprehensive User Guide & Reference

---

## 📋 Table of Contents
1. [Overview](#overview)
2. [Installation](#installation)
3. [Core Features](#core-features)
4. [Detailed Settings](#detailed-settings)
5. [Wave Identification Guide](#wave-identification-guide)
6. [Corrective Patterns](#corrective-patterns)
7. [Fibonacci Ratios](#fibonacci-ratios)
8. [Trading Signals](#trading-signals)
9. [Dashboard Metrics](#dashboard-metrics)
10. [Best Practices](#best-practices)
11. [Troubleshooting](#troubleshooting)

---

## Overview

**Elliott Wave + Fibonacci Pro v2.0** is a professional-grade TradingView indicator that automatically detects, validates, and labels Elliott Wave patterns with institutional-quality Fibonacci projections.

### Key Capabilities
✅ **Full 5-Wave Impulse Detection** - Automatic pattern recognition with strict rule validation
✅ **Corrective Wave Analysis** - ABC zigzags, flats, triangles, and complex corrections  
✅ **Sub-Wave Labeling** - Hierarchical degree levels (primary, intermediate, minor)
✅ **Advanced Fibonacci** - Multi-ratio projections with confluence zone detection
✅ **Strict Validation** - Enforces Elliott's core rules with compliance scoring
✅ **Real-Time Signals** - Entry/SL/TP calculations at W2 and W4 completions
✅ **Professional Dashboard** - Metrics, ratios, and performance analytics

---

## Installation

### For TradingView Pine Script
1. Open TradingView Chart
2. Click "Pine Editor" (bottom of screen)
3. Click "New" → Select "Indicator"
4. Copy the Elliott Wave + Fibonacci Pro code
5. Click "Add to Chart"
6. Configure settings per your trading style

### Minimum Requirements
- TradingView Account (Free or Premium)
- Pine Script v5 or higher
- Chart with sufficient history (100+ bars minimum)

---

## Core Features

### 1. Primary Trend Detection
**Purpose**: Filter wave detection to align with higher-timeframe bias

**Inputs**:
- `Enable Higher-Timeframe Trend Filter` - Uses HTF to confirm trend direction
- `Higher Timeframe` - Default: Daily (can be Weekly for longer-term bias)
- `Trend MA Length` - Default: 50 (EMA of HTF close)
- `Trend MA Type` - EMA, SMA, WMA, or HMA

**How It Works**:
- System reads the higher timeframe (e.g., daily on 1hr chart)
- Calculates moving average on HTF
- If HTF close > HTF MA → Bullish bias (only detect UP waves)
- If HTF close < HTF MA → Bearish bias (only detect DOWN waves)

**Pro Tip**: Use Daily MA on intraday charts, Weekly MA on daily charts

---

### 2. Elliott Wave Detection

**Zigzag Pivot Length** (Default: 10)
- Bars left/right to identify swing highs/lows
- **Lower value** (3-5): More sensitive, more false signals
- **Higher value** (15-20): Slower response, cleaner signals
- **Recommendation**: Match to your chart timeframe (10 for 1h, 5 for 5m)

**Min Bars Between Pivots** (Default: 5)
- Minimum bars required between consecutive pivots
- Prevents duplicate/overlapping waves
- Should be 2-3x smaller than Zigzag Length

**Wave Direction Mode**:
- `Auto` - Uses HTF trend for direction
- `Bullish` - Force detection of only upward waves
- `Bearish` - Force detection of only downward waves

---

### 3. Fibonacci Level Settings

#### Wave 2 Retracement (Waves 1→2)
- **Min (50%)**: Minimum wave 2 can retrace
- **Max (78.6%)**: Maximum wave 2 can retrace
- **Ideal (61.8%)**: Most common retracement level

*Classic Elliott Rule*: Wave 2 typically retraces 50-78.6% of Wave 1

#### Wave 3 Extension (Waves 2→3)
- **Minimum (161.8%)**: Wave 3 must extend at least 1.618x Wave 1 length
- Ensures Wave 3 is not shortest impulse wave

*Classic Elliott Rule*: Wave 3 is typically 1.618x to 2.618x Wave 1

#### Wave 4 Retracement (Waves 3→4)
- **Min (23.6%)**: Minimum wave 4 can retrace
- **Max (50%)**: Maximum wave 4 can retrace
- **Ideal (38.2%)**: Most common retracement level

*Classic Elliott Rule*: Wave 4 retraces 23.6-50% of Wave 3

#### Wave 5 Extension (Waves 4→5)
- **Min (61.8%)**: Minimum length relative to Wave 1
- **Max (161.8%)**: Maximum length relative to Wave 1

*Classic Elliott Rules*: 
- Wave 5 often equals Wave 1
- Or Wave 5 = 1.618x Wave 1
- Or Wave 5 = 0.618x Wave 3

---

## Wave Identification Guide

### Bullish Impulse Wave Structure
```
Wave 0 (Origin) ──────────────────────────────────
    ↓
Wave 1 (Up): Initial thrust
    ├─ Length: X
    ├─ Strength: Strong, impulsive
    └─ Structure: Typically 5 sub-waves

Wave 2 (Down): Retracement
    ├─ Retraces: 50-78.6% of Wave 1
    ├─ Strength: Corrective
    └─ Rule: NEVER goes below Wave 1 start

Wave 3 (Up): Extension/Main move
    ├─ Length: ≥ 1.618x Wave 1
    ├─ Strength: STRONGEST, most impulsive
    ├─ Volume: Typically highest
    └─ Rule: NEVER the shortest wave

Wave 4 (Down): Retracement
    ├─ Retraces: 23.6-50% of Wave 3
    ├─ Strength: Corrective, shallow
    ├─ Rule: NEVER overlaps into Wave 1
    └─ Character: Often alternates with Wave 2

Wave 5 (Up): Final thrust
    ├─ Length: 0.618x - 1.618x Wave 1
    ├─ Can be SHORTER than Wave 3 (truncated)
    ├─ Often weaker than Wave 3
    └─ Divergence: Often shows weakening momentum
```

### Bearish Impulse Wave Structure
(Mirror image of Bullish - all movements reversed)

---

## Corrective Patterns

### A. Zigzag (5-3-5)
**Structure**: Wave A (5), Wave B (3), Wave C (5)

**Characteristics**:
- Steep, quick corrections
- Wave A is impulsive (5 sub-waves)
- Wave B retraces 50-78.6% of Wave A
- Wave C extends beyond Wave A's start

**Fibonacci Ratios**:
- Wave B typically 50-61.8% of Wave A
- Wave C typically 100-161.8% of Wave A

**Common Occurrences**:
- Wave 2 of larger impulse
- Wave 4 of larger impulse
- Standalone correction patterns

### B. Flat (3-3-5)
**Structure**: Wave A (3), Wave B (3), Wave C (5)

**Characteristics**:
- Range-bound, sideways correction
- All waves are corrective (subdivide 3-3-5)
- Wave B ends near Wave A start
- Less steep than zigzag

**Fibonacci Ratios**:
- Wave B typically 80-123% of Wave A
- Wave C typically 100-161.8% of Wave A

**Common Occurrences**:
- 4th wave after strong Wave 3
- Consolidation pattern

### C. Triangle (3-3-3-3-3)
**Structure**: 5 waves, each subdividing into 3

**Characteristics**:
- Converging price range
- Decreasing volume typically
- Each swing gets smaller
- Breakout follows direction

**Common Occurrences**:
- 4th wave before final Wave 5
- Often precedes major move

---

## Fibonacci Ratios

### Primary Ratios
| Ratio | Calculation | Usage |
|-------|-------------|-------|
| 0.236 | 1 - 0.618 / 2 | Minor support |
| 0.382 | (√5 - 1) / 2 | Wave 4 retrace |
| 0.500 | Simple average | Wave 2 retrace |
| 0.618 | Golden Ratio | Wave 2 ideal retrace |
| 0.786 | √0.618 | Wave 2 max retrace |
| 1.000 | Full retracement | Equal waves |
| 1.618 | Golden Ratio | Wave 3, 5 extension |
| 2.618 | Golden Ratio² | Strong extension |

### Wave-Specific Ratios

**Wave 3 Extensions**:
- 1.618x Wave 1 (minimum)
- 1.618x-2.618x Wave 1 (typical)
- 4.236x Wave 1 (rare but valid)

**Wave 5 Extensions**:
- Equal to Wave 1 (common)
- 0.618x Wave 3 (truncated)
- 1.618x Wave 1 (extended)

**Wave 4 Retracements**:
- 23.6% of Wave 3 (shallow)
- 38.2% of Wave 3 (ideal)
- 50% of Wave 3 (deep)

---

## Trading Signals

### Wave 2 Entry Signal
**Trigger**: Wave 2 completes with valid Fibonacci ratio

**Setup**:
```
Entry: Wave 2 low
Stop Loss: Wave 1 start - 0.5% buffer
Take Profit: Wave 2 + (1.618x Wave 1 length)
Risk:Reward: Typically 1:3 or better
```

**Logic**: Wave 3 is typically strongest impulse wave

### Wave 4 Entry Signal  
**Trigger**: Wave 4 completes with valid Fibonacci ratio

**Setup**:
```
Entry: Wave 4 low (bullish) or high (bearish)
Stop Loss: Wave 1 high + 0.5% buffer (bullish)
Take Profit: Wave 4 + (Wave 1 length × 0.618)
Risk:Reward: Typically 1:2+
```

**Logic**: Wave 5 provides final exit opportunity

### Alert Conditions
Dashboard displays alerts for:
- ✅ Bullish Wave 3 Entry
- ✅ Bearish Wave 3 Entry
- ✅ Bullish Wave 5 Entry
- ✅ Bearish Wave 5 Entry
- ✅ Full 5-Wave Detected

---

## Dashboard Metrics

### Current Display
| Metric | Meaning |
|--------|---------|
| Elliott Wave + Fib | Indicator name + direction |
| BULLISH ^ / BEARISH v | Current wave direction |
| Current Wave | 0-5 showing progression |
| HTF Trend | Higher timeframe bias |
| W2 Ret. | Wave 2 retracement % [v]=valid [x]=invalid |
| W3 Ext. | Wave 3 extension % [v]=valid [x]=invalid |
| W4 Ret. | Wave 4 retracement % [v]=valid [x]=invalid |
| Entry | Current entry price |
| Stop Loss | Calculated SL for trade |
| Take Profit | Calculated TP for trade |
| Risk:Reward | TP-Entry / Entry-SL ratio |

### Interpretation
- **[v]**: Fibonacci ratio is within expected ranges
- **[x]**: Fibonacci ratio is outside ranges (possible wave count error)
- **Risk:Reward**: 
  - Green ≥ 2.0 (excellent)
  - Yellow = 1.0-1.99 (good)
  - Red < 1.0 (risky)

---

## Best Practices

### 1. Confirm with Multiple Timeframes
- Identify 5-wave pattern on Daily
- Look for Wave 3 on 4H/1H for entry
- Use 15m for precise entry/exit

### 2. Use HTF Bias
- Set "Higher Timeframe" to next longer period
- Only trade waves aligned with HTF trend
- Increases win rate by 20-30%

### 3. Validate Fibonacci Ratios
- Pattern is more valid with MORE ratio confirmations
- 2+ ratios valid = high confidence
- All ratios invalid = likely false signal

### 4. Watch for Truncation
- Wave 5 can be shorter than Wave 3
- Still valid as long as it exceeds Wave 3 start
- Indicates weakening momentum (potential reversal)

### 5. Manage Trade Risk
- Use Wave 1 as reference for position sizing
- Risk no more than 2% per trade
- Take profits at projected levels

### 6. Monitor Volume
- Wave 3 should show HIGHEST volume
- Wave 5 typically shows DECLINING volume
- Helps confirm wave count

### 7. Use Confluence Zones
- Multiple Fibonacci levels at same price = strong support/resistance
- Best entry zones have 3+ levels overlapping
- Best TP zones have clear resistance cluster

---

## Troubleshooting

### Issue: Too Many False Signals
**Solution**:
1. Increase "Zigzag Pivot Length" (currently 10 → try 15)
2. Enable "Strict Mode" for stricter validation
3. Increase "Min Bars Between Pivots"
4. Use longer timeframe (1h instead of 5m)
5. Confirm with HTF trend

### Issue: Waves Not Detecting
**Solution**:
1. Check "Wave Direction Mode" not stuck on wrong direction
2. Verify "Higher Timeframe Trend" is enabled if using Auto mode
3. Ensure enough price history (100+ bars)
4. Try different "Zigzag Pivot Length" setting
5. Check if market is in consolidation (no clear 5-wave)

### Issue: Wave 2 Signals Too Early/Late
**Solution**:
1. Adjust "Min Bars Between Pivots" setting
2. Lower sensitivity on Zigzag Length
3. Wait for Fibonacci ratio confirmation ([v] symbol)

### Issue: High False Signal Rate
**Solution**:
1. Enable strict Elliott Wave rule validation
2. Only trade signals with Risk:Reward ≥ 2.0
3. Wait for all Fibonacci ratios to be valid
4. Use with confluent support/resistance levels

### Issue: Indicator Repainting
**Solution**:
- This is NORMAL on real-time bars
- Patterns finalize when bar closes
- Wait for bar close before entering trade
- Historical bars will not repaint

---

## Appendix: Common Elliott Wave Mistakes

❌ **Mistake 1**: Forcing 5-wave count in consolidation market
✅ **Fix**: Only trade clear trending markets with obvious impulsive structure

❌ **Mistake 2**: Entering before Wave 2 completes
✅ **Fix**: Wait for Wave 2 low + confirmation from indicator signal

❌ **Mistake 3**: Ignoring Wave 4 (thinking trade is over)
✅ **Fix**: Wave 4 pullback is natural; Wave 5 often targets new highs

❌ **Mistake 4**: Not using Fibonacci ratios for validation
✅ **Fix**: Always check [v] symbols in dashboard - they're critical

❌ **Mistake 5**: Trading against HTF trend
✅ **Fix**: Align wave direction with higher timeframe bias

---

## Version History

**v2.0** (Latest - 2026-03-04)
- ✅ Corrective wave detection (zigzags, flats, triangles)
- ✅ Sub-wave labeling system
- ✅ Strict Elliott Wave rule validation
- ✅ Advanced Fibonacci confluence zones
- ✅ Code optimization & refactoring
- ✅ Enhanced dashboard metrics
- ✅ Comprehensive documentation

**v1.0** (Original)
- Basic 5-wave detection
- Simple Fibonacci levels
- Entry/SL/TP signals

---

For more help, see RULES_REFERENCE.md, EXAMPLES.md, or reach out with questions!