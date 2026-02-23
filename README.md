                                                            **FMCG Sales Demand Forecasting using Time Series & Machine Learning**


**1. Business Problem**

  In the FMCG industry, especially for perishable products like milk, accurate demand forecasting is critical to:
  
      a) Prevent stock-outs (lost sales)
      
      b) Avoid overstocking (wastage)
      
      c) Optimize warehouse planning
      
      d) Improve promotional strategy
      
      e) Support production planning

**2. Project Objective**

      a) Forecast daily product sales using historical data
      
      b) Compare traditional time-series models with ML-based approaches
      
      c) Evaluate the impact of promotional strategies on future demand
      
      d) Generate business insights to support inventory and marketing decisions

    📊 Dataset Overview
**3. Dataset Overview**
  
  The dataset contains daily sales information from Jan 2022 to Dec 2024, along with external operational factors such as:

      a) Promotion flag
      
      b) Stock availability
      
      c) Delivery lead time
      
      d) Product price


  **4. Model Approach**


  1. ARIMA (Baseline Statistical Model)
        
     a) Confirmed presence of trend using ADF test and decomposition
        
     b) No strong seasonality detected
        
     c) Built ARIMA as a univariate benchmark model

  2. SARIMAX (Multivariate Time Series)

    Extended ARIMA by including external variables:
    
      a) Promotion
        
      b) Stock availability
        
      c) Delivery days
        
      d) Price

    Improved forecasting accuracy by incorporating business drivers

  3. XGBoost (Machine Learning Model)

    a) Engineered lag-based features:

      lag_1, lag_7, lag_14

    b) Rolling statistics:

      7-day rolling mean
      
      7-day rolling standard deviation

    c) Captured non-linear relationships between demand and external factors


  **5. Rolling Time-Series Validation**

  To simulate real-world deployment:

    Expanding window validation was implemented
    
    Model retrained periodically
    
    Forecast evaluated month-wise
    
  Average Performance (Rolling Validation):
    
    MAE ≈ 11.5 units
    
    RMSE ≈ 14.7 units
    
    MAPE ≈ ~11%
    
  This confirms model stability across multiple time periods.


  **6. Promotion Lift Scenario Analysis**

  Three promotional strategies were simulated for Jan 2025:
  Scenario	Total Forecasted Sales
      a) No Promotion (0 Days)	2527 Units
      
      b) 15-Day Promotion	2714 Units
      
      c) Full-Month Promotion (31 Days)	2890 Units


  Incremental Lift:

    a) 15-Day Promotion: +187 Units (~7.4% uplift)
    
    b) Full-Month Promotion: +363 Units (~14.3% uplift)


  **7. Key Business Insights**

  Recent demand trends strongly influence near-term sales.

  Stock availability directly impacts demand realization.
  
  Promotions show measurable incremental sales lift.
  
  Continuous promotions increase volume but with diminishing returns.
  
  These insights can support:
  
      a) Campaign planning
      
      b) Inventory allocation
      
      c) Production scheduling
      
      d) Revenue forecasting

**8. Model Comparison**

  Model	  MAE	RMSE MAPE
  ARIMA	  ~22	~30	~23%
  SARIMAX	~15	~19	~14%
  XGBoost	~11	~15	~11%
  
  XGBoost was selected as the final production model due to superior performance.

**9. Limitations**

  a) Weather and holiday effects not included
    
  b) Competitor pricing unavailable
    
  c) Scenario simulation assumes static future external factors
    
  d) Model performance depends on quality of future inputs


**10. Tech stack**

  Python | Pandas | Statsmodels | XGBoost
  Time-Series Analysis | Feature Engineering
  Rolling Validation | Scenario Simulation







Author Mohit Kushwaha LinkedIn: www.linkedin.com/in/mohit-kushwaha-024401112
  
