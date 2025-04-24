Flight Delay Project — Part 2

✈️ Flight Delay Prediction Using Flight and Weather Data

🚀 Project Overview

This project aims to analyze patterns in flight delays by integrating flight schedule data with external factors such as weather conditions, time of departure, airline, and route information. The objective is to identify key factors contributing to delays and perform statistical testing to understand their impact. These insights will form the foundation for developing a machine learning model to predict delays, helping airlines optimize operations and enabling passengers to make informed decisions.

📄 Data Collection

Flight Data Source:

Kaggle Flight Delay Dataset (2018–2024) — Includes flight dates, scheduled and actual departure times, delay durations, airlines, and airport details.

Weather Data Source:

NOAA Local Climatological Data — Hourly weather conditions (e.g., temperature, wind speed, precipitation, sky condition) recorded at airport stations.

Transformations & Enrichments:

Feature Engineering:

Extracted Day_of_Week, Month, Hour_of_Day, and Season from flight times.

Categorized delays into: On-time (<15 min), Short Delay (15-60 min), Long Delay (>60 min).

Grouped weather conditions into: Clear, Rainy, Stormy.

Merged Datasets:

Combined flight and weather data using flight_date and origin_airport.

Calculated Congestion Metric:

Number of flights per airport per hour to assess congestion impact.

Processed data is stored in /data/processed/.

📊 Exploratory Data Analysis (EDA)

Descriptive Statistics:

Average delay: 42 minutes

Percentage of delayed flights (>15 min): 27%

Peak delays observed during evening flights and in winter months.

Key Insights from Correlation:

Delays increase significantly under stormy conditions.

Higher congestion correlates with longer delays.

Certain airlines and airports consistently show higher average delays.

Visualizations:

Histogram of delay durations: delay_distribution.png

Boxplot of delays by airline: boxplot_delays_airline.png

Bar chart: Average delay by weather condition: bar_avg_delay_weather.png

Heatmap of feature correlations: feature_correlation_heatmap.png

Visualizations are available in the /exploratory_data_analysis/ folder.

🧪 Hypothesis Testing

1️⃣ Impact of Weather on Flight DelaysH₀: Weather conditions do not significantly affect the likelihood of flight delays.H₁: Severe weather conditions increase the likelihood of flight delays.

Test Used: Chi-Square Test (Categorical: Weather vs. Delay occurrence)

Result:p-value = 0.004 ➔ Reject H₀ → Weather conditions do significantly impact delays.

2️⃣ Effect of Congestion on Delay DurationH₀: There is no difference in average delay times across different congestion levels.H₁: Higher airport congestion leads to longer average delays.

Test Used: ANOVA (Comparing delay times across low, medium, high congestion)

Result:p-value = 0.012 ➔ Reject H₀ → Congestion has a significant effect on delays.

Full hypothesis test results are available in /hypothesis-testing/results.csv.



🎯 Findings & Insights

Severe weather increases delay probability by approximately 20%.

Flights during peak congestion hours have significantly longer delays.

Airlines differ in operational efficiency, with Airline X showing the lowest average delays.

Winter months and evening flights are most prone to delays.

⚠️ Limitations

Data limited to domestic US flights due to available datasets.

Weather data reflects general airport conditions, not specific runway-level variations.

The analysis covers recent years only; long-term trends were not evaluated.

