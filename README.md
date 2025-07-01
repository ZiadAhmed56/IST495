# Sentiment Analysis for Financial News Trading

### Overview

This project performs real-time sentiment analysis on financial news articles to generate trading signals. It uses **FinBERT** and **VADER** to extract sentiment scores from news scraped from Finviz, then ranks relevant stock tickers by aggregated sentiment. The model supports momentum-based strategies and was used to generate **over $100,000 in simulated profit** during 8 weeks of backtesting.

### Key Features

- Fetches top stock tickers based on % change from **Finviz**
- Analyzes sentiment using **FinBERT** (finance-tuned BERT) and **VADER**
- Combines scores into a single, weighted sentiment metric
- Filters and analyzes **today's news** for relevant tickers
- Outputs ranked news articles and stock tickers by sentiment score

### Setup

**Prerequisites:**
- Python 3.8+
- Pip

**Install dependencies:**
pip install requests pandas transformers vaderSentiment beautifulsoup4 notify-py matplotlib

### Usage

1. Replace `FINVIZ_AUTH_TOKEN` in the script with your Finviz API token.
2. Run the script:
python sentiment_analysis.py

### Key Functions

fetch_finviz_data(url): Fetches and parses data from Finviz screener  
analyze_sentiment(article): Returns combined FinBERT + VADER sentiment score  
filter_news_for_today(news_data, tickers): Filters news by date + ticker and appends sentiment  
get_top_tickers(screener_data): Returns top 10 stock tickers by % change  
get_top_sentiment(news_data, top_n): Returns top N news headlines by sentiment  
generate_finviz_news_url(tickers): Constructs Finviz URL for multi-ticker sentiment scraping

### Example Output

Top 10 Tickers:  
Ticker   | Company         | Change  
-------- | --------------- | -------  
AAPL     | Apple Inc.      | +5.42%  
MSFT     | Microsoft Corp  | +4.89%  

Today's News:  
Ticker | Headline                          | Sentiment  
------ | --------------------------------- | ---------  
AAPL   | Apple unveils new chip...         | 0.78  
MSFT   | Microsoft expands into AI...      | 0.65  

Top 5 Articles by Sentiment:  
"Apple surges after earnings..."            → 0.88  
"Microsoft leads tech rebound..."           → 0.85

### Future Enhancements

- Real-time visualization of sentiment vs price action  
- Cron-based automation of periodic scraping  
- Expansion to other sources (Twitter, SEC filings, Yahoo Finance)

### Disclaimer

This model was used in an academic trading simulation and is **not** deployed in live trading environments. Code is simplified for demonstration and educational purposes.
