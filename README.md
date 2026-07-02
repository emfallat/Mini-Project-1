# ECE5644 Mini Project 1

## What this project does

This repository takes a raw, half-million-row transaction export (December 2010 – December
2011) and:

1. Profiles the raw data to identify data-quality issues (missing IDs, blank descriptions,
   duplicate rows, cancellations, invalid prices/quantities, non-product line items).
2. Applies pandas' full data-wrangling toolkit (21 techniques: creating, selecting, filtering,
   sorting, replacing, renaming, handling missing values, dropping, deduplicating, applying
   functions, grouping, aggregating, resampling, concatenating, merging) to build a clean,
   completed-sales dataset.
3. Uses the cleaned dataset to answer seven business questions about seasonality, best sellers,
   markets, customer concentration, order value, returns/cancellations, and overall data quality.

## Repository contents

| File | Description |
|---|---|
| `e-commerce-data.ipynb` | Cleaning notebook, labeled by technique number |
| `clean_online_retail.csv` | Cleaned, completed-sales dataset |
| `data.csv` | Uncleaned data from Kaggle |
| `data_dictionary.md` | Column-by-column description of the final cleaned dataset |
| `findings_summary.md` | One-page answers to the seven business questions, with charts |
| `cleaning_decisions_log.md` | Judgment calls made during cleaning, and why |
| `requirements.txt` | Python library versions needed to reproduce this work |

## Dataset

**E-Commerce Data (UK Online Retail)** — a real, anonymised transaction export from a UK
online gift retailer, originally compiled at London South Bank University and hosted on the
UCI Machine Learning Repository.

Kaggle page: https://www.kaggle.com/datasets/carrie1/ecommerce-data

### How to download

**Option A — website**
1. Open the Kaggle page above.
2. Click **Download** and unzip the archive.
3. You should have a single file named `data.csv` (~45 MB, 541,909 rows).
4. Place `data.csv` in the same folder as the notebook.

**Option B — Kaggle API**
```bash
pip install kaggle
# place your kaggle.json API token in ~/.kaggle/
kaggle datasets download -d carrie1/ecommerce-data
unzip ecommerce-data.zip
```

**Encoding note:** the file is not UTF-8. It must be loaded with:
```python
pd.read_csv('data.csv', encoding='ISO-8859-1')
```
Loading it without specifying the encoding will raise a decoding error on the £ symbol.

## How to run

1. Clone this repository.
2. Create a virtual environment and install dependencies:
   ```bash
   python -m venv venv
   source venv/bin/activate    # Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```
3. Download `data.csv` per the instructions above and place it in the repository root.
4. Open `e-commerce-data.ipynb` in Jupyter or VS Code.
5. Run all cells from top to bottom (**Restart Kernel + Run All** is recommended — the
   notebook is stateful, and running cells out of order or more than once can produce
   misleading intermediate counts, e.g. a "rows removed" count that reads 0 on a re-run).
6. The notebook will produce `clean_online_retail.csv` in the repository root.

## Summary of findings

*(See `findings_summary.md` for the full write-up with charts and supporting numbers.)*
