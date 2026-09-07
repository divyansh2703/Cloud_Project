# Formula 1 Lap and Pit Context Feature Engineering

A collaborative exploratory data engineering repository for Formula 1 lap timing, pit stops, safety cars and red flags. The main notebook develops timing and contextual features and exports an analytical table. Additional notebooks preserve earlier iterations and debugging work.

## The question

How can heterogeneous race data be transformed into a consistent lap table with pace, cumulative timing, gap and pit context?

## Tools and methods

Python, PySpark, pandas, Window functions, Parquet, Feature engineering.

## Work in this repository

1. Loaded timing and event inputs and normalised race and driver fields.
2. Created cumulative timing, position and gap features using Spark window operations.
3. Explored joins between lap, pit, safety car and red flag records.
4. Recorded an exported lap table and wrote CSV and Parquet outputs.

## Evidence and scope

| Measure | Recorded value |
| --- | --- |
| Recorded lap input rows | 589,081 |
| Recorded pit input rows | 7,374 |
| Recorded safety car input rows | 362 |
| Recorded red flag input rows | 98 |
| Recorded final lap table rows | 589,081 |

## Repository guide

| File or folder | Purpose |
| --- | --- |
| [notebooks/Cloud_Data_Pipeline_f1.ipynb](https://github.com/divyansh2703/Cloud_Project/blob/main/notebooks/Cloud_Data_Pipeline_f1.ipynb) | Main feature engineering notebook |
| [notebooks/Data_Pipeline_Cloud.ipynb](https://github.com/divyansh2703/Cloud_Project/blob/main/notebooks/Data_Pipeline_Cloud.ipynb) | Earlier pipeline iteration |
| [notebooks/Untitled.ipynb](https://github.com/divyansh2703/Cloud_Project/blob/main/notebooks/Untitled.ipynb) | Exploratory debugging notebook |
| [notebooks/output/f1_full_engineered_csv](https://github.com/divyansh2703/Cloud_Project/tree/main/notebooks/output/f1_full_engineered_csv) | CSV output directory |

## Getting started

Start with `notebooks/Cloud_Data_Pipeline_f1.ipynb`. Use PySpark with a compatible Java runtime, pandas and the relevant Excel reader. Update local paths for pitstop, lap timing, safety car and red flag source files. Inspect notebook outputs and debugging branches before rerunning. The companion notebooks are historical iterations, not a required execution sequence.

## Current limitations

1. Some joins use incomplete race context, and the notebook records unresolved mapping concerns. The exported table requires key and grain validation before modelling.
2. A matching input and output row count does not prove that event joins are correct.
3. The repository does not demonstrate an operating cloud deployment or measured scalability benefit.

## Next steps

1. Resolve the race key and join cardinality concerns.
2. Consolidate this work with the related Formula 1 pipeline repositories.

## Authors and reuse

Divyansh Doshi and Amisha Sanjay Kadukar.

Documentation reviewed against the public repository on 7 September 2026. Counts are taken from the named saved artifacts or directly inspected CSVs; this review did not rerun model training or validate a complete deployment. No source code licence was found in the reviewed project tree. Data and third party material may have separate terms.
