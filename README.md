# Pine Script Indicators

## 1H RSI Realtime Break Signals (5m)

`htf_rsi_realtime_signals.pine` is a Pine Script v5 indicator intended for use on a 5-minute TradingView chart.

### Behavior

- Pulls the 1-hour RSI with `request.security()`.
- Uses `barmerge.lookahead_on` so the still-forming 1-hour RSI is reflected in realtime instead of waiting for the 1-hour candle close.
- Shows only small signal characters on the 5-minute chart:
  - Red `S` above the candle when the 1-hour RSI enters `>= 70` from below.
  - Blue `L` below the candle when the 1-hour RSI enters `<= 30` from above.
- Includes alert conditions for both realtime signals.

### Default settings

- Chart timeframe: 5 minutes
- Higher timeframe RSI: 1 hour
- RSI length: 14
- Overbought: 70
- Oversold: 30

### Important warning

This is a realtime alert/observation indicator, not a confirmed-signal or backtesting tool. Because the signal uses the current, unclosed 1-hour RSI, it can repaint. If the 1-hour RSI returns below 70 or above 30 before the 1-hour candle closes, the displayed signal can disappear or change.
