# Data Analysis in Finance

```mermaid
graph TD;
    A[Raw 10-K Filings] -->|Data Extraction| B[Preprocessing & Cleaning];
    B -->|Text Parsing| C[Sentiment Analysis];

    C -->|Dictionary-Based Approach| D1[Sentiment Scores - Loughran & McDonald];
    C -->|Language Similarity| D2[TF-IDF & Cosine Similarity];
    C -->|Deep Learning Approach| D3[Sentiment Analysis with FinBERT];

    D1 -->|Feature Engineering| E[Feature Integration];
    D2 -->|Feature Engineering| E;
    D3 -->|Feature Engineering| E;

    E -->|Predictive Modeling| F[Regression & Machine Learning];
    F -->|Stock Ranking| G[Long-Short Portfolio Strategy];
```

## Data Analysis Finance Environment Setup

To set up the environment for data analysis in finance, follow these steps:

```bash
conda create --name data_analysis_finance python=3.11.9
```
```bash
conda activate data_analysis_finance
```
```bash
pip install -r requirements.txt
```

## Notebooks Overview

This repository contains several Jupyter notebooks, each focusing on different stages of data analysis and financial modeling:

### 1. `filter_dow30_10K.ipynb`
   - Extracts Item 7 from 10-K filings for Dow 30 companies.
   - Uses regex patterns for initial data parsing.
   - Highlights challenges and introduces API-based extraction as an alternative.

### 2. `api_data_extraction.ipynb`
   - Fetches structured financial data using the SEC API.
   - Ensures consistency in data retrieval across different companies and years.
   - Saves extracted reports for further processing.

### 3. `signal_generation.ipynb`
   - Generates sentiment-based signals from textual data.
   - Implements dictionary-based sentiment analysis, language similarity analysis, and BERT-based sentiment extraction.
   - Prepares extracted features for integration into predictive models.

### 4. `trading_strat_data.ipynb`
   - Integrates sentiment signals with market performance data.
   - Performs feature engineering to construct datasets for predictive modeling.
   - Stores intermediate results as CSV files for later use.

### 5. `trading_strat_modelling.ipynb`
   - Implements the predictive model using an Ordinary Least Squares (OLS) regression.
   - Trains the model using an expanding window approach.
   - Generates predicted returns and ranks stocks based on expected performance.

## Additional Resources
- All generated datasets and visualization outputs are stored in the `trading_strat_data` folder.
- The results of each notebook are linked and contribute to the final trading strategy analysis.