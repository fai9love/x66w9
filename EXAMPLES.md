# Elliott Wave + Fibonacci Pro v2 – Visual Examples & Case Studies

## How to Read These Examples

Each example describes a wave pattern with:
- **Setup context**: What the chart looked like
- **Wave structure**: Price action at each wave
- **Fibonacci validation**: Which ratios were confirmed
- **Compliance score**: Overall rule adherence
- **Trade action**: Entry, SL, TP levels

---

## Example 1: Classic Bullish Impulse (BTC Daily, Historical)

### Setup
- Timeframe: Daily chart
- HTF Trend: Weekly EMA 50 – Bullish
- Wave Direction Mode: Auto (Bullish)

### Wave Structure
```
Wave 0: $16,500 (Cycle low – origin)
Wave 1: $25,000 (+51.5% move up)
Wave 2: $19,800 (retraced 75.9% of W1) [v] valid
Wave 3: $31,000 (W3/W1 = 2.03x, extension 203%) [v] valid
Wave 4: $24,900 (retraced 38.2% of W3) [v] valid
Wave 5: $31,800 (W5/W1 = 1.38x) [v] valid
```

### Fibonacci Validation
| Check | Value | Valid? |
|-------|-------|--------|
| W2 Ret. | 75.9% | Yes [v] |
| W3 Ext. | 203.0% | Yes [v] |
| W4 Ret. | 38.2% | Yes [v] |
| W5/W1  | 1.38x | Yes [v] |

### Compliance Score: 100% (8/8 rules)

### Trade at Wave 2 Completion (Wave 3 Entry)
- Entry: $19,800
- Stop Loss: $16,170 (origin - 2% buffer)
- Take Profit: $25,667 (W2 + W1 x 1.618)
- Risk:Reward: 1:1.6

### Dashboard Display
```
Elliott Wave + Fib v2   BULLISH ^
Current Wave            5 of 5
HTF Trend               Bullish
Compliance              100% (8/8)
W2 Ret.                 75.9% [v]
W3 Ext.                 203.0% [v]
W4 Ret.                 38.2% [v]
W3/W1                   2.03x
W5/W1                   1.38x
W4/W3                   0.19x
Risk:Reward             1:1.60
Entry                   19,800
Stop Loss               16,170
Take Profit             25,667
```

---

## Example 2: Bearish Impulse (SPX 4H, Bear Market Decline)

### Setup
- Timeframe: 4-Hour chart
- HTF Trend: Daily EMA 50 – Bearish
- Wave Direction Mode: Auto (Bearish)

### Wave Structure
```
Wave 0: $4,200 (Cycle high – origin)
Wave 1: $3,900 (-7.1% move down)
Wave 2: $4,050 (retraced 50% of W1) [v] valid
Wave 3: $3,550 (W3/W1 = 1.83x extension) [v] valid
Wave 4: $3,720 (retraced 38.2% of W3) [v] valid
Wave 5: $3,400 (W5/W1 = 1.67x) [v] valid
```

### Compliance Score: 100% (8/8 rules)

### Key Observations
- Wave 3 was the strongest, with highest volume on the decline
- Wave 4 showed a clean 38.2% bounce (alternation with W2's 50%)
- Confluence zone detected at W4 area (38.2% W1 / 38.2% W3 overlap)

---

## Example 3: Partial Pattern – Wave 3 In Progress

### Setup
The indicator detects waves 1, 2, and the start of wave 3, but the full 5-wave sequence
is not yet complete. This triggers the **Wave 2 Entry Signal**.

### Wave Structure (In Progress)
```
Wave 0: $100.00 (Origin)
Wave 1: $125.00 (+25% thrust)
Wave 2: $107.50 (retraced 70% of W1) [v] valid
Wave 3: In progress, currently at $135.00
```

### Signal Generated
- Type: Wave 2 complete → Wave 3 long entry
- Entry: $107.50
- Stop Loss: $99.50 (below W1 origin)
- Take Profit: $148.00 (W2 + W1 x 1.618)

### Compliance Score: 75% (partial – W1/W2 only available)

---

## Example 4: ABC Zigzag Correction

### Setup
After a completed 5-wave bullish impulse, the indicator identifies a bearish ABC zigzag.

### Pattern Structure
```
A Start: $320 (Wave 5 high – impulse complete)
(A) end: $290 (-9.4% down – Wave A)
(B) end: $308 (+62% retracement of A) [v] valid Zigzag B
(C) end: $282 (-84% extension of A) [v] valid Zigzag C
```

### Classification: Zigzag (B retraced 62% of A → within 50-78.6% range)

### Chart Display
- Purple dashed lines connecting A→B→C
- Labels: **(A) Zigzag** at $290, **(B)** at $308, **(C)** at $282
- Dashboard shows: "Correction: Zigzag Bear"

---

## Example 5: Confluence Zone Hit

### Setup
After Wave 3 completes, two Fibonacci clusters overlap in the Wave 4 pullback zone:
- 38.2% of Wave 1 retracement = $156.80
- 38.2% of Wave 3 retracement = $157.20

### Confluence Detection
- Price proximity: $0.40 apart (within `confluenceTolerance` of 0.5%)
- A yellow highlight box appears around $156.80-$157.20
- Label: **"Confluence: 38.2% W1 / 38.2% W3"**

### Trading Implication
This double confluence makes $157 a high-probability Wave 4 support zone. Combined
with the Wave 4 entry signal, the Risk:Reward significantly improves.

---

## Example 6: Strict Mode – Low Compliance Pattern Filtered

### Without Strict Mode
A pattern is detected with:
- W2 Ret: 82% (outside 50-78.6% range → Rule 6 violated)
- W3 Ext: 145% (below 161.8% minimum → Rule 8 violated)
- Compliance Score: 75% (6/8 rules)

Pattern is shown with amber compliance score in dashboard.

### With Strict Mode (minComplianceScore = 80%)
The same pattern scores 75%, which is below the 80% threshold. The wave lines and
labels are **suppressed** (not drawn). Only patterns meeting the quality bar are shown.

---

## Sub-Wave Labeling Example

### Enabling Sub-Wave Labeling
With `Enable Sub-Wave Labeling = true` and `Sub-Wave Pivot Length = 5`:

### Primary Wave 3 Internal Structure
```
Wave 3 (primary): $100 → $162 (+62%)
  (3a): $100 → $115  – sub-impulse 1
  (3b): $115 → $108  – sub-correction
  (3c): $108 → $135  – sub-impulse 2
  (3d): $135 → $127  – sub-correction
  (3e): $127 → $162  – final sub-impulse
```

Sub-labels appear in **gray** with **tiny** font to distinguish from primary labels
(which are colored and slightly larger).

---

## Tips for Using These Examples

1. **Compare with your chart**: Look for similar structural proportions, not exact prices
2. **Fibonacci validation is key**: Patterns with more [v] checks are higher quality
3. **Watch for confluence zones**: Yellow boxes indicate strongest support/resistance
4. **Check compliance score**: Always prefer patterns scoring 75%+
5. **Use HTF alignment**: Best trades align with the higher-timeframe trend

---

*See DOCUMENTATION.md for full user guide and RULES_REFERENCE.md for rule details.*
