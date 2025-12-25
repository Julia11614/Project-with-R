# Project: Energy Forecasting at Vancouver International Airport

**Academic Assignment | Time Series Analysis & Forecasting**

## Project Overview

This repository contains an academic project for **BABS 502** under the instruction of **Professor Martha Essak**. The project focuses on developing forecasting models to predict monthly energy consumption at Vancouver International Airport (YVR) to assist with budget planning and contract negotiations with energy suppliers.

## 👥 Team Members

- **Julia Krumgant** (Student ID: 40566465)
- **Pranav Mehta** (Student ID: 19184282)

## 🎯 Project Objective

Develop accurate time series models to forecast monthly energy usage at YVR for the next three years (January 2011 - December 2013) to support:
- Budget planning and cost forecasting
- Negotiation of favorable contracts with energy suppliers
- Understanding patterns in energy consumption

## Dataset

The analysis uses **14 years of historical data** (1997-2010) from the YVR database, including:
- **Energy Use**: Monthly electricity consumption (thousands of kWh)
- **Temperature**: Mean monthly temperature (°C)
- **Terminal Area**: Total terminal space (sq. m.)
- **Passenger Data**: Total, domestic, US, and international passenger counts (thousands)

**Dataset**: `Energy use at YVR.csv` (168 monthly records)

## Methodology

The project implements and compares multiple forecasting approaches:

### Part A: Data Preparation & Transformation
- Time series visualization and exploratory data analysis
- Box-Cox transformation for variance stabilization
- Calendar adjustment for varying month lengths
- Training/test set split (Training: 1997-2007, Test: 2008-2010)

### Part B: Model Development & Comparison

1. **Basic Forecasting Methods**
   - Mean Method
   - Drift Method
   - Naïve Method
   - Seasonal Naïve Method

2. **Exponential Smoothing (ETS) Models**
   - Holt-Winters Additive: ETS(A,A,A)
   - Holt-Winters Multiplicative
   - Damped variants
   - Selected best model: **ETS(A,A,A)**

3. **ARIMA Models**
   - Multiple ARIMA specifications tested
   - Selected best model: **ARIMA(1,1,0)(0,1,1)[12]**

## Key Findings

- **Best Model**: ARIMA(1,1,0)(0,1,1)[12] outperformed all other methods
  - Test Set RMSE: 159.94
  - Test Set MASE: 0.47
  - Theil's U: 0.34
- **Seasonal Pattern**: Strong seasonality with peaks in July-August and lows in February-March
- **Trend**: Clear upward trend in energy consumption over time
- **Key Drivers**: Temperature, passenger traffic, and terminal area expansion

## 📁 Repository Contents

```
Project-with-R/
├── BABS 502 project template_PM_JK_PartB .ipynb  # Main analysis notebook
├── Energy use at YVR.csv                          # Dataset (if included)
└── README.md                                       # This file
```

## Technologies Used

- **Language**: R
- **Key Libraries**: 
  - `forecast` - Time series forecasting
  - `ggplot2` - Data visualization
  - `stats` - Statistical analysis

## Academic Context

**Note**: This is an academic project completed as part of coursework requirements. The analysis demonstrates proficiency in:
- Time series decomposition and analysis
- Statistical forecasting methods
- Model selection and validation
- Residual diagnostics
- Business interpretation of statistical results


## References

- Course materials from BABS 502
- Hyndman, R.J., & Athanasopoulos, G. (2021). Forecasting: principles and practice
- Vancouver International Airport open data sources

---

**Disclaimer**: This project was completed for educational purposes as part of an academic assignment. The forecasts and analyses are meant to demonstrate statistical methodology and should not be used for actual business decisions without further validation.
