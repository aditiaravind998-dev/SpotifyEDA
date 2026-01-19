# SpotifyEDA
# Spotify Dataset EDA Project

## 📊 Project Overview

This project performs an **Exploratory Data Analysis (EDA)** on a large Spotify dataset to uncover patterns, trends, and insights about songs, artists, genres, and audio features.

## 📁 Dataset

The dataset is downloaded from Kaggle and contains:

- **Songs**: 50,683 tracks with 21 features
- **Artists**: 8,317 unique artists
- **Years covered**: 1900–2022
- **Source**: Spotify API + Last.fm tags

### Main Files

| File | Description | Rows | Columns |
|------|-------------|------|---------|
| `Music Info.csv` | Song metadata + audio features | 50,683 | 21 |
| `User Listening History.csv` | User listening records | — | — |

## 🛠️ Setup

### Installation

```bash
pip install pandas numpy matplotlib seaborn missingno kagglehub
```

### Data Download

```python
import kagglehub
path = kagglehub.dataset_download("undefinenull/million-song-dataset-spotify-lastfm")
```

## 📊 Dataset Schema

### Columns in `Music Info.csv`

| Column | Type | Description |
|--------|------|-------------|
| `track_id` | `str` | Unique track identifier |
| `name` | `str` | Song title |
| `artist` | `str` | Artist name |
| `spotify_id` | `str` | Spotify track ID |
| `tags` | `str` | Comma-separated genre tags |
| `genre` | `str` | Main genre (many missing) |
| `year` | `int` | Release year |
| `duration_ms` | `int` | Duration in milliseconds |
| `danceability` | `float` | How suitable for dancing (0–1) |
| `energy` | `float` | Intensity measure (0–1) |
| `key` | `int` | Musical key (0–11) |
| `loudness` | `float` | Overall loudness in dB |
| `mode` | `int` | Major=1, Minor=0 |
| `speechiness` | `float` | Presence of spoken words |
| `acousticness` | `float` | Likelihood of being acoustic |
| `instrumentalness` | `float` | Predicts no vocals |
| `liveness` | `float` | Audience presence |
| `valence` | `float` | Positivity (0–1) |
| `tempo` | `float` | Beats per minute |
| `time_signature` | `int` | Meter (3/4, 4/4, etc.) |

## 📈 Missing Values

| Column | Missing Count | % Missing |
|--------|---------------|-----------|
| `tags` | 1,127 | 2.22% |
| `genre` | 28,335 | 55.91% |

## 🎯 Objectives

1. **Understand distributions** of audio features
2. **Explore genre trends** over time
3. **Identify correlations** between features
4. **Analyze artist popularity** patterns
5. **Prepare data** for ML applications

## 🔍 Analysis Performed

### 1. **Data Loading & Inspection**
- Load CSV files
- Check shape, info, and head
- Drop irrelevant columns

### 2. **Missing Data Analysis**
- Count missing values per column
- Visualize with `missingno.matrix()`

### 3. **Basic Statistics**
```python
df_songs.shape      # (50683, 21)
df_songs.info()
df_songs.describe()
```

### 4. **Feature Engineering**
- Removed `spotify_preview_url`
- Kept relevant audio features for analysis

## 📊 Sample Data

| track_id | name | artist | year | danceability | energy | tempo |
|----------|------|--------|------|--------------|--------|-------|
| TRIOREW128F424EAF0 | Mr. Brightside | The Killers | 2004 | 0.355 | 0.918 | 148.114 |
| TRRIVDJ128F429B0E8 | Wonderwall | Oasis | 2006 | 0.409 | 0.892 | 174.426 |

## 📈 Future Work

- [ ] Analyze user listening patterns
- [ ] Merge user and song data
- [ ] Build genre classification model
- [ ] Create recommendation system
- [ ] Deploy interactive dashboard

## 📄 License

Dataset: [Million Song Dataset Spotify Last.fm](https://www.kaggle.com/datasets/undefinenull/million-song-dataset-spotify-lastfm)  
Code: MIT License

## 📧 Contact

For questions or contributions, please open an issue or submit a pull request.
