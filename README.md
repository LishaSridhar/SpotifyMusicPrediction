# Spotify Music Popularity Prediction
A machine learning analysis investigating what drives music success on Spotify's Global Top 200 charts (2017-2023). This project explores temporal streaming patterns and compares the predictive power of audio features versus artist reputation in determining track popularity.

📄 Full write-up: [`report/report.pdf`](report/report.pdf)

## Project Structure

```
.
├── data/                  # Raw dataset (see Data Source below)
├── notebooks/
│   ├── main.ipynb                 # Feature engineering, EDA, modelling
│   └── Temporal Analysis.ipynb    # Streaming/longevity/collaboration trends
├── report/                # Full write-up (LaTeX source + PDF)
├── requirements.txt
└── README.md
```

## Data Source

This project uses the **Spotify Global Top 200 Streams (2017–2023)** dataset (`Spotify_Dataset_V3.csv`). The dataset is included as a zip file in data/Spotify_Dataset_V3.zip — unzip it before running the notebooks.

## Installation & Setup

Clone the repo and set up a virtual environment:

```bash
python -m venv venv

# macOS / Linux
source venv/bin/activate

# Windows
venv\Scripts\activate

pip install -r requirements.txt
```

Then launch Jupyter and open the notebooks:

```bash
jupyter notebook
```

Run all cells in **`main.ipynb`** and **`Temporal Analysis.ipynb`** to reproduce the results:

**`main.ipynb`**
- Builds artist history and time-aware features
- EDA with univariate histograms, bivariate boxplots by target class, and a correlation heatmap
- Model development and performance comparison across models
- Confusion matrices and classification reports for the best combined models, with per-class metrics

**`Temporal Analysis.ipynb`**
- Streaming patterns (yearly, monthly, weekly)
- Song chart longevity (yearly)
- Collaboration trends (yearly)

## Key Findings

1. Artist reputation features consistently outperform audio features in predicting song success
2. XGBoost achieved the highest accuracy (~70%) across all feature configurations
3. Song chart longevity decreased by 56% from 2017 to 2022 (73 days → 32 days)
4. Weekend streaming peaks at +2.2% above weekday average (Saturday highest)
5. The COVID-19 pandemic caused a 7.8% drop in streaming points and reduced collaborations

## Technical Details

**Algorithms used:**
- Random Forest
- Logistic Regression
- XGBoost
- Support Vector Machine (SVM)

**Feature engineering:**
- Audio features: danceability, energy, loudness, speechiness, acousticness, instrumentalness, valence
- Artist features: historical performance, experience, release frequency, collaboration metrics
- Time-aware aggregation for artist reputation tracking

## Contributors

This project was completed as part of a postgraduate Data Science course by a team of four. I led the majority of the implementation and analysis (~90% of the work), covering feature engineering, model development, and results analysis.

## License

This project is shared for portfolio purposes. No license is currently specified — please contact me before reuse.
