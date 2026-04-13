# SUPER3_Brahmastra

A comprehensive all-in-one **TradingView** indicator written in **Pine Script v5**. It combines multiple technical analysis tools into a single overlay, giving traders a complete view of market structure, momentum, trend, and key price levels — all on one chart.

> **Short title:** `sukurtt123`  
> **License:** GNU Affero General Public License v3 (AGPL-3.0)

---

## Features

### 1. Central Pivot Range (CPR)
- **Today's CPR** — Pivot (P), Top Central (TC), and Bottom Central (BC) levels for the current trading session.
- **Tomorrow's CPR** — Pre-calculated CPR levels for the next session so you can plan ahead.
- **Historical CPR** — Plots all past CPR levels as circles for historical reference.
- **Weekly CPR** — Weekly Pivot, TC, and BC levels alongside weekly R1/R2/R3 and S1/S2/S3.
- **Resistance levels:** R1, R2, R3 (daily and weekly).
- **Support levels:** S1, S2, S3 (daily and weekly).
- **Previous Day High / Low / Close** — Optional lines showing yesterday's price extremes.
- Configurable **session start time** (default: 09:15 IST) for adaptation to non-Indian markets.

### 2. Moving Average
- **89-period EMA** plotted in yellow with a line width of 3, acting as the dynamic trend baseline.

### 3. VWAP (Volume-Weighted Average Price)
- Standard session VWAP with a configurable source (default: HLC3).
- Toggleable display.

### 4. SuperTrend
- ATR-based SuperTrend with configurable **ATR period** (default: 10) and **ATR multiplier** (default: 2.2).
- Optional wick-based calculations for tighter stops.
- **Buy / Sell labels** directly on the chart.
- Built-in **alerts** for direction change, buy signal, and sell signal.

### 5. RSI Bar Color
- Candle bar colors change dynamically based on RSI:
  | Condition | Color |
  |---|---|
  | Overbought (53–80) | Green |
  | Oversold (25–47) | Red |
  | Very Overbought (> 80) | White |
  | Very Oversold (< 25) | Yellow |
- All RSI thresholds are configurable.

### 6. MACD Signal Ribbon
- Displays MACD signal-line dots at the bottom of the chart.
- Configurable fast (12), slow (26), and signal (9) lengths.
- Color changes from green → light green → red based on signal direction.

### 7. Price Channel
- Choose from four channel types:
  - **Bollinger Bands** (default) — EMA ± 2 standard deviations.
  - **Donchian Channel** — Highest high / lowest low over the period.
  - **Envelope** — EMA ± a percentage.
  - **NONE** — Disable the channel.
- Configurable length (default: 14) and envelope percentage.

### 8. Super XTrend (HalfTrend)
- A half-trend indicator that smooths out noise using ATR-based channels.
- Configurable **Amplitude** and **Channel Deviation**.
- Plots a colored line (green = uptrend, red = downtrend) and prints arrow signals on trend reversals.
- Built-in **alerts** for buy and sell signals.

### 9. SonarLab Order Blocks
- Automatically detects **Bullish** and **Bearish** order blocks based on price momentum.
- Configurable **Sensitivity** (lower = more blocks shown).
- OB **Mitigation Type**: Close or Wick.
- Boxes are automatically deleted when price mitigates the order block.
- Built-in **alerts** when price re-enters an order block.

### 10. Market Structure Break (MSB) & Advanced Order Blocks
- ZigZag-based market structure engine with configurable **ZigZag Length** (default: 9) and **Fib Factor** for breakout confirmation.
- Detects **Market Structure Breaks (MSB)** and labels them on the chart.
- Draws four types of boxes at each MSB:
  - **Bu-OB** — Bullish Order Block
  - **Bu-BB / Bu-MB** — Bullish Break Block / Mitigation Block
  - **Be-OB** — Bearish Order Block
  - **Be-BB / Be-MB** — Bearish Break Block / Mitigation Block
- Supports multiple timeframes (Chart, 5m, 15m, 30m, 1h, 2h, 4h, D).
- Boxes are deleted when price mitigates them; up to 5 active boxes per type.
- Built-in **MSB alert**.

### 11. ADX Table
- Real-time **ADX values** for the 3-minute, 5-minute, and 15-minute timeframes displayed in a table at the bottom-right of the chart.
- The current chart's timeframe is highlighted with a distinct background color.
- Configurable decimal precision and colors.

### 12. RSI Divergence
- Detects **regular bullish and bearish divergences** between price and RSI.
- Configurable pivot bar lookback (left/right bars), RSI length, overbought/oversold levels, and lookback depth (1–5).
- Optional pivot high/low markers.

---

## Installation

1. Open [TradingView](https://www.tradingview.com) and go to the **Pine Script Editor** (bottom panel).
2. Copy the entire contents of `SUPER3_Brahmastra_v2.txt`.
3. Paste it into the Pine Script editor.
4. Click **"Add to chart"**.

---

## Configuration

All settings are accessible via the indicator's **Settings** panel, organized into groups:

| Group | Description |
|---|---|
| Session | Trading session start time (hour & minute) |
| CPR | Toggle daily/weekly CPR, R/S levels, PDHL, PDC |
| VWAP | Toggle VWAP and set its source |
| SuperTrend | ATR period, multiplier, wicks, labels |
| RSI Bar Color | RSI thresholds for bar coloring |
| MACD | Fast, slow, signal lengths and color lookback |
| Channel | Channel type, length, and envelope % |
| Super XTrend | Amplitude and channel deviation |
| Order Block | Sensitivity, mitigation type, and colors |
| Settings | ZigZag length, timeframe, fib factor, MSB box colors |
| ADX | Smoothing, DI length, colors, decimal precision |
| RSI Divergence | Pivot bars, RSI length, OB/OS levels, lookback depth |
| Alerts | Toggle buy/sell alerts for order blocks |

---

## Alerts

The indicator includes the following alert conditions:

- **SuperTrend Direction Change**
- **SuperTrend Buy**
- **SuperTrend Sell**
- **Super XTrend (ultra) Buy**
- **Super XTrend (ultra) Sell**
- **Price inside Bullish OB**
- **Price inside Bearish OB**
- **Market Structure Break (MSB)**

To activate, right-click the indicator on the chart → **Add alert**.

---

## Requirements

- TradingView account (free or paid)
- Pine Script v5 support (available on all TradingView plans)

---

## License

This project is licensed under the **GNU Affero General Public License v3.0 (AGPL-3.0)**. See the [LICENSE](LICENSE) file for details.