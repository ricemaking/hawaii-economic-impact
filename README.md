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

### 📈 Results

#### How significantly does Hawaii’s economy rely on tourism-related industries?

To develop an answer to this question, I first identified tourism-related industries within my dataset. I came to a conclusion regarding which industries were related to tourism: Arts, Entertainment, and Recreation & Accommodation and Food Services.
- I chose the Arts, Entertainment, and Recreation industry to be included within my analysis as this most likely has to deal with traditional performances in Hawaii, This is including but not limited to hula dancing, luaus, or maybe even museums containing traditional and ancient Hawaiian art. Tourists are most likely to visit such attractions, which makes up most of the GDP within this industry.
- I chose the Accommodation and Food Services industry as this industry has to deal with lodging and hotel services. Most times, tourists stay within hotels during their stay, so the tourists make up most of the GDP of the Accommodation and Food Services industry.

Next, I needed some way to quantify tourist-related industry impact on Hawaii's economy. I decided on finding out the total share that these tourism-related industries hold of the state's total GDP. This is called the Tourism Share, or the percentage of the total GDP that tourism industries make up:

$$
\begin{aligned}
\text{Let } GDP_T &= \text{ total GDP} \\
\text{Let } GDP_1 &= \text{ GDP of Arts, Entertainment, and Recreation} \\
\text{Let } GDP_2 &= \text{ GDP of Accommodation and Food Services} \\
\text{Tourism Share} &= \frac{GDP_1 + GDP_2}{GDP_T}\cdot(100)
\end{aligned}
$$

I found the tourism share across all quarters spanning from 2005 Q1 to 2024 Q4, then plotted it on a timeline plot to assess tourism's affect on the economy of Hawaii.

%%html
<iframe width="700" height="500" src="graphs/employment_share.html" frameborder="0"></iframe>

Upon plotting my findings, I found that the Tourism Share stayed at a consistent 8-12% of the time. I then grew curious about how that compares to other industries. so I created a multi line plot of all other industries GDPs and how it compares to the tourism industry.

%%html
<iframe width="700" height="500" src="graphs/industry_gdp.html" frameborder="0"></iframe>

It can be seen that the tourism group makes up the third most of Hawaii's GDP.

After interpreting my findings, I came to the conclusion that Hawaii's economy does infact rely heavily on tourism. It could be seen that Hawaii has consistently made up about 8-12% of Hawaii's economy from 2005 to 2024, which is huge margin of the state's GDP. Not only that, but between all the other industries, these two industries combined make up the third most of Hawaii's total GDP. The one thing that is concerning, however, is how in 2020 during the COVID-19 pandemic, a huge drop occurred in the tourism related industries. Which leads me to my next research question.

#### What economic trends or declines did Hawaii experience during the COVID-19 pandemic when tourism was severely restricted?

To answer this question, I first defined the COVID-19 pandemic period as starting in 2020 Q1 and ending in 2022 Q1. I then analyzed three key metrics across this timeframe:

- **Visitor Arrivals** (as a measure of tourism)  
- **Employed Civilians** (as an indicator of unemployment)  
- **GDP from Accommodation and Food Services & Arts, Entertainment, and Recreation** (as a tourism-dependent industries of the economy)  

These metrics were filtered to include only statewide data to reflect Hawaii's overall economic trends. I merged together these datasets and visualized them in a multi-line plot with individual Y-axis scaling to show how they varied across different units.

%%html
<iframe width="700" height="500" src="graphs/tourism_employment_gdp_relationship.html" frameborder="0"></iframe>

Upon analyzing the graph, it could be seen that Visitor Arrivals saw a sharp decline in 2020 Q2, dropping dramatically from over 2 million to under 100,000 due to lockdowns and travel restrictions. Unemployment also surged during this time, with employment dropping to its lowest of 525k in 2020 Q2, reflecting the collapse in tourism-related jobs. Tourism-related GDP also declined during this period, though more gradually than arrivals, showing economic hardship in tourism-reliant sectors. As tourism began recovering in late 2020 and into 2021, improvements in both GDP and employment followed, though not immediately returning to pre-pandemic levels by 2022 Q1.

This demonstrates the direct impact of tourism restrictions on both employment and economic output. It shows how as a result of visitor arrivals dropping during the pandemic in 2020 Q2, the number of civilians had dropped, as well as the GDP from tourism-related industries.

#### How did the decline in visitor arrivals during the COVID-19 pandemic affect state-level housing affordability?

Residents often claim that tourists coming to Hawaii oftentimes inflates housing prices, most likely due to affording long/short-term rentals in Hawaii during their stay and even taking up the already relatively low amounts of housing available to residents. Due to this demand for housing in Hawaii, prices get raised higher and higher every year. For this reason, there's a substantial majority of homeless residents in Hawaii, with 80.5 out of 10,0000 people being homeless (https://usafacts.org/articles/which-states-have-the-highest-and-lowest-rates-of-homelessness/).

To answer this question on whether or not tourists inflate housing prices, I planned on using another dataset regarding median housing prices across certain counties of Hawaii, and visitor arrivals in Hawaii, then comparing these two datasets on a dual-axis time series line chart. The only downside to the dataset of median housing prices is that it only contained quarterly data for Honolulu and yearly data for Maui. Visitor arrivals are also only counted statewide, which in turn will mask the housing rates across the different islands. To address this issue, I decided to focus solely on housing prices in Honolulu inside my housing prices dataset. I justify this usage of comparing Honolulu's housing prices to housing prices as Oahu (considered Honolulu county) is one of the most visited islands throughout Hawaii, accounting for 52% of visitors across the state in 2024 alone (https://www.hawaii-guide.com/hawaii-tourism-statistics).

%%html
<iframe width="700" height="500" src="graphs/arrivals_housing.html" frameborder="0"></iframe>

Analyzing the plot, it's observable that there exists a slight correlation between visitor arrivals and median housing price. Starting from 2005 Q2, it can be seen that the two variables follow the same trend, one increasing as the other increases. This correlation is lost when the pandemic hits in 2020 Q2 and tourism is restricted, where the median housing price rapidly increases. Then after tourism is opened up and visitors come to Hawaii, the Median Housing Price keeps correlation with visitor arrivals as well.

From this, it can be seen that visitor arrivals may have some sort of association/correlation with the increase in the cost of housing. As the number of visitors rise, so does the median housing price. This may likely be from broader economic growth. However, this correlation does not necessarily prove causation, as the median of the housing price continues to increase as the number of visitors increases. Thus, tourism is not a direct cause of housing price inflation, at least from this graph. This housing price inflation could be caused by other demographic or economic factors.

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
