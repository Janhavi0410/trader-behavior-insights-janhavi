# **Trader Behavior Insights — Linking Market Sentiment to Trader Performance**

### **By: Janhavi Rewale**

---

## 📌 **Overview**

This project analyzes how trader behavior (using Hyperliquid historical data) interacts with market sentiment (Fear & Greed Index).  
Traditional sentiment analysis assumes that *fear = loss* and *greed = profit* — but real traders rarely behave that simply.

This study reverses the problem and explores:

🔍 **Which traders outperform sentiment expectations?**  
🔍 **When do traders generate alpha in “unexpected” environments (fear but profit, greed but loss)?**  
🔍 **Which behavioral personas emerge from trading activity?**  
🔍 **How does sentiment divergence create tradable insights?**  

This assignment is part of the hiring challenge for the **Junior Data Scientist – Trader Behavior Insights** role at PrimeTrade.ai.

---

## 📁 **Datasets Used**

### **1. Hyperliquid Trader Data (`trader_data.csv`)**

Contains 200K+ rows of real trading behavior:

- Account  
- Symbol  
- Execution price  
- Size (USD, tokens)  
- Side  
- Time  
- Closed PnL  
- Event  
- Leverage  
- Trade ID, etc.

### **2. Bitcoin Sentiment Data (`sentiment.csv`)**

- Date  
- Classification (Fear / Greed / Extreme Fear / Extreme Greed)  
- Sentiment score (0–100)

---

## 🧠 **Approach**

This analysis is structured to reflect real-world data science workflow:

### **1. Data Cleaning & Timestamp Fixes**
- Cleaned multiple timestamp formats  
- Converted to standardized `Timestamp IST`  
- Extracted clean daily `date`  
- Resolved timezone inconsistencies  

### **2. Daily Performance Aggregation**
- Summed daily PnL and daily volume  
- Merged with sentiment labels  
- Engineered features:  
  - `leverage`  
  - `leverage_delta`  
  - `sentiment_flag`  

### **3. Trader Personas (Behavior Clustering)**
Using KMeans, traders were grouped into 4 personas:

- **Risk-heavy high-volume traders**  
- **Consistent medium-risk traders**  
- **Low-frequency cautious traders**  
- **Volatile high-PnL traders**

### **4. Alpha Pocket Discovery**

Alpha Pockets =  
Moments where trader behavior **contradicts** sentiment expectations:

- Profit during *Fear* → unusual strength  
- Loss during *Greed* → hidden weakness  
- High volume during *Fear* → accumulation  
- Low volume during *Greed* → caution  

These are crucial for trading strategy design.

### **5. Visualization & Insights**
Includes:

- PnL trend  
- Persona clustering  
- PnL vs sentiment scatter  
- Alpha pocket markers  
- Alpha frequency per persona  

### **6. Predictive Modeling**
A regression model predicts next-day PnL using:

- leverage  
- leverage_delta  
- daily volume  
- sentiment_flag  

---

## 📊 **Key Insights**

### **1. Sentiment Alone Cannot Predict Trader Performance**
Some personas outperform even during Fear — especially Persona 2.

### **2. Greed Days Are Often Overestimated**
Several personas lose money during Greed → shorting opportunities.

### **3. Volume Spikes During Fear = Hidden Accumulation**
Indicates strategic buying behavior.

### **4. Personas behave differently under sentiment**
Segmenting traders gives better predictability than sentiment alone.

---

## 🗂️ **Project Structure**

```
.
├── notebook.ipynb
├── ds_report.pdf
├── csv_files/
│   ├── persona_table.csv
│   ├── persona_daily.csv
│   └── model_data.csv
├── outputs/
│   ├── persona_plot.png
│   ├── pnl_vs_sentiment_alpha.png
│   └── alpha_pockets_by_persona.png
└── README.md
```

---

## ⚙️ **How to Run**

Clone this repository:

```bash
git clone https://github.com/Janhavi0410/trader-behavior-insights-janhavi.git
cd trader-behavior-insights-janhavi
pip install -r requirements.txt
```

---

## 📬 **Contact**

**Janhavi Rewale**  
*(Add your email / LinkedIn if you want)*

