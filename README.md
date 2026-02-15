# Google-Capstone-Cyclistic
This repository contains my attempt to complete the Case Study n°1 in the 8th course of the Google data analyst certificate on Coursera.



In this case study, I act as a junior analyst for the marketing team at **Cyclistic**, a bike-share company in Chicago.

The Director of Marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, my goal is to understand how casual riders and annual members use Cyclistic bikes differently to identify conversion opportunities.

To accomplish this, I followed a structured data analysis process: outlining the project scope, preparing and processing the data for consistency, and conducting a deep-dive analysis. Finally, I visualized key findings to provide data-driven recommendations to stakeholders.

🛠 **Tools Used:**
* **Python (Pandas)**: Data Cleaning, Merging & Manipulation
* **SQL (DuckDB)**: Exploratory Data Analysis (EDA) & Summary Statistics
* **Tableau Public**: Data Visualization & Dashboarding
* **Jupyter Notebook**: Interface for the Process and the Analysis phases

📅 **Timeline:**
12 Months of historical data analyzed (Feb 2025 - Jan 2026).

🎯 **Objective:**
Design a User Conversion Strategy.

---

## 1. Phase 1: ASK
**Business Task:**
Identify differences in usage patterns between casual riders and annual members to design a marketing strategy aimed at converting casual riders into annual members.

**Key Stakeholders:**
Lily Moreno (Director of Marketing), Cyclistic Marketing Analytics Team, Cyclistic Executive Team.

---

## 2. Phase 2: PREPARE
**Data Source & Organization:**
The data is located in Zip files stored on the AWS Cloud, containing CSV files. Each file corresponds to one month of Cyclistic's bike trip data.
* **Process:** I downloaded the 12 previous months of data, unzipped them, and stored them in a secure local directory to facilitate the manipulation steps.

**Data Quality Assessment (ROCCC Analysis):**
* **Reliable & Original:** The data is sourced directly from the operator (Motivate International Inc.), ensuring it is an internal, primary dataset without third-party alteration.
* **Comprehensive:** The dataset includes all key metrics (start/end times, station names, user types) required to answer the business question.
* **Current:** The analysis covers the most recent 12-month period (Feb 2025 - Jan 2026), making the insights relevant to current trends.
* **Cited:** The data is provided under a formal [Data License Agreement](https://divvybikes.com/data-license-agreement). The City of Chicago owns all rights, title, and interest in the Data.

**Privacy & Ethics:**
The data is strictly anonymous. It does not contain personally identifiable information (PII) about riders, ensuring the protection of individual identities.

**Data Clarity:**
The dataset is structured with clear column headers. Technical acronyms for geographic coordinates (lat/lng) are used, which are standard terms understood by the analytics team and stakeholders.

---

## 3. Phase 3: PROCESS (Python)
**Goal:** Clean, merge, and prepare the raw data for analysis.

I used **Python (Pandas)** in a Jupyter Notebook to handle the large volume of data (approx. [5,5] million rows).

**Key Steps Performed:**
* **Merging:** Combined 12 separate CSV files into a single dataframe.
* **Data Cleaning:**
    * Removed rows with missing station names or IDs.
    * Checked for and removed duplicate entries.
* **Feature Engineering:**
    * Created a `ride_length` column (duration of trips).
    * Created a `day_of_week` column to analyze weekly trends.
* **Quality Control:** Filtered out "bad data" (e.g., negative ride lengths or maintenance trips).

👉 **[View the Python Cleaning Notebook here](https://github.com/Geoffrey-L/Google-Capstone-Cyclistic/blob/main/Capstone_Processing1.ipynb)**

---

## 4. Phase 4: ANALYZE (SQL - DuckDB)
**Goal:** Uncover trends and patterns using SQL queries.

Once the data was clean, I used **DuckDB** (SQL within Jupyter) to perform the exploratory analysis. SQL allowed for efficient querying of the aggregated dataset.

**Key Insights Uncovered:**
* **Ride Duration:** Casual riders take significantly longer trips on average compared to members.
* **Weekly Patterns:** Members dominate usage during weekdays (commuting), while casual riders peak on weekends (leisure).
* **Monthly Trends:** A massive spike in casual usage occurs during the summer months (June-August).

👉 **[View the SQL Analysis Notebook here](https://github.com/Geoffrey-L/Google-Capstone-Cyclistic/blob/main/Capstone_Analysis.ipynb)**

---

## 5. Phase 5: SHARE
**Goal:** Visualize the findings to tell a compelling story.

I created an interactive dashboard in Tableau to illustrate the differences between the two user groups.

![Dashboard Screenshot](https://github.com/Geoffrey-L/Google-Capstone-Cyclistic/blob/main/Cyclistic_Dashboard.png)

* **Key Visualization:** The Heatmap clearly shows the contrast between the "9-to-5" commute pattern of members vs. the weekend afternoon preference of casuals.

📊 **[Explore the Interactive Dashboard on Tableau Public](https://public.tableau.com/app/profile/geoffrey.liebart/viz/Capstone_project_17709944497150/Tableaudebord1)**
