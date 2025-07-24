
# 📊 Stock Market Analysis Dashboard

A comprehensive stock market analysis and visualization project focused on leading tech stocks: **AAPL**, **MSFT**, **NVDA**, **AMZN**, **META**, and **GOOG**.

This project leverages Python and key data science libraries to analyze historical stock data, visualize trends, calculate technical indicators, and compare stock behaviors over time using both static and interactive visualizations.

---

## 🚀 Key Features

* ✅ Daily returns calculation & plotting
* ✅ Drawdown detection from historical peaks
* ✅ 20-day and 50-day moving averages
* ✅ 20-day rolling volatility
* ✅ Normalized price comparisons across stocks
* ✅ Correlation heatmap between assets
* ✅ Grid-based plotting for multi-stock comparison

---

## 🧪 Technologies & Libraries

| Technology       | Purpose                         |
| ---------------- | ------------------------------- |
| **Python 3.10+** | Core programming language       |
| **Pandas**       | Data manipulation and analysis  |
| **Matplotlib**   | Static data visualization       |
| **Seaborn**      | Enhanced heatmaps and plots     |
| **Plotly**       | Interactive plotting (optional) |
| **yfinance**     | Stock data download from Yahoo  |


---

## 📈 Analysis Workflow

### 1. 📥 Fetch Historical Stock Data

Data is pulled from Yahoo Finance using the `yfinance` library.

```python
import yfinance as yf

tickers = ['AAPL', 'MSFT', 'NVDA', 'AMZN', 'META', 'GOOG']
data = yf.download(tickers, start="2020-01-01", end="2024-12-31")['Close']
```

---

### 2. ⚖️ Normalize Prices for Comparison

Normalize all stock prices to start from 1 to visually compare percentage growth over time.

```python
normalized = data / data.iloc[0]
normalized.plot(figsize=(12,6), title='Normalized Stock Prices')
```

---

### 3. 📊 Calculate Daily Returns

Used for risk analysis and volatility measurement.

```python
daily_returns = data.pct_change()
daily_returns.plot(figsize=(12,6), title='Daily Returns')
```

---

### 4. 📉 Drawdown Analysis

Drawdown helps visualize how much a stock has fallen from its peak.

```python
drawdowns = data / data.cummax() - 1
drawdowns.plot(figsize=(12,6), title='Drawdown from Peak')
```

---

### 5. 📏 Moving Averages & Volatility

Simple moving averages (SMA) and rolling volatility help smooth price movements and capture risk.

```python
ma_20 = data.rolling(20).mean()
ma_50 = data.rolling(50).mean()
volatility = data.pct_change().rolling(20).std()
```

All metrics are visualized in a subplot grid for each stock.


---

### 6. 🧠 Correlation Heatmap

Understand inter-stock relationships and portfolio diversification potential.

```python
import seaborn as sns
import matplotlib.pyplot as plt

plt.figure(figsize=(10, 8))
sns.heatmap(daily_returns.corr(), annot=True, cmap='coolwarm', fmt=".2f")
plt.title("Stock Correlation Heatmap")
plt.show()
```

---

## 🖼️ Sample Visuals

* 📈 Normalized stock price chart
  <img width="988" height="520" alt="output" src="https://github.com/user-attachments/assets/69d092a4-1485-4d11-9b6b-835a7dc43835" />

* 📉 Drawdown curves for each stock
* <img width="1488" height="590" alt="output4" src="https://github.com/user-attachments/assets/95f9e943-25f4-44ed-9943-d2dd94641ac5" />
<img width="2240" height="985" alt="output5" src="https://github.com/user-attachments/assets/2cf9f3ce-1962-4dc8-8471-68be7fa0ca03" />

* 📊 Daily returns comparison
<img width="1183" height="584" alt="output11" src="https://github.com/user-attachments/assets/c8a73757-5546-41c0-b136-a1c83f467a35" />


* 🧮 Moving averages and volatility overlay
* 
* <img width="1786" height="989" alt="output6" src="https://github.com/user-attachments/assets/402784a9-470a-475b-b747-5a50bd22824d" />

* 📌 Correlation heatmap
* <img width="524" height="435" alt="output3" src="https://github.com/user-attachments/assets/e9fa09f3-3291-4e59-829c-dbecad4daa4d" />

---
### Insight Summary – Stock Market Analysis (AI Era Context)

Here, we analyzed the price dynamics of leading tech stocks — AAPL, MSFT, META, NVDA, GOOG, and AMZN — by employing 20-day and 50-day moving averages, as well as volatility indicators. These stocks are the pillars of the AI mania and major contenders in the race for infrastructure, cloud leadership, and AI implementation.

### Key Observations:

- **NVDA (NVIDIA)** demonstrates maximum short-term volatility among all stocks — in line with its growth fueled by AI GPU demand.
- **META and AMZN** revealed crossover among the MA20 and MA50, which indicates possible bullish momentum changes — valuable for swing traders who are placing bets on AI-driven ad and cloud revenue.
- **AAPL and MSFT** fluctuated relatively less, with narrower volatility bands — indicating institutional confidence and gradual, consistent growth in the face of AI integration.
- **GOOG (Alphabet)** demonstrated a recent increase in volatility, which may be related to its thrust in generative AI with Gemini and cloud offerings.
As AI shapes the tech industry further, tracking short-term volatility and moving average crossovers in these prominent firms holds important insight for both short-term traders and long-term investors. Technical analysis such as this can serve as a ground layer when combined with AI sentiment models and finance forecasting software.

 Next Step: Combine this with an LLM-based sentiment monitor or news analyzer to tie technical signals to actual-world AI advancements.

## 📝 Getting Started

1. **Clone this repository:**

```bash
git clone https://github.com/00Harshh/stock-analysis-dashboard.git
cd stock-analysis-dashboard
```

2. **Install dependencies (recommended in a virtual environment):**

```bash
pip install -r requirements.txt
```

3. **Launch the Jupyter Notebook:**

```bash
jupyter notebook notebooks/stock_analysis.ipynb
```

---

## 📌 Future Enhancements

* [ ] Add Bollinger Bands and RSI
* [ ] Integrate real-time stock updates
* [ ] Convert to interactive dashboard using **Plotly Dash** or **Streamlit**
* [ ] Add sector-wise comparisons and fundamental ratios

---

## 📃 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 🤝 Contributing

Contributions are welcome and appreciated!

* Fork the repository
* Create a new branch for your changes
* Submit a pull request with a clear description

---

## 🙌 Acknowledgements

* [Yahoo Finance API via yfinance](https://pypi.org/project/yfinance/)
* [Pandas](https://pandas.pydata.org/)
* [Matplotlib](https://matplotlib.org/)
* [Seaborn](https://seaborn.pydata.org/)
* [mplfinance](https://github.com/matplotlib/mplfinance)

---

