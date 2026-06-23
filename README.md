# Time Series Analysis of Recorded Air-Raid Alert Starts in Ukraine

## Overview

This project presents a descriptive time-series analysis of historical records of oblast-level air-raid alert starts in Ukraine.

The goal is to explore how the number of recorded alert starts changed over time in the available dataset. The project does not forecast future alerts, provide real-time monitoring, estimate danger, or explain military causes of changes.

## Research question

How did the daily number of recorded oblast-level air-raid alert starts in Ukraine change over time in the available historical dataset?

## Data source

The analysis uses the volunteer oblast-level dataset from the public repository:

[Vadimkin/ukrainian-air-raid-sirens-dataset](https://github.com/Vadimkin/ukrainian-air-raid-sirens-dataset)

The notebook downloads the file:

`datasets/volunteer_data_en.csv`

Original timestamps are recorded in UTC. For daily and monthly analysis, timestamps are converted to the `Europe/Kyiv` time zone.

## Method

The notebook performs the following steps:

1. Downloads the public CSV dataset.
2. Inspects the first records, columns, data types, and missing values.
3. Checks timestamp validity, exact duplicate rows, and records where an end time is earlier than a start time.
4. Aggregates recorded alert starts into a daily time series.
5. Excludes the incomplete current day.
6. Creates daily, monthly, and rolling-average visualisations.
7. Compares complete calendar years and identifies months with the highest and lowest average daily values.

## Main outputs

The notebook includes:

* daily recorded oblast-level alert starts;
* 7-day and 30-day rolling averages;
* monthly totals;
* monthly average recorded starts per day;
* a month-by-year heatmap;
* descriptive summaries for 2023, 2024, and 2025;
* ranked months with the highest and lowest average daily values.

## Snapshot of results

The notebook was executed on 23 June 2026.

At that time, the downloaded dataset contained 101,705 records covering the period from 25 February 2022 to 23 June 2026.

For complete calendar years:

| Year | Average recorded starts per day |
| ---- | ------------------------------: |
| 2023 |                           52.21 |
| 2024 |                           69.16 |
| 2025 |                           67.51 |

The highest monthly daily averages in the available data occurred in January-May 2026.

## Important limitations

* This is a descriptive analysis of one historical dataset.
* A recorded oblast-level alert start is not equivalent to an attack, casualty, damage event, or direct measure of danger.
* One broader alert event may create records for several oblasts.
* The dataset is volunteer-based and may be affected by changes in collection practices or coverage over time.
* The source dataset may change when the notebook is run again because it is updated over time.
* The results must not be used for real-time safety decisions or operational interpretation.

## How to run

### Option 1: Google Colab

Open `01_time_series_analysis.ipynb` in Google Colab and run all cells from top to bottom.

### Option 2: Local environment

Install the required libraries:

```bash
pip install -r requirements.txt
```

Then open the notebook with Jupyter:

```bash
jupyter notebook
```

## Project files

```text
01_time_series_analysis.ipynb  # Main analysis notebook
README.md                      # Project overview
requirements.txt               # Python dependencies
LICENSE                        # MIT License for this project code
```

## AI usage disclosure

AI was used as an engineering assistant to help structure the project, explain Python code, draft code, and identify methodological limitations.

All results in this repository come from the executed notebook and the cited public dataset. AI was not used as a source of data or as a substitute for checking the output.

## License

This repository is licensed under the MIT License.

The upstream dataset has its own source terms and attribution requirements. Please refer to the original dataset repository for details.
