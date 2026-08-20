# UK Road Accidents Analysis

Exploratory analysis, association rule mining, regional clustering, and 
time series forecasting on UK road accident data (2021–2022).

## Questions I explored
- How do time of day and lighting conditions relate to accident frequency and severity?
- Which junction types and traffic controls see the highest accident counts and severity?
- Do specific combinations of weather, lighting, and junction control co-occur with more severe accidents?
- Can short-term accident volume be forecast from limited historical data?
- Do different UK districts show distinct accident "profiles," and does urban vs rural status matter?

## Dataset
UK road accident data (2021–2022), ~308,000 records.
Source: [Kaggle — Road Accidents Dataset](https://www.kaggle.com/datasets/atharvasoundankar/road-accidents-dataset)

## Approach
1. Data cleaning and preprocessing
2. Exploratory data analysis (time of day, lighting, junctions)
3. Association rule mining (Apriori) on contributing factors
4. Time series forecasting of monthly accident volume
5. Regional clustering (K-means) on district-level accident profiles

## Tools
Python, pandas, scikit-learn, mlxtend, statsmodels, matplotlib, seaborn, Jupyter

## Key findings

**Timing & lighting:** Accident frequency peaks during commuting hours. Severity 
profiles shift under darkness compared to daylight conditions.

**Junctions:** Certain junction types and control setups (e.g. give-way/uncontrolled) 
carry a disproportionately higher share of severe accidents than signal-controlled junctions.

**Association rules:** Specific combinations of weather, lighting, and junction control 
co-occur with higher-severity accidents at rates meaningfully above chance (lift > 1.2).

**Forecasting:** Short-term trend structure is statistically detectable (ARIMA(1,1,1), 
p < 0.001), but 24 months of data isn't enough to reliably fit a seasonal model therefore the 
seasonal SARIMA produced unstable, non-significant estimates. Forecasts are shown with 
confidence intervals, and should be read as indicative rather than precise.

**Regional clustering (headline finding):** Districts split into four distinct profiles. 
The most striking result: low-traffic rural districts have the *highest* severe/fatal 
accident rate (~21%, some over 30%), despite having the *fewest* total accidents — while 
high-volume urban districts have the *lowest* severity rate despite the highest raw 
accident counts. Likely drivers: higher speed limits, longer emergency response times, 
and less traffic forcing lower speeds on rural roads.

## Limitations
- Two years of data limits forecasting reliability, particularly for seasonal effects.
- Association rules describe co-occurrence, not causation.
- Clustering uses aggregate district-level features; individual accident context is lost at that level.

## Status
✅ Complete
