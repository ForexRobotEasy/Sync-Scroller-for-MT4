# Sync Scroller

Sync Scroller is a MetaTrader 4 (MT4) expert advisor developed by Forex Robot Easy. It allows users to synchronize the scrolling position of multiple charts, making it easier to analyze multiple currency pairs simultaneously.

## Input Parameters

- `timeframe` (default: PERIOD_H1): Specifies the timeframe for the charts.
- `symbols` (default: 'EURUSD,GBPUSD,USDJPY'): Specifies the symbols (currency pairs) to be opened and synchronized.

## Global Variables

- `chartHandle`: Stores the handle of the current chart.
- `symbolArray`: Stores an array of symbols split from the input parameter.
- `chartHandles`: Stores an array of chart handles for the opened charts.

## Expert Initialization Function (OnInit)

This function is called when the expert advisor is initialized. It performs the following steps:

1. Retrieves the handle of the current chart.
2. Splits the symbols string into an array.
3. Loops through all symbols and opens the corresponding charts, storing their handles in the `chartHandles` array.

## Expert Deinitialization Function (OnDeinit)

This function is called when the expert advisor is deinitialized. It closes all opened charts by looping through the `chartHandles` array and calling the `ChartClose` function.

## Expert Tick Function (OnTick)

This function is called on every tick. It performs the following steps:

1. Retrieves the current position of the current chart.
2. Loops through all chart handles in the `chartHandles` array.
3. Sets the same position for all charts by calling the `ChartSetInteger` function with the `CHART_FIRST_VISIBLE_BAR` parameter.

For detailed reviews and trading results of this product, please visit [Forex Robot Easy - Sync Scroller Review](https://forexroboteasy.com/forex-robot-review/sync-scroller-for-mt4-review-enhance-your-forex-backtesting/). Please note that Forex Robot Easy is not the official developer of this product. We are only showcasing sample code that can work as described in this product. To find the official developer of this product, please use MQL5.
