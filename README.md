# 🌺 Will Hawaii Sink or Swim without Tourists?

## Overview

Born and raised in the Hawaiian Islands, I’ve seen how tourism serves as both a lifeline and a pressure point for Hawai‘i. While it drives the economy, it also raises critical questions about sustainability, housing affordability, and long-term well-being for residents. This project investigates Hawai‘i’s economic dependence on tourism, using data from state and federal sources to quantify its impact on GDP, employment, and housing affordability—especially in the wake of the COVID-19 pandemic.

By combining multiple datasets with interactive visualizations using Python’s `Plotly` library, this project reveals how reliant Hawai‘i is on tourism—and whether it needs to be.

---

## 🔍 Research Questions

1. **How significantly does Hawai‘i’s economy rely on tourism-related industries?**  
   > Tourism-related industries (Arts, Entertainment & Recreation and Accommodation & Food Services) consistently made up **8–12% of the state’s GDP** from 2005 to 2024, making tourism the **third-largest industry group** in the economy. This affirms a deep economic reliance on tourism.

2. **What economic declines occurred during the COVID-19 tourism collapse?**  
   > During 2020 Q2, **visitor arrivals dropped by over 95%**, **employment hit its lowest point (525k civilians employed)**, and **tourism-related GDP fell steeply**. As tourism slowly recovered, so did both GDP and employment—demonstrating a strong causal relationship.

3. **Does tourism affect housing affordability?**  
   > A **positive correlation** was found between **visitor arrivals** and **median housing prices in Honolulu**. However, the pandemic disrupted this trend, and housing prices continued to rise despite a drop in tourism. This suggests tourism **may influence housing**, but **is not the sole cause** of inflation.

---

## 📊 Datasets Used

### 1. DBEDT (Hawai‘i Department of Business, Economic Development & Tourism)
- Quarterly visitor arrival and spending data  
- County-level unemployment/employment rates  
- Median housing prices (Honolulu & Maui)

### 2. UHERO (University of Hawai‘i Economic Research Organization)
- Statewide GDP (total + industry-specific from 2005–2024)

---

## 🧠 Methods

- Cleaned and merged data using `pandas`
- Built custom tourism share metric:

```math
\text{Tourism Share} = \frac{\text{GDP}_{\text{Arts}} + \text{GDP}_{\text{Accom/Food}}}{\text{Total GDP}} \cdot 100
```

### 📊 Visualizations

**Used Plotly to create interactive visualizations:**
- 📈 Line charts of **industry GDP trends over time**
- 📉 Multi-axis time series of **arrivals, GDP, and employment**
- 🏠 Dual-axis plots of **housing prices vs. visitor arrivals**

---

### 📈 Key Findings

- 🏨 **Tourism-related industries** account for **8–12%** of the state GDP (2005–2024)
- 🦠 **COVID-19** caused a dramatic collapse in:
  - Visitor arrivals  
  - Statewide employment  
  - Tourism sector GDP  
- 🏘️ A **correlation exists** between visitor numbers and housing prices, but **causation is unclear**

---

### 📌 Limitations

1. **Correlation ≠ Causation**  
   While the data shows a correlation between tourism activity and median housing prices, this does not prove a direct cause. Housing costs are shaped by many factors beyond visitor arrivals.

2. **Incomplete Geographic and Temporal Coverage**  
   Housing data is limited to **Honolulu**, while visitor data is **statewide**. This may skew interpretation.

3. **Pandemic-Specific Behavior**  
   **COVID-19** created unusual patterns in economics and behavior, which may not reflect normal conditions.

---

### 🤝 Implications

This analysis can inform:

- 🏛️ **Policymakers**: Diversify economic strategies beyond tourism and create safety nets during downturns  
- 🌐 **Economic development orgs**: Invest in emerging industries and tech to build resilience  
- 👥 **General public**: Gain perspective on the deeper causes of housing inflation and economic vulnerability

---
