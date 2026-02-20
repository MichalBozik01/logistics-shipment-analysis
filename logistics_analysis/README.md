# Logistics Shipment Performance Analysis

## Project Overview

This project analyzes shipment performance across multiple logistics segments to identify delays, variability, and operational bottlenecks. The goal was to determine how long shipments actually take, how performance compares to plans, and which stages contribute most to delays.

The analysis was conducted using Microsoft Excel, Power Query, and Pivot Tables.

---

## Objectives

* Measure actual shipment duration
* Compare planned vs actual performance
* Identify early vs delayed shipments
* Detect bottlenecks in shipment stages
* Evaluate variability and reliability
* Handle extreme outliers appropriately

---

## Dataset Description

The dataset contains shipment-level records identified by a unique shipment ID and associated airport information. Each shipment passes through four key logistics segments:

* **RCS** — Received from shipper
* **DEP** — Departure
* **RCF** — Received from flight
* **DLV** — Delivered to consignee

These segments may occur across multiple transport legs (LEG1–LEG4).

Durations were recorded in minutes and converted to days for analysis.

---

## Data Preparation

Key preprocessing steps:

* Transformed dataset from wide to long format using Power Query
* Aggregated event data to shipment level
* Calculated planned duration, actual duration, and delay
* Converted time units from minutes to days
* Identified extreme outliers (delay > 500,000 minutes)
* Excluded outliers from core analysis while documenting them separately

---

## Key Findings

* Shipment durations exhibit a strongly right-skewed distribution

* Median duration: **7.4 days**

* Mean duration: **19.81 days** (inflated by long delays)

* 90th percentile: **18.12 days**

* **72% of shipments were completed earlier than planned**, while **28% were delayed**

* The **DEP (departure) stage** was identified as the primary source of delays

* The **DLV stage showed the highest variability**, indicating inconsistent final delivery performance

Overall, most shipments perform efficiently, but a small subset of delayed cases disproportionately affects overall performance and predictability.

---

## Visualization

The project includes a histogram of shipment durations (aggregated per shipment) up to the 90th percentile to clearly illustrate the distribution of typical deliveries while avoiding distortion from extreme outliers.

---

## Limitations

* Extreme delay values were excluded from the main analysis to preserve statistical validity
* External factors (weather, customs, operational disruptions) were not available
* Results are descriptive and do not imply causation

---

## Tools Used

* Microsoft Excel
* Power Query
* Pivot Tables
* Descriptive Statistics
* Percentile Analysis

---

## Repository Structure

```
logistics-shipment-analysis/
│
├── logistics_dataset_analysis.xlsx   # Main analysis workbook
├── data/
│   ├── raw_data.xlsx
│   ├── cleaned_data.xlsx
│   └── outliers.xlsx
│
├── visuals/
│   └── shipment_duration_histogram.png
│
└── README.md
```

---

## Author

**Michal Božík**
Aspiring Data Analyst

---

## Project Purpose

This project was created as part of a personal data analytics portfolio to demonstrate skills in data cleaning, statistical analysis, and business insight generation using real-world-style logistics data.
