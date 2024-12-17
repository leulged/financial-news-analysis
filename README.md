
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


---

# Task 3: Correlation Between News Sentiment and Stock Movement

## Objective
In this task, we aim to analyze the relationship between news sentiment and stock price movements. The primary steps include:
- Aligning dates between stock price data and news headlines.
- Performing sentiment analysis on news headlines.
- Analyzing the correlation between stock price movements and the sentiment of the news.

## Steps Involved

### 1. **Date Alignment**
   - Ensure that both datasets (news and stock prices) are aligned by dates. This is done by normalizing the timestamps and ensuring that stock prices and news articles are available for the same dates.

### 2. **Sentiment Analysis**
   - Sentiment analysis is performed on the news headlines to classify them into positive, negative, or neutral. We use libraries like **TextBlob** and **NLTK** for sentiment classification.

### 3. **Stock Price Movements**
   - Daily stock returns are calculated by computing the percentage change in daily closing prices. This will represent the daily stock price movements.

### 4. **Correlation Analysis**
   - Using **Pearson Correlation**, we test the relationship between average daily sentiment scores and stock returns. This will help us determine if there is a correlation between the news sentiment and stock price movements.

---

## Task Workflow

### 1. **Data Preparation**  
The news data and stock price data are loaded and preprocessed. The `Date` column from both datasets is normalized to ensure that news headlines correspond to the appropriate trading day.

### 2. **Sentiment Analysis**  
Sentiment scores are calculated for each headline using **TextBlob** or **NLTK's** SentimentIntensityAnalyzer. The sentiment score ranges from -1 (very negative) to 1 (very positive). 

### 3. **Calculate Stock Movements**  
Daily stock returns are calculated using the formula:
\[
\text{Daily Return} = \frac{\text{Closing Price on Day n} - \text{Closing Price on Day n-1}}{\text{Closing Price on Day n-1}} \times 100
\]

### 4. **Correlation Calculation**  
The daily sentiment scores are aggregated by date, and Pearson correlation is computed between daily sentiment and stock returns to test the strength of their relationship.

---

## Results

### Correlation Between Sentiment and Stock Returns
The results of the correlation analysis help to understand the impact of news sentiment on stock movements. A positive correlation suggests that positive news leads to stock price increases, while negative sentiment corresponds to price declines.

### Example Visualization

Below is an example visualization of the correlation between news sentiment and stock returns for **AAPL**:

![Sentiment vs Stock Price Movement](https://github.com/leulged/financial-news-analysis/blob/main/screenshot/output.png)

---

## Code and Explanation

### 1. **Import Libraries**
We import necessary libraries like `pandas`, `matplotlib`, and `TextBlob` for sentiment analysis.

```python
import pandas as pd
import matplotlib.pyplot as plt
from textblob import TextBlob
```

### 2. **Load and Preprocess Data**
We load the stock and news datasets, normalize the date, and perform sentiment analysis on the headlines.

```python
def load_stock_data(data_folder, stock_files):
    stock_data = {}
    for file in stock_files:
        df = pd.read_csv(os.path.join(data_folder, file))
        df['Date'] = pd.to_datetime(df['Date'])
        stock_data[file.split('_')[0]] = df
    return stock_data
```

### 3. **Sentiment Analysis Function**
This function calculates sentiment scores for each headline.

```python
def analyze_sentiment(news_df):
    news_df['sentiment_score'] = news_df['headline'].apply(lambda x: TextBlob(x).sentiment.polarity)
    return news_df
```

### 4. **Correlation Analysis**
This function merges stock data and news sentiment, then calculates the Pearson correlation.

```python
def analyze_correlation(stock_data, news_sentiment):
    results = {}
    for stock_name, stock_df in stock_data.items():
        merged_df = pd.merge(stock_df, news_sentiment, left_on='Date', right_on='date', how='inner')
        correlation = merged_df['sentiment_score'].corr(merged_df['daily_return'])
        results[stock_name] = correlation
    return results
```

---

## Technologies Used:
- **Python**: Programming language used for data manipulation, sentiment analysis, and statistical computations.
- **Pandas**: For data handling and preprocessing.
- **TextBlob**: Sentiment analysis tool for processing text data.
- **Matplotlib**: For visualizing stock price movements and sentiment.
- **Scikit-learn**: For statistical analysis (correlation).
- **Jupyter Notebook**: For running the analysis interactively.

---

## Conclusion

In Task 3, we explored the relationship between the sentiment of news articles and stock price movements. By analyzing the correlation between daily sentiment scores and stock returns, we gained valuable insights into how media and news sentiment can influence financial markets.

--- 

