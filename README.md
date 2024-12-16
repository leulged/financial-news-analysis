
# Quantitative Analysis Using PyNance and Custom Indicators

## 📋 Project Overview
This project extends the financial data analysis dashboard by incorporating **quantitative analysis** for stock price data using Python. The focus is on:
- Loading and preprocessing historical stock price data.
- Calculating essential **technical indicators** like Simple Moving Averages (SMA), Relative Strength Index (RSI), and Moving Average Convergence Divergence (MACD).
- Visualizing the stock prices alongside these indicators for actionable insights.

---

## 🚀 Key Features
1. **Data Preprocessing**:
   - Loaded stock price data for multiple stocks: `AAPL`, `AMZN`, `GOOG`, `META`, `MSFT`, `NVDA`, and `TSLA`.
   - Cleaned and converted date fields into a usable format.
   - Dropped unused fields like `Dividends` and `Stock Splits`.

2. **Custom Technical Indicators**:
   - Replaced TA-Lib with custom implementations for:
     - **SMA**: Simple Moving Averages (10-day and 30-day).
     - **RSI**: Relative Strength Index.
     - **MACD**: Moving Average Convergence Divergence.
   - Made calculations efficient and reusable.

3. **Visualization**:
   - Plotted `Close` prices, SMAs, RSI, and MACD to observe trends and patterns.
   - Created clear and informative charts for each stock.
4. **Extensibility**:
   - Modularized the code for scalability, enabling the addition of more indicators or stocks.

---

## 🛠️ Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/leulged/financial-news-analysis.git
cd financial-news-analysis
```

### 2. Set Up a Virtual Environment
Create and activate a virtual environment:
#### On Windows:
```bash
python -m venv venv
.\venv\Scripts\activate
```

#### On macOS/Linux:
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
Install the required Python libraries:
```bash
pip install -r requirements.txt
```

---

## 🧑‍💻 How to Use
### 1. Run the Notebook
- Navigate to the `notebooks` directory:
  ```bash
  cd notebooks
  jupyter notebook
  ```
- Open the `task_2_analysis.ipynb` file.

### 2. Analyze and Visualize
The notebook guides you through:
1. Loading the stock data for analysis.
2. Preprocessing the data.
3. Calculating and visualizing custom indicators.

---

## 📊 Results and Insights
### AAPL (Example)
- **Simple Moving Averages (10-day & 30-day)**: 
  Identify short- and long-term trends.
- **RSI**: 
  Highlight overbought (RSI > 70) or oversold (RSI < 30) conditions.
- **MACD**: 
  Used for identifying buy/sell signals when the MACD crosses the signal line.

![visualization](https://github.com/leulged/financial-news-analysis/blob/main/screenshot/AAPLMACD.png)
![visualization](https://github.com/leulged/financial-news-analysis/blob/main/screenshot/AAPL_closeandsmas.png)
![visualization](https://github.com/leulged/financial-news-analysis/blob/main/screenshot/AAP_RSI.png)
![visualization](https://github.com/leulged/financial-news-analysis/blob/main/screenshot/AMZNMACd.png)
![visualization]([https://github.com/leulged/financial-news-analysis/blob/main/screenshot/AAPLMACD.png)
![](https://github.com/leulged/financial-news-analysis/blob/main/screenshot/AMZNclose.png))


*(and more.)*

### Summary
The analysis reveals valuable insights into stock price trends and technical indicators, helping investors make informed decisions.

---

## 🛠️ Technologies Used
- **Python**: Programming and analysis.
- **Pandas**: Data manipulation.
- **Matplotlib**: Visualization.
- **NumPy**: Numerical calculations.
- **TA-Lib (Replaced)**: Custom technical indicators implemented.

---

## 💼 Acknowledgments
- **10 Academy**: For guiding this structured learning project.
- **Community**: For resources on custom technical indicator calculations.

---

## 📝 Contributing
To contribute:
1. Fork the repository.
2. Create a branch for your feature:
   ```bash
   git checkout -b feature-name
   ```
3. Commit and push changes:
   ```bash
   git commit -m "Add your feature description"
   git push origin feature-name
   ```
4. Open a Pull Request.

---

## 📩 Contact
For queries, feel free to contact:
- **Leul Gedion**: leulgedion224@gmail.com

---
