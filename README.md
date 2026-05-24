<img width="1271" height="539" alt="image" src="https://github.com/user-attachments/assets/817174fe-a59a-4c99-b2f4-ee452ec612b9" />
# 🎬 Netflix Data Pipeline — ELT Architecture with Snowflake & dbt

![Pipeline Architecture](./architecture.png)

A modern **ELT (Extract → Load → Transform)** data pipeline that ingests Netflix data from raw source files, stages it in Amazon S3, loads it into Snowflake, and transforms it using dbt — serving clean, production-ready data to BI tools like Looker Studio, Power BI, and Tableau.

---

## 📋 Table of Contents

- [Architecture Overview](#architecture-overview)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Pipeline Layers](#pipeline-layers)
- [Getting Started](#getting-started)
- [dbt Setup & Usage](#dbt-setup--usage)
- [Snowflake Configuration](#snowflake-configuration)
- [Data Transformation](#data-transformation)
- [Testing](#testing)
- [BI & Reporting](#bi--reporting)
- [Contributing](#contributing)

---

## 🏗️ Architecture Overview

```
[Netflix / CSV]
      │
      ▼
[Amazon S3]          ← Extract & Load
      │
      ▼
[Snowflake Raw Layer]        ① Raw Layer
      │
      ▼
[Snowflake Staging Layer]    ② Staging Layer  ← dbt (Transform, Test, Orchestrate)
      │
      ▼
[Snowflake Dev/Prod Layer]   ③ Serving Layer
      │
      ▼
[Looker Studio / Power BI / Tableau]
```

The pipeline follows a **3-layer Snowflake architecture**:

| Layer | Symbol | Description |
|-------|--------|-------------|
| **Raw** | ① | Unmodified source data loaded from S3 into Snowflake |
| **Staging** | ② | Cleaned, renamed, and typed data ready for transformation |
| **Serving (Dev/Prod)** | ③ | Final, business-ready models exposed to BI tools |

---

## 🛠️ Tech Stack

| Component | Tool | Purpose |
|-----------|------|---------|
| **Source Data** | Netflix exports / CSV files | Raw input data |
| **Cloud Storage** | Amazon S3 | Staging area for raw files before loading |
| **Data Warehouse** | Snowflake | Central storage and compute for all layers |
| **Transformation** | dbt (data build tool) | SQL-based transformation, testing, and orchestration |
| **BI Layer** | Looker Studio, Power BI, Tableau | Data visualization and reporting |

---



