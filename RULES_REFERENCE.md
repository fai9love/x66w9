# Elliott Wave Rules Reference

## The 8 Core Elliott Wave Rules

The EW-Fib Pro v2 indicator validates all 8 rules automatically and reports a compliance score (0-100%).

---

### Rule 1 – Wave 2 Cannot Retrace Beyond Wave 1 Start
**Principle**: Wave 2 corrects Wave 1, but price can never return to the origin of Wave 1.

| Direction | Condition |
|-----------|-----------|
| Bullish   | Wave 2 low > Wave 0 (Wave 1 start) |
| Bearish   | Wave 2 high < Wave 0 (Wave 1 start) |

**Why it matters**: If Wave 2 breaks below Wave 1's start, the impulse count is invalid.

---

### Rule 2 – Wave 3 Must Advance Beyond Wave 1
**Principle**: Wave 3 must make a new extreme beyond Wave 1's endpoint.

| Direction | Condition |
|-----------|-----------|
| Bullish   | Wave 3 high > Wave 1 high |
| Bearish   | Wave 3 low < Wave 1 low |

**Why it matters**: This confirms the impulse is progressing, not forming a corrective pattern.

---

### Rule 3 – Wave 3 Is Never the Shortest Impulse Wave
**Principle**: Among Waves 1, 3, and 5, Wave 3 cannot be the shortest in price length.

- W3 length >= W1 length **AND** W3 length >= W5 length
- Wave 3 is often the longest (1.618x W1 or more)

**Why it matters**: This is one of the most critical rules in Elliott Wave theory.

---

### Rule 4 – Wave 4 Cannot Overlap Wave 1 Territory
**Principle**: Wave 4 cannot retrace into the price range covered by Wave 1.

| Direction | Condition |
|-----------|-----------|
| Bullish   | Wave 4 low > Wave 1 high |
| Bearish   | Wave 4 high < Wave 1 low |

**Exception**: Diagonal triangles (terminal patterns) may violate this rule but are rare.

---

### Rule 5 – Wave 5 Advances Beyond Wave 3 (With Truncation Allowance)
**Principle**: Wave 5 should create a new price extreme beyond Wave 3.

- Bullish: Wave 5 high >= Wave 3 high x 0.99 (1% truncation allowed)
- Bearish: Wave 5 low <= Wave 3 low x 1.01

**Note**: Truncated 5th waves occur when Wave 3 was exceptionally extended.

---

### Rule 6 – Wave 2 Retracement Within Fibonacci Range
**Principle**: Wave 2 typically retraces 50-78.6% of Wave 1.

| Setting      | Default | Description |
|--------------|---------|-------------|
| W2 Ret. Min  | 50.0%   | Minimum valid retracement |
| W2 Ret. Max  | 78.6%   | Maximum valid retracement |
| W2 Ret. Ideal| 61.8%   | Most common retracement level |

---

### Rule 7 – Wave 4 Retracement Within Fibonacci Range
**Principle**: Wave 4 typically retraces 23.6-50% of Wave 3.

| Setting      | Default | Description |
|--------------|---------|-------------|
| W4 Ret. Min  | 23.6%   | Minimum valid retracement |
| W4 Ret. Max  | 50.0%   | Maximum valid retracement |
| W4 Ret. Ideal| 38.2%   | Most common retracement level |

---

### Rule 8 – Wave 3 Extension Meets Minimum Threshold
**Principle**: Wave 3 must extend at least 161.8% of Wave 1 in length.

- Default minimum: 161.8% (configurable in settings)
- Typical range: 161.8% to 261.8%
- Extended Wave 3: up to 423.6%

---

## Compliance Score

The compliance score is calculated as:



| Score   | Interpretation |
|---------|----------------|
| 100%    | Perfect – all 8 rules satisfied |
| 75-99%  | Good – minor deviations |
| 50-74%  | Moderate – review the pattern |
| < 50%   | Poor – likely invalid count |

In **Strict Mode**, patterns scoring below the minimum compliance threshold are hidden.

---

## Alternation Guideline (Advisory)

While not enforced as a hard rule, Elliott Wave theory suggests:

- If Wave 2 is a **sharp** (zigzag) correction → Wave 4 tends to be **flat/complex**
- If Wave 2 is a **flat/sideways** correction → Wave 4 tends to be **sharp/steep**

This alternation helps distinguish genuine wave counts from false signals.

---

## Wave Personality (Reference)

| Wave | Character | Typical Length |
|------|-----------|----------------|
| 1    | Initial thrust, moderate | Base length |
| 2    | Corrective, retraces 50-78.6% W1 | 50-79% of W1 |
| 3    | Strongest, highest volume | 161.8-261.8% of W1 |
| 4    | Corrective, shallow | 23.6-50% of W3 |
| 5    | Weak, divergent | 61.8-161.8% of W1 |

---

*See DOCUMENTATION.md for full usage guide and CONFIGURATION_GUIDE.md for settings recommendations.*
