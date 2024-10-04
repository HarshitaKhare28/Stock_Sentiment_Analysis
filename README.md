# Stock Sentiment Analysis

This project scrapes Reddit posts from the 'wallstreetbets' subreddit, analyzes the sentiment of stock-related posts, and performs data analysis to derive actionable insights. The project uses `praw` for scraping, `vaderSentiment` for sentiment analysis, and `yfinance` for stock price data.

## Table of Contents
- [Setup](#setup)
- [Dependencies](#dependencies)
- [Instructions to Run](#instructions-to-run)
- [Reddit API Key Setup](#reddit-api-key-setup)
- [Data Analysis](#data-analysis)
- [Future Improvements](#future-improvements)

## Setup

1. Clone the repository to your local machine:
    ```bash
    git clone https://github.com/your-username/reddit-stock-sentiment-analysis.git
    cd reddit-stock-sentiment-analysis
    ```

2. Ensure that you have Python installed. You can check this by running:
    ```bash
    python --version
    ```


## Dependencies

The project requires the following Python packages:

- `pandas`: For handling and analyzing data.
- `praw`: To scrape Reddit data using the Reddit API.
- `vaderSentiment`: For sentiment analysis of post titles.
- `yfinance`: For fetching stock price data.
- `nltk`: For natural language processing, specifically for stopword removal.
- `gensim`: For topic modeling using LDA.

## Instructions to Run

1. Place your Reddit API credentials (client ID and secret) in a separate `config.py` file. Your `config.py` should look like this:
    ```python
    client_id = 'your_client_id'
    client_secret = 'your_client_secret'
    ```

2. Run the data scraping script:
    ```bash
    python data_scraping.py
    ```

   The scraped data will be stored in a CSV file (`Reddit_Stock_Sentiment_Data.csv`).

3. To run the analysis and visualization, use the provided Jupyter notebook or additional Python scripts.

## Reddit API Key Setup

To use the Reddit API, follow these steps:

1. Go to the [Reddit App Preferences page](https://www.reddit.com/prefs/apps).
2. Click on **Create App** or **Create Another App**.
3. Fill in the details:
    - **App Name**: Name your app (e.g., "StockSentimentAnalysis").
    - **App Type**: Select "Script".
    - **Redirect URI**: Set this to `http://localhost:8000` (or any URL of your choice, as it's not needed for this project).
    - **Personal Use Script**: This is your `client_id`.
    - **Secret**: This is your `client_secret`.
    
4. Save these details in your `config.py` file as described above.

## Data Analysis

The data analysis process focused on preparing the data and uncovering insights through the following steps:

#### 1. Data Cleaning
- Handled missing values using forward fill.
- Removed duplicate rows and detected outliers with the z-score method.
- Reset the DataFrame index post-cleaning.

#### 2. Sentiment Categorization
- Applied VADER sentiment analysis to categorize posts into positive, negative, and neutral categories.

#### 3. Topic Modeling
- Used Latent Dirichlet Allocation (LDA) to identify 5 key topics from the text data.

#### 4. Grouping by Stock Tickers
- Aggregated sentiment scores by stock tickers to analyze trends across different companies.

#### 5. Stock Price Data
- Fetched stock price data using **yfinance** and integrated it with sentiment data to visualize potential correlations.

#### 6. Visualization
- Created pie charts, histograms, box plots, and time-series plots to visualize sentiment distribution and its relationship with stock price movements.

This streamlined analysis provided essential insights into how social media sentiment can potentially influence stock prices.


## Future Improvements

- Integrate data from multiple sources such as news articles or financial reports.
- Use machine learning models for more advanced sentiment analysis.
