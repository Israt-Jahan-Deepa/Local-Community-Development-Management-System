# Local-Community-Development-Management-System
Source code and project documentation for the Local Community Development Management System.
# Safeguard Mechanism Compliance Gap Analysis

## Overview

This repository contains the quantitative analysis behind a policy brief on **Australia's Safeguard Mechanism**, prepared for a Master of Public Policy application portfolio at Flinders University.

The analysis models the legislated aggregate baseline decline against covered industrial emissions from 2023-24 to 2029-30. It highlights the widening **compliance gap** — the shortfall that covered facilities must close through Australian Carbon Credit Units (ACCUs), Safeguard Mechanism Credits (SMCs), or on-site abatement.

## Files

| File | Description |
|------|-------------|
| `dataset.csv` | Time-series data on covered emissions, aggregate baseline, and compliance gap. |
| `analysis.py` | Python script that loads the data, computes derived statistics, and generates the shaded gap chart. |
| `safeguard_gap_chart.png` | Output chart produced by `analysis.py`. |

## Data

`dataset.csv` combines:

- **Actual CER compliance data** for 2023-24 and 2024-25.
- **Projected values** for 2025-26 to 2029-30, extending the observed 2023-24 → 2024-25 emissions reduction rate (≈2.3% p.a.) and applying the legislated 4.9% annual baseline decline.

| Column | Description |
|--------|-------------|
| `Financial Year` | Australian financial year (e.g., 2023-24). |
| `Covered Emissions (Mt CO2-e)` | Aggregate emissions from Safeguard facilities. |
| `Aggregate Baseline (Mt CO2-e)` | Statutory baseline after the 4.9% annual decline. |
| `Compliance Gap (Mt CO2-e)` | Covered emissions minus baseline when emissions exceed the baseline. |
| `Status` | Whether the year is at parity or offset-dependent. |

## Requirements

- Python 3.8+
- pandas
- matplotlib

Install dependencies with:

```bash
pip install pandas matplotlib
```

## Usage

Run the analysis from this directory:

```bash
python analysis.py
```

The script will:

1. Load `dataset.csv`.
2. Compute year-on-year changes and the average annual widening of the gap.
3. Print a summary table to the console.
4. Save `safeguard_gap_chart.png` in the same directory.

## Key Findings

- The compliance gap opens in **2024-25** at **3.5 Mt CO2-e**.
- By **2029-30**, the gap is projected to reach **~17.3 Mt CO2-e**.
- This represents a **394% cumulative increase** from 2024-25.
- The gap widens by an average of **~2.8 Mt CO2-e per year** over the projection period.
- Because covered emissions decline at only **~2.3% per year** while the baseline falls at **4.9% per year**, offset demand must accelerate unless firms invest more in on-site abatement.

## Policy Implications

The trajectory suggests that current fixed-price ACCU settings may crowd out capital investment in genuine emissions reductions. The policy brief recommends three structural reforms:

1. **Facility-level cap on offset use** — limit the share of compliance that can be met through ACCU or SMC surrender.
2. **Dynamic ACCU price corridor** — adjust price ceilings as headroom disappears to preserve abatement incentives.
3. **Automated, real-time emissions tracking** — move beyond annual NGER reporting to enable earlier intervention.

## Sources

- Clean Energy Regulator. (2024). *Safeguard Mechanism: Data Insights 2023-24*. Australian Government.
- Clean Energy Regulator. (2025). *Safeguard Mechanism: Data Insights 2024-25*. Australian Government.
- Department of Climate Change, Energy, the Environment and Water (DCCEEW). (2024). *Safeguard Mechanism reforms*. Australian Government.
- Parliament of Australia. (2023). *Safeguard Mechanism Legislation Amendment (Reforms) Act 2023*.

## License

This code is provided for academic and portfolio use. Please replace the GitHub URL in the policy brief with your own repository link before submission.

