# china-shock-europe
Replicating Autor, Dorn &amp; Hanson (2013) on European trade data using Python
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

---
*Built as part of an Economics × AI research portfolio targeting 
World Bank and OECD internships.*
