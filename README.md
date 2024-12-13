Sentiment Analysis for Financial News

This project analyzes the sentiment of financial news articles using FinBERT and VADER. It dynamically fetches data from Finviz and provides insights into top-performing stocks and the sentiment of related news articles.

Features

- Fetch top stock tickers based on percentage change from Finviz.
- Analyze sentiment using FinBERT (a financial sentiment analysis model) and VADER.
- Combine sentiment scores for a comprehensive analysis.
- Filter and display today's news related to top stock tickers.
- Provide a ranked list of articles with the highest sentiment scores.

Prerequisites

Ensure you have the following installed:

- Python 3.8+
- Pip

Install the required Python libraries:

```bash
pip install requests pandas transformers vaderSentiment beautifulsoup4 notify-py matplotlib
```

Usage

1. Set Up API Token:
   Replace the placeholder `FINVIZ_AUTH_TOKEN` in the code with your valid Finviz API token.

2. Run the Script:
   Execute the Python script in your terminal or IDE:

   ```bash
   python sentiment_analysis.py
   ```

3. Output:
   - The script fetches screener data and displays the top 10 stocks by percentage change.
   - It analyzes today's news articles and calculates sentiment scores.
   - Outputs top articles ranked by sentiment scores.

Code Explanation

Libraries Used

- `requests`: For fetching data from the web.
- `pandas`: For data manipulation and analysis.
- `transformers`: To use the FinBERT model for sentiment analysis.
- `vaderSentiment`: For VADER-based sentiment analysis.
- `io`: To handle data streams.
- `datetime`: To filter articles by date.

 Key Functions

- `fetch_finviz_data(url)`:
  Fetches data from Finviz using the provided URL. It returns the data as a Pandas DataFrame.

- `analyze_sentiment(article)`:
  Analyzes the sentiment of a given article using FinBERT and VADER. Returns a combined sentiment score.

- `filter_news_for_today(news_data, tickers)`:
  Filters news articles for today's date and relevant stock tickers. Adds sentiment scores to the filtered articles.

- `get_top_tickers(screener_data)`:
  Extracts the top 10 stock tickers from the screener data, sorted by percentage change.

- `get_top_sentiment(news_data, top_n)`:
  Retrieves the top N news articles by sentiment score.

- `generate_finviz_news_url(tickers)`:
  Constructs a Finviz news URL based on the provided tickers.

 Example Output

1. Top 10 Tickers:

```
Ticker    Company        Change
AAPL      Apple Inc.     5.42
MSFT      Microsoft Corp 4.89
...
```

2. Today's News for Top Tickers:

```
Ticker    Title                               Sentiment Score
AAPL      "Apple releases new product..."    0.78
MSFT      "Microsoft announces new AI..."   0.65
...
```

3. Top 5 Articles by Sentiment Score:

```
Title                                  Sentiment Score
"Apple's market value surges..."      0.88
"Microsoft achieves breakthrough..."  0.85
...
```

 Future Enhancements

- Integrate visualization of sentiment trends.
- Automate periodic data fetches and analysis.
- Extend support to other data sources beyond Finviz.

 Contributions

Contributions are welcome! Please submit a pull request or open an issue to get involved.


