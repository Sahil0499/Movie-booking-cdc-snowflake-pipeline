# 🎬 Movie Booking Real-Time CDC Aggregation with Snowflake

A real-time data pipeline that simulates change data capture (CDC) on movie booking data using Snowflake Streams, Dynamic Tables, and Tasks. The pipeline processes incoming records through a layered (Bronze–Silver–Gold) architecture and visualizes live booking trends via a Streamlit dashboard powered by Snowpark.

---

## Tech Stack

- **Snowflake** (Streams, Tasks, Dynamic Tables)
- **Python**
- **Snowpark for Python**
- **Streamlit (in Snowflake)**

---

## Project Architecture

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
