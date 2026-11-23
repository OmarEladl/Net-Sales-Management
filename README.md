# Net Revenue Management (NRM) Analysis — Shampoo Category

Market, portfolio, promotion, and new-launch analysis for a shampoo/hair-care business, built to give a single, fact-based view of market position, SKU profitability, promotion ROI, and a 2024 net sales forecast.

## Problem Statement

The business could not answer, in one place and with confidence:

1. **Market position** — What is the total market worth, how is it split between suppliers and brands, and is the company gaining or losing share by region and year?
2. **Portfolio profitability** — Which SKUs (by brand, product, pack size) generate the best net sales, gross profit, and gross margin, and which underperform?
3. **Promotion effectiveness** — Do trade promotions generate enough incremental (uplift) sales over baseline to justify their cost, and which mechanics have a positive ROI?
4. **New product economics** — What net sales, gross profit, and margin can be expected from new launches before committing spend?
5. **Forward outlook** — Based on 2018–2023 market values, what is a defensible 2024 forecast, and what could specific growth levers (category growth, organic shampoo, 50ml pack size) add?

Without resolving these, pricing, trade-spend, and launch decisions were being made on fragmented, inconsistent data — risking margin leakage from over-discounting or ineffective promotions, and missed or overstated growth opportunities.

## Objectives

- Consolidate market, internal sales, promotion, and new-launch data into one consistent analytical structure.
- Quantify market share by brand/supplier/region/year.
- Quantify SKU-level profitability for the current internal portfolio.
- Evaluate promotion ROI (uplift vs. baseline, net of cost).
- Model new product launch economics from estimated share, price, and cost assumptions.
- Produce a 2024 market forecast with confidence bounds and a named-driver growth bridge.

## Repository Contents

| File | Description |
|---|---|
| `Net_Revenue_Management_Analysis.xlsx` | Master workbook: raw data tabs plus derived analysis tabs (`Brands per Supplier`, `Market Share`, `SKU Profitability`, `Forcast 2024`) |
| `dataset_shampoo.csv` | Monthly market data by category/subcategory/supplier/brand/region, 2018–2024 (~4,400 rows) |
| `internal_sales_data.csv` | Internal SKU-level pricing, COGS, and 2022 volume |
| `new_product_launch.csv` | Candidate new products with estimated market share, price, and cost assumptions |
| `promotion_analysis.csv` | Individual promotion events with value sales, baseline sales, uplift, and cost |

## Data Dictionary (key fields)

- **Values Month / Units Month** — Monthly market value and volume by brand/supplier/region.
- **Net Price / Retail Price / COGS** — Pricing and cost inputs used to derive gross profit and margin.
- **Volume 2022** — Annual unit volume used for internal SKU net sales.
- **Estimated Unit Market Share** — Assumed share used to size new-launch volume.
- **Value sales / Baseline sales / Uplift / Costs / ROI** — Promotion performance fields; Uplift = Value sales − Baseline sales, ROI = Uplift ÷ Costs.

## Methodology

1. **Data consolidation & cleaning** — Normalize currency/number formats (comma decimals, dot thousands separators) and align sources on common keys (Brand, Year, Month).
2. **Market sizing & share** — Aggregate market values by supplier/brand/year to build the share pivots.
3. **Profitability** — Derive Net Sales, Gross Profit (per unit and per product), and Gross Margin for each internal SKU.
4. **Promotion ROI** — Compare promoted value sales to an estimated non-promoted baseline; ROI expressed net of promotion cost.
5. **New launch modeling** — Apply estimated market share to a category volume assumption, then apply price/COGS to estimate net sales, gross profit, and margin.
6. **Forecasting** — Fit a trend forecast with confidence bounds to 2018–2022 market values, project 2023–2024, and bridge to an internal net sales estimate with named growth drivers (organic shampoo, 50ml pack size).

## Assumptions & Limitations

- Promotion baselines are estimated as an average of non-promoted months, not derived from a controlled experiment.
- New-launch and forecast figures depend on assumed category volumes and share-to-units conversions not independently validated against external market research.
- The `Market Share` pivot is populated only through 2021 in the source workbook and should be refreshed as new data arrives.
- Source files use mixed numeric formats that must be normalized before any further automated analysis.
- Findings are specific to the shampoo category and the brands/suppliers present in the data.

## Next Steps

1. Validate the promotion baseline methodology (ideally with a holdout/control period) before setting future trade-spend budgets on these ROI figures.
2. Refresh the `Market Share` pivot through the latest year on a regular cadence.
3. Recalibrate the 2024 forecast and net-sales-to-market ratio against actuals as they become available.
4. Use the SKU profitability ranking to flag low-margin SKUs for pricing/cost review, and prioritize new-launch funding using the modeled economics.
5. Standardize raw data intake formats to reduce manual cleanup on future refreshes.
