# MovieLens 100k: Hybrid Cloud Big Data Analytics Pipeline

A comprehensive Big Data engineering and analytics pipeline leveraging the distributed compute capabilities of **Apache Spark 4.0.3** integrated with a dual **NoSQL Cloud Data** layer (**MongoDB Atlas** & **DataStax Astra DB / Cassandra**).

This project processes over 100,000 system rating transactions across 943 users and 1,682 movies to model a production-ready enterprise data infrastructure.

---

## 🔗 Live Interactive Dashboard
The data engineering pipeline results have been converted into a production-grade interactive dashboard and deployed live in the cloud. You can explore the filtered metrics, user segments, and NoSQL payloads directly:

👉 **[Launch Production Analytics Dashboard](https://tinyurl.com/mwprkfhx/)**

---

## System Architecture & Stack

The infrastructure is engineered for scalable distributed ETL processing and low-latency analytics:

- **Compute Engine:** Apache Spark 4.0.3 (PySpark Classic DataFrame & RDD APIs)
- **Language Runtime:** Python 3.12.13
- **Document NoSQL Storage:** MongoDB Atlas Cloud (via native PyMongo driver)
- **Wide-Column NoSQL Storage:** DataStax Astra DB Cloud Cassandra (via REST Data API)
- **Analytics & Web App:** Streamlit, Pandas, Plotly Express, pgeocode, Seaborn

---

## Project Objectives

1. **Top-Tier Content Performance:** Identify the top 10 highest-rated movies (min. 20 ratings) and conduct deep-dive demographic profiling (gender, age, occupation, timelines, and geospatial footprints).
2. **User Segmentation Modeling:** Isolate power users ($\ge$ 50 reviews) and mathematically extract their ultimate favorite genre using distributed window functions.
3. **Multi-Engine Cloud Ingestion:** Implement an idempotent ETL egress mechanism to route transactional intelligence into optimal hybrid NoSQL cloud clusters.

---

## Core Insights & Data Discoveries

### 1. Demographic & Temporal Behavioral Profiles
* **The Student Monopoly:** Users under 20 are almost completely homogenous, with students representing **64 out of 77 total active users**, showing that teen tracking is heavily tied to academic cycles.
* **The Nighttime Binge-Watching Culture:** Users under 20 capture an absolute traffic monopoly during **Night/Late Night windows (9 PM – 5 AM)**, accounting for **55.8%** of total system activities. Conversely, **Afternoon (12 PM – 5 PM)** drops to its lowest at **6.15%**, reflecting active school or lecture hours.
* **Geospatial Concentration:** Choropleth mapping shows demand is highly concentrated in specific coastal and midwestern tech hubs, with **California (CA)** leading national viewership numbers, followed by **Minnesota (MN)** due to native academic dataset origins.

### 2. Temporal Macro Trends
* **November 1997 Operational Spike:** A massive, anomalous ingestion event occurred in November 1997, peaking at nearly **24,000 reviews** (2x–3x higher than any surrounding month). This suggests a historical database injection or major marketing campaign.
* **January Sentiment Reset:** Every post-holiday January window (e.g., Jan 1998) shows a distinct dip in user sentiment down to a **3.40 average rating baseline**, revealing a cyclical pattern where users apply stricter evaluation habits at the start of the new year.

---

## NoSQL Cloud Integration Implementation

### A. Document Storage: MongoDB Atlas Cloud
Processes and stores long-term power-user profile metrics (`user_id`, `genre`, `frequency`). It uses a bulk write operation combined with an automatic document refresh strategy to serve real-time dashboard applications.

### B. Columnar Storage: DataStax Astra DB / Cassandra Cloud
Maintains real-time platform tracking logs for top-performing items using an API-driven environment setup. By mapping the business domain `movie_id` to the specialized document `_id` key, it eliminates randomized text string hashes and ensures rapid indexing.

---

## How to Run Sessions

### Option 1: Open the Interactive Web Application
Skip local environment configurations by exploring the web interface directly on the Streamlit Cloud network:
- **Production Link:** [https://spark-nosql-movielens-pipeline-8bqtkcs3m7uoie6nmjs4hm.streamlit.app/](https://spark-nosql-movielens-pipeline-8bqtkcs3m7uoie6nmjs4hm.streamlit.app/)

### Option 2: Local Repository Execution Sequence

For developers looking to download, inspect, and host the cluster configurations locally:

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/haniyturana/spark-nosql-movielens-pipeline.git](https://github.com/haniyturana/spark-nosql-movielens-pipeline.git)
   cd spark-nosql-movielens-pipeline
