Netflix Shows & Movies: Exploratory Data Analysis

An end-to-end exploratory analysis of the Netflix catalogue using Python (pandas, seaborn, matplotlib) with one visualisation built in R (ggplot2).

The project covers data preparation, cleaning, statistical exploration and visualisation, and answers a simple question: what does Netflix's catalogue actually look like, and how recent is it?

Key Findings
The catalogue is dominated by recent content. release_year is strongly left-skewed (skewness = -3.71). The median release year is 2016, while the mean is 2013.4, pulled down by a small number of much older titles.
Genres: International Movies is the most common genre, followed by Dramas and Comedies. (See the genre chart below.)
Ratings: TV-MA is the most frequent rating, which suggests the catalogue leans towards all audiences.
Countries: The United States leads with 2,026 titles, followed by India (777) and the United Kingdom (347). A further 474 titles have no country listed.
Dataset
Size: 6,223 titles, 12 columns
Columns: show_id, type, title, director, cast, country, date_added, release_year, rating, duration, listed_in, description
Methodology
1. Data preparation

The dataset was unzipped programmatically with Python's zipfile module and renamed to Netflix_shows_movies.csv.

2. Data cleaning
The dataset had no true NaN values, but missing information was stored as the text 'Unknown': director (1,958 rows, 31.5%), cast (569, 9.1%) and country (474, 7.6%). These were converted to NaN rather than dropped or imputed, so no rows were lost. Missing values are excluded only from analyses that use those columns. director was not analysed because nearly a third of its values are missing."
3. Data exploration
Summary statistics with describe() and info()
Shape of the release_year distribution: mean, median and skewness
Frequency counts for type, rating and country
4. Data visualisation
Most common genres: the listed_in column holds several genres per title, so each cell was split with str.split() and expanded with explode() before counting.
Ratings distribution: a count plot of content ratings.
Release year distribution: a histogram showing the skew towards recent titles.

5. Visualisations

Add your exported images to an images/ folder and update the file names below.


Limitations
The dataset has no viewing figures, so "most watched" genres means the genres with the most titles, not the most hours viewed.
release_year is when a title was originally made, not when it joined Netflix.
The dataset is a snapshot, so it may not reflect the current catalogue.
Project Structure
.
├── Netflix_movies_sample.ipynb   # Main analysis (Python)
├── Netflix_shows_movies.csv      # Dataset
├── netflix_clean.csv             # Cleaned data exported for R
├── images/                       # Exported charts
└── README.md
How to Run
bash
git clone https://github.com/[your-username]/[repo-name].git
cd Netflix_Movies_Analysis
pip install pandas numpy seaborn matplotlib jupyter
jupyter notebook Netflix_movies_sample.ipynb

For the R chart, install R and run:

r
install.packages("tidyverse")
source("netflix_ratings.R")
Tools Used

Python · pandas · NumPy · seaborn · matplotlib · R · ggplot2 · Jupyter

Author

Moses Ogriki LinkedIn · GitHub