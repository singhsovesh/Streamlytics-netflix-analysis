<div align="center">

![Python](https://img.shields.io/badge/Python_3.10+-3776AB?style=flat-square&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit_1.x-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=flat-square&logo=plotly&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Dataset](https://img.shields.io/badge/Dataset-Kaggle-20BEFF?style=flat-square&logo=kaggle&logoColor=white)

# 🎬 Netflix EDA Dashboard

### Exploratory Data Analysis · Interactive Streamlit App

**A production-grade interactive dashboard that uncovers patterns in Netflix's global content library — spanning 8,800+ titles across 100+ countries. Filter by year, genre, country, and content type to watch every chart update in real time.**

[▶ Live Demo](#) · [⭐ Star on GitHub](#) · [📥 Download Dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows)

---

</div>

## 📸 Dashboard Preview

> *Sidebar filters → KPI cards → Charts → Auto-generated insights, all reactive in real time.*

```
┌──────────────────────────────────────────────────────────────────┐
│  localhost:8501 — Netflix EDA Dashboard                          │
├──────────────┬───────────────────────────────────────────────────┤
│ 🎬 NETFLIX   │  8,807    6,131     2,676     112       42        │
│  EDA         │  Total    Movies   TV Shows  Countries  Genres    │
│              │                                                    │
│ Content Type │  ┌─────────────┐  ┌──────────────────────────┐   │
│ ☑ Movie      │  │Movies vs    │  │  Content Added by Year   │   │
│ ☑ TV Show    │  │TV Shows     │  │  ████████████████        │   │
│              │  │  ●●●        │  │  ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓       │   │
│ Year Added   │  └─────────────┘  └──────────────────────────┘   │
│ ══════●═══   │                                                    │
│              │  💡 Netflix is movie-dominant at 69.6% of the     │
│ Genre        │     catalogue. Peak year: 2019 — 2,153 titles.   │
│ Country      │                                                    │
└──────────────┴───────────────────────────────────────────────────┘
```

---

## ✦ Features

| # | Feature | Description |
|---|---------|-------------|
| 📊 | **5 KPI Cards** | Total titles, Movies, TV Shows, Countries, Genres — all reactive to sidebar filters |
| 🌍 | **Interactive World Map** | Choropleth map showing production density by country using Plotly's geo engine |
| 📈 | **6 Chart Sections** | Content mix, geography, genre, ratings, duration histograms, and release-year trends |
| 🔧 | **Sidebar Filter System** | Filter by content type, year range (slider), genre, and country — all charts update live |
| 💡 | **Auto-Generated Insights** | Dynamic insight boxes below every chart that recompute as filters change |
| 📋 | **Raw Data Explorer** | Expandable filtered data table at the bottom — 10 key columns, scrollable & searchable |

---

## ⚙️ Tech Stack

`streamlit` &nbsp; `plotly` &nbsp; `pandas` &nbsp; `numpy` &nbsp; `python 3.10+` &nbsp; `kaggle dataset`

---

## 🚀 Quick Start

Clone the repo, install dependencies, drop in the dataset, and run:

```bash
# 1. Clone the repository
git clone https://github.com/your-username/netflix-eda-dashboard.git
cd netflix-eda-dashboard

# 2. Create a virtual environment (optional but recommended)
python -m venv venv && source venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Add the dataset — download netflix_titles.csv from Kaggle
#    and place it in the project root folder

# 5. Launch the dashboard
streamlit run netflix_dashboard.py
```

**`requirements.txt`**
```
streamlit>=1.28.0
pandas>=2.0.0
plotly>=5.18.0
numpy>=1.25.0
```

---

## 📁 Project Structure

```
netflix-eda-dashboard/
├── netflix_dashboard.py    # Main Streamlit app
├── netflix_titles.csv      # Dataset (not committed — download from Kaggle)
├── requirements.txt        # Python dependencies
└── README.md               # This file
```

---

## 🔍 Key Insights from the Data

> Findings derived from the full 8,807-title dataset before any filtering.

- 📽 Netflix is **movie-dominant** — ~70% of the catalogue are Movies vs 30% TV Shows.
- 📅 **2019** was the peak year for content additions, with over **2,100 titles** added in a single year.
- 🇺🇸 The **United States** leads production by a wide margin, followed by India, UK, Canada, and Japan.
- 🎭 **International Movies** and **Dramas** are the top genres — signalling a global-first content strategy.
- 🔞 **TV-MA** is the most frequent content rating — Netflix primarily targets mature adult audiences.
- ⏱ Median movie runtime is **~98 minutes** — closely matching the classic feature-film format.
- 📉 The **2020–2021 dip** in new content directly reflects COVID-19 global production shutdowns.

---

## 🚀 Future Enhancements

| Enhancement | Description |
|-------------|-------------|
| 🔤 **NLP on Descriptions** | Topic modelling and sentiment analysis on show descriptions using spaCy or BERTopic |
| 🕸️ **Actor / Director Network** | Graph-based analysis of collaborations using NetworkX + PyVis |
| 🤖 **Recommendation Engine** | Content-based filtering using genres, cast, and description embeddings |
| 📉 **Forecasting** | Time-series models (Prophet / SARIMA) to predict future content additions |

---

## 📂 Dataset

The dataset used is the publicly available **Netflix Movies and TV Shows** dataset from [Kaggle (shivamb/netflix-shows)](https://www.kaggle.com/datasets/shivamb/netflix-shows). It contains **8,807 titles** with attributes including title, type, director, cast, country, date added, release year, rating, duration, and genre.

> ⚠️ The CSV file is **not committed** to this repo. Download it separately from Kaggle and place it in the project root as `netflix_titles.csv`.

---

<div align="center">

Built with ❤️ using Streamlit & Plotly &nbsp;·&nbsp; Netflix EDA Dashboard &nbsp;·&nbsp; MIT License

*Dataset © Kaggle — for educational and research purposes only.*

</div>
