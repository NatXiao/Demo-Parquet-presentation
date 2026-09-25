# CSV vs Parquet Demo

A small demo comparing CSV and Parquet using `pandas` and `pyarrow`: file
size and compression, column pruning, binary-but-inspectable metadata, full
metadata inspection (schema, row groups, compression, encoding), and
predicate pushdown with its limitations.

## Files

- `demo.ipynb` — runs the comparison demo.

## Requirements

See [pyproject.toml](parquet-demo/pyproject.toml)

## Setup

1. Run ```uv init``` or install the dependencies with uv:

   ```bash
   uv add pandas pyarrow
   ```

   (or, if you don't have a `pyproject.toml` yet: `uv init` first, then the
   command above.)

2. Create a `data/` folder at the project root and place your source CSV
   file in it:

   ```bash
   mkdir data
   # copy your CSV file into data/, e.g. data/fichier.csv
   ```

3. Open [the demo](parquet-demo/src/parquet_demo/demo.ipynb) (you can use ```uv run jupyter lab```)

adjust the file names/paths and column names to match your dataset:

   - `CSV_PATH` / `PARQUET_PATH` — path to your CSV and the Parquet file to
     generate.


`uv run` automatically uses the project's virtual environment, so there's
no need to activate it manually.

## Notes

- The demo also writes a few extra Parquet files with different
  compression codecs (`data/fichier_none.parquet`,
  `data/fichier_snappy.parquet`, etc.) as part of the compression
  comparison — these are demo artifacts, not required inputs.

