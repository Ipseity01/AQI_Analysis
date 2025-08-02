# Air Quality Index (AQI) Analysis for India

This project performs a comprehensive analysis of air quality data across various cities in India from 2015 to 2020. The primary goal is to uncover trends, identify key pollutants, pinpoint the most polluted cities, and group cities with similar air quality characteristics using machine learning.

---
## Dataset

The analysis is based on the "Air Quality Data in India (2015-2020)" dataset, which contains daily air quality measurements for multiple cities.

* **Source:** [Kaggle](https://www.kaggle.com/rohanrao/air-quality-data-in-india)
* **Features:** `Date`, `City`, `PM2.5`, `PM10`, `NO`, `NO2`, `NOx`, `NH3`, `CO`, `SO2`, `O3`, `Benzene`, `Toluene`, `Xylene`, `AQI`, and `AQI_Bucket`.

---
## Methodology

The project follows a structured data analysis pipeline:

1.  **Data Cleaning:** Loaded the dataset, converted date columns to datetime objects, and handled missing values by filling them with the median of their respective columns to maintain data integrity.
2.  **Exploratory Data Analysis (EDA):** Performed time-series, seasonal, and city-wise analysis to understand the data's underlying patterns.
3.  **Correlation Analysis:** Investigated the relationships between different pollutants and the overall AQI.
4.  **KPI Development:** Created a "Bad Air Days" metric to quantify and compare the frequency of poor air quality across cities.
5.  **Clustering:** Applied the K-Means algorithm to group cities with similar pollution profiles, using the Elbow Method to determine the optimal number of clusters.

---
## Analysis and Insights

Here are the key findings from the analysis, explained through the generated visualizations.

### 1. National Average AQI Trend

This plot shows the daily average AQI for India over the five-year period.

<img width="500" height="400" alt="national_average_aqi_trend_over_ime" src="https://github.com/user-attachments/assets/b0dfc565-10e8-436b-b487-04ebd13bf5c8" />


* **Insight:** The AQI in India shows significant **seasonal fluctuations**. There is a recurring pattern where pollution levels rise towards the end of the year and drop mid-year. A noticeable dip is visible around early 2020, which may correspond to the reduced industrial and vehicular activity during the initial COVID-19 lockdowns.
  
### 2. City-wise AQI Analysis (Top 5 most polluted cities)

This plot shows the city-wise analysis of AQI.

<img width="500" height="400" alt="AQI Trend in Top 5 Most Polluted Cities" src="https://github.com/user-attachments/assets/a3eb4bb4-fcc4-47db-9754-1578f77886cf" />

### 3. Pollutant Correlation Heatmap

This heatmap reveals the strength of the linear relationship between different pollutants and the AQI.

<img width="400" height="400" alt="Correlation Heatmap of Pollutants and AQI" src="https://github.com/user-attachments/assets/826ebc17-d9e3-40bf-aba7-8c7117a62a4f" />


* **Insight:** **Particulate matter (PM2.5 and CO) exhibits the strongest positive correlation with AQI** (0.63 and 0.65, respectively). This indicates that these microscopic particles are the primary drivers of poor air quality in India. Other pollutants like NO2 and PM10 also show a moderate positive correlation.

### 4. Distribution of AQI Buckets

This pie chart breaks down the air quality across India into the standard AQI categories.

<img width="400" height="400" alt="Distribution of AQI Buckets" src="https://github.com/user-attachments/assets/213bddf8-394c-4144-9476-f6db18fa6d9f" />


* **Insight:** The majority of days fall into the **'Moderate' (35.7%)**, **'Satisfactory' (29.2%)**, and **'Poor' (13.7%)** categories. While 'Good' air quality days account for a small fraction (9.2%), a significant portion of days are in the 'Poor', 'Very Poor', or 'Severe' buckets, highlighting a persistent air quality challenge.

### 5. Top 10 Cities with the Most "Bad Air Days"

This chart ranks cities by the number of days they experienced 'Poor', 'Very Poor', or 'Severe' air quality.

<img width="500" height="400" alt="Top 10 cities with the most Bad Air Days" src="https://github.com/user-attachments/assets/c8bc726a-0742-4047-849a-470b883dd8bb" />


* **Insight:** **Delhi is by far the most polluted city**, with over 1,000 "Bad Air Days" in the five-year period. It is followed by other northern Indian cities like Ahmedabad, Lucknow, and Patna. This points to a severe, localized air pollution crisis in specific urban centers.

### 6. Monthly Average AQI

This plot shows the cyclical nature of air pollution throughout the year.

<img width="500" height="400" alt="Monthly Average AQI in India" src="https://github.com/user-attachments/assets/b11d8ad0-4388-44e1-87df-1b76dbe10deb" />


* **Insight:** Air quality worsens significantly during the **winter months (October to January)** and is at its best during the **monsoon season (July to September)**. This pattern is likely due to a combination of meteorological factors like temperature inversion in winter and the cleansing effect of rain during the monsoon. In northern cities like Delhi, burning of crop stubble is also one of the major contributors of high AQI during the winter months.

### 7. PM2.5 vs. AQI Scatter Plot

This scatter plot visually confirms the relationship between PM2.5 levels and the overall AQI.

<img width="500" height="400" alt="newplot" src="https://github.com/user-attachments/assets/d6c2fed0-41c2-4fa7-9a20-717463f2b2d3" />


* **Insight:** There is a clear, positive relationship: as **PM2.5 levels increase, the AQI also increases**, and the AQI bucket shifts from 'Good' to 'Severe'. This reinforces the finding from the heatmap that PM2.5 is a dominant pollutant.

### 7. K-Means Clustering of Cities

To group cities with similar pollution characteristics, a K-Means clustering algorithm was applied.

#### a) Elbow Method

First, the Elbow Method was used to find the optimal number of clusters.

<img width="500" height="400" alt="Elbow Method for Optimal Number of Clusters" src="https://github.com/user-attachments/assets/df68869b-7477-48cc-a4e7-e1966cf51bfa" />


* **Insight:** The "elbow" in the plot appears at **k=3**, suggesting that the cities in the dataset can be meaningfully grouped into **three distinct clusters**.

#### b) City Clusters

The cities were then grouped into three clusters based on their average PM2.5 and AQI levels.

<img width="500" height="400" alt="Clusters of Cities based on PM2 5 and AQI" src="https://github.com/user-attachments/assets/aa33118b-ca20-4f11-a1e5-b4f2acdce531" />


* **Insight:**
    * **Cluster 0 (Dark Blue):** Represents cities with the **highest levels of PM2.5 and AQI**, indicating consistently poor air quality. These are the most polluted cities.
    * **Cluster 1 (Medium Blue):** Includes cities with **moderate** PM2.5 and AQI levels.
    * **Cluster 2 (Light Blue):** Consists of cities with relatively **lower** pollution levels and better air quality compared to the others.

This clustering helps in identifying regional patterns and allows for targeted policy-making.

---
## Conclusion

This analysis reveals that air quality in India is a significant concern driven primarily by particulate matter (PM2.5). Pollution follows a strong seasonal pattern, peaking in winter. While some cities enjoy relatively better air, major urban centers, especially Delhi, face severe and persistent air pollution. Clustering cities based on their pollution profiles can help authorities to understand the varying severity of the problem across the country and devise more effective, region-specific strategies to combat it.

---
## Technologies Used
* **Python**
* **Pandas & NumPy** for data manipulation
* **Matplotlib, Seaborn & Plotly** for data visualization
* **Scikit-learn** for K-Means clustering
* **Power Bi** for dashboard
