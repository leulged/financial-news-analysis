### **Financial News Analysis: Comprehensive Data Analysis and Visualization**

---

### **Project Overview**
This project focuses on analyzing financial news headlines and their metadata to derive meaningful insights. Using Python and its ecosystem of libraries, we performed exploratory data analysis, text analysis, time series analysis, and publisher analysis. The insights gained from this analysis could help traders, analysts, and decision-makers understand trends and correlations in financial news data.

---

### **Key Objectives**
1. **Exploratory Data Analysis (EDA)**:
   - Uncover basic statistics, patterns, and trends in the data.
   - Perform descriptive statistics to understand headline lengths, publisher activity, and publication patterns.
2. **Text Analysis**:
   - Conduct sentiment analysis to classify news as positive, negative, or neutral.
   - Perform topic modeling to identify frequently mentioned terms or topics in the headlines.
3. **Time Series Analysis**:
   - Analyze publication frequency over time to identify trends or spikes.
   - Examine publishing times to understand when most news articles are released.
4. **Publisher Analysis**:
   - Identify the most active publishers contributing to the dataset.
   - Extract and analyze email domains from publisher names to uncover organizational contributions.

---

### **Technologies Used**
- **Python**: Core programming language for analysis.
- **Libraries**:
  - **Pandas**: Data manipulation and analysis.
  - **Matplotlib**: Data visualization.
  - **Seaborn**: Enhanced data visualization.
  - **NLTK**: Sentiment analysis using natural language processing.
  - **Scikit-learn**: Feature extraction for text analysis.
  - **Wordcloud**: Generate word clouds for topic modeling.

---

### **Folder Structure**
```
financial-news-analysis/
├── .vscode/                          # VSCode settings
├── .github/                          # GitHub workflows
│   └── workflows/
│       └── unittests.yml             # CI/CD pipeline
├── notebooks/                        # Jupyter notebooks
│   ├── eda_task1.ipynb               # EDA and visualization notebook
├── scripts/                          # Custom Python scripts
├── src/                              # Source code
│   └── __init__.py                   # Initialization file
├── tests/                            # Unit tests
├── requirements.txt                  # Dependencies
└── README.md                         # Project documentation
```

---

### **Steps and Analyses**
#### **1. Exploratory Data Analysis (EDA)**
- **Descriptive Statistics**:
  - Computed headline lengths using `apply(len)`.
  - Analyzed article contributions by publishers.
  - Visualized headline length distribution and publisher activity.
- **Code Example**:
```python
data['headline_length'] = data['headline'].apply(len)
headline_stats = data['headline_length'].describe()
```
![Distribution of headline lengths](https://github.com/leulged/financial-news-analysis/blob/task-1/screenshot/headline%20length.png)
![publication trends over time](https://github.com/leulged/financial-news-analysis/blob/task-1/screenshot/publication%20trend%20over%20time.png)

#### **2. Text Analysis**
- **Sentiment Analysis**:
  - Used `NLTK SentimentIntensityAnalyzer` to classify news headlines.
  - Categories: Positive, Neutral, Negative.
  - Code Example:
    ```python
    sia = SentimentIntensityAnalyzer()
    data['sentiment_score'] = data['headline'].apply(lambda x: sia.polarity_scores(x)['compound'])
    ```
    
- **Topic Modeling**:
  - Generated word clouds of frequent terms in the headlines.
  - Used `CountVectorizer` for feature extraction.
  - Code Example:
    ```python
    wordcloud = WordCloud().generate(' '.join(data['headline']))
    ``
    
![sentiment distribution of headlines](https://github.com/leulged/financial-news-analysis/blob/task-1/screenshot/sentiment%20distribution%20of%20headlines.png)
![Word ccloud of top keywoards](https://github.com/leulged/financial-news-analysis/blob/task-1/screenshot/word%20cloud%20of%20top%20keywords.png)
#### **3. Time Series Analysis**
- Analyzed publication frequency by day and hour.
- Visualized spikes in article publications.
- Code Example:
```python
data['date_only'] = pd.to_datetime(data['date']).dt.date
daily_counts = data.groupby('date_only').size()
```
![publication frequencies over time](https://github.com/leulged/financial-news-analysis/blob/task-1/screenshot/publication%20frequency%20over%20time.png)
![publication frequency by hour](https://github.com/leulged/financial-news-analysis/blob/task-1/screenshot/publication%20frequency%20by%20hour.png)
#### **4. Publisher Analysis**
- Identified the top publishers contributing to the dataset.
- Extracted and analyzed email domains from publisher names.
- Code Example:
```python
data['email_domain'] = data['publisher'].str.extract(r'@([\w\.-]+)')
domain_counts = data['email_domain'].value_counts()
```
![top publishers](https://github.com/leulged/financial-news-analysis/blob/task-1/screenshot/top%2010%20publishers.png)
![top email domain by contribution](https://github.com/leulged/financial-news-analysis/blob/task-1/screenshot/top10%20email%20doamins%20publishers.png)
---

### **Setup Instructions**
#### **1. Clone the Repository**
```bash
git clone https://github.com/leulged/financial-news-analysis.git
cd financial-news-analysis
```

#### **2. Create a Virtual Environment**
```bash
python -m venv venv
source venv/bin/activate  # macOS/Linux
.\venv\Scripts\activate   # Windows
```

#### **3. Install Dependencies**
```bash
pip install -r requirements.txt
```

#### **4. Run Jupyter Notebook**
```bash
jupyter notebook
```

#### **5. Explore the Notebooks**
- Open and run `notebooks/eda_task1.ipynb`.

---

### **Results**
- **Sentiment Distribution**:
  - Classified headlines into positive, negative, or neutral sentiment.
- **Publisher Trends**:
  - Identified the most active publishers.
  - Highlighted organizations based on email domain contributions.
- **Time Patterns**:
  - Found publication spikes during specific events.
  - Analyzed hourly publication frequency.

---

### **Acknowledgments**
Special thanks to the contributors for their dedication and insights in analyzing this dataset.

---

### **Contributing**
- Fork the repository.
- Create a new branch for your features/bug fixes.
- Submit a pull request for review.

---

### **Contact**
**Leul Gedion**  
Email: leulgedion224@gmail.com  
GitHub: [https://github.com/leulged/financial-news-analysis](https://github.com/leulged/financial-news-analysis)  

---

