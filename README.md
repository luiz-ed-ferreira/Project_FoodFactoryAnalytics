# Project Food Factory – Comunidados November 2026 Data Analysis Challenge

### Project Overview

<p align="center">
  <img src="img/comunidados_logo.png" alt="Comunidados Logo" height="200" width="300">
</p>

> The **Food Factory OEE Analytics** project aims to develop an end-to-end data analytics solution for a fictional food manufacturing company, **Vale Norte Alimentos**.

> The company operates four packaging lines and faces challenges consolidating production, downtime, quality inspection, and machine sensor data from multiple systems. The main objective is to establish a single source of truth capable of transforming shop-floor records into reliable operational indicators for management decision-making.

> The project covers the complete data pipeline, from raw data ingestion and data quality validation to analytical datasets and interactive dashboards.

### Business Questions

1. What is the Overall Equipment Effectiveness (OEE) of each production line?
2. Which downtime reasons account for the greatest production losses?
3. Which products have the highest rejection rates, and how much excess product weight is generated?
4. How much machine downtime remains unreported in the production system?

### Project Status & Improvements

In Progress

- [x] Environment and infrastructure setup.
- [ ] Raw data ingestion (Bronze Layer).
- [ ] Data standardization and validation (Silver Layer).
- [ ] Quarantine implementation.
- [ ] Analytical data modeling (Gold Layer).
- [ ] OEE calculations and validation.
- [ ] Downtime and quality analysis.
- [ ] IoT integration and micro-stoppage detection.
- [ ] Incremental processing and pipeline orchestration.
- [ ] Interactive Streamlit dashboard.
- [ ] Documentation and final project review.

### Project Scope

- Production performance monitoring across four packaging lines (L1–L4).
- Availability, Performance, and Quality (OEE) calculations.
- Downtime analysis and loss categorization.
- Product quality, rejection rates, and excess weight analysis.
- Detection of unreported machine micro-stoppages using IoT sensor data.
- Data quality management, validation, and quarantine processes.
- Automated and incremental data processing.

**Analysis Period:** November 2–14, 2026.

### Criterion

> The project is structured around tree levels of technical complexity.

#### Basic Level

- Implement a Medallion Architecture (Bronze, Silver, and Gold).
- Ingest all source files while preserving original data, filenames, and ingestion timestamps.
- Standardize production line identifiers, dates, and numeric fields.
- Remove duplicate records and retain the latest version of each production order.
- Implement a quarantine layer to store invalid records along with their respective rejection reasons.
- Develop Gold analytical tables for daily OEE by production line and downtime analysis by reason.
- Calculate Availability, Performance, Quality, and Overall Equipment Effectiveness (OEE).
- Aggregate downtime occurrences and total downtime minutes by reason.
- Implement a fixed pipeline execution sequence with execution logs.
- Develop an interactive Streamlit dashboard featuring an OEE monitoring panel, downtime Pareto chart, and quality report.

#### Intermediate Level

- Implement a Medallion Architecture (Bronze, Silver, and Gold).
- Ingest and consolidate seven datasets from MES, Laboratory, IoT, and ERP systems.
- Standardize Brazilian date, numeric, and text formats.
- Handle duplicate files and retain the latest version of production orders.
- Implement data validation rules and a quarantine layer for invalid records.
- Build OEE indicators by production line and day.
- Analyze downtime by reason, including occurrence counts and total downtime minutes.
- Incorporate laboratory inspections into product quality and excess weight analyses.
- Identify incomplete production days and exclude them from reliable OEE comparisons.
- Ensure idempotent processing, preventing duplicate records across pipeline executions.
- Implement data quality tests for uniqueness, mandatory fields, and referential integrity.

#### Advanced Level

- Integrate IoT sensor readings with production and downtime records.
- Convert UTC timestamps into Brasília local time.
- Detect unreported machine micro-stoppages.
- Implement incremental data ingestion and processing.
- Orchestrate pipeline execution with execution logs.
- Investigate the relationship between machine vibration patterns and mechanical failures.

### Data Sources

> The project uses seven datasets distributed across four operational systems.

| Dataset | Source System | Format | Description |
|---|---|---|---|
| `ordens_producao` | MES | CSV | Production orders |
| `paradas` | MES | CSV | Machine downtime records |
| `inspecoes` | Laboratory | CSV | Quality inspection samples |
| `sensores` | IoT | JSONL | Machine sensor readings |
| `produtos` | ERP | CSV | Product master data |
| `linhas` | ERP | CSV | Production line registry |
| `motivos_parada` | ERP | CSV | Downtime reason registry |

> The dataset covers four packaging lines, producing biscuits, pasta, and powdered chocolate products.

#### Data Processing Considerations

- Brazilian data format: semicolon-separated CSV files, decimal commas, and day/month/year dates.
- Different time zones: MES and laboratory records use Brasília time, while IoT sensor timestamps are in UTC.
- Daily files: operational datasets are delivered as separate daily files, while ERP registries are provided as consolidated files.
- File resubmissions: some MES production order files were corrected and resent, requiring version management.

### Project Architecture

```text
Project_FoodFactoryAnalytics/
│
├── docs/
│   └── project/
│       ├── project_overview.txt
│       └── project_description.pdf
│
├── img/
│   └── comunidados_logo.png
│
├── requirements.txt
├── README.md
└── .gitignore
```

. *The project structure will evolve as the data engineering and analytics components are implemented.*

### Prerequisites & Software

- Windows 11 with WSL2 (Linux/Ubuntu).
- Python 3.12.3.

> Attention! Consult the requirements.txt file for more information about python libraries used.

### Collaborators

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/luiz-ed-ferreira" title="Luiz Eduardo">
        <img src="https://avatars3.githubusercontent.com/u/145693602" width="100px;" alt="Luiz Eduardo GitHub Profile"/><br>
        <sub><b>Luiz Eduardo</b></sub>
      </a>
    </td>
  </tr>
</table>