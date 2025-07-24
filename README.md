
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
* 📉 Drawdown curves for each stock
* 📊 Daily returns comparison
* 🧮 Moving averages and volatility overlay
* 📌 Correlation heatmap


---

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

