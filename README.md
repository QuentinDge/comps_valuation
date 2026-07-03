# Comparable Companies Valuation
A comparable companies valuation: estimating a fair EV range for a tech company from its listed peers' EV/EBITDA multiples.

## Result
For a target with approximately $5bn EBITDA, the model estimates an EV of **~$80bn** (range $63-94bn). *All figures in USD.*

## Method
- Pull fundamentals for 8 large-cap tech peers via yfinance
- Store the data in two SQL tables (companies, financials) and join them in SQLite
- Compute the sector's median EV/EBITDA, with the interquartile range for a robust valuation range

## How to run
`pip install yfinance pandas`, then open `comps_valuation.ipynb` and run all cells.

## Limitations 
- Small sample (8 companies): the median is sensitive to any single outlier
- Single multiple (EV/EBITDA): a serious analysis would cross-check several
- All peers sit in the broad "Technology" sector but have different business models

## Tech stack
Python, pandas, SQLite, yfinance
