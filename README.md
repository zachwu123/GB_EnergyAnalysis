# GB Power Prices Analysis and Forecasting

## Objectives
The main objective of this project is to analyze the driving factors of GB power prices, investigate the transition to renewable energy, and develop predictive models for forecasting power prices. This involves understanding the correlations between commodity prices and power prices, assessing the seasonality of power prices, and evaluating the performance of different predictive models.

## Datasets Used
1. **Commodity Prices Data** (`gbr_commodities_1d.csv`): Contains daily prices for gas, coal, and carbon from 2018 to October 2020.
2. **System Data** (`gbr_system_30M_2018.csv`, `gbr_system_30M_2019.csv`): Contains half-hourly data on wholesale market prices and other system-related metrics for the years 2018 and 2019.
3. **Technology Data** (`gbr_technology_30M_2018.csv`, `gbr_technology_30M_2019.csv`): Contains half-hourly data on power generation by different technologies for the years 2018 and 2019.

## Data Exploration
The data exploration phase involved the following steps:
- Merging the system and technology data on a half-hourly basis.
- Aggregating data to daily averages for easier analysis.
- Exploring the correlations between wholesale market prices and commodity prices (gas, coal, carbon).
- Analyzing the seasonal trends in power prices, generation, and underlying demand.
- Comparing renewable and non-renewable power generation over time.
- Visualizing the feature importance and partial dependence plots for the linear regression model.

## Results and Forecasting

### Key Insights

#### Commodity Prices and Power Prices
![correlation](https://github.com/user-attachments/assets/637f2824-19f4-405e-992d-1597ff6b0999)
- Gas prices have a strong positive correlation with wholesale market prices, explaining 73.9% of the variability in power prices.
![WholesaleVsCommodities](https://github.com/user-attachments/assets/c81c9166-e298-4bf5-bcce-890f2a1f376f)
![PowerVsComm](https://github.com/user-attachments/assets/8093e9e0-95b3-40e2-ace5-dcebb8f151c8)
- Coal prices also show a moderate correlation with power prices.
- Power prices exhibit significant seasonality, driven by underlying demand and heating needs in winter.
![SeasonalDemand](https://github.com/user-attachments/assets/d37adff1-8259-4fa7-be84-de289dda42f7)

#### Renewable Energy Transition
- Renewable energy generation has been steadily increasing, with wind (offshore and onshore) and biomass leading the generation.
- The gap between renewable and non-renewable generation is decreasing, indicating a shift towards renewable energy sources.
- Biomass has the highest load factor, showing consistent and efficient output.

#### Predictive Modeling
- Linear regression outperforms other models (XGBoost, Random Forest) in predicting power prices for 2020.
![LinearTest](https://github.com/user-attachments/assets/a749bc54-b35e-41a8-a7fc-17357214e63c)
![XGBoostTest](https://github.com/user-attachments/assets/c401e8c3-1412-4a18-b9ae-c23349b88c91)
![RandomForest](https://github.com/user-attachments/assets/8ce19ee7-7e01-4c7c-881e-b3135c670f21)

- Gas price is the most important feature for the model, followed by day of the week and the power price of the previous day.
![LinearFeatures](https://github.com/user-attachments/assets/9eb180de-24c9-426c-9620-deffd2508813)
![LinearShap](https://github.com/user-attachments/assets/3807137f-bf60-4334-be90-c548589d15e8)
![LinearShap2](https://github.com/user-attachments/assets/0c4f7fe0-9cbf-42d4-8a49-d9906302d2af)

- The model accurately captures the significant events in 2020, such as the oil price war and the impact of COVID-19 on power prices.

### Forecasting for 2020
- The linear regression model predicts a sharp drop in power prices in the first half of 2020, followed by a gradual recovery in the second half.
- The predicted power prices closely follow the gas prices, highlighting the influence of gas prices on power market dynamics.
![LinearPredictWGas](https://github.com/user-attachments/assets/ccd83519-cc6e-4d79-b3e3-c5f13a385bc0)
- The predicted power price generally aligns with the global power price
![quarterly-average-electricity-prices-in-selected-markets-2016-2020](https://github.com/user-attachments/assets/1bf6895b-973c-4244-8d6c-b3a4b25fd9e9)


## Future Work
1. **Model Enhancement**: 
   - Explore additional features and more sophisticated models, such as ensemble methods or deep learning models, to improve predictive accuracy.
   - Incorporate external factors such as weather data, economic indicators, and policy changes for a more comprehensive model.

2. **Real-Time Analysis**:
   - Implement real-time data streaming and analysis to provide up-to-date forecasts and insights.
   - Develop a dashboard for stakeholders to monitor and visualize power price trends and forecasts.

3. **Scenario Analysis**:
   - Conduct scenario analysis to understand the impact of different factors (e.g., changes in commodity prices, renewable energy adoption rates) on future power prices.
   - Assess the potential effects of policy interventions and technological advancements on the power market.

## Repository Structure
- `data/`: Contains all the datasets used in the project.
- `scripts/`: Python scripts for data processing and model training.
- `results/`: Outputs and visualizations generated from the analysis.
- `powerpoint/`: The final PowerPoint presentation summarizing the findings and insights.


