# China-Shock-Europe
Replicating Autor, Dorn & amp; Hanson (2013) on European trade data using Python
# The China Shock in Europe
### Replicating Autor, Dorn & Hanson (2013) on European Trade Data

---

## Research Question
Did Chinese import competition increase unemployment in Europe after China's 
WTO entry in 2001 — and did it hit all countries equally?

## Key Finding
Contrary to findings for the United States, European countries with higher 
import exposure to China experienced *lower* unemployment in 2015. The most 
exposed economies (Czech Republic, Germany) adapted through industrial 
upgrading, while high unemployment in Spain and Portugal reflected the 
compounding effect of the 2010 Eurozone debt crisis.

## Methodology
- **Data:** World Bank API (wbgapi), 12 European economies, 1990–2022
- **Exposure index:** Manufacturing share (2001) × China export growth (2001–2015)
- **Outcome variable:** Unemployment rate (2015)
- **Estimation:** OLS regression (statsmodels)
- **Replication basis:** Autor, Dorn & Hanson (2013), AER


## Main Results

| Finding | Value |
|---|---|
| Coefficient on exposure index | -0.30 |
| R-squared | 0.17 |
| p-value | 0.186 |
| China export growth 2001–2015 | $2,090 billion |
| Most exposed country | Czech Republic (index: 49.2) |
| Least exposed country | Netherlands (index: 26.2) |

## Visualisations
- Trade openness across Europe (1990–2022)
- China's export boom with WTO entry annotated
- Exposure index vs unemployment scatter plot
- Interactive choropleth map of exposure across Europe

## Tools
`Python` `pandas` `wbgapi` `matplotlib` `plotly` `statsmodels` `Google Colab`

## Reference
Autor, D., Dorn, D., & Hanson, G. (2013). The China Syndrome: Local Labor 
Market Effects of Import Competition in the United States. 
*American Economic Review*, 103(6), 2121–2168.

## Interactive Map Image Visualization:

https://nbviewer.org/github/Poonum-Malhi/china-shock-europe/blob/main/01_data_collection.ipynb 
---
*Built as part of an Economics × AI research

----
## Addendum — Panel Extension (July 2026)

The original analysis above tests a single-year cross-section (12 countries, 2015). This addendum
extends it to a full panel to check whether the null result is robust to a larger sample.

### Methodology

A shift-share exposure index was built following Autor, Dorn and Hanson (2013): each country's fixed
2001 manufacturing share of GDP, interacted with China's time-varying exports of goods and services,
2001–2022. This was regressed on unemployment with two-way fixed effects (country and year), standard
errors clustered by country.

### Results

| Specification | Coefficient | p-value | Observations |
|---|---|---|---|
| Original (2015 cross-section) | -0.264 | 0.190 | 12 |
| Pooled OLS, no fixed effects | -0.040 | 0.202 | 264 |
| Two-way fixed effects panel | -0.107 | 0.544 | 264 |

### Interpretation

Unlike a companion extension of the GVC/Reshoring analysis (Part 5/6 of this series), where expanding
the sample turned a non-significant subsample result into a significant one, expanding this China Shock
analysis to 264 country-year observations does **not** produce significance — if anything, adding fixed
effects moves the result further from significance. This is treated as evidence that the China Shock
null result is a genuine null, not merely a product of insufficient statistical power in the original
12-country sample.

### Data

World Bank WDI: manufacturing value added (% GDP, `NV.IND.MANF.ZS`), unemployment rate
(`SL.UEM.TOTL.ZS`), China's exports of goods and services (`NE.EXP.GNFS.CD`), 2001–2022.
