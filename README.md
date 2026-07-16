# transport-stocks-lead-indicator
# Do Transport Stocks Lead the Market?

A test of Dow Theory using modern data: Does movement in transport 
stocks (FedEx, UPS, Union Pacific, Norfolk Southern) predict future 
moves in the S&P 500?

## Background

Dow Theory, holds that transportation stocks move 
ahead of the broader market since goods must be shipped before 
they're sold. I wanted to test whether this holds up in modern daily 
data.

## Method

- Pulled daily price data (2010–2026) for FDX, UPS, UNP, NSC, and the 
  S&P 500 using Python (`yfinance`)
- Built a normalized transport composite index from the four stocks
- Converted prices to daily returns
- Tested correlation between transport returns and *future* S&P 500 
  returns at four lags: 1 day, 1 week, 1 month, 1 quarter

## Results

| Lag | Correlation |
|-----|-------------|
| 1 day | -0.080 |
| 1 week | 0.031 |
| 1 month | -0.002 |
| 1 quarter | -0.031 |

All correlations were close to zero: No statistically meaningful 
lead-lag relationship was found at any horizon tested.

## Interpretation

This is consistent with efficient markets: if transports reliably 
predicted the broader market, that signal would likely already be 
priced in by other participants. The chart below shows both series 
tracking closely together, including a simultaneous drop during the 
2020 crash, rather than one clearly leading the other.

![Transport vs S&P 500](transport_vs_sp500.png)

## Limitations & next steps

- Daily data may be too short-horizon to catch a slower-moving signal. Worth retesting with monthly or quarterly data
- Only tested US large-cap transport stocks; an international angle 
  (e.g. Deutsche Post/DHL) could provide alterior insight
- Correlation doesn't imply causation: Both series may simply react 
  to the same news simultaneously

## Tools

Python, pandas, yfinance, matplotlib, Jupyter Notebook

## Author
  Fred Warner — [LinkedIn](www.linkedin.com/in/fred-louis-warner
) · [GitHub]()
