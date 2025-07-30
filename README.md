# Demand Forecasting and Inventory Optimization

## Project Overview
This project focuses on analyzing historical demand and inventory data for a product, building a time series model to forecast future demand, and then leveraging these forecasts to calculate key inventory management parameters such as **optimal order quantity**, **reorder point**, and **safety stock**.  
The goal is to optimize inventory levels to meet customer demand efficiently while minimizing costs.

---

## Problem Statement
Businesses often face challenges in managing inventory effectively due to unpredictable demand fluctuations.  
- **Overstocking** leads to increased holding costs and potential waste.  
- **Understocking** results in lost sales, customer dissatisfaction, and stockout costs.  

The core problem is to accurately predict future demand and translate these predictions into actionable inventory control strategies to maintain optimal stock levels.

---

## Project Objective
The primary objectives of this project are:

1. **Analyze** historical demand and inventory trends to understand underlying patterns.
2. **Build** a robust time series forecasting model (e.g., ARIMA) for future demand.
3. **Utilize** the demand forecasts to calculate optimal inventory parameters, including:
   - Reorder points
   - Safety stock
   - Order quantities  
   aiming for a specified service level.
4. **Demonstrate** the application of time series analysis in practical inventory management scenarios.

---

## Column Dictionary
| Column       | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| **Date**     | The specific date for which the demand and inventory data are recorded. (e.g., YYYY-MM-DD) |
| **Product_ID** | A unique identifier for the product being tracked. (e.g., P1)             |
| **Demand**   | The quantity of the product demanded on that specific date. (Integer)       |
| **Inventory**| The quantity of the product available in stock at the end of that date. (Integer) |

---


### Insights from Data Analysis
- **Demand Volatility:**  
  Analysis of "Demand Over Time" revealed significant day-to-day fluctuations, indicating a highly volatile demand pattern with no clear overall trend over the observed period (June 2023 - January 2024).  
  ➜ This underscores the need for a robust forecasting approach.

- **Decreasing Inventory:**  
  The "Inventory Over Time" plot showed a consistent downward trend in inventory levels, suggesting demand was depleting stock faster than it was replenished.  
  ➜ This highlighted a potential risk of stockouts if left unaddressed.

- **Time Series Properties (ACF/PACF):**  
  The Autocorrelation Function (ACF) plot exhibited a slow decay, indicating **non-stationarity** in the demand time series.  
  ➜ First-order differencing (d=1) was required to stabilize the series before applying ARIMA.

---

### Forecasting and Inventory Optimization

#### ARIMA Model
- A non-seasonal **ARIMA(1,1,1)** model was implemented.  
- The choice of **d=1** was validated by the ACF plot.  
- For the simulated data used, the model produced a **flat forecast of 74 units/day for 10 days**.  
  ➜ While useful for demonstration, real-world cases may require **SARIMA** or other advanced models to capture seasonality and complex patterns.

---

### Inventory Parameter Calculation
Using the forecasted demand, the following inventory parameters were derived:

| Parameter             | Value  | Description |
|-----------------------|--------|-------------|
| **Optimal Order Quantity** | 148 units | Recommended order size when stock reaches the reorder point. |
| **Reorder Point**         | 148 units | The inventory level at which a new order should be placed. |
| **Safety Stock**          | 74 units  | Buffer stock to mitigate stockout risks due to demand spikes or lead time variability. |
| **Total Cost**            | 557.4     | Driven mainly by holding costs due to high initial inventory and zero stockout costs. |

---

## Conclusion
This project successfully demonstrates a pipeline for **demand forecasting** and its application in deriving **practical inventory management parameters**.  

- By understanding historical patterns, forecasting future demand, and applying inventory models, businesses can make **data-driven decisions** to:
  - Optimize stock levels
  - Minimize holding and stockout costs
  - Improve customer service  

The flat ARIMA forecast (on simulated data) highlights the importance of selecting appropriate model parameters and potentially incorporating **seasonal components (SARIMA)** in real-world scenarios.  

### ✅ **Future Work**
- Refine forecasting models with more complex techniques.  
- Incorporate advanced inventory optimization methods.  
- Integrate real-time data for dynamic inventory adjustments.
```
