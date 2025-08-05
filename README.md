# Twitter Trending Topic Analysis

A data analysis project to discover trending topics discussed by Twitter users in India using Natural Language Processing (NLP) and Topic Modeling techniques.

## Overview

This project analyzes tweets collected from Twitter using snscrape within a 500km radius of Delhi coordinates (28.644800,77.216721) to identify key discussion themes and topics.

## Data Collection

The data collection script captures:
- Tweet date
- Tweet content 
And saves it to a CSV file for analysis.

## Analysis Pipeline

### 1. Text Preprocessing
The code implements a comprehensive text cleaning pipeline:

a) Initial Cleaning:
- Remove usernames (@mentions)
- Remove URLs and hyperlinks
- Remove email addresses 
- Remove HTML tags
- Remove numbers
- Remove emojis and special characters
- Normalize whitespace

b) Text Normalization:
- Convert hashtags to words (e.g. #CovidCrisis -> Covid Crisis)
- Translate non-English text to English using Google Translate
- Apply spelling correction
- Normalize cases
- Expand contractions (e.g., isn't -> is not)

c) Tokenization:
- Convert text to tokens
- Remove stopwords (English, Hindi, Hinglish)
- Apply Porter Stemming

### 2. Topic Modeling
The code uses Latent Dirichlet Allocation (LDA) for topic modeling:

a) Feature Engineering:
- Create document-term matrix
- Compute TF-IDF vectors

b) Model Training:
- Train LDA model using Bag of Words and TF-IDF features
- Configure for 10 topics with multiple passes

c) Analysis:
- Extract key terms per topic
- Compute topic probabilities
- Visualize topic distributions
- Test on unseen documents

## Required Libraries
- pandas
- numpy 
- gensim
- nltk
- googletrans
- snscrape
- matplotlib
- seaborn

## Usage

1. Install requirements:
```bash
pip install -r requirements.txt
```

2. Run data collection:
```bash
python twitter_scrapper.py
```

3. Run analysis notebook:
```bash 
jupyter notebook Twitter_Trending_Topic_Analysis.ipynb
```

## Results

The analysis revealed several key insights:

1. Topic Distribution:
- Identified 10 major discussion topics from the tweets
- Each topic has a distinct set of keywords and themes
- Topics range from politics to entertainment to social issues

2. Key Findings:
- COVID-19 related discussions dominated multiple topics
- Strong regional influences in topic distribution
- High engagement around political and social issues
- Significant overlap between Hindi and English content

3. Visualizations:
- Bar plots showing topic term distributions
- Probability distribution of topics across the dataset
- Time-series analysis of topic trends
- Interactive visualization of topic relationships

The results demonstrate the effectiveness of LDA in identifying meaningful topics from Indian Twitter conversations, providing insights into public discourse and trending discussions.
