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
Identify differences in usage patterns between casual riders and annual members to design a marketing strategy aimed at converting casual riders into annual members (using the last 12 months of user data to complete the task).

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

I used **Python (Pandas)** in a Jupyter Notebook to handle the large volume of data (approx. 5,5 million rows).

**Key Steps Performed:**
* **Merging:** Combined 12 separate CSV files into a single dataframe.
* **Data Cleaning and Standardization:**
    * Standardized the station references based on the most recent data.
    * Checked for and removed duplicate entries.  
* **Feature Engineering:**
    * Created a `ride_length_minutes` column (duration of trips).
    * Created a `day_of_week` column to analyze weekly trends.
* **Quality Control:** Filtered out "bad data" (e.g., negative ride lengths, maintenance and micro trips).
* **Handling Nulls:** Rows with missing station names were retained as they represent valid bike trips (verified via GPS coordinates). Only trip with technical anomalies were removed.


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

**Key Visualization:** This interactive dashboard highlights three fundamental differences in the use of Cyclistic bikes:
  
 * Annual Members use the service heavily on weekdays (Monday through Friday), suggesting utilitarian use (commuting). Conversely, Casual users are             more active on weekends, indicating recreational or tourist use;
 * Members show a relatively smooth and stable activity pattern throughout the year, even in cooler periods. Casual users have very seasonal                    behavior, with a strong peak in summer (+17% of trips in July/August) and a drastic drop in winter.
 * The heat map reveals that members have two very clear peaks of activity: 8 a.m. and 5 p.m. (office hours). Occasional users have a smoother curve            that gradually increases throughout the day, reaching its peak in the early afternoon (2pm-4pm).

📊 **[Explore the Interactive Dashboard on Tableau Public](https://public.tableau.com/app/profile/geoffrey.liebart/viz/Capstone_project_17709944497150/Tableaudebord1)**

---

## 6. Phase 6: ACT

We successfully demonstrated how bike usage patterns differ significantly between our two user groups. Based on these findings, we can now suggest data-driven recommendations to help the company convert more casual riders into annual members :

**Recommendations:**

   * **Introduce a Seasonal "Summer Pass":** Given the massive activity peak in July and August, a specific summer subscription could serve as a stepping           stone. It would attract casual users initially, with the long-term objective of upgrading them to full annual members once they are in the                   ecosystem.
   * **Target Weekend Riders for Membership Conversion:** Since casual riders are most active on weekends, we should launch specific "Weekend Membership"           offers or provide incentives for signing up for an Annual Plan during the weekend (e.g., "Sign up this Saturday and get your first month free").
   * **Launch a Spring Campaign:** Marketing efforts should intensify in late spring (April/May), just before the usage spike. Capturing these users                right before their peak activity period could maximize the Return on Investment (ROI).

      
      
**Next Steps & Future Analysis:**

To further refine this strategy, it would be relevant to analyze the geographical distribution of casual trips. Visualizing station data could help identify strategic locations for advertising campaigns or determine where to expand the station network to better serve the users.
