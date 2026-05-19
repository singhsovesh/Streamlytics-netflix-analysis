[netflix_dashboard_readme.html](https://github.com/user-attachments/files/28024827/netflix_dashboard_readme.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Netflix EDA Dashboard — README</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=JetBrains+Mono:wght@400;500&family=Figtree:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --red: #e50914;
    --red-dim: #9b0a0f;
    --red-glow: rgba(229,9,20,0.18);
    --bg: #0d0d12;
    --bg2: #13131c;
    --bg3: #1a1a26;
    --border: rgba(255,255,255,0.07);
    --border-strong: rgba(255,255,255,0.13);
    --text: #e4e4e4;
    --muted: #888;
    --mono: 'JetBrains Mono', monospace;
    --sans: 'Figtree', sans-serif;
    --display: 'Bebas Neue', sans-serif;
  }

  body {
    font-family: var(--sans);
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    padding: 0;
  }

  /* ─── HEADER ─── */
  .hero {
    background: linear-gradient(170deg, #0d0d12 0%, #180008 60%, #0d0d12 100%);
    border-bottom: 1px solid var(--border);
    padding: 56px 48px 44px;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    top: -60px; left: -60px;
    width: 320px; height: 320px;
    background: radial-gradient(circle, rgba(229,9,20,0.12) 0%, transparent 70%);
    pointer-events: none;
  }
  .hero-inner { max-width: 780px; position: relative; }

  .badge-row { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 24px; }
  .badge {
    font-family: var(--mono);
    font-size: 11px;
    padding: 4px 10px;
    border-radius: 4px;
    border: 1px solid;
    letter-spacing: 0.5px;
  }
  .badge-red    { background: rgba(229,9,20,0.12); border-color: rgba(229,9,20,0.4); color: #ff6b6b; }
  .badge-blue   { background: rgba(0,132,255,0.1);  border-color: rgba(0,132,255,0.35); color: #5fb5ff; }
  .badge-green  { background: rgba(34,197,94,0.1);  border-color: rgba(34,197,94,0.35); color: #6ee7a0; }
  .badge-orange { background: rgba(249,115,22,0.1); border-color: rgba(249,115,22,0.35); color: #fba96c; }
  .badge-gray   { background: rgba(255,255,255,0.05); border-color: var(--border-strong); color: #aaa; }

  .hero-title {
    font-family: var(--display);
    font-size: clamp(40px, 7vw, 72px);
    letter-spacing: 5px;
    line-height: 1;
    color: #fff;
    margin-bottom: 6px;
  }
  .hero-title span { color: var(--red); }

  .hero-sub {
    font-size: 13px;
    text-transform: uppercase;
    letter-spacing: 4px;
    color: var(--muted);
    margin-bottom: 20px;
  }

  .hero-desc {
    font-size: 15px;
    color: #bbb;
    line-height: 1.75;
    max-width: 640px;
    margin-bottom: 28px;
  }

  .btn-row { display: flex; gap: 12px; flex-wrap: wrap; }
  .btn {
    display: inline-flex; align-items: center; gap: 7px;
    font-family: var(--sans);
    font-size: 13px; font-weight: 500;
    padding: 9px 18px;
    border-radius: 6px;
    border: 1px solid;
    text-decoration: none;
    cursor: pointer;
    transition: all 0.2s;
  }
  .btn-primary { background: var(--red); border-color: var(--red); color: #fff; }
  .btn-primary:hover { background: #c0070f; }
  .btn-ghost { background: transparent; border-color: var(--border-strong); color: #ccc; }
  .btn-ghost:hover { background: var(--bg3); border-color: rgba(255,255,255,0.25); }

  /* ─── PREVIEW MOCKUP ─── */
  .preview-wrap {
    padding: 40px 48px;
    background: var(--bg2);
    border-bottom: 1px solid var(--border);
  }
  .preview-label {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 14px;
  }
  .mockup {
    border: 1px solid var(--border-strong);
    border-radius: 10px;
    overflow: hidden;
    background: #0a0a0f;
  }
  .mockup-bar {
    background: #111118;
    padding: 10px 16px;
    display: flex; align-items: center; gap: 8px;
    border-bottom: 1px solid var(--border);
  }
  .dot { width: 11px; height: 11px; border-radius: 50%; }
  .dot-r { background: #e50914; }
  .dot-y { background: #f5a623; }
  .dot-g { background: #27c93f; }
  .mockup-url {
    flex: 1;
    background: #1a1a24;
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 4px 10px;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    margin-left: 8px;
  }
  .mockup-body {
    display: grid;
    grid-template-columns: 200px 1fr;
    min-height: 340px;
  }
  .mock-sidebar {
    background: #111118;
    border-right: 1px solid var(--border);
    padding: 20px 14px;
  }
  .mock-sidebar-title {
    font-family: var(--display);
    font-size: 17px;
    letter-spacing: 2px;
    color: var(--red);
    margin-bottom: 16px;
  }
  .mock-filter-label {
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    color: var(--muted);
    margin-bottom: 6px;
  }
  .mock-filter-box {
    background: #1a1a26;
    border: 1px solid var(--border);
    border-radius: 5px;
    padding: 6px 8px;
    font-size: 11px;
    color: #888;
    margin-bottom: 12px;
  }
  .mock-slider { height: 3px; background: #2a2a38; border-radius: 2px; margin-bottom: 12px; position: relative; }
  .mock-slider-fill { height: 100%; width: 70%; background: var(--red); border-radius: 2px; }
  .mock-slider-thumb { width: 10px; height: 10px; background: #fff; border-radius: 50%; position: absolute; top: -3.5px; left: 70%; transform: translateX(-50%); }
  .mock-main { padding: 18px 20px; overflow: hidden; }
  .mock-kpi-row { display: grid; grid-template-columns: repeat(5, 1fr); gap: 8px; margin-bottom: 16px; }
  .mock-kpi {
    background: #13131c;
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 10px 8px;
    text-align: center;
  }
  .mock-kpi-num { font-family: var(--display); font-size: 18px; color: var(--red); line-height: 1; }
  .mock-kpi-lbl { font-size: 8px; text-transform: uppercase; letter-spacing: 1px; color: var(--muted); margin-top: 2px; }
  .mock-charts { display: grid; grid-template-columns: 1fr 2fr; gap: 10px; margin-bottom: 10px; }
  .mock-chart-box {
    background: #13131c;
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 10px;
    height: 110px;
    position: relative;
    overflow: hidden;
  }
  .mock-chart-title { font-size: 9px; text-transform: uppercase; letter-spacing: 1px; color: var(--muted); margin-bottom: 6px; }
  /* Fake donut */
  .fake-donut {
    width: 70px; height: 70px;
    border-radius: 50%;
    background: conic-gradient(var(--red) 0% 63%, #0084ff 63% 100%);
    margin: auto;
    position: relative;
  }
  .fake-donut::after {
    content: '';
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%,-50%);
    width: 40px; height: 40px;
    background: #13131c;
    border-radius: 50%;
  }
  /* Fake stacked bar */
  .fake-bars { display: flex; align-items: flex-end; gap: 3px; height: 70px; padding-top: 6px; }
  .fake-bar-grp { display: flex; flex-direction: column; align-items: center; flex: 1; gap: 1px; }
  .bar-seg { width: 100%; border-radius: 1px 1px 0 0; }

  /* ─── BODY ─── */
  .body-wrap { max-width: 900px; margin: 0 auto; padding: 48px 48px 64px; }

  /* Section */
  .section { margin-bottom: 44px; }
  .section-title {
    font-family: var(--display);
    font-size: 20px;
    letter-spacing: 3px;
    color: #ccc;
    border-left: 3px solid var(--red);
    padding-left: 12px;
    margin-bottom: 16px;
  }

  /* Features grid */
  .features-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 12px; }
  .feature-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px 18px;
    transition: border-color 0.2s;
  }
  .feature-card:hover { border-color: rgba(229,9,20,0.4); }
  .feature-icon { font-size: 20px; margin-bottom: 8px; }
  .feature-title { font-size: 13px; font-weight: 600; color: #ddd; margin-bottom: 4px; }
  .feature-desc { font-size: 12px; color: var(--muted); line-height: 1.6; }

  /* Tech stack */
  .tech-row { display: flex; flex-wrap: wrap; gap: 8px; }
  .tech-pill {
    font-family: var(--mono);
    font-size: 12px;
    padding: 5px 12px;
    border-radius: 20px;
    background: var(--bg3);
    border: 1px solid var(--border-strong);
    color: #ccc;
  }
  .tech-pill.main { border-color: rgba(229,9,20,0.45); color: #ff8a8a; background: rgba(229,9,20,0.08); }

  /* Code block */
  .code-block {
    background: #0d0d12;
    border: 1px solid var(--border-strong);
    border-radius: 8px;
    overflow: hidden;
    margin: 12px 0;
  }
  .code-header {
    background: var(--bg3);
    padding: 8px 14px;
    display: flex; align-items: center; gap: 8px;
    border-bottom: 1px solid var(--border);
  }
  .code-lang { font-family: var(--mono); font-size: 11px; color: var(--muted); }
  .code-copy { margin-left: auto; font-size: 11px; color: var(--muted); cursor: pointer; }
  .code-body {
    padding: 16px 18px;
    font-family: var(--mono);
    font-size: 12.5px;
    line-height: 1.8;
    color: #d4d4d4;
    overflow-x: auto;
  }
  .code-comment { color: #6a9955; }
  .code-kw  { color: #569cd6; }
  .code-str { color: #ce9178; }
  .code-fn  { color: #dcdcaa; }
  .code-var { color: #9cdcfe; }

  /* File tree */
  .file-tree {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px 20px;
    font-family: var(--mono);
    font-size: 12.5px;
    line-height: 2;
    color: #bbb;
  }
  .tree-dir { color: #5fb5ff; }
  .tree-file { color: #ccc; }
  .tree-dim { color: var(--muted); }

  /* Screenshots grid */
  .screens-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  .screen-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
  }
  .screen-body { padding: 28px 24px; min-height: 120px; display: flex; align-items: center; justify-content: center; position: relative; overflow: hidden; }
  .screen-label { padding: 8px 14px; font-size: 11px; color: var(--muted); border-top: 1px solid var(--border); font-family: var(--mono); }

  /* Mini chart fakes */
  .mini-bar-chart { display: flex; align-items: flex-end; gap: 4px; height: 60px; }
  .mini-bar { border-radius: 2px 2px 0 0; }
  .mini-world { width: 100%; height: 70px; background: #111118; border-radius: 4px; position: relative; overflow: hidden; }

  /* Insights */
  .insight-list { list-style: none; display: flex; flex-direction: column; gap: 8px; }
  .insight-item {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-left: 3px solid var(--red);
    border-radius: 0 6px 6px 0;
    padding: 10px 14px;
    font-size: 13px;
    color: #bbb;
    line-height: 1.6;
  }
  .insight-item strong { color: #ff8a8a; }

  /* Footer */
  .footer {
    border-top: 1px solid var(--border);
    padding: 28px 48px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
  }
  .footer-left { font-size: 12px; color: var(--muted); line-height: 1.7; }
  .footer-right { display: flex; gap: 8px; }

  hr.divider { border: none; border-top: 1px solid var(--border); margin: 0 0 32px; }
</style>
</head>
<body>

<!-- ═══════ HERO ═══════ -->
<div class="hero">
  <div class="hero-inner">
    <div class="badge-row">
      <span class="badge badge-red">Python 3.10+</span>
      <span class="badge badge-blue">Streamlit 1.x</span>
      <span class="badge badge-blue">Plotly</span>
      <span class="badge badge-orange">Pandas · NumPy</span>
      <span class="badge badge-green">MIT License</span>
      <span class="badge badge-gray">Kaggle Dataset</span>
    </div>
    <h1 class="hero-title"><span>Netflix</span> EDA Dashboard</h1>
    <p class="hero-sub">Exploratory Data Analysis · Interactive Streamlit App</p>
    <p class="hero-desc">
      A production-grade interactive dashboard that uncovers patterns in Netflix's global content library — spanning 8,800+ titles across 100+ countries. Filter by year, genre, country, and content type to watch every chart update in real time.
    </p>
    <div class="btn-row">
      <a class="btn btn-primary" href="#">▶ &nbsp;Live Demo</a>
      <a class="btn btn-ghost" href="#">⭐ &nbsp;Star on GitHub</a>
      <a class="btn btn-ghost" href="#">📥 &nbsp;Download Dataset</a>
    </div>
  </div>
</div>

<!-- ═══════ BROWSER MOCKUP ═══════ -->
<div class="preview-wrap">
  <p class="preview-label">// Dashboard Preview</p>
  <div class="mockup">
    <div class="mockup-bar">
      <div class="dot dot-r"></div>
      <div class="dot dot-y"></div>
      <div class="dot dot-g"></div>
      <div class="mockup-url">localhost:8501 — Netflix EDA Dashboard</div>
    </div>
    <div class="mockup-body">
      <div class="mock-sidebar">
        <div class="mock-sidebar-title">🎬 NETFLIX EDA</div>
        <div class="mock-filter-label">Content Type</div>
        <div class="mock-filter-box">☑ Movie &nbsp; ☑ TV Show</div>
        <div class="mock-filter-label">Year Added</div>
        <div class="mock-slider"><div class="mock-slider-fill"></div><div class="mock-slider-thumb"></div></div>
        <div class="mock-filter-label">Genre</div>
        <div class="mock-filter-box" style="color:#555">Select genres...</div>
        <div class="mock-filter-label">Country</div>
        <div class="mock-filter-box" style="color:#555">Select countries...</div>
      </div>
      <div class="mock-main">
        <div style="font-family:'Bebas Neue',sans-serif;font-size:22px;color:#e50914;letter-spacing:3px;margin-bottom:2px;">NETFLIX</div>
        <div style="font-size:8px;text-transform:uppercase;letter-spacing:3px;color:#444;margin-bottom:12px;">Exploratory Data Analysis — Interactive Dashboard</div>
        <div class="mock-kpi-row">
          <div class="mock-kpi"><div class="mock-kpi-num">8,807</div><div class="mock-kpi-lbl">Total</div></div>
          <div class="mock-kpi"><div class="mock-kpi-num">6,131</div><div class="mock-kpi-lbl">Movies</div></div>
          <div class="mock-kpi"><div class="mock-kpi-num">2,676</div><div class="mock-kpi-lbl">TV Shows</div></div>
          <div class="mock-kpi"><div class="mock-kpi-num">112</div><div class="mock-kpi-lbl">Countries</div></div>
          <div class="mock-kpi"><div class="mock-kpi-num">42</div><div class="mock-kpi-lbl">Genres</div></div>
        </div>
        <div class="mock-charts">
          <div class="mock-chart-box">
            <div class="mock-chart-title">Movies vs TV Shows</div>
            <div class="fake-donut"></div>
          </div>
          <div class="mock-chart-box">
            <div class="mock-chart-title">Content Added by Year</div>
            <div class="fake-bars">
              <div class="fake-bar-grp"><div class="bar-seg" style="height:12px;background:#e50914;"></div><div class="bar-seg" style="height:5px;background:#0084ff;"></div></div>
              <div class="fake-bar-grp"><div class="bar-seg" style="height:18px;background:#e50914;"></div><div class="bar-seg" style="height:7px;background:#0084ff;"></div></div>
              <div class="fake-bar-grp"><div class="bar-seg" style="height:25px;background:#e50914;"></div><div class="bar-seg" style="height:10px;background:#0084ff;"></div></div>
              <div class="fake-bar-grp"><div class="bar-seg" style="height:38px;background:#e50914;"></div><div class="bar-seg" style="height:18px;background:#0084ff;"></div></div>
              <div class="fake-bar-grp"><div class="bar-seg" style="height:55px;background:#e50914;"></div><div class="bar-seg" style="height:28px;background:#0084ff;"></div></div>
              <div class="fake-bar-grp"><div class="bar-seg" style="height:42px;background:#e50914;"></div><div class="bar-seg" style="height:22px;background:#0084ff;"></div></div>
              <div class="fake-bar-grp"><div class="bar-seg" style="height:30px;background:#e50914;"></div><div class="bar-seg" style="height:16px;background:#0084ff;"></div></div>
            </div>
          </div>
        </div>
        <div style="background:#13131c;border:1px solid rgba(255,255,255,0.07);border-left:3px solid #e50914;border-radius:0 4px 4px 0;padding:7px 10px;font-size:9px;color:#888;line-height:1.6;">
          💡 Netflix is <span style="color:#ff6b6b">movie-dominant</span> at 69.6% of the catalogue. Peak year: <span style="color:#ff6b6b">2019</span> with 2,153 titles added.
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ═══════ MAIN BODY ═══════ -->
<div class="body-wrap">

  <!-- FEATURES -->
  <div class="section">
    <div class="section-title">✦ FEATURES</div>
    <div class="features-grid">
      <div class="feature-card">
        <div class="feature-icon">📊</div>
        <div class="feature-title">5 KPI Cards</div>
        <div class="feature-desc">Total titles, Movies, TV Shows, Countries, Genres — all reactive to sidebar filters.</div>
      </div>
      <div class="feature-card">
        <div class="feature-icon">🌍</div>
        <div class="feature-title">Interactive World Map</div>
        <div class="feature-desc">Choropleth map showing production density by country using Plotly's geo engine.</div>
      </div>
      <div class="feature-card">
        <div class="feature-icon">📈</div>
        <div class="feature-title">6 Chart Sections</div>
        <div class="feature-desc">Content mix, geography, genre, ratings, duration histograms, and release-year trends.</div>
      </div>
      <div class="feature-card">
        <div class="feature-icon">🔧</div>
        <div class="feature-title">Sidebar Filter System</div>
        <div class="feature-desc">Filter by content type, year range (slider), genre, and country — all charts update live.</div>
      </div>
      <div class="feature-card">
        <div class="feature-icon">💡</div>
        <div class="feature-title">Auto-Generated Insights</div>
        <div class="feature-desc">Dynamic insight boxes below every chart that recompute as filters change.</div>
      </div>
      <div class="feature-card">
        <div class="feature-icon">📋</div>
        <div class="feature-title">Raw Data Explorer</div>
        <div class="feature-desc">Expandable filtered data table at the bottom — 10 key columns, scrollable & searchable.</div>
      </div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section">
    <div class="section-title">⚙ TECH STACK</div>
    <div class="tech-row">
      <span class="tech-pill main">streamlit</span>
      <span class="tech-pill main">plotly</span>
      <span class="tech-pill">pandas</span>
      <span class="tech-pill">numpy</span>
      <span class="tech-pill">python 3.10+</span>
      <span class="tech-pill">kaggle dataset</span>
    </div>
  </div>

  <!-- SETUP -->
  <div class="section">
    <div class="section-title">🚀 QUICK START</div>
    <p style="font-size:13px;color:var(--muted);margin-bottom:12px;">Clone the repo, install dependencies, drop in the dataset, and run:</p>

    <div class="code-block">
      <div class="code-header">
        <span class="code-lang">bash</span>
        <span class="code-copy">copy</span>
      </div>
      <div class="code-body">
<span class="code-comment"># 1. Clone the repository</span>
<span class="code-kw">git</span> <span class="code-fn">clone</span> <span class="code-str">https://github.com/your-username/netflix-eda-dashboard.git</span>
<span class="code-kw">cd</span> netflix-eda-dashboard

<span class="code-comment"># 2. Create a virtual environment (optional but recommended)</span>
<span class="code-kw">python</span> -m venv venv &amp;&amp; source venv/bin/activate

<span class="code-comment"># 3. Install dependencies</span>
<span class="code-kw">pip</span> install -r requirements.txt

<span class="code-comment"># 4. Add the dataset — download netflix_titles.csv from Kaggle</span>
<span class="code-comment">#    and place it in the project root folder</span>

<span class="code-comment"># 5. Launch the dashboard</span>
<span class="code-kw">streamlit</span> run netflix_dashboard.py
      </div>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="code-lang">requirements.txt</span>
      </div>
      <div class="code-body">
<span class="code-var">streamlit</span><span class="code-str">>=1.28.0</span>
<span class="code-var">pandas</span><span class="code-str">>=2.0.0</span>
<span class="code-var">plotly</span><span class="code-str">>=5.18.0</span>
<span class="code-var">numpy</span><span class="code-str">>=1.25.0</span>
      </div>
    </div>
  </div>

  <!-- FILE STRUCTURE -->
  <div class="section">
    <div class="section-title">📁 PROJECT STRUCTURE</div>
    <div class="file-tree">
<span class="tree-dir">netflix-eda-dashboard/</span>
├── <span class="tree-file">netflix_dashboard.py</span>    <span class="tree-dim"># Main Streamlit app</span>
├── <span class="tree-file">netflix_titles.csv</span>      <span class="tree-dim"># Dataset (not committed — download from Kaggle)</span>
├── <span class="tree-file">requirements.txt</span>        <span class="tree-dim"># Python dependencies</span>
└── <span class="tree-file">README.md</span>               <span class="tree-dim"># This file</span>
    </div>
  </div>

  <!-- KEY INSIGHTS -->
  <div class="section">
    <div class="section-title">🔍 KEY INSIGHTS FROM THE DATA</div>
    <ul class="insight-list">
      <li class="insight-item">📽 Netflix is <strong>movie-dominant</strong> — ~70% of the catalogue are Movies vs 30% TV Shows.</li>
      <li class="insight-item">📅 <strong>2019</strong> was the peak year for content additions, with over 2,100 titles added in a single year.</li>
      <li class="insight-item">🇺🇸 The <strong>United States</strong> leads production by a wide margin, followed by India, UK, Canada, and Japan.</li>
      <li class="insight-item">🎭 <strong>International Movies</strong> and <strong>Dramas</strong> are the top genres — signalling a global-first content strategy.</li>
      <li class="insight-item">🔞 <strong>TV-MA</strong> is the most frequent content rating — Netflix primarily targets mature adult audiences.</li>
      <li class="insight-item">⏱ Median movie runtime is <strong>~98 minutes</strong> — closely matching the classic feature-film format.</li>
      <li class="insight-item">📉 The <strong>2020–2021 dip</strong> in new content directly reflects COVID-19 global production shutdowns.</li>
    </ul>
  </div>

  <!-- FUTURE IDEAS -->
  <div class="section">
    <div class="section-title">🚀 FUTURE ENHANCEMENTS</div>
    <div class="features-grid">
      <div class="feature-card">
        <div class="feature-title">🔤 NLP on Descriptions</div>
        <div class="feature-desc">Topic modelling and sentiment analysis on show descriptions using spaCy or BERTopic.</div>
      </div>
      <div class="feature-card">
        <div class="feature-title">🕸️ Actor / Director Network</div>
        <div class="feature-desc">Graph-based analysis of collaborations using NetworkX + PyVis.</div>
      </div>
      <div class="feature-card">
        <div class="feature-title">🤖 Recommendation Engine</div>
        <div class="feature-desc">Content-based filtering using genres, cast, and description embeddings.</div>
      </div>
      <div class="feature-card">
        <div class="feature-title">📉 Forecasting</div>
        <div class="feature-desc">Time-series models (Prophet / SARIMA) to predict future content additions.</div>
      </div>
    </div>
  </div>

  <hr class="divider">

  <!-- DATASET NOTE -->
  <div class="section">
    <div class="section-title">📂 DATASET</div>
    <p style="font-size:13.5px;color:#aaa;line-height:1.8;">
      The dataset used is the publicly available <strong style="color:#ddd;">Netflix Movies and TV Shows</strong> dataset from
      <a href="https://www.kaggle.com/datasets/shivamb/netflix-shows" style="color:#5fb5ff;text-decoration:none;">Kaggle (shivamb/netflix-shows)</a>.
      It contains <strong style="color:#ddd;">8,807 titles</strong> with attributes including title, type, director, cast, country, date added, release year, rating, duration, and genre. The file is not committed to this repo — download it separately and place it in the project root as <code style="background:var(--bg3);padding:2px 6px;border-radius:4px;font-family:var(--mono);font-size:12px;">netflix_titles.csv</code>.
    </p>
  </div>

</div>

<!-- ═══════ FOOTER ═══════ -->
<div class="footer">
  <div class="footer-left">
    Built with <strong style="color:#e50914;">❤</strong> using Streamlit &amp; Plotly &nbsp;·&nbsp;
    Netflix EDA Dashboard &nbsp;·&nbsp; MIT License<br>
    <span style="font-size:11px;color:#555;">Dataset © Kaggle — for educational and research purposes only.</span>
  </div>
  <div class="footer-right">
    <a class="btn btn-ghost" href="#" style="font-size:12px;padding:7px 14px;">📄 View Code</a>
    <a class="btn btn-ghost" href="#" style="font-size:12px;padding:7px 14px;">🐛 Report Issue</a>
  </div>
</div>

</body>
</html>
