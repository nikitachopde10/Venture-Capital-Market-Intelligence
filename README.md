# Venture Capital Market Intelligence Pipeline 🚀
### Advanced Database Management | Cross-Platform Data Engineering

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-green.svg)](https://www.mongodb.com/)
[![Google BigQuery](https://img.shields.io/badge/Google_Cloud-BigQuery-blue.svg)](https://cloud.google.com/bigquery)
[![ETL](https://img.shields.io/badge/Pipeline-ETL/ELT-orange.svg)]()

## 📌 Project Overview
This project implements a multi-stage data engineering pipeline designed to provide actionable intelligence for **Horizon Ventures**. By processing large-scale Crunchbase data, the system transforms raw, nested JSON documents into high-performance relational tables to analyze global venture capital trends.

The core challenge was managing **unstructured NoSQL data** and converting it into a **structured schema** optimized for complex analytical SQL queries.

---

## 🏗️ Architecture & Pipeline
The project follows a modern ELT (Extract, Load, Transform) architecture:

1.  **Ingestion:** Streamed 18,800+ raw company profiles from Google Cloud Storage into **MongoDB Atlas**.
2.  **Transformation (NoSQL):** Engineered a MongoDB Aggregation Pipeline to calculate:
    * `total_funding`: Summing individual funding rounds.
    * `founder_count`: Regex-based extraction of leadership roles.
    * `latest_funding_year`: Date normalization.
3.  **Migration:** Developed a Python-based migration script to flatten nested arrays and schema-map data into **Google BigQuery**.
4.  **Analytics:** Executed advanced SQL (Window Functions, CTEs) to identify geographic and sector-specific "sweet spots" for investment.

---

## 📊 Key Data Insights
Through the pipeline, I uncovered several high-value insights for venture capital allocation:

* **Category Specialization:** Identified that while California leads in total volume, states like **Washington (Mobile)** and **Maryland (Games/Video)** show higher "funding efficiency" (Average funding per company).
* **Funding Concentration:** Applied `DENSE_RANK()` to prove that in mature sectors like Advertising, capital is heavily skewed toward top leaders, suggesting a "winner-takes-all" market dynamic.
* **Anomaly Detection:** Calculated percentage differences against annual averages to identify outlier funding rounds that signaled market shifts.


---

## 🛠️ Technical Stack
* **Database:** MongoDB Atlas (NoSQL), Google BigQuery (Data Warehouse)
* **Languages:** Python (Pandas, Pymongo, Google-Cloud-BQ)
* **Tools:** MongoDB Aggregation Framework, Advanced SQL (Window Functions, CTEs)
* **Data Source:** Crunchbase Market Intelligence

---

## 🚀 How to Use
1.  **Setup MongoDB:** Ensure your connection string is configured in a `.env` file or environment variable.
2.  **Run Pipeline:** Execute the `Advanced_Database_Venture_Capital.ipynb` to trigger the ingestion and MongoDB transformation.
3.  **BigQuery Load:** Use the BigQuery client library to transfer the `companies_analysis` collection into structured tables.
4.  **Querying:** Run the included SQL scripts in Task 3 & 4 to replicate the market intelligence reports.

---

## 📈 Strategic Conclusion
This project demonstrates that **Geographic "Efficiency" often beats sheer volume.** For a firm like Horizon Ventures, the data suggests a "Barbell Strategy": maintain presence in mature hubs (CA/MA) while making concentrated, high-impact bets in specialized regions like Washington or Alabama where capital competition is lower but funding-per-company is higher.

---
*Developed as part of the Advanced Database Management Course.*
