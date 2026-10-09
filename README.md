# The Android app market on Google Play

Cleaning and exploratory analysis of about 9,600 Google Play apps: categories, ratings, size, price, free vs paid, and
review sentiment.

This is a DataCamp guided project (2021). DataCamp wrote the questions, the narrative text and the outline of each
step; I completed the code. I keep it here as early practice.

## Data

DataCamp's copy of the Google Play Store data, which was scraped and published on Kaggle by Lavanya Gupta
([Google Play Store Apps](https://www.kaggle.com/datasets/lava18/google-play-store-apps)):

- `datasets/apps.csv`: one row per app (13 features)
- `datasets/user_reviews.csv`: 100 pre-processed reviews per app, with sentiment label, polarity and subjectivity

The CSV files are not included in this repository.

## What the notebook does

1. Drop duplicate rows (9,659 apps left), strip `+`, `,` and `$` from `Installs` and `Price`, and convert them to numbers.
2. Count apps per category (33 categories) and plot the rating distribution (mean rating 4.17).
3. Plot size and price against rating, and price per category. Apps priced above $200 are almost all "I am rich"-style
   joke apps, so the price-per-category chart is redrawn with apps under $100 only.
4. Compare installs for free and paid apps, and review sentiment polarity for free and paid apps.

## Results

This is descriptive analysis only, with no model or metric. The main observations, as written in the notebook:

- Family and Game are the largest categories, followed by Tools, Business and Medical.
- Most top-rated apps (rating above 4) are 2–20 MB, and most paid apps cost under $10.
- Paid apps have fewer installs than free apps.
- Reviews of free apps include more strongly negative sentiment than reviews of paid apps.

## How to run

Download the two CSVs (from the DataCamp project or the Kaggle dataset above) into a `datasets/` folder next to the
notebook, then run it with pandas, plotly, seaborn and matplotlib installed.

## Notes

- Three of the charts (apps per category, rating histogram, installs of free vs paid apps) are interactive Plotly charts.
  GitHub's notebook preview does not run JavaScript, so they show as blank space on GitHub. To see them, open the
  notebook in Jupyter, or paste its GitHub URL into [nbviewer](https://nbviewer.org/). The seaborn charts render normally.
