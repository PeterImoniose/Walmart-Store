# Walmart Store-Level Time Series: Growth, Volatility, and Forecastability

Real weekly sales totals for 45 Walmart stores, Feb 2010 - Oct 2012.

## A note on the data

This covers the same underlying stores and time period as the companion
[walmart-recruiting-sales-analysis](https://github.com/PeterImoniose/walmart-recruiting-sales-analysis)
repo - the weekly totals match it almost exactly (both show £80,931,415.60 for the week
of 24-26 Dec 2010). That repo has department-level detail this one doesn't; this one is
aggregated to one row per store per week, which sets up a genuinely different question:
not *what* drives sales, but **which stores behave predictably enough to forecast well.**

## What's in this repo

[`notebooks/walmart_store_timeseries_analysis.ipynb`](notebooks/walmart_store_timeseries_analysis.ipynb)
- store-level growth, volatility, and seasonal-consistency analysis, framed around
forecastability rather than sales drivers.

## Key findings

- Store scale varies enormously: an 8.1x gap between the top and bottom store's average
  weekly sales.
- Fleet-wide growth was essentially flat (-0.9%) from 2010 to 2011, but that masks real
  divergence: 21 of 45 stores grew, ranging from -22.0% to +11.0% individually.
- Predictability varies a lot between stores (coefficient of variation ranging 0.042 to
  0.230) - some stores are far more erratic than others.
- The seasonal week-of-year pattern is highly consistent year to year (r = 0.953 between
  2010 and 2011) - strong evidence a seasonal-naive baseline would already perform well.
- The holiday-week uplift (+7.8%) closely matches the department-level finding (+7.1%) in
  the companion repo - a useful consistency check across aggregation levels.

Full detail and charts are in the notebook.

## Data

The dataset is not included in this repository (see the notebook for the source link) -
point `DATA_DIR` in the first code cell at your own local copy.

## Next steps

Per-store forecasting, prioritised by what this notebook found: start with a
seasonal-naive baseline given how strong the year-over-year correlation is, then focus
modelling effort on the higher-CV (less predictable) stores identified here.

## Author

Avwerosuo Peter Imoniose
