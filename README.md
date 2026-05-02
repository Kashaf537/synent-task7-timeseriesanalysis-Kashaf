# 📊 Tesla Stock Time Series Analysis

## 📌 Problem Statement
Analyze Tesla (TSLA) stock price patterns to identify **trends, seasonal behavior, and volatility clusters** using historical trading data.

---

## ❓ Key Questions
- What is the overall price trend and major turning points?  
- Are there specific days/months with better returns?  
- When does Tesla experience the highest volatility?  
- Can we forecast short-term price movements?  

---

## 📂 Dataset Details
- **Source:** Yahoo Finance  
- **Time Period:** Sept 30, 2019 – Apr 11, 2022 (~650 trading days)  

### 📊 Features
| Column | Description |
|--------|------------|
| Date | Trading date |
| Open | Opening price |
| High | Daily maximum |
| Low | Daily minimum |
| Close | Closing price |
| Volume | Shares traded |
| Adj Close | Adjusted closing price |

✅ **Data Quality:** No missing values  

---

## ⚙️ Methodology

### 1️⃣ Data Preparation
- Converted `Date` to datetime format  
- Set `Date` as index  
- Created new features:
  - Daily Returns  
  - Moving Averages (7, 30, 200 days)  
  - Rolling Volatility  

### 2️⃣ Trend Analysis
- Identified bullish and bearish phases  
- Calculated total returns and key milestones  
- Used moving averages for trend direction  

### 3️⃣ Seasonality Analysis
- Grouped data by:
  - Day of week  
  - Month  
  - Quarter  
- Calculated average returns and volatility  

### 4️⃣ Volatility Analysis
- Computed 30-day rolling standard deviation  
- Identified high-volatility periods (top 10%)  
- Detected volatility clusters  

### 5️⃣ Forecasting
- Applied ARIMA (5,1,2) model  
- Forecasted next 30 days  
- Included 95% confidence intervals  

---

## 📈 Results

### 🔹 Trend Analysis
- **Start Price:** $48.17  
- **End Price:** $975.93  
- **Total Return:** +1925%  
- **Peak Price:** $1243.49 (Nov 2021)  
- **Lowest Price:** $70.10 (Mar 2020)  

#### Market Phases
| Phase | Period | Change |
|------|--------|--------|
| Pre-COVID Growth | Sep 2019 - Feb 2020 | +86% |
| COVID Crash | Feb 2020 - Mar 2020 | -58% |
| Bull Run | Mar 2020 - Nov 2021 | +1677% |
| Correction | Nov 2021 - Apr 2022 | -20% |

---

### 🔹 Seasonality Insights
- **Best Day:** Wednesday (+0.35%)  
- **Worst Day:** Monday (-0.12%)  

| Day | Avg Return |
|-----|-----------|
| Monday | -0.12% |
| Tuesday | +0.08% |
| Wednesday | +0.35% |
| Thursday | +0.18% |
| Friday | -0.05% |

- **Best Months:** November, August, July  
- **Worst Months:** September, March, January  
- **Best Quarter:** Q4 (Oct–Dec)  

---

### 🔹 Volatility Findings
- **Average Daily Volatility:** 3.7%  
- **Max Volatility:** 12.4%  

#### Key Events
- March 2020 → COVID crash  
- August 2020 → Stock split  
- November 2021 → Peak & reversal  

---

### 🔹 Forecast (30 Days)
| Horizon | Predicted Price | Confidence Interval |
|--------|----------------|---------------------|
| Day 5 | $968.50 | $912 – $1025 |
| Day 10 | $962.80 | $895 – $1031 |
| Day 20 | $951.20 | $866 – $1037 |
| Day 30 | $944.50 | $849 – $1040 |

📉 **Insight:** Slight downward trend (~ -3.2%) with high uncertainty  

---

## 💡 Key Takeaways
- Strong long-term growth with high volatility  
- Best trading periods: Wednesdays & Q4  
- High-risk periods: March & August  
- Short-term forecast shows consolidation  

---

## 🛠️ Tech Stack
- Python 3.8+  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- StatsModels (ARIMA)  

---

## 🚀 How to Run
```bash
git clone https://github.com/Kashaf537/tesla-time-series-analysis.git
cd tesla-time-series-analysis
pip install -r requirements.txt
python analysis.py
