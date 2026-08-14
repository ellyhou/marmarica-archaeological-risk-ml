# Data

This project uses the **Marmarica archaeological spatial dataset**, a regional database of archaeological and cultural heritage sites across northeastern Libya and northwestern Egypt.

The dataset contains **3,355 records** with information including geographic coordinates, site type and subtype, environmental context, visible remains, coordinate accuracy, chronology, and recorded heritage risk.

## Source

The original dataset and metadata are available from Zenodo:

- DOI: [10.5281/zenodo.7678852](https://doi.org/10.5281/zenodo.7678852)

The original files are not redistributed in this repository. Please download them from the source record and review the usage terms provided there.

## Local Directory Structure

```text
data/
├── README.md
├── raw/
│   ├── Marmarica_sites.csv
│   └── Metadata.xlsx
└── processed/
    └── Marmarica_sites_analysis_ready.csv
```

Only this `README.md` is tracked by Git. The contents of `raw/` and `processed/` are excluded to avoid redistributing third-party data and generated files.

## Setup

1. Download the dataset from the Zenodo record.
2. Create a `raw/` directory inside `data/` if it does not already exist.
3. Place the main CSV file at:

   ```text
   data/raw/Marmarica_sites.csv
   ```

4. Optionally place the accompanying metadata file at:

   ```text
   data/raw/Metadata.xlsx
   ```

5. Run the notebook:

   ```text
   notebooks/marmarica_site_analysis.ipynb
   ```

The notebook reads the raw CSV using a semicolon delimiter and writes the cleaned analysis-ready dataset to:

```text
data/processed/Marmarica_sites_analysis_ready.csv
```

## Data-Quality Notes

Several issues in the original data require preprocessing before analysis:

- Coordinate values contain inconsistent decimal-point formatting.
- Placeholder categories such as `Unknown` and `Undetermined` are not represented as missing values.
- Approximately 95.8% of chronology records are marked as `Undetermined`.
- The recorded `Risk_level` values require verification against `Cod_Risk` and the dataset metadata.

The complete cleaning and validation procedure is documented in the project notebook.
