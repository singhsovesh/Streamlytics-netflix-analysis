<div align="center">

[![Python](https://img.shields.io/badge/Python_3.10+-e50914?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit_1.x-0084ff?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io)
[![Plotly](https://img.shields.io/badge/Plotly-f5a623?style=for-the-badge&logo=plotly&logoColor=white)](https://plotly.com)
[![Pandas](https://img.shields.io/badge/Pandas_·_NumPy-27c93f?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![License](https://img.shields.io/badge/MIT_License-555555?style=for-the-badge)](LICENSE)
[![Kaggle](https://img.shields.io/badge/Kaggle_Dataset-555555?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/shivamb/netflix-shows)

<br/>

# <span>NETFLIX</span> EDA DASHBOARD

**EXPLORATORY DATA ANALYSIS · INTERACTIVE STREAMLIT APP**

<br/>

A production-grade interactive dashboard that uncovers patterns in Netflix's global content library — spanning **8,800+ titles** across **100+ countries**. Filter by year, genre, country, and content type to watch every chart update in real time.

<br/>

[![Live Demo](https://img.shields.io/badge/▶_Live_Demo-e50914?style=for-the-badge)](https://your-demo-link.com)
[![Star on GitHub](https://img.shields.io/badge/⭐_Star_on_GitHub-f5a623?style=for-the-badge&logo=github&logoColor=white)](https://github.com/your-username/netflix-eda-dashboard)
[![Download Dataset](https://img.shields.io/badge/📥_Download_Dataset-555555?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/shivamb/netflix-shows)

</div>

<br/>

---

## `//` DASHBOARD PREVIEW

<br/>

<div align="center">

<img src="screenshot1.png" alt="Netflix EDA Dashboard - Hero & KPI Preview" width="100%"/>

</div>

<br/>

---

## ✦ FEATURES

<br/>

<div align="center">

<img src="screenshot2.png" alt="Features, Tech Stack & Quick Start" width="100%"/>

</div>

<br/>

<table>
<tr>
<td width="33%" valign="top">

### 📊 5 KPI Cards
Total titles, Movies, TV Shows, Countries, Genres — all reactive to sidebar filters.

</td>
<td width="33%" valign="top">

### 🌍 Interactive World Map
Choropleth map showing production density by country using Plotly's geo engine.

</td>
<td width="33%" valign="top">

### 📈 6 Chart Sections
Content mix, geography, genre, ratings, duration histograms, and release-year trends.

</td>
</tr>
<tr>
<td width="33%" valign="top">

### 🔧 Sidebar Filter System
Filter by content type, year range (slider), genre, and country — all charts update live.

</td>
<td width="33%" valign="top">

### 💡 Auto-Generated Insights
Dynamic insight boxes below every chart that recompute as filters change.

</td>
<td width="33%" valign="top">

### 📋 Raw Data Explorer
Expandable filtered data table at the bottom — 10 key columns, scrollable & searchable.

</td>
</tr>
</table>

<br/>

---

## ⚙ TECH STACK

<br/>

[![Streamlit](https://img.shields.io/badge/streamlit-e50914?style=flat-square&logo=streamlit&logoColor=white)](https://streamlit.io)
[![Plotly](https://img.shields.io/badge/plotly-e50914?style=flat-square&logo=plotly&logoColor=white)](https://plotly.com)
[![Pandas](https://img.shields.io/badge/pandas-444444?style=flat-square&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![NumPy](https://img.shields.io/badge/numpy-444444?style=flat-square&logo=numpy&logoColor=white)](https://numpy.org)
[![Python](https://img.shields.io/badge/python_3.10+-444444?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Kaggle](https://img.shields.io/badge/kaggle_dataset-444444?style=flat-square&logo=kaggle&logoColor=white)](https://kaggle.com)

<br/>

---

## 🚀 QUICK START

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

```
# requirements.txt
streamlit>=1.28.0
pandas>=2.0.0
plotly>=5.18.0
numpy>=1.25.0
```

<br/>

---

## 📁 PROJECT STRUCTURE

```
netflix-eda-dashboard/
├── assets/
│   ├── screenshot1.png         # Dashboard hero & KPI preview
│   ├── screenshot2.png         # Features, tech stack & quick start
│   ├── screenshot3.png         # Project structure & key insights
│   └── screenshot4.png         # Future enhancements & dataset
├── netflix_dashboard.py        # Main Streamlit app
├── netflix_titles.csv          # Dataset (not committed — download from Kaggle)
├── requirements.txt            # Python dependencies
└── README.md                   # This file
```

<br/>

---

## 🔍 KEY INSIGHTS FROM THE DATA

<br/>

<div align="center">

<img src="screenshot3.png" alt="Key Insights & Project Structure" width="100%"/>

</div>

<br/>

> 📽 Netflix is **movie-dominant** — ~70% of the catalogue are Movies vs 30% TV Shows.

> 📅 **2019** was the peak year for content additions, with over **2,100 titles** added in a single year.

> 🇺🇸 The **United States** leads production by a wide margin, followed by India, UK, Canada, and Japan.

> 🎭 **International Movies** and **Dramas** are the top genres — signalling a global-first content strategy.

> 🔞 **TV-MA** is the most frequent content rating — Netflix primarily targets mature adult audiences.

> ⏱ Median movie runtime is **~98 minutes** — closely matching the classic feature-film format.

> 📉 The **2020–2021 dip** in new content directly reflects COVID-19 global production shutdowns.

<br/>

---

## 🚀 FUTURE ENHANCEMENTS

<br/>

<div align="center">

<img src="screenshot4.png" alt="Future Enhancements, Dataset & Footer" width="100%"/>

</div>

<br/>

<table>
<tr>
<td width="33%" valign="top">

### 🔤 NLP on Descriptions
Topic modelling and sentiment analysis on show descriptions using spaCy or BERTopic.

</td>
<td width="33%" valign="top">

### 🕸️ Actor / Director Network
Graph-based analysis of collaborations using NetworkX + PyVis.

</td>
<td width="33%" valign="top">

### 🤖 Recommendation Engine
Content-based filtering using genres, cast, and description embeddings.

</td>
</tr>
<tr>
<td width="33%" valign="top">

### 📉 Forecasting
Time-series models (Prophet / SARIMA) to predict future content additions.

</td>
<td width="33%" valign="top"></td>
<td width="33%" valign="top"></td>
</tr>
</table>

<br/>

---

## 📂 DATASET

The dataset used is the publicly available **Netflix Movies and TV Shows** dataset from [Kaggle (shivamb/netflix-shows)](https://www.kaggle.com/datasets/shivamb/netflix-shows). It contains **8,807 titles** with attributes including title, type, director, cast, country, date added, release year, rating, duration, and genre.

> ⚠️ The file is **not committed** to this repo — download it separately and place it in the project root as `netflix_titles.csv`.

<br/>

---

<div align="center">

Built with ❤️ using **Streamlit** & **Plotly** &nbsp;·&nbsp; Netflix EDA Dashboard &nbsp;·&nbsp; MIT License

<sub>Dataset © Kaggle — for educational and research purposes only.</sub>

<br/>

[![View Code](https://img.shields.io/badge/📄_View_Code-333333?style=flat-square)](https://github.com/your-username/netflix-eda-dashboard)
[![Report Issue](https://img.shields.io/badge/🐛_Report_Issue-333333?style=flat-square)](https://github.com/your-username/netflix-eda-dashboard/issues)

</div>
