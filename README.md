# Clean the Netflix Dataset

Project URL: https://roadmap.sh/projects/cleaning-netflix-dataset

A data-cleaning exercise on the Netflix Movies and TV Shows dataset using **pandas**.
The notebook walks through inspecting the raw data, handling missing values, fixing
data types, splitting the `duration` column, checking for duplicates, and exporting a
clean CSV.

## Files

| File | Description |
| --- | --- |
| `analyse.ipynb` | Jupyter notebook with the full cleaning workflow |
| `netflix_titles.csv` | Raw dataset |
| `netflix_titles_cleaned.csv` | Cleaned dataset produced by the notebook |

## Cleaning steps

1. **Inspect the data** — `df.info()`, `df.head()` and `df.describe(include="all")` to
   get a first look at shape, dtypes and distributions.
2. **Report missing values** — a table of missing counts and percentages per column,
   sorted worst-first.
3. **Fill missing values** — `director`, `cast`, `country`, `rating`, `listed_in` and
   `description` are filled with `"Unknown"` so no rows are lost.
4. **Parse dates** — `date_added` is converted to a real `datetime` with
   `errors="coerce"` for unparseable values.
5. **Split `duration`** — extracted into `duration_value` (nullable `Int64`) and
   `duration_unit` (`min` / `Seasons`, with `Season` normalised to `Seasons`).
6. **Check duplicates** — exact duplicate rows and duplicated `show_id` values.
7. **Validate and export** — re-check dtypes and missing values, then write
   `netflix_titles_cleaned.csv`.

## Requirements

```bash
pip install pandas jupyter
```

## Usage

```bash
jupyter notebook analyse.ipynb
```

Run the cells top to bottom; the last cell writes `netflix_titles_cleaned.csv`.
