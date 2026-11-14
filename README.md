# Used Car Listings: Pandas Data Analysis & EDA

Assignment: data ingestion and quality profiling, DataFrame queries (2.1 to 2.12) and visualisation with insights (3.1 to 3.7)
on `car_prices.csv` (558,837 used car listings).

## Files
| File | What it is |
|---|---|
| `car_prices_analysis.ipynb` | Full solution: code, outputs, charts and written insights, already executed |
| `car_prices_analysis.html` | Same notebook as a static page, readable without Jupyter |
| `requirements.txt` | Python packages |
| `Dataset/` | Put `car_prices.csv` here (84 MB, not included in this repo because of size) |

## Run it
```bash
pip install -r requirements.txt
# copy car_prices.csv into Dataset/
jupyter notebook car_prices_analysis.ipynb
```

## Key data-quality decisions
- 26 column-shifted rows and 12 rows with no selling price removed (558,799 rows kept); no duplicates found.
- Text standardised (lower case, brand aliases merged: 96 make labels became 56).
- `odometer = 999999` treated as missing; numeric gaps filled with medians, text gaps with `unknown`. The notebook has a table explaining each choice.
- The `condition` column mixes two scales (1 to 5 and 11 to 49); this is flagged in 3.5 and 3.6.
