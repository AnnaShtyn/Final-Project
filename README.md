# 🏨 Hotel Booking Analysis: Demand and Financial Performance

An analytical project comparing two types of hotels in Portugal — **Resort Hotel** (Algarve) and **City Hotel** (Lisbon) — in terms of financial performance and demand, based on real booking data.

## About the Project

The project is dedicated to a comparative analysis of two hotels — a resort hotel and a city hotel — covering the period from **July 2015 to August 2017**. The research covers two key areas:

1. **Financial performance and ADR** — average daily rate per room, revenue per booking, and length of guest stay.
2. **Hotel demand** — seasonality, booking cancellations, guest geography, and popular room types and meal plans.

## Dataset

- Original dataset: **119,000+** booking records, **31** columns.
- The analysis uses a cleaned dataset (181 rows with missing values and negative prices were removed), supplemented with additional calculated columns — **49 columns** in total.
- Hotels: Resort Hotel (Algarve, Atlantic coast) and City Hotel (Lisbon), roughly 270 km apart.
- Users' personal data has been removed from the dataset.

## Tools

| Tool | Purpose |
|---|---|
| **SQL / BigQuery** | Aggregating and calculating key metrics |
| **Python** (Pandas, Matplotlib, Seaborn, Plotly, matplotlib-venn) | Data processing and visualization |
| **Canva** | Assembling the final dashboards |

Color coding on charts: 🟠 **Resort Hotel** — orange, 🔵 **City Hotel** — blue.

## Goals and Research Questions

The goal of the study is to analyze demand and the key financial performance of both hotels, comparing their common and distinctive features.

**Block 1. Financial Performance and ADR**
- What is the average daily rate (ADR) and the average revenue per booking?
- How does check-in dynamics change over time — is there seasonality and sustained growth?
- Does ADR growth correlate with the number of check-ins?
- What is the price range for different room types?

**Block 2. Hotel Demand**
- Which room types are most popular among guests?
- Which calendar months are the busiest, and do they coincide for both hotels?
- Is there a relationship between the length of the booking confirmation wait time and cancellations?
- Where do guests come from, and which meal plan do they choose most often?

## Dashboards

### 1. Financial Performance and ADR Analysis
A line chart of check-in and ADR dynamics by month + a violin plot of price distribution by room type, supplemented with key metric cards (average ADR, average revenue per booking, total revenue, average length of stay).

### 2. Hotel Demand Analysis
Bar charts of check-in dynamics by room type, a scatter plot (stripplot) of confirmation wait time vs. cancellations, a table of the top 5 guest countries, and a Venn diagram of the busiest months.

## Answers to the Research Questions

### Block 1. Financial Performance and ADR

**Key Financial Indicators of Hotels**

| Indicator | Resort Hotel | City Hotel |
| ---------------------------------- | -----------: | ---------: |
| Average ADR, EUR                   |        90.15 |     **105.91** |
| Average Revenue per Booking, EUR   |       **398.18** |     311.81 |
| Total Hotel Revenue, thousand EUR  |       11,518 |     **14,369** |
| Average Length of Guest Stay, days |         **4.14** |       2.92 |

**1. What is the average daily rate (ADR) and the average revenue per booking?**

The average ADR is higher at City Hotel — **€105.91** compared to **€90.15** at Resort Hotel. However, in terms of average revenue per booking, Resort Hotel leads — **€398.18** compared to **€311.81** at City Hotel. This is explained by the fact that, despite the lower nightly rate, Resort Hotel guests stay longer, so the total bill per booking turns out to be higher.

**2. What is the average length of guest stay, and how does it affect revenue?**

For Resort Hotel, the average length of stay is **4.14 days**, compared to **2.92 days** for City Hotel — meaning resort hotel guests stay more than a full day longer (+1.22 days). It is precisely this longer stay that offsets the lower ADR and drives the higher average revenue per booking.

**3. Which hotel has higher total revenue over the entire period?**

City Hotel's total revenue is roughly **25%** higher (€14,369K vs. €11,518K). Since the average revenue per booking is lower at City Hotel, the difference is explained by a significantly higher number of actual check-ins — this is confirmed by the check-in dynamics chart.

![Dashboard](https://drive.google.com/thumbnail?id=1mPTL4M-Y4XGCQIn2YzWe6_uv7G30s6Wj&sz=w1200)

**4. Are there seasonality trends in check-in dynamics? Is there sustained growth over time?**

Seasonality is clearly pronounced, especially for City Hotel: demand rises sharply from February to May, remains high until around October, and then drops sharply. This is likely related to the most favorable travel period in Portugal — the "velvet season" (September–October). The dynamics also show steady growth in the number of bookings at City Hotel throughout the study period, while fluctuations at Resort Hotel are minor — possibly because City Hotel is relatively new and rapidly gaining popularity, while Resort Hotel already has a stable audience.

**5. Is there a correlation between ADR growth and the number of check-ins?**

At City Hotel, ADR dynamics align with check-in dynamics, with prices fluctuating within a relatively narrow range (€80–140) depending on demand. At Resort Hotel, the opposite pattern is observed: prices rise abnormally starting in June, peaking in August (€190–200), and then drop sharply to €60–80 during the most popular months (September–October) — meaning pricing policy is not synchronized with actual demand.

**6. What is the price range for different room types?**

The ADR distribution by room type (violin plot with quartiles) shows that Resort Hotel has a much wider price spread, although average prices are lower (median ~€60–160). At City Hotel, prices are on average higher — median in the range of ~€90–240. In both hotels, ADR increases more or less steadily with room type from A to G.

### Block 2. Hotel Demand

**1. Which room types are most popular among guests?**

Types **A and D** are consistently the most booked at both hotels. At Resort Hotel, type **E** rooms are also in additional demand — likely due to a favorable balance between the number of guests per booking and price.

**2. Which calendar months are most popular (most booked)? Do they coincide for both hotels?**

The shared busiest months for both hotels are **March, May, and October**. At the same time, Resort Hotel additionally sees peak check-ins in September and June, while City Hotel peaks in April and February.

**3. Is there a relationship between the length of the booking confirmation wait time and cancellations?**

Cancellations are significant, especially at City Hotel — **41.8%** compared to **27.8%** at Resort Hotel. However, the scatter plot (stripplot) shows no clear correlation between confirmation wait time and cancellation for either hotel: guests are willing to wait several months for confirmation regardless of whether the booking is ultimately canceled.

**4. Where do guests come from, and which meal plan do they choose most often?**

At Resort Hotel, more than a third of guests are Portuguese (**35.2%**), roughly one in five is British (**20.5%**), and one in ten is Spanish (**10.7%**). At City Hotel, the picture is different: only **23.4%** of guests are Portuguese, followed by French (**15.3%**), German (**10.9%**), and British (**8.1%**) guests — likely reflecting the fact that Lisbon frequently attracts tourists and businesspeople from EU countries. At both hotels, the predominant meal plan is **Bed & Breakfast** (~77%), with no significant difference between the hotels on this metric.

## Overall Conclusions and Recommendations

1. **Resort Hotel** should reconsider its room pricing policy with seasonality in mind — this would help increase the hotel's accessibility to guests during peak-demand months.
2. Both hotels should consider reallocating the least in-demand room types in favor of the most popular ones (A, B, D, E).
3. Further detailed research is needed into the causes of the high cancellation rate, especially for **City Hotel**.
