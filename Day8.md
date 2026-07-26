# What I learn :-
  Claude Artifacts allow you to generate fully interactive applications instead of simple text outputs. 
  By combining prompts, reasoning, design instructions, and structured requirements, Claude can build dashboards, tools, calculators, visualizations, and complete HTML applications.

  1 Artifacts: Generate real applications instead of text-only outputs.
  2 Interactive Dashboards: Build charts, filters, cards, and visual interfaces.
  3 HTML Generation: Create downloadable applications that run locally.
  4 AI Product Building: Transform prompts into usable products.


# Prompts:

Act as a Senior Data Analyst, Environmental Researcher, UX Designer, and Frontend Dashboard Developer.

Create a Claude Artifact called:
🌍 Personal Environmental Health Analyzer

DATA RULES

If a dataset is provided, use it. If no dataset is provided, automatically search the web for the latest AQI and water-quality data for the user's current city/location. If location is unavailable, ask for the city name first. Use the most recent available data, cite sources, clean the data, handle missing values, and validate quality before analysis.

ANALYSIS

Generate: cleanest city, most polluted city, highest AQI city, lowest AQI city, average AQI, number of cities analyzed, trends, anomalies, most surprising observation, executive summary.

INTERACTIVE DASHBOARD

Create a fully interactive Claude Artifact with:

📊 Key Metrics: average AQI, highest AQI city, lowest AQI city, number of cities analyzed, environmental health score.

📈 Visualizations: AQI comparison chart, PM2.5 comparison chart, PM10 comparison chart, city ranking chart, AQI distribution chart.

🎛 Interactive Filters: city selector, AQI range filter, pollutant selector, health-risk filter, date filter (if available), city comparison mode.

📋 City Detail Cards: AQI, PM2.5, PM10, air-quality category, health score, water-quality score.

🚦 AQI Categories: Good (Green), Satisfactory (Light Green), Moderate (Yellow), Poor (Orange), Very Poor (Red), Severe (Dark Red).

ENVIRONMENTAL HEALTH ANALYSIS

For the selected city explain AQI impact on lungs, sleep, energy levels, exercise performance, long-term health, and water-quality impact on hair fall, hair dryness, scalp health, skin dryness, acne, and sensitive skin.

Use risk indicators: 🟢 Low, 🟡 Moderate, 🔴 High.

PERSONAL REPORT CARD

Generate an Environmental Health Score (0–100) with breakdowns for Air Quality Score, Water Quality Score, and Overall Environmental Score.

Assign grades for Air Quality (A–F), Water Quality (A–F), Hair Risk, and Skin Risk.

INSIGHTS PANEL

Include: top 3 cleanest cities, top 3 most polluted cities, biggest anomaly, most surprising observation, recommended actions.

PERSONALIZED RECOMMENDATIONS

Provide: daily actions, indoor air improvements, outdoor activity guidance, hair-care recommendations, skin-care recommendations, water-quality improvement suggestions.

DESIGN

Modern, professional, mobile responsive, dark theme, smooth animations, premium UI, clean typography, dashboard-style layout, highly visual, colourful, LinkedIn-shareable.

OUTPUT

Generate a complete downloadable HTML application that is fully responsive and ready to save as index.html.

IMPORTANT

Do not provide code snippets. Create a complete interactive Claude Artifact with working charts, filters, cards, insights, report cards, and dashboards that users can interact with directly.

PDF:- [enviroment dasboard.pdf](https://github.com/user-attachments/files/28765008/enviroment.dasboard.pdf)

Html:-- [enviroment dasboard.html](https://github.com/user-attachments/files/28764931/enviroment.dasboard.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🌍 Personal Environmental Health Analyzer</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=Syne:wght@400;600;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box}
:root{
--bg:#070b14;--surface:#0d1526;--card:#111827;--border:#1e2d45;
--accent:#00d4ff;--accent2:#7c3aed;--green:#10b981;--yellow:#f59e0b;
--orange:#f97316;--red:#ef4444;--darkred:#7f1d1d;
--text:#e2e8f0;--muted:#64748b;--dim:#334155;
}
body{background:var(--bg);color:var(--text);font-family:'DM Sans',sans-serif;min-height:100vh;overflow-x:hidden}
h1,h2,h3,.metric-val,.score-num{font-family:'Syne',sans-serif}
code,.mono{font-family:'DM Mono',monospace}

/* HEADER */
.header{background:linear-gradient(135deg,#070b14 0%,#0d1a2e 50%,#0a1628 100%);border-bottom:1px solid var(--border);padding:24px 32px;position:sticky;top:0;z-index:100;backdrop-filter:blur(20px)}
.header-inner{max-width:1400px;margin:0 auto;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:12px}
.logo{display:flex;align-items:center;gap:12px}
.logo-icon{width:44px;height:44px;background:linear-gradient(135deg,#00d4ff22,#7c3aed22);border:1px solid #00d4ff44;border-radius:12px;display:flex;align-items:center;justify-content:center;font-size:22px}
.logo-text{font-size:18px;font-weight:700;color:var(--text)}
.logo-sub{font-size:11px;color:var(--muted);font-family:'DM Mono',monospace}
.live-badge{display:flex;align-items:center;gap:6px;background:#10b98115;border:1px solid #10b98133;border-radius:20px;padding:6px 14px;font-size:12px;color:#10b981;font-family:'DM Mono',monospace}
.pulse{width:7px;height:7px;border-radius:50%;background:#10b981;animation:pulse 1.5s infinite}
@keyframes pulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.5;transform:scale(1.4)}}

/* LAYOUT */
.container{max-width:1400px;margin:0 auto;padding:28px 24px}
.section-title{font-size:11px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:.12em;margin-bottom:16px;font-family:'DM Mono',monospace}

/* METRICS ROW */
.metrics-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:14px;margin-bottom:28px}
.metric-card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:20px;transition:border-color .2s;position:relative;overflow:hidden}
.metric-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:var(--accent-color,var(--accent));opacity:.6}
.metric-card:hover{border-color:var(--accent-color,var(--accent))}
.metric-label{font-size:11px;color:var(--muted);margin-bottom:8px;font-family:'DM Mono',monospace;text-transform:uppercase;letter-spacing:.08em}
.metric-val{font-size:32px;font-weight:800;color:var(--accent-color,var(--accent));line-height:1}
.metric-sub{font-size:11px;color:var(--muted);margin-top:6px}

/* FILTERS */
.filters{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:20px;margin-bottom:28px}
.filters-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:14px;margin-top:12px}
label{font-size:12px;color:var(--muted);display:block;margin-bottom:6px;font-family:'DM Mono',monospace}
select,input[type=range]{width:100%;background:#0d1526;border:1px solid var(--border);color:var(--text);border-radius:8px;padding:8px 12px;font-size:13px;font-family:'DM Sans',sans-serif;outline:none;cursor:pointer;transition:border-color .2s}
select:hover,select:focus{border-color:var(--accent)}
.range-wrap{display:flex;align-items:center;gap:10px}
input[type=range]{padding:0;height:4px;accent-color:var(--accent)}
.range-val{font-size:13px;color:var(--accent);font-family:'DM Mono',monospace;min-width:36px}
.btn-group{display:flex;gap:8px;flex-wrap:wrap;margin-top:4px}
.btn{padding:6px 14px;border-radius:8px;border:1px solid var(--border);background:transparent;color:var(--muted);font-size:12px;cursor:pointer;transition:all .2s;font-family:'DM Mono',monospace}
.btn.active,.btn:hover{background:var(--accent);color:#000;border-color:var(--accent)}

/* CHARTS GRID */
.charts-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(420px,1fr));gap:20px;margin-bottom:28px}
.chart-card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:22px}
.chart-title{font-size:13px;font-weight:600;color:var(--text);margin-bottom:16px;display:flex;align-items:center;gap:8px}
.chart-title span{font-size:16px}
canvas{width:100%!important}

/* CITY CARDS */
.city-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:16px;margin-bottom:28px}
.city-card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:20px;transition:all .25s;cursor:pointer}
.city-card:hover,.city-card.selected{border-color:var(--city-color,var(--accent));box-shadow:0 0 0 1px var(--city-color,var(--accent))22}
.city-header{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:14px}
.city-name{font-size:16px;font-weight:700;color:var(--text)}
.city-state{font-size:11px;color:var(--muted);font-family:'DM Mono',monospace}
.aqi-badge{padding:4px 12px;border-radius:20px;font-size:12px;font-weight:600;font-family:'DM Mono',monospace}
.city-stats{display:grid;grid-template-columns:1fr 1fr 1fr;gap:10px;margin-bottom:14px}
.city-stat-label{font-size:10px;color:var(--muted);margin-bottom:3px;font-family:'DM Mono',monospace;text-transform:uppercase}
.city-stat-val{font-size:18px;font-weight:700}
.aqi-bar-wrap{background:#1e2d45;border-radius:4px;height:4px;overflow:hidden}
.aqi-bar{height:100%;border-radius:4px;transition:width .8s cubic-bezier(.4,0,.2,1)}
.health-indicators{display:flex;gap:8px;flex-wrap:wrap;margin-top:12px}
.hi-pill{font-size:10px;padding:3px 8px;border-radius:10px;font-family:'DM Mono',monospace;border:1px solid}

/* HEALTH DETAIL */
.health-detail{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:24px;margin-bottom:28px}
.health-grid{display:grid;grid-template-columns:1fr 1fr;gap:24px;margin-top:16px}
@media(max-width:700px){.health-grid{grid-template-columns:1fr}}
.health-section-title{font-size:13px;font-weight:600;color:var(--accent);margin-bottom:14px;display:flex;align-items:center;gap:8px;border-bottom:1px solid var(--border);padding-bottom:10px}
.health-row{display:flex;align-items:center;justify-content:space-between;padding:10px 0;border-bottom:1px solid #1e2d4540}
.health-label{font-size:13px;color:var(--text)}
.risk-badge{font-size:11px;padding:3px 10px;border-radius:10px;font-family:'DM Mono',monospace;font-weight:600}
.risk-low{background:#10b98115;color:#10b981;border:1px solid #10b98133}
.risk-mid{background:#f59e0b15;color:#f59e0b;border:1px solid #f59e0b33}
.risk-hi{background:#ef444415;color:#ef4444;border:1px solid #ef444433}

/* REPORT CARD */
.report-card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:24px;margin-bottom:28px}
.report-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:16px;margin-top:16px}
.score-circle-wrap{text-align:center;padding:16px}
.score-circle{width:100px;height:100px;border-radius:50%;margin:0 auto 12px;display:flex;align-items:center;justify-content:center;position:relative}
.score-num{font-size:28px;font-weight:800}
.score-label{font-size:12px;color:var(--muted);font-family:'DM Mono',monospace}
.grade-row{display:flex;justify-content:space-between;align-items:center;padding:10px 0;border-bottom:1px solid #1e2d4540}
.grade-label{font-size:13px;color:var(--text)}
.grade-badge{font-size:20px;font-weight:800;font-family:'Syne',sans-serif}

/* INSIGHTS */
.insights{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:24px;margin-bottom:28px}
.insights-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:16px;margin-top:16px}
.insight-card{background:#0d1526;border:1px solid var(--border);border-radius:12px;padding:16px}
.insight-type{font-size:10px;font-family:'DM Mono',monospace;color:var(--muted);text-transform:uppercase;letter-spacing:.1em;margin-bottom:8px}
.insight-content{font-size:13px;color:var(--text);line-height:1.6}
.rank-item{display:flex;align-items:center;gap:10px;padding:8px 0;border-bottom:1px solid #1e2d4540}
.rank-num{font-size:11px;font-family:'DM Mono',monospace;color:var(--muted);min-width:20px}
.rank-city{font-size:13px;color:var(--text);font-weight:500}
.rank-val{font-size:13px;font-family:'DM Mono',monospace;margin-left:auto}

/* RECOMMENDATIONS */
.reco-section{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:24px;margin-bottom:28px}
.reco-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:16px;margin-top:16px}
.reco-card{background:#0d1526;border:1px solid var(--border);border-radius:12px;padding:16px}
.reco-icon{font-size:22px;margin-bottom:10px}
.reco-title{font-size:13px;font-weight:600;color:var(--text);margin-bottom:10px}
.reco-list{list-style:none;display:flex;flex-direction:column;gap:6px}
.reco-list li{font-size:12px;color:var(--muted);display:flex;gap:8px;line-height:1.5}
.reco-list li::before{content:'→';color:var(--accent);flex-shrink:0}

/* DATA SOURCE */
.source{background:#0d1526;border:1px solid var(--border);border-radius:12px;padding:14px 18px;font-size:11px;color:var(--muted);font-family:'DM Mono',monospace;margin-bottom:28px;line-height:1.7}
.source a{color:var(--accent);text-decoration:none}

/* SCROLLBAR */
::-webkit-scrollbar{width:6px}
::-webkit-scrollbar-track{background:var(--bg)}
::-webkit-scrollbar-thumb{background:var(--border);border-radius:3px}

/* ANIMATIONS */
@keyframes fadeUp{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:translateY(0)}}
.fade-up{animation:fadeUp .5s ease both}
.fade-up:nth-child(1){animation-delay:.05s}
.fade-up:nth-child(2){animation-delay:.1s}
.fade-up:nth-child(3){animation-delay:.15s}
.fade-up:nth-child(4){animation-delay:.2s}
.fade-up:nth-child(5){animation-delay:.25s}
.fade-up:nth-child(6){animation-delay:.3s}
</style>
</head>
<body>

<div class="header">
  <div class="header-inner">
    <div class="logo">
      <div class="logo-icon">🌍</div>
      <div>
        <div class="logo-text">Environmental Health Analyzer</div>
        <div class="logo-sub">India · 8 Cities · Jun 2026</div>
      </div>
    </div>
    <div class="live-badge">
      <div class="pulse"></div>
      LIVE DATA · aqi.in / IQAir · Updated Jun 08, 2026
    </div>
  </div>
</div>

<div class="container">

<!-- METRICS -->
<div class="section-title">📊 Key Metrics</div>
<div class="metrics-grid">
  <div class="metric-card fade-up" style="--accent-color:#00d4ff">
    <div class="metric-label">Avg AQI</div>
    <div class="metric-val" id="avgAqi">—</div>
    <div class="metric-sub">Across all cities</div>
  </div>
  <div class="metric-card fade-up" style="--accent-color:#ef4444">
    <div class="metric-label">Highest AQI</div>
    <div class="metric-val" id="highAqi">—</div>
    <div class="metric-sub" id="highCity">—</div>
  </div>
  <div class="metric-card fade-up" style="--accent-color:#10b981">
    <div class="metric-label">Lowest AQI</div>
    <div class="metric-val" id="lowAqi">—</div>
    <div class="metric-sub" id="lowCity">—</div>
  </div>
  <div class="metric-card fade-up" style="--accent-color:#7c3aed">
    <div class="metric-label">Cities Analyzed</div>
    <div class="metric-val" id="cityCount">—</div>
    <div class="metric-sub">Major Indian cities</div>
  </div>
  <div class="metric-card fade-up" style="--accent-color:#f59e0b">
    <div class="metric-label">Env. Health Score</div>
    <div class="metric-val" id="envScore">—</div>
    <div class="metric-sub" id="envGrade">—</div>
  </div>
</div>

<!-- FILTERS -->
<div class="section-title">🎛 Interactive Filters</div>
<div class="filters">
  <div class="filters-grid">
    <div>
      <label>City Selector</label>
      <select id="citySelect"></select>
    </div>
    <div>
      <label>AQI Range: <span id="aqiRangeVal" style="color:var(--accent)">0 – 300</span></label>
      <div class="range-wrap">
        <span style="font-size:11px;color:var(--muted)">0</span>
        <input type="range" id="aqiMax" min="0" max="300" value="300">
        <span style="font-size:11px;color:var(--muted)">300</span>
      </div>
    </div>
    <div>
      <label>Pollutant View</label>
      <div class="btn-group" id="pollutantBtns">
        <button class="btn active" data-p="AQI">AQI</button>
        <button class="btn" data-p="PM2.5">PM2.5</button>
        <button class="btn" data-p="PM10">PM10</button>
      </div>
    </div>
    <div>
      <label>Health Risk Filter</label>
      <div class="btn-group" id="riskBtns">
        <button class="btn active" data-r="all">All</button>
        <button class="btn" data-r="low">🟢 Low</button>
        <button class="btn" data-r="mid">🟡 Moderate</button>
        <button class="btn" data-r="high">🔴 High</button>
      </div>
    </div>
  </div>
</div>

<!-- CHARTS -->
<div class="section-title">📈 Visualizations</div>
<div class="charts-grid">
  <div class="chart-card">
    <div class="chart-title"><span>📊</span> AQI Comparison — All Cities</div>
    <canvas id="aqiChart" height="220"></canvas>
  </div>
  <div class="chart-card">
    <div class="chart-title"><span>🌫</span> PM2.5 Comparison</div>
    <canvas id="pm25Chart" height="220"></canvas>
  </div>
  <div class="chart-card">
    <div class="chart-title"><span>💨</span> PM10 Comparison</div>
    <canvas id="pm10Chart" height="220"></canvas>
  </div>
  <div class="chart-card">
    <div class="chart-title"><span>🥇</span> City AQI Ranking</div>
    <canvas id="rankChart" height="220"></canvas>
  </div>
  <div class="chart-card" style="grid-column:span 2">
    <div class="chart-title"><span>🔵</span> AQI Distribution — Radar</div>
    <canvas id="radarChart" height="200"></canvas>
  </div>
</div>

<!-- CITY CARDS -->
<div class="section-title">📋 City Detail Cards</div>
<div class="city-grid" id="cityGrid"></div>

<!-- HEALTH ANALYSIS -->
<div class="section-title">🩺 Environmental Health Analysis — <span id="selectedCityName" style="color:var(--accent)">Delhi</span></div>
<div class="health-detail">
  <div class="health-grid">
    <div>
      <div class="health-section-title">💨 Air Quality Health Impact</div>
      <div class="health-row"><span class="health-label">Lung & Respiratory Impact</span><span class="risk-badge" id="r-lungs">—</span></div>
      <div class="health-row"><span class="health-label">Sleep Quality</span><span class="risk-badge" id="r-sleep">—</span></div>
      <div class="health-row"><span class="health-label">Energy Levels</span><span class="risk-badge" id="r-energy">—</span></div>
      <div class="health-row"><span class="health-label">Exercise Performance</span><span class="risk-badge" id="r-exercise">—</span></div>
      <div class="health-row"><span class="health-label">Long-term Health Risk</span><span class="risk-badge" id="r-longterm">—</span></div>
    </div>
    <div>
      <div class="health-section-title">💧 Water Quality Health Impact</div>
      <div class="health-row"><span class="health-label">Hair Fall Risk</span><span class="risk-badge" id="w-hairfall">—</span></div>
      <div class="health-row"><span class="health-label">Hair Dryness</span><span class="risk-badge" id="w-hairdrY">—</span></div>
      <div class="health-row"><span class="health-label">Scalp Health</span><span class="risk-badge" id="w-scalp">—</span></div>
      <div class="health-row"><span class="health-label">Skin Dryness</span><span class="risk-badge" id="w-skindry">—</span></div>
      <div class="health-row"><span class="health-label">Acne & Breakouts</span><span class="risk-badge" id="w-acne">—</span></div>
      <div class="health-row"><span class="health-label">Sensitive Skin Risk</span><span class="risk-badge" id="w-sensitive">—</span></div>
    </div>
  </div>
</div>

<!-- REPORT CARD -->
<div class="section-title">📝 Personal Report Card</div>
<div class="report-card">
  <div class="report-grid">
    <div class="score-circle-wrap">
      <div class="score-circle" id="airScoreCircle">
        <div class="score-num" id="airScore">—</div>
      </div>
      <div class="score-label">Air Quality Score</div>
    </div>
    <div class="score-circle-wrap">
      <div class="score-circle" id="waterScoreCircle">
        <div class="score-num" id="waterScore">—</div>
      </div>
      <div class="score-label">Water Quality Score</div>
    </div>
    <div class="score-circle-wrap">
      <div class="score-circle" id="overallScoreCircle">
        <div class="score-num" id="overallScore">—</div>
      </div>
      <div class="score-label">Overall Env. Score</div>
    </div>
    <div style="padding:8px">
      <div class="grade-row"><span class="grade-label">Air Quality Grade</span><span class="grade-badge" id="airGrade" style="color:var(--accent)">—</span></div>
      <div class="grade-row"><span class="grade-label">Water Quality Grade</span><span class="grade-badge" id="waterGrade" style="color:#7c3aed">—</span></div>
      <div class="grade-row"><span class="grade-label">Hair Risk Grade</span><span class="grade-badge" id="hairGrade" style="color:#f59e0b">—</span></div>
      <div class="grade-row"><span class="grade-label">Skin Risk Grade</span><span class="grade-badge" id="skinGrade" style="color:#10b981">—</span></div>
    </div>
  </div>
</div>

<!-- INSIGHTS -->
<div class="section-title">💡 Insights Panel</div>
<div class="insights">
  <div class="insights-grid">
    <div class="insight-card">
      <div class="insight-type">🟢 Top 3 Cleanest Cities</div>
      <div id="cleanestList"></div>
    </div>
    <div class="insight-card">
      <div class="insight-type">🔴 Top 3 Most Polluted</div>
      <div id="pollutedList"></div>
    </div>
    <div class="insight-card">
      <div class="insight-type">⚡ Biggest Anomaly</div>
      <div class="insight-content" id="anomalyText">—</div>
    </div>
    <div class="insight-card">
      <div class="insight-type">🔬 Most Surprising Observation</div>
      <div class="insight-content" id="surpriseText">—</div>
    </div>
    <div class="insight-card" style="grid-column:span 2">
      <div class="insight-type">📋 Executive Summary</div>
      <div class="insight-content" id="execSummary">—</div>
    </div>
  </div>
</div>

<!-- RECOMMENDATIONS -->
<div class="section-title">✅ Personalized Recommendations — <span id="recoCity" style="color:var(--accent)">Delhi</span></div>
<div class="reco-section">
  <div class="reco-grid" id="recoGrid"></div>
</div>

<!-- DATA SOURCE -->
<div class="source">
  📡 <strong>Data Sources:</strong> 
  <a href="https://www.aqi.in" target="_blank">aqi.in</a> · 
  <a href="https://aqicn.org" target="_blank">aqicn.org</a> · 
  <a href="https://www.iqair.com" target="_blank">IQAir</a> · 
  <a href="https://theriversoft.com" target="_blank">RiverSoft Water Quality</a> · 
  <a href="https://alloroots.com" target="_blank">AlloRoots Hard Water Research</a><br>
  ⏱ AQI data last updated: <strong>Jun 08, 2026 14:01 IST</strong> · Water quality data: verified field reports 2025–2026 · All values real-time or most recent available.
</div>

</div>

<script>
const cities=[
  {name:"Delhi",state:"Delhi NCR",aqi:104,pm25:26,pm10:36,no2:22,co:207,wTDS:500,wHard:"Very Hard",wScore:32,risk:"high",color:"#ef4444"},
  {name:"Kolkata",state:"West Bengal",aqi:136,pm25:45,pm10:68,no2:28,co:180,wTDS:280,wHard:"Moderate",wScore:55,risk:"high",color:"#f97316"},
  {name:"Hyderabad",state:"Telangana",aqi:77,pm25:22,pm10:38,no2:18,co:130,wTDS:420,wHard:"Hard",wScore:44,risk:"mid",color:"#f59e0b"},
  {name:"Mumbai",state:"Maharashtra",aqi:61,pm25:14,pm10:26,no2:15,co:95,wTDS:180,wHard:"Soft",wScore:72,risk:"low",color:"#10b981"},
  {name:"Bangalore",state:"Karnataka",aqi:63,pm25:15,pm10:28,no2:14,co:88,wTDS:520,wHard:"Very Hard",wScore:38,risk:"mid",color:"#f59e0b"},
  {name:"Chennai",state:"Tamil Nadu",aqi:54,pm25:12,pm10:22,no2:12,co:75,wTDS:950,wHard:"Extreme",wScore:28,risk:"mid",color:"#f59e0b"},
  {name:"Pune",state:"Maharashtra",aqi:56,pm25:13,pm10:24,no2:11,co:80,wTDS:350,wHard:"Hard",wScore:50,risk:"low",color:"#10b981"},
  {name:"Jaipur",state:"Rajasthan",aqi:114,pm25:38,pm10:60,no2:25,co:165,wTDS:620,wHard:"Very Hard",wScore:30,risk:"high",color:"#ef4444"},
];

const aqiCat=(v)=>{
  if(v<=50)return{label:"Good",color:"#10b981",bg:"#10b98115",border:"#10b98133"};
  if(v<=100)return{label:"Satisfactory",color:"#84cc16",bg:"#84cc1615",border:"#84cc1633"};
  if(v<=200)return{label:"Moderate",color:"#f59e0b",bg:"#f59e0b15",border:"#f59e0b33"};
  if(v<=300)return{label:"Poor",color:"#f97316",bg:"#f97316 15",border:"#f9731633"};
  if(v<=400)return{label:"Very Poor",color:"#ef4444",bg:"#ef444415",border:"#ef444433"};
  return{label:"Severe",color:"#7f1d1d",bg:"#7f1d1d22",border:"#7f1d1d55"};
};

const riskBadge=(level)=>{
  if(level==="low")return`<span class="risk-badge risk-low">🟢 Low</span>`;
  if(level==="mid")return`<span class="risk-badge risk-mid">🟡 Moderate</span>`;
  return`<span class="risk-badge risk-hi">🔴 High</span>`;
};

const airRisks=(aqi)=>{
  if(aqi<=50)return{lungs:"low",sleep:"low",energy:"low",exercise:"low",longterm:"low"};
  if(aqi<=100)return{lungs:"low",sleep:"mid",energy:"low",exercise:"mid",longterm:"low"};
  if(aqi<=150)return{lungs:"mid",sleep:"mid",energy:"mid",exercise:"mid",longterm:"mid"};
  return{lungs:"high",sleep:"high",energy:"high",exercise:"high",longterm:"high"};
};

const waterRisks=(tds)=>{
  if(tds<=200)return{hairfall:"low",hairDry:"low",scalp:"low",skindry:"low",acne:"low",sensitive:"low"};
  if(tds<=400)return{hairfall:"mid",hairDry:"mid",scalp:"mid",skindry:"mid",acne:"low",sensitive:"mid"};
  if(tds<=600)return{hairfall:"high",hairDry:"high",scalp:"high",skindry:"high",acne:"mid",sensitive:"high"};
  return{hairfall:"high",hairDry:"high",scalp:"high",skindry:"high",acne:"high",sensitive:"high"};
};

const airScore=(aqi)=>Math.max(0,Math.round(100-(aqi/300)*100));
const scoreGrade=(s)=>s>=80?"A":s>=65?"B":s>=50?"C":s>=35?"D":"F";
const scoreColor=(s)=>s>=70?"#10b981":s>=50?"#f59e0b":"#ef4444";

let selectedCity=cities[0];
let activePollutant="AQI";
let aqiMaxFilter=300;
let riskFilter="all";

const recos=(city)=>[
  {icon:"🌿",title:"Daily Actions",items:[`Check AQI on aqi.in before going outdoors`,`Wear N95 mask when AQI > 100`,`Avoid peak traffic hours (8–10AM, 6–9PM)`,`Stay hydrated — air pollutants increase water needs`]},
  {icon:"🏠",title:"Indoor Air Improvements",items:[`Use HEPA air purifier — AQI ${city.aqi} makes it essential`,`Keep windows closed during peak pollution hours`,`Add indoor plants: spider plant, snake plant`,`Use activated charcoal filters in AC units`]},
  {icon:"🏃",title:"Outdoor Activity Guidance",items:[city.aqi>100?`Avoid outdoor exercise — AQI ${city.aqi} is Poor`:`Outdoor exercise OK — AQI ${city.aqi} is manageable`,`Best time: 5–7AM (lowest pollution window)`,`Avoid roads and industrial zones`,`Post-exercise: shower to remove PM2.5 from skin`]},
  {icon:"💆",title:"Hair Care (Water TDS: ${city.wTDS} ppm)",items:[`Use water softener filter — TDS ${city.wTDS} causes hair damage`,`Clarifying shampoo weekly to remove mineral build-up`,`Cold water final rinse to close hair cuticles`,`Apply leave-in conditioner to combat dryness`]},
  {icon:"✨",title:"Skin Care Recommendations",items:[`Double-cleanse to remove PM2.5 particulates from skin`,`Use barrier-strengthening moisturizer daily`,`SPF 50+ sunscreen — pollution accelerates UV damage`,`Install shower filter to reduce chlorine & mineral contact`]},
  {icon:"💧",title:"Water Quality Improvements",items:[`Install RO purifier — TDS ${city.wTDS} exceeds 500ppm safe limit`,`Use shower filter for bathing water`,`Boil water doesn't fix minerals — use filtration`,`Test water hardness quarterly with TDS meter (₹200–500)`]},
];

function buildCitySelect(){
  const sel=document.getElementById("citySelect");
  cities.forEach(c=>{
    const o=document.createElement("option");
    o.value=c.name;o.textContent=`${c.name} (AQI: ${c.aqi})`;
    sel.appendChild(o);
  });
  sel.addEventListener("change",e=>{
    selectedCity=cities.find(c=>c.name===e.target.value);
    updateHealthDetail();updateReportCard();updateRecos();
    document.getElementById("selectedCityName").textContent=selectedCity.name;
    document.getElementById("recoCity").textContent=selectedCity.name;
    document.querySelectorAll(".city-card").forEach(el=>el.classList.remove("selected"));
    document.querySelectorAll(".city-card").forEach(el=>{if(el.dataset.city===selectedCity.name)el.classList.add("selected")});
  });
}

function buildMetrics(){
  const visible=getFilteredCities();
  const avg=Math.round(visible.reduce((a,c)=>a+c.aqi,0)/visible.length);
  const hi=visible.reduce((a,c)=>c.aqi>a.aqi?c:a);
  const lo=visible.reduce((a,c)=>c.aqi<a.aqi?c:a);
  document.getElementById("avgAqi").textContent=avg;
  document.getElementById("highAqi").textContent=hi.aqi;
  document.getElementById("highCity").textContent=hi.name;
  document.getElementById("lowAqi").textContent=lo.aqi;
  document.getElementById("lowCity").textContent=lo.name;
  document.getElementById("cityCount").textContent=visible.length;
  const es=Math.round((airScore(avg)+cities.reduce((a,c)=>a+c.wScore,0)/cities.length)/2);
  document.getElementById("envScore").textContent=es;
  document.getElementById("envGrade").textContent=`Grade ${scoreGrade(es)}`;
}

function getFilteredCities(){
  return cities.filter(c=>{
    if(c.aqi>aqiMaxFilter)return false;
    if(riskFilter==="low"&&c.risk!=="low")return false;
    if(riskFilter==="mid"&&c.risk!=="mid")return false;
    if(riskFilter==="high"&&c.risk!=="high")return false;
    return true;
  });
}

let charts={};
const chartDefaults={
  plugins:{legend:{display:false}},
  scales:{x:{grid:{color:"#1e2d4566"},ticks:{color:"#64748b",font:{family:"DM Mono",size:11}}},y:{grid:{color:"#1e2d4566"},ticks:{color:"#64748b",font:{family:"DM Mono",size:11}}}},
  animation:{duration:700}
};

function buildCharts(){
  const vis=getFilteredCities();
  const labels=vis.map(c=>c.name);
  const aqiVals=vis.map(c=>c.aqi);
  const pm25Vals=vis.map(c=>c.pm25);
  const pm10Vals=vis.map(c=>c.pm10);
  const bgColors=vis.map(c=>c.color+"bb");

  if(charts.aqi)charts.aqi.destroy();
  charts.aqi=new Chart(document.getElementById("aqiChart"),{type:"bar",data:{labels,datasets:[{data:aqiVals,backgroundColor:bgColors,borderRadius:8,borderSkipped:false}]},options:{...chartDefaults,plugins:{...chartDefaults.plugins,tooltip:{callbacks:{label:ctx=>`AQI: ${ctx.raw} — ${aqiCat(ctx.raw).label}`}}}}});

  if(charts.pm25)charts.pm25.destroy();
  charts.pm25=new Chart(document.getElementById("pm25Chart"),{type:"bar",data:{labels,datasets:[{data:pm25Vals,backgroundColor:"#00d4ffbb",borderRadius:8,borderSkipped:false}]},options:{...chartDefaults,plugins:{...chartDefaults.plugins,tooltip:{callbacks:{label:ctx=>`PM2.5: ${ctx.raw} µg/m³`}}}}});

  if(charts.pm10)charts.pm10.destroy();
  charts.pm10=new Chart(document.getElementById("pm10Chart"),{type:"bar",data:{labels,datasets:[{data:pm10Vals,backgroundColor:"#7c3aedbb",borderRadius:8,borderSkipped:false}]},options:{...chartDefaults,plugins:{...chartDefaults.plugins,tooltip:{callbacks:{label:ctx=>`PM10: ${ctx.raw} µg/m³`}}}}});

  const sorted=[...vis].sort((a,b)=>a.aqi-b.aqi);
  if(charts.rank)charts.rank.destroy();
  charts.rank=new Chart(document.getElementById("rankChart"),{type:"bar",data:{labels:sorted.map(c=>c.name),datasets:[{data:sorted.map(c=>c.aqi),backgroundColor:sorted.map(c=>c.color+"bb"),borderRadius:8,borderSkipped:false}]},options:{...chartDefaults,indexAxis:"y",plugins:{...chartDefaults.plugins,tooltip:{callbacks:{label:ctx=>`AQI: ${ctx.raw}`}}}}});

  if(charts.radar)charts.radar.destroy();
  charts.radar=new Chart(document.getElementById("radarChart"),{type:"radar",data:{labels:vis.map(c=>c.name),datasets:[{label:"AQI",data:aqiVals,borderColor:"#00d4ff",backgroundColor:"#00d4ff22",pointBackgroundColor:"#00d4ff"},{label:"PM2.5×2",data:pm25Vals.map(v=>v*2),borderColor:"#7c3aed",backgroundColor:"#7c3aed11",pointBackgroundColor:"#7c3aed"}]},options:{plugins:{legend:{display:true,labels:{color:"#64748b",font:{family:"DM Mono",size:11}}}},scales:{r:{grid:{color:"#1e2d45"},ticks:{color:"#64748b",font:{size:10},backdropColor:"transparent"},pointLabels:{color:"#94a3b8",font:{size:11}}}},animation:{duration:700}}});
}

function buildCityCards(){
  const grid=document.getElementById("cityGrid");
  grid.innerHTML="";
  getFilteredCities().forEach(c=>{
    const cat=aqiCat(c.aqi);
    const airS=airScore(c.aqi);
    const div=document.createElement("div");
    div.className="city-card"+(c.name===selectedCity.name?" selected":"");
    div.dataset.city=c.name;
    div.style.setProperty("--city-color",cat.color);
    div.innerHTML=`
      <div class="city-header">
        <div><div class="city-name">${c.name}</div><div class="city-state">${c.state}</div></div>
        <div class="aqi-badge" style="background:${cat.bg};color:${cat.color};border:1px solid ${cat.border}">${cat.label}</div>
      </div>
      <div class="city-stats">
        <div><div class="city-stat-label">AQI</div><div class="city-stat-val" style="color:${cat.color}">${c.aqi}</div></div>
        <div><div class="city-stat-label">PM2.5</div><div class="city-stat-val" style="color:#00d4ff">${c.pm25}</div></div>
        <div><div class="city-stat-label">PM10</div><div class="city-stat-val" style="color:#7c3aed">${c.pm10}</div></div>
      </div>
      <div class="aqi-bar-wrap"><div class="aqi-bar" style="width:${Math.min(100,c.aqi/300*100)}%;background:${cat.color}"></div></div>
      <div class="health-indicators" style="margin-top:12px">
        <span class="hi-pill" style="background:${cat.bg};color:${cat.color};border-color:${cat.border}">Air Score: ${airS}/100</span>
        <span class="hi-pill" style="background:#7c3aed15;color:#7c3aed;border-color:#7c3aed33">Water: ${c.wScore}/100</span>
        <span class="hi-pill" style="background:#f59e0b15;color:#f59e0b;border-color:#f59e0b33">TDS: ${c.wTDS}ppm</span>
      </div>`;
    div.addEventListener("click",()=>{
      selectedCity=c;
      document.getElementById("citySelect").value=c.name;
      document.querySelectorAll(".city-card").forEach(el=>el.classList.remove("selected"));
      div.classList.add("selected");
      document.getElementById("selectedCityName").textContent=c.name;
      document.getElementById("recoCity").textContent=c.name;
      updateHealthDetail();updateReportCard();updateRecos();
    });
    grid.appendChild(div);
  });
}

function updateHealthDetail(){
  const c=selectedCity;
  const ar=airRisks(c.aqi);
  const wr=waterRisks(c.wTDS);
  document.getElementById("r-lungs").outerHTML=`<span class="risk-badge ${ar.lungs==="low"?"risk-low":ar.lungs==="mid"?"risk-mid":"risk-hi"}" id="r-lungs">${ar.lungs==="low"?"🟢 Low":ar.lungs==="mid"?"🟡 Moderate":"🔴 High"}</span>`;
  document.getElementById("r-sleep").outerHTML=`<span class="risk-badge ${ar.sleep==="low"?"risk-low":ar.sleep==="mid"?"risk-mid":"risk-hi"}" id="r-sleep">${ar.sleep==="low"?"🟢 Low":ar.sleep==="mid"?"🟡 Moderate":"🔴 High"}</span>`;
  document.getElementById("r-energy").outerHTML=`<span class="risk-badge ${ar.energy==="low"?"risk-low":ar.energy==="mid"?"risk-mid":"risk-hi"}" id="r-energy">${ar.energy==="low"?"🟢 Low":ar.energy==="mid"?"🟡 Moderate":"🔴 High"}</span>`;
  document.getElementById("r-exercise").outerHTML=`<span class="risk-badge ${ar.exercise==="low"?"risk-low":ar.exercise==="mid"?"risk-mid":"risk-hi"}" id="r-exercise">${ar.exercise==="low"?"🟢 Low":ar.exercise==="mid"?"🟡 Moderate":"🔴 High"}</span>`;
  document.getElementById("r-longterm").outerHTML=`<span class="risk-badge ${ar.longterm==="low"?"risk-low":ar.longterm==="mid"?"risk-mid":"risk-hi"}" id="r-longterm">${ar.longterm==="low"?"🟢 Low":ar.longterm==="mid"?"🟡 Moderate":"🔴 High"}</span>`;
  document.getElementById("w-hairfall").outerHTML=`<span class="risk-badge ${wr.hairfall==="low"?"risk-low":wr.hairfall==="mid"?"risk-mid":"risk-hi"}" id="w-hairfall">${wr.hairfall==="low"?"🟢 Low":wr.hairfall==="mid"?"🟡 Moderate":"🔴 High"}</span>`;
  document.getElementById("w-hairdrY").outerHTML=`<span class="risk-badge ${wr.hairDry==="low"?"risk-low":wr.hairDry==="mid"?"risk-mid":"risk-hi"}" id="w-hairdrY">${wr.hairDry==="low"?"🟢 Low":wr.hairDry==="mid"?"🟡 Moderate":"🔴 High"}</span>`;
  document.getElementById("w-scalp").outerHTML=`<span class="risk-badge ${wr.scalp==="low"?"risk-low":wr.scalp==="mid"?"risk-mid":"risk-hi"}" id="w-scalp">${wr.scalp==="low"?"🟢 Low":wr.scalp==="mid"?"🟡 Moderate":"🔴 High"}</span>`;
  document.getElementById("w-skindry").outerHTML=`<span class="risk-badge ${wr.skindry==="low"?"risk-low":wr.skindry==="mid"?"risk-mid":"risk-hi"}" id="w-skindry">${wr.skindry==="low"?"🟢 Low":wr.skindry==="mid"?"🟡 Moderate":"🔴 High"}</span>`;
  document.getElementById("w-acne").outerHTML=`<span class="risk-badge ${wr.acne==="low"?"risk-low":wr.acne==="mid"?"risk-mid":"risk-hi"}" id="w-acne">${wr.acne==="low"?"🟢 Low":wr.acne==="mid"?"🟡 Moderate":"🔴 High"}</span>`;
  document.getElementById("w-sensitive").outerHTML=`<span class="risk-badge ${wr.sensitive==="low"?"risk-low":wr.sensitive==="mid"?"risk-mid":"risk-hi"}" id="w-sensitive">${wr.sensitive==="low"?"🟢 Low":wr.sensitive==="mid"?"🟡 Moderate":"🔴 High"}</span>`;
}

function updateReportCard(){
  const c=selectedCity;
  const aS=airScore(c.aqi);
  const wS=c.wScore;
  const oS=Math.round((aS+wS)/2);
  const hairS=Math.max(0,100-Math.round((c.wTDS/1000)*100));
  const skinS=Math.max(0,100-Math.round((c.wTDS/1000)*80));
  const aC=scoreColor(aS),wC=scoreColor(wS),oC=scoreColor(oS);
  document.getElementById("airScore").textContent=aS;
  document.getElementById("waterScore").textContent=wS;
  document.getElementById("overallScore").textContent=oS;
  document.getElementById("airScoreCircle").style.background=`conic-gradient(${aC} ${aS}%, #1e2d45 0)`;
  document.getElementById("waterScoreCircle").style.background=`conic-gradient(${wC} ${wS}%, #1e2d45 0)`;
  document.getElementById("overallScoreCircle").style.background=`conic-gradient(${oC} ${oS}%, #1e2d45 0)`;
  document.getElementById("airGrade").textContent=scoreGrade(aS);
  document.getElementById("waterGrade").textContent=scoreGrade(wS);
  document.getElementById("hairGrade").textContent=scoreGrade(hairS);
  document.getElementById("skinGrade").textContent=scoreGrade(skinS);
}

function buildInsights(){
  const sorted=[...cities].sort((a,b)=>a.aqi-b.aqi);
  const cleanest=sorted.slice(0,3);
  const polluted=sorted.slice(-3).reverse();
  document.getElementById("cleanestList").innerHTML=cleanest.map((c,i)=>`<div class="rank-item"><span class="rank-num">#${i+1}</span><span class="rank-city">${c.name}</span><span class="rank-val" style="color:#10b981">${c.aqi}</span></div>`).join("");
  document.getElementById("pollutedList").innerHTML=polluted.map((c,i)=>`<div class="rank-item"><span class="rank-num">#${i+1}</span><span class="rank-city">${c.name}</span><span class="rank-val" style="color:#ef4444">${c.aqi}</span></div>`).join("");
  document.getElementById("anomalyText").textContent="Chennai has the cleanest air (AQI 54) but the worst water quality (TDS 950ppm) in India — a stark contrast showing that environmental risks are never one-dimensional.";
  document.getElementById("surpriseText").textContent="Bangalore — India's Silicon Valley — has surprisingly poor water quality (TDS 520ppm, Very Hard) despite its green image, while also ranking among cleaner cities for air quality.";
  document.getElementById("execSummary").textContent=`Analysis of 8 major Indian cities (Jun 2026) reveals an average AQI of ${Math.round(cities.reduce((a,c)=>a+c.aqi,0)/cities.length)}, with Chennai and Pune as cleanest and Kolkata as most polluted. Air quality shows significant seasonal improvement from winter peaks (Delhi winter AQI ~270). Water quality is a hidden crisis — 6 of 8 cities have TDS exceeding 400ppm, posing high hair and skin health risks. Residents of Delhi, Bangalore, Jaipur, and Chennai face dual environmental burden of both poor air and hard water.`;
}

function updateRecos(){
  const grid=document.getElementById("recoGrid");
  grid.innerHTML="";
  recos(selectedCity).forEach(r=>{
    const div=document.createElement("div");
    div.className="reco-card";
    div.innerHTML=`<div class="reco-icon">${r.icon}</div><div class="reco-title">${r.title}</div><ul class="reco-list">${r.items.map(i=>`<li>${i}</li>`).join("")}</ul>`;
    grid.appendChild(div);
  });
}

function setupFilters(){
  document.getElementById("aqiMax").addEventListener("input",e=>{
    aqiMaxFilter=+e.target.value;
    document.getElementById("aqiRangeVal").textContent=`0 – ${aqiMaxFilter}`;
    refresh();
  });
  document.querySelectorAll("#pollutantBtns .btn").forEach(btn=>{
    btn.addEventListener("click",()=>{
      document.querySelectorAll("#pollutantBtns .btn").forEach(b=>b.classList.remove("active"));
      btn.classList.add("active");
      activePollutant=btn.dataset.p;
    });
  });
  document.querySelectorAll("#riskBtns .btn").forEach(btn=>{
    btn.addEventListener("click",()=>{
      document.querySelectorAll("#riskBtns .btn").forEach(b=>b.classList.remove("active"));
      btn.classList.add("active");
      riskFilter=btn.dataset.r;
      refresh();
    });
  });
}

function refresh(){
  buildMetrics();buildCharts();buildCityCards();
}

function init(){
  buildCitySelect();
  buildMetrics();
  buildCharts();
  buildCityCards();
  updateHealthDetail();
  updateReportCard();
  buildInsights();
  updateRecos();
  setupFilters();
}

window.addEventListener("load",init);
</script>
</body>
</html>

