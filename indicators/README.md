# Elliott Wave + Fibonacci Analyzer

**File:** `indicators/elliott_wave_fibonacci.pine`  
**Pine Script Version:** v5  
**Overlay:** Yes (plots directly on the price chart)

---

## What the Indicator Does

This indicator combines two complementary technical-analysis frameworks:

1. **Elliott Wave Detection** – automatically identifies 5-wave impulse structures (both bullish and bearish) from confirmed pivot highs and lows.
2. **Fibonacci Retracement & Extension Levels** – draws horizontal Fibonacci levels for Wave 2 retracements, Wave 3 extensions, and Wave 4 retracements, directly derived from confirmed wave lengths.

Additional features include:

- **Higher-Timeframe Trend Filter** – requests data from a configurable HTF and determines whether the market is in a bullish or bearish trend using an EMA.
- **Trade Signal Generation** – plots entry signals when price reaches the optimal Wave 3 or Wave 5 entry zone, aligned with the HTF trend.
- **Automated Stop-Loss Calculation** – computes and draws SL levels just below (or above) the most recent corrective wave with an ATR buffer.
- **Risk:Reward Display** – shows approximate R:R in the SL label tooltip.
- **Info Table Dashboard** – a compact top-right table summarising HTF trend, current wave count, validity flags, targets, and SL level.
- **Alert Conditions** – four configurable alerts for Wave 3 / Wave 5 bullish and bearish entries.

---

## How to Add It to TradingView

1. Open [TradingView](https://www.tradingview.com) and open any chart.
2. Click **Pine Editor** at the bottom of the screen.
3. Click **Open** → **New blank indicator**.
4. Copy the entire contents of `elliott_wave_fibonacci.pine` and paste it into the editor.
5. Click **Save** (give it a name, e.g. "EW+Fib Analyzer").
6. Click **Add to chart** – the indicator will appear as an overlay on your price chart.

---

## Input Parameters

### Trend Detection

| Parameter | Default | Description |
|-----------|---------|-------------|
| `Higher Timeframe` | `240` (4H) | The timeframe used for trend determination. Options: 60 (1H), 240 (4H), D (Daily), W (Weekly). |
| `Trend EMA Length` | `200` | The EMA period applied on the HTF to classify trend direction. Price above EMA = bullish; below = bearish. |

### Wave Detection

| Parameter | Default | Description |
|-----------|---------|-------------|
| `Pivot Lookback Left` | `10` | Number of bars to the left of a pivot bar used to confirm a pivot high/low. Higher values = fewer but more significant pivots. |
| `Pivot Lookback Right` | `10` | Number of bars to the right required before a pivot is confirmed. Causes a lag equal to this value. |
| `Wave Sensitivity Multiplier` | `1.0` | Minimum required wave size expressed as a multiple of ATR(14). Increase to filter out minor swings; decrease for more detections. |

### Fibonacci

| Parameter | Default | Description |
|-----------|---------|-------------|
| `Show Fibonacci Levels` | `true` | Toggles all Fibonacci lines on/off. |
| `Wave 2 Retracement Ratio` | `0.618` | Primary Fibonacci ratio used to validate a Wave 2 retracement (±5% tolerance). |
| `Wave 3 Extension Ratio` | `1.618` | Primary ratio for the Wave 3 projection target from the Wave 2 low. |
| `Wave 4 Retracement Ratio` | `0.382` | Primary ratio for the Wave 4 retracement zone from the Wave 3 high. |

### Display

| Parameter | Default | Description |
|-----------|---------|-------------|
| `Show Wave Labels` | `true` | Draws connecting lines between wave pivots and labels them W1–W5. |
| `Show Entry/SL Signals` | `true` | Plots entry triangles and SL lines when signal conditions are met. |
| `Show Trend Background` | `true` | Shades the chart background teal (bullish) or red (bearish) based on HTF trend. |
| `Bullish Color` | Teal 85% transparent | Background color when trend is bullish. |
| `Bearish Color` | Red 85% transparent | Background color when trend is bearish. |

---

## Interpreting Wave Labels and Fibonacci Lines

### Wave Labels (W1–W5)

- **W1** (green line + label) – first impulse leg; label appears at the pivot high (bull) or low (bear).
- **W2** (red line + label) – corrective retracement of W1; label at the corrective pivot.
- **W3** (thick green line + label) – the strongest and often longest impulse; always longer than W1.
- **W4** (red line + label) – shallow correction that must *not* overlap W1 territory.
- **W5** (green line + label) – final impulse; may equal W1 in length.

### Fibonacci Lines

**Wave 2 zone** (drawn from W1 pivot, dashed lines):
- 🟠 Orange dashed – 0.382 retracement  
- 🟡 Yellow dashed – 0.500 retracement  
- 🟢 Lime dashed – 0.618 retracement *(primary target)*  
- 🔴 Red dashed – 0.786 retracement *(maximum valid W2)*

**Wave 3 extension zone** (drawn from W2 pivot):
- 🔵 Aqua dashed – 1.272 extension  
- 🟢 Lime solid – 1.618 extension *(primary target)*  
- 🟠 Orange solid – 2.000 extension  
- 🟣 Fuchsia solid – 2.618 extension *(aggressive target)*

**Wave 4 zone** (drawn from W3 pivot, dashed lines):
- 🟠 Orange dashed – 0.236 retracement  
- 🟢 Lime dashed – 0.382 retracement *(primary target)*  
- 🟡 Yellow dashed – 0.500 retracement *(maximum valid W4)*

### Trade Signals

| Shape | Color | Meaning |
|-------|-------|---------|
| ▲ triangle below bar | Green | Bullish Wave 3 entry (wave count = 2, HTF bullish, price near W2 Fib zone) |
| ▲ triangle below bar | Aqua | Bullish Wave 5 entry (wave count = 4, HTF bullish, price near W4 Fib zone) |
| ▼ triangle above bar | Red | Bearish Wave 3 short (wave count = 2, HTF bearish, price near W2 Fib zone) |
| ▼ triangle above bar | Orange | Bearish Wave 5 short (wave count = 4, HTF bearish, price near W4 Fib zone) |

### Stop-Loss Line

A red dashed horizontal line appears at the computed SL level:
- **Wave 3 trade SL** = Wave 2 low − 0.5 × ATR(14)
- **Wave 5 trade SL** = Wave 4 low − 0.5 × ATR(14)

Hover over the SL label to see the approximate **Risk:Reward ratio**.

### Info Table

The top-right dashboard provides a real-time summary:

| Row | Description |
|-----|-------------|
| HTF Trend | "Bullish" (teal) or "Bearish" (red) |
| Current Wave | The last confirmed wave number (W1–W5) |
| W2 Valid | ✓ if Wave 2 retracement is within 5% of the configured ratio |
| W3 Target | Projected Wave 3 price target (1.618 × W1 from W2 low) |
| W4 Valid | ✓ if Wave 4 retracement is within 5% of the configured ratio |
| SL Level | Current stop-loss price level |

---

## Setting Up Alerts

1. After adding the indicator to your chart, click the **Alerts** (bell) icon.
2. Under **Condition**, select "EW+Fib Analyzer".
3. Choose one of the four alert conditions:
   - **EW Wave 3 Entry** – bullish W3 long setup
   - **EW Wave 5 Entry** – bullish W5 long setup
   - **EW Wave 3 Short** – bearish W3 short setup
   - **EW Wave 5 Short** – bearish W5 short setup
4. Configure notification method (email, webhook, popup, etc.) and save.

---

## Risk Disclaimer

> **This indicator is provided for educational and informational purposes only. It does not constitute financial or investment advice. Elliott Wave analysis is inherently subjective, and automated detection may not always align with manual wave counts or real-time market conditions. Past patterns do not guarantee future results. Always use proper risk management, never risk more than you can afford to lose, and consult a qualified financial advisor before making any trading decisions.**
