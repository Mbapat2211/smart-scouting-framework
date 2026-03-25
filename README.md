# smart-scouting-framework

## Project Overview
The **Smart-Scouting-Framework** is a professional-grade data science pipeline designed to transform raw football event data into actionable recruitment intelligence. By leveraging unsupervised machine learning, this framework moves beyond traditional scouting by mathematically identifying **Tactical Archetypes**—grouping players by their functional roles (e.g., Physical Hubs, Clinical Finishers) rather than simple performance rankings.

Using a dataset from the 2022 FIFA World Cup, this repository demonstrates a modular, scalable workflow that can be adapted by professional recruitment departments to align transfer targets with specific tactical philosophies.

---

## Core Methodology
The framework follows a structured four-stage pipeline to ensure data integrity and scouting accuracy.

### 1. Data Ingestion & EDA
* **Source Handling:** Automated loading of raw tournament event data.
* **Exploratory Analysis:** Initial data profiling to identify missing values and tournament-specific anomalies (e.g., varying substitute minutes).

### 2. Feature Engineering & Pre-Processing
* **Minute Aggregation:** Reconstructs total playing time to ensure accurate "Per-90" normalization.
* **Metric Scaling:** Utilizes `MinMaxScaler` to standardize features (Goals, xG, Aerial Wins, G-xG) into a $[0, 1]$ range, ensuring balanced weighting in clustering.
* **DNA Metrics:** Engineering of the **Smart Scout Score**, a weighted index designed to highlight players with elite efficiency and physical dominance.

### 3. Machine Learning & Archetype Clustering
* **K-Means Clustering:** Grouping the striker population into three distinct tactical profiles based on the **Elbow Method** for mathematical parsimony.
* **Archetype Definition:** * **Elite Finishers:** High-volume threats with superior xG and conversion rates.
    * **Aerial Hubs:** Physical