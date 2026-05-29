# Euro Exchange Rate Analysis: Macroeconomic Trends & Political Shocks 💶📉

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/11mkPg7OuVQZiv5SWKpOsJpD7nFb4jJMo?usp=sharing)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=flat&logo=Matplotlib&logoColor=black)](https://matplotlib.org/)

## 📖 Executive Summary
This project explores 25 years of daily Euro (EUR) exchange rate data to identify structural macroeconomic inflection points and political shocks. By cleaning and transforming raw financial time-series data, this analysis reveals how events like the 2008 Financial Crisis, Brexit, and the COVID-19 Pandemic permanently reshaped global currency valuations.

The final deliverable includes narrative-driven data visualizations built with **Information Design** and **Gestalt principles** to maximize data-ink ratio and cognitive clarity.

---

## 💾 The Dataset
* **Source:** European Central Bank (ECB)
* **Scope:** Daily exchange rates from 1999 to 2025 across multiple global currencies (USD, GBP, CHF, etc.).
* **Format:** Time-series data initially formatted with mixed object/string types and non-trading day placeholders.

---

## 🛠️ Key Data Science & Engineering Challenges Solved

### 1. Robust Type Conversion & Null Handling
Financial datasets often contain placeholders for days when the market is closed. Used Pandas' `pd.to_numeric(errors='coerce')` to safely convert currency columns from `object` to `float64`, automatically transforming text hyphens (`'-'`) into mathematically viable `NaN` values without losing rows.

### 2. Time-Series Forward Filling (with a Catch)
To maintain an unbroken chronological calendar for mathematical modeling, I implemented a **Forward Fill (`ffill`)** strategy to carry Friday closing rates into the weekends. 
* **Zombie Data Prevention:** I engineered a conditional forward-fill algorithm to truncate data for defunct currencies (e.g., the Croatian Kuna or Slovenian Tolar) immediately after they officially adopted the Euro, ensuring historically accurate dead-ends.

### 3. Narrative Data Visualization
Shifted from exploratory to **explanatory** data visualization using Matplotlib:
* **Smoothing Volatility:** Applied 30-day and 90-day rolling averages to filter out daily market noise and expose true macroeconomic trends.
* **Information Design:** Minimized cognitive load by removing heavy gridlines and borders (maximizing the data-ink ratio).
* **Gestalt Enclosure:** Used programmatic shading (`axvspan`) to visually group distinct crisis eras (2008 Crisis, Brexit, Pandemic) to guide pre-attentive focus.

---

## 📊 Core Macroeconomic Insights

1. **The Brexit Political Shock (EUR/GBP):** The data vividly captures the June 2016 UK referendum, demonstrating how an overnight political vote triggered a permanent structural devaluation of the British Pound against the Euro.
2. **The 2008 Liquidity Crisis (EUR/USD):** Shows the highest historical peak of the Euro (approx. $1.60) as the US subprime mortgage meltdown forced the Federal Reserve to aggressively slash interest rates, causing a massive flight from the US Dollar.
3. **The Swiss Peg Removal (EUR/CHF):** Visualizes the January 2015 "Frankenshock" when the Swiss National Bank unexpectedly abandoned its currency ceiling, causing instantaneous market repricing.

*(Note: You can view the full visualizations directly in the notebook!)*

---

## 🚀 How to Run the Project

**Option 1: In the Cloud (Recommended)**
Click the "Open in Colab" badge at the top of this page to launch the interactive notebook instantly in your browser.

**Option 2: Local Installation**
1. Clone this repository:
   ```bash
   git clone [https://github.com/](https://github.com/)[nasro10z]/euro-exchange-rate-analysis.git
