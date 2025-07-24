
# 📊 Stock Market Analysis Dashboard

This project performs exploratory analysis and visualization of major tech stocks such as **AAPL**, **MSFT**, **NVDA**, **AMZN**, **META**, and **GOOG**. It includes drawdown analysis, moving averages, volatility tracking, normalized price comparisons, daily returns, and correlation heatmaps using Python.

---

## 🚀 Features

- ✅ Daily returns calculation  
- ✅ Drawdown detection and visualization  
- ✅ Moving averages and volatility overlay  
- ✅ Candlestick chart visualization  
- ✅ Price normalization for comparative analysis  
- ✅ Correlation heatmap between stocks  
- ✅ Grid layout visualizations for multiple stocks

---

## 🧰 Technologies Used

- **Python 3.10+**
- **Pandas**
- **Matplotlib**
- **Seaborn**
- **Plotly**
- **yfinance** (for stock data)
- **mplfinance** (for candlestick charts)

---

## 📂 Project Structure

```

├── data/
│   └── \*.csv               # Optional pre-downloaded data
├── notebooks/
│   └── stock\_analysis.ipynb # Main analysis notebook
├── plots/
│   └── \*.png               # Saved visualizations
├── README.md
└── requirements.txt

````

---

## 📈 Analysis Steps

### 1. Fetch Historical Stock Data

Data is fetched using `yfinance`:

```python
import yfinance as yf
tickers = ['AAPL', 'MSFT', 'NVDA', 'AMZN', 'META', 'GOOG']
data = yf.download(tickers, start="2020-01-01", end="2024-12-31")['Close']
````

---

### 2. Normalize Prices for Comparison

Normalize all stock prices to start from 1 for direct comparison:

```python
normalized = data / data.iloc[0]
```

---

### 3. Calculate Daily Returns

```python
daily_returns = data.pct_change()
```

---

### 4. Drawdown Calculation

A drawdown is the decline from a historical peak:

```python
drawdowns = data / data.cummax() - 1
```

### 📉 Drawdown Plot

* Grid layout for multiple stocks
* Comparison chart across all tickers

---

### 5. Moving Averages & Volatility

```python
ma_20 = data.rolling(20).mean()
ma_50 = data.rolling(50).mean()
volatility = data.pct_change().rolling(20).std()
```

---

### 6. Correlation Heatmap

```python
import seaborn as sns
sns.heatmap(daily_returns.corr(), annot=True, cmap='coolwarm')
```

---

### 7. Candlestick Charts

Use `mplfinance` to visualize OHLC candles:

```python
import mplfinance as mpf
mpf.plot(df, type='candle', style='charles', mav=(20, 50))
```

---

## 📊 Visual Output Examples


---

## 📝 How to Run

1. Clone the repo:

```bash
git clone https://github.com/yourusername/stock-analysis-dashboard.git
cd stock-analysis-dashboard
```

2. Create virtual environment and install dependencies:

```bash
pip install -r requirements.txt
```

3. Run the Jupyter Notebook:

```bash
jupyter notebook notebooks/stock_analysis.ipynb
```

---

## 📌 Future Improvements

* Add Bollinger Bands and RSI
* Interactive dashboards using Plotly Dash or Streamlit
* Real-time stock data integration

---

## 📃 License

MIT License. See `LICENSE` for more details.

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

---

## 🙌 Acknowledgements

* [Yahoo Finance](https://finance.yahoo.com/)
* [Matplotlib](https://matplotlib.org/)
* [Seaborn](https://seaborn.pydata.org/)
* [Pandas](https://pandas.pydata.org/)




