Economic Trend Analysis (2000--2024)
===================================

This project explores key economic indicators from 2000 to 2024, including GDP, Federal Funds Rate, S&P 500 Index, Median CPI, and Unemployment Rate. The goal is to analyze historical trends, build predictive models, and visualize insights through an interactive dashboard.

Table of Contents
-----------------

-   [Project Goals](#project-goals)
-   [Data Sources](#data-sources)
-   [Technologies Used](#technologies-used)
-   [Installation and Setup](#installation-and-setup)
-   [Methodology](#methodology)
    -   [Data Collection](#data-collection)
    -   [Data Cleaning and Preprocessing](#data-cleaning-and-preprocessing)
    -   [Exploratory Data Analysis](#exploratory-data-analysis)
    -   [Predictive Modeling](#predictive-modeling)
    -   [Clustering Analysis](#clustering-analysis)
    -   [Time-Series Forecasting](#time-series-forecasting)
-   [Findings and Insights](#findings-and-insights)
-   [Challenges and Solutions](#challenges-and-solutions)
-   [Limitations](#limitations)
-   [Conclusion](#conclusion)
-   [Acknowledgments](#acknowledgments)

Project Goals
-------------

1.  **Data Cleaning and Preprocessing**: Prepare datasets by handling missing values and ensuring consistency.
2.  **Exploratory Data Analysis (EDA)**: Analyze economic indicators to identify trends and relationships.
3.  **Predictive and Clustering Models**: Build models to forecast future economic trends and group similar periods.
4.  **Data Visualization**: Create visual representations to highlight key insights and patterns.
5.  **Dashboard Development**: Develop an interactive dashboard to present analysis and findings.

Data Sources
------------

-   **Federal Funds Effective Rate**: Federal Reserve Economic Data (FRED)
-   **Gross Domestic Product (GDP)**: FRED
-   **Median Consumer Price Index (CPI)**: FRED
-   **S&P 500 Index**: [Yahoo Finance](https://finance.yahoo.com/)
-   **Unemployment Rate**: FRED

Technologies Used
-----------------

-   **Programming Languages**: Python
-   **Libraries**: Pandas, NumPy, Matplotlib, Seaborn, Scikit-Learn, Statsmodels, TensorFlow, Keras
-   **Database**: SQLite
-   **Data Visualization**: Tableau
-   **Others**: Jupyter Notebook

Installation and Setup
----------------------

1.  **Clone the repository**:

    bash

    Copy code

    `git clone https://github.com/yourusername/economic-trend-analysis.git`

2.  **Navigate to the project directory**:

    bash

    Copy code

    `cd economic-trend-analysis`

3.  **Create a virtual environment** (optional but recommended):

    bash

    Copy code

    `python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate`

4.  **Install required packages**:

    bash

    Copy code

    `pip install -r requirements.txt`

5.  **Run Jupyter Notebook**:

    bash

    Copy code

    `jupyter notebook`

Methodology
-----------

### Data Collection

Data was collected from reliable sources like the Federal Reserve Economic Data (FRED) and Yahoo Finance. The datasets cover the period from 2000 to 2024.

### Data Cleaning and Preprocessing

-   **Standardization**: Column names were standardized for consistency.
-   **Date Parsing**: Dates were converted to datetime objects for time-series analysis.
-   **Missing Values**: Handled using linear interpolation and forward/backward filling.
-   **Data Integration**: Cleaned datasets were saved into an SQLite database for efficient querying and merged into a single DataFrame for analysis.

### Exploratory Data Analysis

-   **Summary Statistics**: Computed mean, median, standard deviation, etc., to understand data distribution.
-   **Correlation Analysis**: Generated a heatmap to identify relationships between economic indicators.
-   **Time-Series Decomposition**: Decomposed GDP data into trend, seasonal, and residual components.

### Predictive Modeling

-   **Features and Target**: Selected relevant features (Federal Funds Rate, Median CPI, S&P 500 Close, Unemployment Rate) to predict GDP.
-   **Train-Test Split**: Divided data into training and testing sets.
-   **Ensemble Model**: Built a Voting Regressor combining Random Forest, Gradient Boosting, and Linear Regression.
-   **Evaluation**: Assessed model performance using MAE, MSE, and RMSE metrics.

### Clustering Analysis

-   **Standardization**: Scaled data using StandardScaler.
-   **K-Means Clustering**: Grouped similar economic periods into clusters.
-   **Visualization**: Created scatter plots to visualize clusters based on GDP and Unemployment Rate.

### Time-Series Forecasting

-   **ARIMA Model**: Used for long-term GDP forecasting (1 year, 5 years, and 10 years horizons).
-   **LSTM Neural Network**: Implemented for short-term GDP forecasting using TensorFlow and Keras.

Findings and Insights
---------------------

### Correlation Analysis

The correlation heatmap revealed significant relationships between the economic indicators:

-   **GDP and Unemployment Rate**: A strong negative correlation (-0.97) indicates that as GDP increases, the Unemployment Rate tends to decrease. This aligns with the economic principle that higher production leads to more job opportunities, reducing unemployment.
-   **GDP and S&P 500 Index**: A strong positive correlation (0.98) suggests that stock market performance is closely tied to the overall economy. As companies generate higher profits in a growing economy, stock prices tend to rise.
-   **Federal Funds Rate and Median CPI**: A moderate positive correlation (0.75) implies that higher interest rates are associated with higher inflation rates, reflecting central bank actions to control inflation.

### Time-Series Decomposition

The decomposition of GDP time series into trend, seasonal, and residual components provided deeper insights:

-   **Trend Component**: Showed a consistent upward trajectory of GDP over the years, signifying long-term economic growth despite short-term fluctuations.
-   **Seasonal Component**: Revealed minimal seasonal effects, indicating that GDP doesn't have strong seasonal patterns on a quarterly basis.
-   **Residual Component**: Captured irregularities and anomalies, such as the economic downturn during the 2008 financial crisis and the impact of other unforeseen events.

### Predictive Modeling and Scenario Analysis

The ensemble model's performance metrics were satisfactory:

-   **MAE**: 773.66
-   **MSE**: 739,099.22
-   **RMSE**: 859.71

#### Impact of Federal Funds Rate Increase

-   **Scenario Simulation**: Modeled the effect of a 1% increase in the Federal Funds Rate.
-   **Findings**:
    -   **GDP Projection**: The model predicted a decrease in GDP growth under the higher interest rate scenario.
    -   **Interpretation**: Higher interest rates can lead to reduced borrowing and spending by businesses and consumers, slowing economic growth.
-   **Visualization**: Plotted the original GDP against the scenario projection, clearly illustrating the potential negative impact on GDP.

### Clustering Results

Using K-Means clustering, the data was segmented into three clusters:

-   **Cluster 0**:
    -   **Characteristics**: Low GDP and high Unemployment Rate.
    -   **Periods**: Corresponds to economic recessions, such as the 2008 financial crisis.
-   **Cluster 1**:
    -   **Characteristics**: Moderate GDP and Unemployment Rate.
    -   **Periods**: Transitional phases between recession and expansion.
-   **Cluster 2**:
    -   **Characteristics**: High GDP and low Unemployment Rate.
    -   **Periods**: Times of strong economic performance and growth.

#### Interpretation

-   The clustering analysis highlights how economic indicators group together during different economic cycles.
-   **Policy Implications**: Understanding these clusters can help policymakers tailor strategies for different economic conditions.

### Rolling Correlation Analysis

Calculated the rolling correlation between GDP and Unemployment Rate over a 12-quarter window:

-   **Observations**:
    -   The negative correlation persisted over time, but the strength varied.
    -   Periods with stronger negative correlation may indicate more robust economic cycles.
-   **Insight**:
    -   The varying correlation strength can help identify shifts in the economic relationship between GDP and unemployment, possibly due to structural changes in the economy.

### Economic Recovery Periods

Identified specific periods where:

-   **Unemployment Rate** was below 6%.
-   **GDP** exceeded $15,000 billion.

#### Findings

-   These periods were marked by strong economic performance and can be considered recovery or expansion phases.
-   **Visual Analysis**:
    -   Highlighted these periods on a plot of GDP and Unemployment Rate.
    -   Showed the alignment between decreasing unemployment and increasing GDP.

### GDP Forecasts

#### ARIMA Model Projections

-   **1-Year Forecast**:
    -   **Projected GDP**: Expected to reach approximately $27,562 billion by Q3 2023.
-   **5-Year Forecast**:
    -   **Projected GDP**: Anticipated to surpass $32,719 billion by Q3 2027.
-   **10-Year Forecast**:
    -   **Projected GDP**: Estimated to exceed $39,166 billion by Q3 2032.

#### Interpretation

-   The ARIMA model forecasts a steady increase in GDP over the next decade.
-   **Assumptions**: Based on historical trends continuing without major disruptions.

#### LSTM Model Forecasts

-   **12-Month Forecast**:
    -   **Projected GDP**: Predicted to reach approximately $38,785 billion by the end of the forecast period.
-   **Observation**:
    -   The LSTM model predicts a more optimistic GDP growth compared to the ARIMA model.
-   **Potential Reasons**:
    -   LSTM models can capture nonlinear patterns and may be more responsive to recent trends.

### Comparative Analysis

-   **ARIMA vs. LSTM**:
    -   **ARIMA** is better suited for linear, stationary data and longer-term forecasts.
    -   **LSTM** can model complex, nonlinear relationships and may perform better with sufficient data.
-   **Ensemble Model vs. Time-Series Models**:
    -   The ensemble model provides immediate predictions based on multiple indicators.
    -   Time-series models focus on historical GDP values to forecast future GDP.

### Overall Insights

-   **Economic Indicators Are Interconnected**: The strong correlations confirm the interplay between different facets of the economy.
-   **Predictive Models Are Useful but Limited**: While models can forecast trends, they are limited by the quality and scope of historical data.
-   **Policy Changes Have Significant Impacts**: Simulations show that changes in interest rates can materially affect economic growth.

Challenges and Solutions
------------------------

### Challenges

1.  **Data Inconsistency**: Merging datasets with different frequencies and formats was complex.
2.  **Missing Data**: Incomplete records could skew analysis and model training.
3.  **Model Overfitting**: Limited data points risked the models capturing noise instead of underlying patterns.
4.  **Technical Warnings**: Encountered deprecation and performance warnings during model execution.

### Solutions

1.  **Standardizing Data**: Converted all datasets to a common date format and frequency (quarterly).
2.  **Imputation Techniques**: Used interpolation and filling methods to handle missing values without introducing bias.
3.  **Cross-Validation**: Employed techniques like train-test split and regularization to improve model generalization.
4.  **Updating Libraries**: Ensured all libraries were up-to-date and adjusted parameters to resolve warnings.

Limitations
-----------

-   **Data Scope**: The analysis is limited to available historical data up to 2024 and may not account for recent developments.
-   **Model Assumptions**: Predictive models assume that past patterns will continue, which may not hold true in the face of unprecedented events.
-   **Exclusion of External Factors**: The models do not incorporate geopolitical events, policy changes, or other external factors that can significantly impact the economy.
-   **Simplified Economic View**: The economy is complex, and the analysis may not capture all nuances, such as income inequality or sector-specific trends.

Conclusion
----------

The project provided a comprehensive analysis of key economic indicators over the past two decades, uncovering significant relationships and trends:

-   **GDP and Unemployment Rate**: The strong inverse relationship reinforces the importance of GDP growth in reducing unemployment.
-   **Impact of Interest Rates**: Higher Federal Funds Rates can negatively affect GDP, highlighting the delicate balance policymakers must maintain.
-   **Stock Market Connection**: The close tie between GDP and the S&P 500 underscores the stock market's reflection of economic health.
-   **Predictive Modeling**: The models offer valuable projections but should be interpreted with caution due to inherent limitations.

**Final Thoughts**:

-   **Economic Interdependencies**: The analysis emphasizes how interconnected economic indicators are and the ripple effects that changes in one area can have on others.
-   **Importance of Data**: High-quality, comprehensive data is crucial for accurate analysis and forecasting.
-   **Utility for Stakeholders**: The insights can aid policymakers, economists, and investors in making informed decisions.

Acknowledgments
---------------

-   **Data Providers**: Federal Reserve Economic Data (FRED), Yahoo Finance
-   **Libraries and Tools**: Contributors to open-source libraries and tools used in this project.