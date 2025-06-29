# 🎬 Movie Booking Real-Time CDC Aggregation with Snowflake

##  Acknowledgements
This project was built as part of hands-on learning to strengthen data engineering skills using Snowflake’s real-time features and visual analytics capabilities.

---

## Tech Stack

- **Snowflake** (Streams, Tasks, Dynamic Tables)
- **SQL**
- **Python**
- **Snowpark for Python**
- **Streamlit (in Snowflake)**

---

## Project Architecture
This project follows the Medallion Architecture pattern — a layered approach to organizing data transformations in Bronze, Silver, and Gold stages for better modularity, scalability, and data governance.
```plaintext
GCS / Volume
   ↓ (Raw File)
Raw Snowflake Table
   ↓ (Stream + Task every 1 min)
Bronze Table (CDC + Metadata)
   ↓ (Dynamic Table - Filtering)
Silver Table (Cleaned Data)
   ↓ (Dynamic Table - Aggregation)
Gold Table (KPIs)
   ↓ (Snowpark + Streamlit)
Dashboard
```
---

## Pipeline Flow
Raw Table
Stores raw movie booking data from simulated file ingestion.

CDC Stream + Bronze Layer
A Snowflake Stream captures changes and loads them to the Bronze table every 1 minute via a scheduled Task.

Silver Layer
A Dynamic Table filters and cleans the CDC-enriched data.

Gold Layer
Another Dynamic Table performs aggregations (e.g., total bookings per movie or time window), refreshing every 2 minutes.

Streamlit Dashboard
Built using Snowpark and Streamlit in Snowflake to visualize real-time booking metrics.

---

## Features
- Real-time CDC handling with Snowflake Streams
- Incremental data refresh using scheduled Tasks
- Implements the **Medallion Architecture** (Bronze–Silver–Gold) using Snowflake Streams and Dynamic Tables
- Live dashboard using Streamlit inside Snowflake

---

## Learning Outcome
This project demonstrates how to:
- Build a real-time ingestion pipeline using Snowflake Streams and Tasks
- Implement Bronze–Silver–Gold architecture using Dynamic Tables
- Visualize KPIs with Snowpark-powered Streamlit dashboards
- Simulate CDC processing and incremental ingestion without external tools

