# final_project
Dataset Description
Title: Monthly Groundwater Levels in Germany 1990-2021

Overview: This dataset includes groundwater level measurements from approximately 6,700 monitoring stations across Germany, spanning the years 1990 to 2021. The dataset aims to provide insights into the long-term trends in groundwater levels, highlighting significant declines during drought years, particularly between 2018 and 2021.

Columns in the Dataset
1. messstellen.csv (Master Data and Trends)
This file contains the primary data for all monitoring stations, including trend analysis results.

ms_nr: Monitoring station number (unique identifier for each monitoring station).
bundesland: Federal state where the monitoring station is located.
behoerde: Authority responsible for the monitoring station.
kreis: District where the monitoring station is located.
bez: Descriptive name or code for the monitoring station.
ags: Official municipality key.
latitude: Latitude of the monitoring station (in EPSG:4326 coordinate system).
longitude: Longitude of the monitoring station (in EPSG:4326 coordinate system).
pct_data_1990_2021: Percentage of available monthly average values from 1990 to 2021.
breakpoint_drop: Indicates whether a monitoring station was excluded from the analysis after manual inspection (True if excluded).
trend_normalized: Normalized trend in groundwater levels, expressed as a percentage per year.
trend_bin: Trend classification, ranging from "stark sinkend" (strongly decreasing) to "stark steigend" (strongly increasing).
trend_raw: Raw trend in groundwater levels, expressed in meters per year.
range: Range of monthly average values in meters.
p_value: P-value from the trend analysis, indicating the statistical significance of the trend.
2. monthly (Monthly Data)
This folder contains monthly groundwater data categorized by federal states.

ms_nr: Monitoring station number.
year: Year of the measurement.
month: Month of the measurement.
min_gwl: Lowest monthly groundwater level (in meters above sea level).
mean_gwl: Average monthly groundwater level (in meters above sea level).
max_gwl: Highest monthly groundwater level (in meters above sea level).
3. tiefststaende_nach_kreis.csv (Lowest Levels by District)
This file contains the yearly lowest groundwater levels for each district.

bundesland: Federal state.
kreis: District.
bez: Descriptive name or code for the district.
ags: Official municipality key.
jahr (1990-2021): Yearly columns indicating the total number of monitoring stations that recorded their lowest groundwater level in that specific year.
Example Calculation and Analysis Files
trendanalyse.ipynb: An example notebook demonstrating how to calculate and analyze trends for selected monitoring stations.
tiefststaende.ipynb: An example notebook demonstrating how to calculate the yearly lowest groundwater levels and summarize the data by district.
Key Points from the Methodology
Data Collection: Data was gathered from various federal states through web scraping and press inquiries.
Normalization: Monthly average groundwater levels were calculated for each monitoring station from 1990 to 2021. Stations with less than 95% data availability were excluded.
Accuracy Check: The Changepoint package in R was used to detect abrupt changes in the data, indicating potential errors. Stations with identified issues were manually reviewed and excluded if necessary.
Trend Calculation: The 32-year trend was calculated using the Mann-Kendall trend test with a Trend-Free Pre-Whitening (TFPW) variation to identify long-term trends. Results were expressed as change in meters per month and normalized to percentage per year.
Classification: Trends were classified into categories from "strongly decreasing" to "strongly increasing".
Summary
This dataset provides a comprehensive overview of groundwater levels across Germany, detailing trends over the past 32 years and highlighting areas of concern. The data can be used for various analyses, such as assessing the impact of climate change on groundwater resources and informing water management policies.










































Source: https://correctiv.org/aktuelles/kampf-um-wasser/2022/10/25/klimawandel-grundwasser-in-deutschland-sinkt/?district=11000&bbox=13.029186795091533%2C52.34487403468921%2C13.777477988256294%2C52.68202302678873&zoom=9.815568400474646#tool
