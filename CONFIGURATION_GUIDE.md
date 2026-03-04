# Configuration Guide

## Recommended Settings by Timeframe & Asset

This guide provides optimised parameter sets for common trading scenarios.

---

## 1-Minute Chart (Scalping)

| Setting | Value | Reason |
|---------|-------|--------|
| Zigzag Pivot Length | 5 | Fast response for short swings |
| Min Bars Between Pivots | 3 | Allows tight pivot spacing |
| Wave Direction Mode | Bullish / Bearish | Set manually, trend changes fast |
| HTF Timeframe | 15m or 1H | Short intraday reference |
| Trend MA Length | 20 | Quick trend identification |
| W3 Ext. Minimum | 1.618 | Keep standard |
| Pattern Tolerance | 15% | More lenient for noisy data |
| Strict Mode | Off | Too many valid 1m signals suppressed |
| Sub-Wave Labeling | Off | Too cluttered on 1m |

---

## 5-Minute Chart (Intraday)

| Setting | Value | Reason |
|---------|-------|--------|
| Zigzag Pivot Length | 8 | Balanced sensitivity |
| Min Bars Between Pivots | 4 | Moderate spacing |
| HTF Timeframe | 1H | Key intraday trend reference |
| Trend MA Length | 50 | Standard EMA |
| W2 Ret. Min | 50% | Standard range |
| W4 Ret. Max | 50% | Standard range |
| Pattern Tolerance | 12% | Slightly lenient |
| Strict Mode | Off | |
| Show Confluence Zones | On | Useful for intraday S/R |

---

## 1-Hour Chart (Swing Trading – Recommended)

| Setting | Value | Reason |
|---------|-------|--------|
| Zigzag Pivot Length | 10 | Default, optimal for 1H |
| Min Bars Between Pivots | 5 | Standard |
| HTF Timeframe | D (Daily) | Primary trend reference |
| Trend MA Length | 50 | Classic trend filter |
| Trend MA Type | EMA | Responsive to recent price |
| W3 Ext. Minimum | 1.618 | Strict Wave 3 requirement |
| Pattern Tolerance | 10% | Default |
| Strict Mode | On | Better signal quality |
| Min Compliance Score | 75% | High-quality patterns only |
| Show Extended Ratios | On | Full Fibonacci library |
| Show Confluence Zones | On | High-value zone detection |
| Projection Bars Forward | 30 | Standard lookahead |
| Sub-Wave Labeling | Optional | Enable for deeper analysis |

**Best for**: Equity indices, large-cap stocks, major Forex pairs

---

## 4-Hour Chart (Position Trading)

| Setting | Value | Reason |
|---------|-------|--------|
| Zigzag Pivot Length | 10 | Standard |
| Min Bars Between Pivots | 6 | Wider pivot spacing |
| HTF Timeframe | W (Weekly) | Macro trend reference |
| Trend MA Length | 50 | Standard |
| W3 Ext. Minimum | 1.618 | |
| Strict Mode | On | |
| Min Compliance Score | 75% | |
| Show Wave Ratios | On | Important for position sizing |
| Projection Bars Forward | 40 | Wider forward projection |

---

## Daily Chart (Long-Term / Macro)

| Setting | Value | Reason |
|---------|-------|--------|
| Zigzag Pivot Length | 15 | Fewer, cleaner pivots |
| Min Bars Between Pivots | 8 | Prevents minor noise |
| HTF Timeframe | W (Weekly) | Macro trend |
| Trend MA Length | 50 | Classic 50-day EMA |
| Strict Mode | On | Only highest-quality patterns |
| Min Compliance Score | 87.5% | 7/8 rules minimum |
| Sub-Wave Labeling | On (subZigzagLen=5) | Reveals internal structure |
| Projection Bars Forward | 60 | Look further ahead |
| Show Confluence Zones | On | Critical for daily TP levels |

---

## Asset-Specific Recommendations

### Crypto (BTC, ETH)
- Zigzag Length: **8** (volatile, fast-moving)
- Pattern Tolerance: **15%** (crypto Fibonacci ratios can be imprecise)
- Strict Mode: **Off** for daily, **On** for weekly
- W3 Extension can reach 4.236x – keep `showExtendedRatios = true`

### Forex (EURUSD, GBPUSD, etc.)
- Zigzag Length: **10** (standard)
- W2 Ret. range: **50-78.6%** (standard)
- HTF Timeframe: **4H** for 1H charts, **D** for 4H charts
- Strict Mode: **On** recommended for Forex (cleaner structures)

### Equity Indices (SPX, NQ, DAX)
- Zigzag Length: **10-12** (medium sensitivity)
- Pattern Tolerance: **8-10%**
- Strict Mode: **On** with 75% minimum
- Enable sub-wave labeling on 4H charts for wave 3 analysis

### Individual Stocks
- Zigzag Length: **12-15** (stocks can be noisy)
- Pattern Tolerance: **12%**
- HTF Timeframe: **W (Weekly)** for daily charts
- Strict Mode: **On** to avoid chasing false breakouts

---

## Tuning the Compliance Threshold

| Threshold | Effect |
|-----------|--------|
| 50% (4/8 rules) | Permissive – many signals, including lower quality |
| 62.5% (5/8 rules) | Balanced – filters obvious violations |
| 75% (6/8 rules) | **Recommended default** – good balance |
| 87.5% (7/8 rules) | Strict – only near-perfect patterns |
| 100% (8/8 rules) | Ultra-strict – very few signals |

---

## Stop-Loss Buffer Recommendations

| Asset Class | SL Buffer | Reason |
|-------------|-----------|--------|
| Crypto | 1.0-2.0% | High volatility, wide wicks |
| Forex | 0.1-0.3% | Low volatility, tight stops |
| Equities (large cap) | 0.3-0.5% | Moderate volatility |
| Equities (small cap) | 0.5-1.5% | Higher volatility |
| Futures / Indices | 0.2-0.5% | Leverage-sensitive |

---

## Migration from v1.0

All v1.0 settings are preserved. New inputs default to safe values:
- `enableCorrectionDetection = true` – ABC patterns visible by default
- `strictMode = false` – no change to existing behavior
- `showExtendedRatios = true` – additional Fib levels shown
- `showWaveRatios = true` – ratio display added to dashboard

To replicate **exact v1.0 behavior**:
1. Set `enableCorrectionDetection = false`
2. Set `showExtendedRatios = false`
3. Set `showConfluenceZones = false`
4. Set `showWaveRatios = false`
5. Set `enableSubWaveLabeling = false` (already default)
6. Set `strictMode = false` (already default)
