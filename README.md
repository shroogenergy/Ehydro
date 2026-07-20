<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Green Hydrogen Techno-Economic &amp; Strategic Decision Platform</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Archivo:wght@600;700;800&family=Inter:wght@400;500;600&family=IBM+Plex+Mono:wght@500;600&display=swap" rel="stylesheet">
<style>
:root{
  --ink:#081C36; --navy:#0D2B4F; --navy2:#16406F;
  --paper:#FFFFFF; --cloud:#EEF2F7; --line:#D8E1EC;
  --steel:#64798F; --steel2:#8FA3B8;
  --cyan:#1FB2D5; --cyan-dk:#0E85A3;
  --gold:#F0B429;
  --good:#1B9E77; --warn:#B47D00; --bad:#C0392B;
  --radius:10px;
}
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:'Inter',sans-serif;background:var(--cloud);color:var(--ink);font-size:14px;line-height:1.55;padding:0 0 60px}

/* ---------- Header ---------- */
.hero{background:linear-gradient(115deg,var(--ink) 0%,var(--navy) 55%,var(--navy2) 100%);color:#fff;padding:40px 24px 56px;position:relative;overflow:hidden}
.hero::after{content:"";position:absolute;right:-70px;top:-90px;width:420px;height:420px;border:1px solid rgba(255,255,255,.07);border-radius:50%}
.hero::before{content:"";position:absolute;right:40px;top:-150px;width:420px;height:420px;border:1px solid rgba(31,178,213,.18);border-radius:50%}
.hero-inner{max-width:1180px;margin:0 auto;position:relative;z-index:1}
.hero-top{display:flex;align-items:center;gap:12px;margin-bottom:18px}
.logo{width:38px;height:38px;flex:none}
.eyebrow{font-size:10.5px;letter-spacing:.22em;text-transform:uppercase;color:var(--cyan);font-weight:600}
.hero h1{font-family:'Archivo',sans-serif;font-weight:800;font-size:27px;letter-spacing:-.01em;line-height:1.25;max-width:720px}
.hero p{margin-top:10px;color:#B9C9DB;max-width:640px;font-size:13.5px}
.hero-meta{display:flex;gap:28px;margin-top:20px;flex-wrap:wrap}
.hero-meta div{font-size:10.5px;color:var(--steel2);text-transform:uppercase;letter-spacing:.1em}
.hero-meta b{display:block;font-family:'IBM Plex Mono',monospace;font-size:14px;color:#fff;font-weight:600;text-transform:none;letter-spacing:0;margin-top:3px}

/* ---------- Layout ---------- */
.container{max-width:1180px;margin:-28px auto 0;padding:0 24px;position:relative;z-index:2}
.grid{display:grid;grid-template-columns:380px 1fr;gap:22px;align-items:start}
@media(max-width:960px){.grid{grid-template-columns:1fr}}
.card{background:var(--paper);border:1px solid var(--line);border-radius:var(--radius);padding:24px;box-shadow:0 8px 24px rgba(8,28,54,.06)}
.card-title{display:flex;align-items:center;gap:10px;margin-bottom:4px}
.card-title svg{stroke:var(--navy2);flex:none}
.card-title h2{font-family:'Archivo',sans-serif;font-size:15px;font-weight:700;letter-spacing:-.01em}
.card-sub{font-size:12px;color:var(--steel);margin-bottom:18px}
.step{font-family:'IBM Plex Mono',monospace;font-size:10.5px;font-weight:600;color:var(--cyan-dk);letter-spacing:.14em;text-transform:uppercase;margin-bottom:6px}
.section{max-width:1180px;margin:22px auto 0;padding:0 24px}
.sec-head{display:flex;align-items:baseline;gap:14px;margin:10px 0 14px}
.sec-head h2{font-family:'Archivo',sans-serif;font-weight:700;font-size:17px;letter-spacing:-.01em}
.sec-head span{font-size:12px;color:var(--steel)}

/* ---------- Inputs ---------- */
.form-group{margin-bottom:16px}
label{display:flex;align-items:center;gap:8px;margin-bottom:7px;color:var(--navy);font-size:12.5px;font-weight:600}
label svg{stroke:var(--steel);flex:none}
.unit-hint{margin-left:auto;font-weight:400;font-size:11px;color:var(--steel2)}
input,select{width:100%;padding:10px 13px;background:var(--paper);border:1.5px solid var(--line);border-radius:7px;color:var(--ink);font-size:14px;font-family:'IBM Plex Mono',monospace;font-weight:500;transition:border-color .15s, box-shadow .15s}
select{font-family:'Inter',sans-serif;cursor:pointer;appearance:none;background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 24 24' fill='none' stroke='%2364798F' stroke-width='2.5' stroke-linecap='round'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E");background-repeat:no-repeat;background-position:right 13px center;padding-right:36px}
input:focus,select:focus{outline:none;border-color:var(--navy2);box-shadow:0 0 0 3px rgba(22,64,111,.12)}
input:hover,select:hover{border-color:var(--steel2)}
.btn{display:flex;align-items:center;justify-content:center;gap:10px;background:var(--ink);color:#fff;border:none;padding:13px 20px;font-family:'Inter',sans-serif;font-size:14px;font-weight:600;border-radius:7px;cursor:pointer;width:100%;margin-top:4px;transition:background .15s, transform .1s}
.btn:hover{background:var(--navy2)}
.btn:active{transform:translateY(1px)}
.btn:focus-visible{outline:2px solid var(--cyan);outline-offset:3px}
.btn svg{stroke:var(--cyan)}
.live-note{display:flex;align-items:center;gap:8px;margin-top:12px;font-size:11px;color:var(--steel2)}
.live-note svg{stroke:var(--cyan-dk);flex:none}

/* ---------- Metrics ---------- */
.results-box{display:grid;grid-template-columns:1fr 1fr;gap:13px;margin-bottom:4px}
.metric{background:var(--paper);border:1px solid var(--line);padding:15px 15px 13px;border-radius:8px;position:relative}
.metric .m-ic{position:absolute;top:13px;right:13px;color:var(--steel2)}
.metric .label{font-size:10.5px;color:var(--steel);text-transform:uppercase;letter-spacing:.09em;font-weight:600;padding-right:26px}
.metric .value{font-family:'IBM Plex Mono',monospace;font-size:21px;font-weight:600;color:var(--ink);margin-top:6px;letter-spacing:-.02em}
.metric .value small{font-size:11px;color:var(--steel);font-weight:500;font-family:'Inter',sans-serif;margin-left:2px}
.metric.primary{background:var(--ink);border-color:var(--ink)}
.metric.primary .label{color:var(--steel2)}
.metric.primary .value{color:var(--cyan)}
.metric.primary .value small{color:var(--steel2)}
.metric.primary .m-ic{color:var(--cyan-dk)}
.metric .value.pos{color:var(--good)} .metric .value.neg{color:var(--bad)} .metric .value.warn{color:var(--warn)}
.section-break{display:flex;align-items:center;gap:10px;margin:20px 0 14px}
.section-break svg{stroke:var(--navy2);flex:none}
.section-break h3{font-family:'Archivo',sans-serif;font-size:13.5px;font-weight:700}
.section-break::after{content:"";flex:1;height:1px;background:var(--line)}

/* ---------- Charts ---------- */
.charts-grid{display:grid;grid-template-columns:1fr 1fr;gap:22px}
@media(max-width:960px){.charts-grid{grid-template-columns:1fr}}
.chart-wrap svg{width:100%;height:auto;display:block}
.legend{display:flex;gap:16px;margin-top:12px;flex-wrap:wrap}
.legend span{display:flex;align-items:center;gap:7px;font-size:11.5px;color:var(--steel);font-weight:500}
.dot{width:10px;height:10px;border-radius:3px;flex:none}

/* ---------- Table ---------- */
table{width:100%;border-collapse:collapse;font-size:13px}
th{font-size:10.5px;text-transform:uppercase;letter-spacing:.1em;color:var(--steel);font-weight:600;text-align:left;padding:9px 12px;border-bottom:1px solid var(--line)}
td{padding:11px 12px;border-bottom:1px solid var(--cloud)}
td.num,th.num{font-family:'IBM Plex Mono',monospace;text-align:right}
td.num{font-weight:500;font-family:'IBM Plex Mono',monospace}
tr:last-child td{border-bottom:none}
.badge{display:inline-flex;align-items:center;gap:6px;padding:3px 10px;border-radius:99px;font-size:11px;font-weight:600}
.badge.ok{background:#E4F4EE;color:var(--good)}
.badge.risk{background:#FBEAE7;color:var(--bad)}
.badge.watch{background:#FFF4DE;color:#9A6B00}

/* ---------- Insight ---------- */
.alert-panel{margin-top:20px;border-radius:8px;padding:17px 19px;border:1px solid var(--line);background:var(--cloud);font-size:13px;color:var(--steel);display:flex;gap:14px;align-items:flex-start;transition:.2s}
.alert-panel svg{flex:none;margin-top:1px;stroke:var(--steel2)}
.alert-panel strong{display:block;font-family:'Archivo',sans-serif;font-size:13.5px;margin-bottom:4px;color:var(--ink)}
.alert-panel.ok{background:#EDF7F3;border-color:#BFE3D5;color:#2C6E56}
.alert-panel.ok svg{stroke:var(--good)} .alert-panel.ok strong{color:var(--good)}
.alert-panel.watch{background:#FFF8EA;border-color:#EBD9AE;color:#7A5C10}
.alert-panel.watch svg{stroke:var(--warn)} .alert-panel.watch strong{color:var(--warn)}
.alert-panel.risk{background:#FBF0EE;border-color:#EBC5BE;color:#8E3226}
.alert-panel.risk svg{stroke:var(--bad)} .alert-panel.risk strong{color:var(--bad)}

.foot{max-width:1180px;margin:28px auto 0;padding:0 24px;font-size:11px;color:var(--steel2);display:flex;justify-content:space-between;gap:16px;flex-wrap:wrap}
@media(prefers-reduced-motion:reduce){*{transition:none!important}}
</style>
</head>
<body>

<header class="hero">
  <div class="hero-inner">
    <div class="hero-top">
      <svg class="logo" viewBox="0 0 30 30" fill="none"><rect x="1.5" y="1.5" width="27" height="27" rx="7" stroke="#1FB2D5" stroke-width="2"/><path d="M9 8v14M21 8v14M9 15h12" stroke="#fff" stroke-width="2.4" stroke-linecap="round"/></svg>
      <span class="eyebrow">Quantitative Simulation Framework · KSA Energy Transition</span>
    </div>
    <h1>Green Hydrogen Techno-Economic &amp; Strategic Decision Platform</h1>
    <p>A unified engineering framework with an integrated machine-learning predictive layer and strategic management sensitivity analysis for asset-level de-risking.</p>
    <div class="hero-meta">
      <div>Project lifetime<b>20 years</b></div>
      <div>OPEX assumption<b>3% of CAPEX</b></div>
      <div>CO₂ avoided factor<b>10 kg / kg H₂</b></div>
      <div>Simulation basis<b>8,760 h / yr</b></div>
    </div>
  </div>
</header>

<div class="container">
  <div class="grid">

    <!-- ============ INPUTS ============ -->
    <div class="card">
      <div class="step">Step 01</div>
      <div class="card-title">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><path d="M4 21v-7M4 10V3M12 21v-9M12 8V3M20 21v-5M20 12V3M1 14h6M9 8h6M17 16h6"/></svg>
        <h2>Technical &amp; Strategic Inputs</h2>
      </div>
      <div class="card-sub">Configure the hybrid asset and market assumptions.</div>

      <div class="form-group">
        <label for="scenario">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 3v18h18"/><path d="M7 15l4-6 3 3 5-8"/></svg>
          Strategic scenario<span class="unit-hint">consulting framework</span>
        </label>
        <select id="scenario">
          <option value="base">Base Case — Standard Vision 2030 trajectory</option>
          <option value="aggressive">Aggressive Transformation — High tech / subsidy</option>
          <option value="pessimistic">Pessimistic Case — Supply chain bottlenecks</option>
        </select>
      </div>

      <div class="form-group">
        <label for="solarInput">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><circle cx="12" cy="12" r="4.5"/><path d="M12 2v2.5M12 19.5V22M2 12h2.5M19.5 12H22M4.9 4.9l1.8 1.8M17.3 17.3l1.8 1.8M19.1 4.9l-1.8 1.8M6.7 17.3l-1.8 1.8"/></svg>
          Solar PV capacity<span class="unit-hint">MW</span>
        </label>
        <input type="number" id="solarInput" value="100" min="0">
      </div>

      <div class="form-group">
        <label for="windInput">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><path d="M9.6 4.6A2 2 0 1111 8H2M12.6 19.4A2 2 0 1014 16H2M17.7 7.7A2.5 2.5 0 1119.5 12H2"/></svg>
          Wind asset capacity<span class="unit-hint">MW</span>
        </label>
        <input type="number" id="windInput" value="50" min="0">
      </div>

      <div class="form-group">
        <label for="electrolyzerSize">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/></svg>
          PEM electrolyzer capacity<span class="unit-hint">MW</span>
        </label>
        <input type="number" id="electrolyzerSize" value="80" min="1">
      </div>

      <div class="form-group">
        <label for="marketPrice">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><path d="M12 1v22M17 5H9.5a3.5 3.5 0 000 7h5a3.5 3.5 0 010 7H6"/></svg>
          Target global market price<span class="unit-hint">$ / kg H₂</span>
        </label>
        <input type="number" id="marketPrice" value="5.50" step="0.1" min="0">
      </div>

      <button class="btn" onclick="calculatePlatform()">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="6 3 20 12 6 21 6 3"/></svg>
        Execute strategic simulation
      </button>
      <div class="live-note">
        <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><path d="M1 12h4l3 8 4-16 3 8h8"/></svg>
        Live mode — outputs and charts also update as you type.
      </div>
    </div>

    <!-- ============ OUTPUTS ============ -->
    <div class="card">
      <div class="step">Step 02</div>
      <div class="card-title">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M8 16v-5M12 16V8M16 16v-3"/></svg>
        <h2>Executive Dashboard &amp; Commercial Metrics</h2>
      </div>
      <div class="card-sub">Core techno-economic outputs of the configured asset.</div>

      <div class="results-box">
        <div class="metric">
          <div class="m-ic"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2v6M12 22a7 7 0 007-7c0-2-1-3.9-3-5.5S12 2 12 2s-2 5.9-4 7.5-3 3.5-3 5.5a7 7 0 007 7z"/></svg></div>
          <div class="label">Annual H₂ production</div>
          <div id="h2Output" class="value">—</div>
        </div>
        <div class="metric">
          <div class="m-ic"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg></div>
          <div class="label">Electrolyzer capacity factor</div>
          <div id="capacityFactor" class="value">—</div>
        </div>
        <div class="metric primary">
          <div class="m-ic"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><path d="M12 1v22M17 5H9.5a3.5 3.5 0 000 7h5a3.5 3.5 0 010 7H6"/></svg></div>
          <div class="label">Levelized cost of H₂ (LCOH)</div>
          <div id="lcohValue" class="value">—</div>
        </div>
        <div class="metric">
          <div class="m-ic"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M23 6l-9.5 9.5-5-5L1 18"/><path d="M17 6h6v6"/></svg></div>
          <div class="label">Net profit margin</div>
          <div id="profitMargin" class="value">—</div>
        </div>
      </div>

      <div class="section-break">
        <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 12h-4l-3 9L9 3l-3 9H2"/></svg>
        <h3>Machine Learning Predictive Layer</h3>
      </div>

      <div class="results-box">
        <div class="metric">
          <div class="m-ic"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 3v18h18"/><path d="M19 9l-5 5-4-4-3 3"/></svg></div>
          <div class="label">Predicted degradation rate</div>
          <div id="degradationRate" class="value warn">—</div>
        </div>
        <div class="metric">
          <div class="m-ic"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M2 22c1.25-1.67 2.5-2.5 5-2.5s3.75 1.67 5 1.67 2.5-1.67 5-1.67 3.75.83 5 2.5M2 17c1.25-1.67 2.5-2.5 5-2.5s3.75 1.67 5 1.67 2.5-1.67 5-1.67 3.75.83 5 2.5M12 2v8M9 7l3 3 3-3"/></svg></div>
          <div class="label">Marginal abatement cost (MAC)</div>
          <div id="macValue" class="value">—</div>
        </div>
      </div>

      <div class="alert-panel" id="strategicInsight">
        <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><circle cx="12" cy="12" r="10"/><path d="M12 16v-4M12 8h.01"/></svg>
        <div><strong>Awaiting simulation</strong>Run the simulation to generate algorithmic insights for project de-risking.</div>
      </div>
    </div>
  </div>
</div>

<!-- ============ POWER BLEND CHART ============ -->
<section class="section">
  <div class="card">
    <div class="step">Step 03</div>
    <div class="card-title">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/></svg>
      <h2>Hybrid Power Blend &amp; Stack Intake — Representative 72 h</h2>
    </div>
    <div class="card-sub">Simulated co-located solar + wind generation against the electrolyzer absorption ceiling. Energy above the ceiling is curtailed.</div>
    <div class="chart-wrap"><svg id="powerChart" viewBox="0 0 1100 300" preserveAspectRatio="xMidYMid meet" role="img" aria-label="72 hour power blend chart"></svg></div>
    <div class="legend">
      <span><i class="dot" style="background:var(--gold)"></i>Solar PV</span>
      <span><i class="dot" style="background:var(--cyan)"></i>Wind</span>
      <span><i class="dot" style="background:var(--navy)"></i>Stack intake</span>
      <span><i class="dot" style="background:var(--line)"></i>Curtailment</span>
    </div>
  </div>
</section>

<!-- ============ ML + SENSITIVITY ============ -->
<section class="section charts-grid">
  <div class="card">
    <div class="card-title">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 12h-4l-3 9L9 3l-3 9H2"/></svg>
      <h2>Predictive Cell Degradation — 10 yr</h2>
    </div>
    <div class="card-sub">Efficiency-fade forecast from the ML-predicted degradation rate, with an uncertainty band and end-of-life replacement trigger.</div>
    <div class="chart-wrap"><svg id="degChart" viewBox="0 0 520 270" role="img" aria-label="Degradation forecast chart"></svg></div>
    <div class="legend">
      <span><i class="dot" style="background:var(--navy)"></i>Current configuration</span>
      <span><i class="dot" style="background:var(--bad)"></i>EOL threshold (85%)</span>
    </div>
  </div>
  <div class="card">
    <div class="card-title">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><path d="M12 3v18M3 12h18M5.6 5.6l12.8 12.8M18.4 5.6L5.6 18.4"/></svg>
      <h2>LCOH Sensitivity — ±15% Parameter Shock</h2>
    </div>
    <div class="card-sub">One-at-a-time perturbation around the live configuration, ranked by impact. Bar length = Δ LCOH in $/kg.</div>
    <div class="chart-wrap"><svg id="tornado" viewBox="0 0 520 270" role="img" aria-label="Sensitivity tornado chart"></svg></div>
    <div class="legend">
      <span><i class="dot" style="background:var(--cyan)"></i>Parameter −15%</span>
      <span><i class="dot" style="background:var(--navy)"></i>Parameter +15%</span>
    </div>
  </div>
</section>

<!-- ============ SCENARIO TABLE ============ -->
<section class="section">
  <div class="sec-head"><h2>Scenario Comparison</h2><span>All three structural baselines evaluated against the live asset configuration</span></div>
  <div class="card" style="padding:8px 6px">
    <table>
      <thead><tr>
        <th>Scenario</th><th class="num">LCOH $/kg</th><th class="num">H₂ t/yr</th><th class="num">Capacity factor</th><th class="num">MAC $/tCO₂</th><th class="num">Margin %</th><th style="text-align:right;padding-right:18px">Status</th>
      </tr></thead>
      <tbody id="scenTable"></tbody>
    </table>
  </div>
</section>

<div class="foot">
  <span>Asset-level techno-economic engine · deterministic simulation core</span>
  <span>Discounted over a 20-year project lifetime · OPEX at 3% of CAPEX</span>
</div>

<script>
"use strict";
/* ================================================================
   Original computational core (unchanged formulas)
   ================================================================ */
const scenarios = {
    base:        { solar: 100, wind: 50,  price: 5.5, factor: 1.00, name: "Base Case" },
    aggressive:  { solar: 150, wind: 100, price: 6.5, factor: 0.85, name: "Aggressive Transformation" },
    pessimistic: { solar: 80,  wind: 20,  price: 4.0, factor: 1.30, name: "Pessimistic Case" }
};

function runModel(solar, wind, electrolyzer, marketPrice, scenKey) {
    let capacityFactor = (solar * 0.25 + wind * 0.40) / electrolyzer;
    if (capacityFactor > 0.9) capacityFactor = 0.9;
    if (!isFinite(capacityFactor) || capacityFactor < 0) capacityFactor = 0;

    const annualHours = 8760;
    const h2PerMWPerHour = 18.5;
    const annualH2Produced = electrolyzer * capacityFactor * annualHours * h2PerMWPerHour;

    const capexBase = electrolyzer * 1100000 + (solar * 800000) + (wind * 1300000);
    const annualOpex = capexBase * 0.03;
    const projectLifetime = 20;

    const localizedCostFactor = scenarios[scenKey].factor;
    const lcoh = annualH2Produced > 0
        ? ((capexBase / projectLifetime) + annualOpex) / annualH2Produced * localizedCostFactor * 10
        : Infinity;

    const netProfitMargin = marketPrice > 0 ? ((marketPrice - lcoh) / marketPrice) * 100 : -100;

    const hybridRatio = wind / (solar + 0.001);
    let predictedDegradation = 1.5 + (1 / (hybridRatio + 0.5));
    if (predictedDegradation > 3.5) predictedDegradation = 3.5;

    const carbonSavedPerKg = 10;
    const annualCarbonSaved = (annualH2Produced * carbonSavedPerKg) / 1000;
    const mac = annualOpex / (annualCarbonSaved + 1);

    return { capacityFactor, annualH2Produced, lcoh, netProfitMargin, predictedDegradation, mac };
}

/* ================================================================
   Hourly renewable profiles (seeded, reproducible) for the chart
   ================================================================ */
function mulberry(seed){return function(){seed|=0;seed=seed+0x6D2B79F5|0;let t=Math.imul(seed^seed>>>15,1|seed);t=t+Math.imul(t^t>>>7,61|t)^t;return((t^t>>>14)>>>0)/4294967296}}
const HOURS = 72;
const solarCF = [], windCF = [];
(function build(){
    const rnd = mulberry(20260720);
    let w = 0.38;
    for(let h=0;h<HOURS;h++){
        const hod = h % 24;
        const sun = Math.max(0, Math.sin(Math.PI*(hod-6)/12));
        const cloud = 1 - 0.10*rnd()*rnd();
        solarCF.push(Math.min(1, 0.97*Math.pow(sun,1.15)*cloud));
        const nightBias = (hod>=19||hod<=6) ? 0.05 : -0.02;
        w += 0.18*(0.40-w) + 0.15*(rnd()-0.5) + nightBias*0.35;
        w = Math.min(0.95, Math.max(0.03, w));
        windCF.push(w);
    }
})();

/* ---------- SVG helpers ---------- */
const NS="http://www.w3.org/2000/svg";
function el(tag,attrs){const e=document.createElementNS(NS,tag);for(const k in attrs)e.setAttribute(k,attrs[k]);return e;}
function txt(x,y,str,size,fill,anchor,weight){const t=el("text",{x,y,"font-size":size,fill,"text-anchor":anchor||"start","font-family":"'IBM Plex Mono',monospace","font-weight":weight||400});t.textContent=str;return t;}
const $id = s => document.getElementById(s);
const fmt = (v,d=2)=> isFinite(v)? v.toLocaleString("en-US",{minimumFractionDigits:d,maximumFractionDigits:d}) : "—";

/* ---------- Chart: power blend (72h stacked area) ---------- */
function drawPower(solar, wind, elec){
    const svg=$id("powerChart"); svg.innerHTML="";
    const W=1100,Hh=300,padL=56,padR=14,padT=16,padB=32;
    const iw=W-padL-padR, ih=Hh-padT-padB;
    let peak=Math.max(elec,10); const sol=[],wnd=[];
    for(let i=0;i<HOURS;i++){
        sol.push(solar*solarCF[i]); wnd.push(wind*windCF[i]);
        peak=Math.max(peak, sol[i]+wnd[i]);
    }
    peak*=1.08;
    const X=i=>padL+i/(HOURS-1)*iw, Y=v=>padT+ih-(v/peak)*ih;

    for(let g=0;g<=4;g++){const v=peak*g/4, y=Y(v);
        svg.appendChild(el("line",{x1:padL,x2:W-padR,y1:y,y2:y,stroke:"#EEF2F7"}));
        svg.appendChild(txt(padL-8,y+4,Math.round(v)+"",10,"#8FA3B8","end"));}
    svg.appendChild(txt(14,padT+10,"MW",10,"#8FA3B8"));

    let dTot="M"+X(0)+" "+Y(sol[0]+wnd[0]);
    for(let i=1;i<HOURS;i++)dTot+=" L"+X(i)+" "+Y(sol[i]+wnd[i]);
    dTot+=" L"+X(HOURS-1)+" "+Y(0)+" L"+X(0)+" "+Y(0)+" Z";
    svg.appendChild(el("path",{d:dTot,fill:"#D8E1EC",opacity:.55}));

    let dW="M"+X(0)+" "+Y(wnd[0]);
    for(let i=1;i<HOURS;i++)dW+=" L"+X(i)+" "+Y(wnd[i]);
    dW+=" L"+X(HOURS-1)+" "+Y(0)+" L"+X(0)+" "+Y(0)+" Z";
    svg.appendChild(el("path",{d:dW,fill:"#1FB2D5",opacity:.75}));

    let dS="M"+X(0)+" "+Y(wnd[0]+sol[0]);
    for(let i=1;i<HOURS;i++)dS+=" L"+X(i)+" "+Y(wnd[i]+sol[i]);
    for(let i=HOURS-1;i>=0;i--)dS+=" L"+X(i)+" "+Y(wnd[i]);
    dS+=" Z";
    svg.appendChild(el("path",{d:dS,fill:"#F0B429",opacity:.85}));

    let dI="";
    for(let i=0;i<HOURS;i++){const v=Math.min(sol[i]+wnd[i],elec);dI+=(i?" L":"M")+X(i)+" "+Y(v);}
    svg.appendChild(el("path",{d:dI,fill:"none",stroke:"#0D2B4F","stroke-width":2.4,"stroke-linejoin":"round"}));

    svg.appendChild(el("line",{x1:padL,x2:W-padR,y1:Y(elec),y2:Y(elec),stroke:"#0D2B4F","stroke-width":1,"stroke-dasharray":"5 4",opacity:.55}));
    svg.appendChild(txt(W-padR,Y(elec)-6,"stack ceiling "+elec+" MW",10,"#64798F","end"));

    for(let d=0;d<3;d++){const x=X(d*24+12);
        svg.appendChild(txt(x,Hh-8,"Day "+(d+1),10.5,"#8FA3B8","middle"));
        if(d)svg.appendChild(el("line",{x1:X(d*24),x2:X(d*24),y1:padT,y2:padT+ih,stroke:"#EEF2F7"}));}
}

/* ---------- Chart: degradation forecast ---------- */
function drawDeg(degRate){
    const svg=$id("degChart"); svg.innerHTML="";
    const W=520,Hh=270,padL=48,padR=16,padT=16,padB=32;
    const iw=W-padL-padR, ih=Hh-padT-padB;
    const yMin=60,yMax=100;
    const X=y=>padL+y/10*iw, Y=v=>padT+ih-(v-yMin)/(yMax-yMin)*ih;
    for(let g=0;g<=4;g++){const v=yMin+(yMax-yMin)*g/4, y=Y(v);
        svg.appendChild(el("line",{x1:padL,x2:W-padR,y1:y,y2:y,stroke:"#EEF2F7"}));
        svg.appendChild(txt(padL-7,y+4,v.toFixed(0)+"%",9.5,"#8FA3B8","end"));}
    svg.appendChild(el("line",{x1:padL,x2:W-padR,y1:Y(85),y2:Y(85),stroke:"#C0392B","stroke-width":1.4,"stroke-dasharray":"5 4"}));

    const eff=(rate,y)=>Math.max(yMin,100*Math.pow(1-rate/100,y));
    let dC="",up="",lo="";
    for(let y=0;y<=10;y+=0.25){
        dC+=(y?" L":"M")+X(y)+" "+Y(eff(degRate,y));
        up+=(y?" L":"M")+X(y)+" "+Y(eff(degRate*0.8,y));
    }
    for(let y=10;y>=0;y-=0.25){lo+=" L"+X(y)+" "+Y(eff(degRate*1.2,y));}
    svg.appendChild(el("path",{d:up+lo+" Z",fill:"#0D2B4F",opacity:.08}));
    svg.appendChild(el("path",{d:dC,fill:"none",stroke:"#0D2B4F","stroke-width":2.4}));

    for(let y=0;y<=10;y+=2)svg.appendChild(txt(X(y),Hh-8,"Y"+y,9.5,"#8FA3B8","middle"));

    const f10=eff(degRate,10);
    svg.appendChild(el("circle",{cx:X(10),cy:Y(f10),r:4,fill:"#1FB2D5",stroke:"#fff","stroke-width":1.5}));
    svg.appendChild(txt(X(10)-6,Y(f10)-9,f10.toFixed(1)+"% @Y10",10,"#0D2B4F","end",600));
    svg.appendChild(txt(padL+4,Y(85)-6,"EOL replacement trigger",9.5,"#C0392B"));

    // Year of EOL crossing
    let eolYear=null;
    for(let y=0;y<=10;y+=0.1){ if(eff(degRate,y)<=85){eolYear=y;break;} }
    if(eolYear!==null){
        svg.appendChild(el("line",{x1:X(eolYear),x2:X(eolYear),y1:Y(85),y2:padT+ih,stroke:"#C0392B","stroke-width":1,"stroke-dasharray":"3 3",opacity:.5}));
        svg.appendChild(txt(X(eolYear),padT+ih-4,"Y"+eolYear.toFixed(1),9,"#C0392B","middle",600));
    }
}

/* ---------- Chart: sensitivity tornado ---------- */
function drawTornado(solar, wind, elec, price, scen, baseLcoh){
    const svg=$id("tornado"); svg.innerHTML="";
    const W=520,Hh=270,padL=140,padR=52,padT=20,padB=28;
    const iw=W-padL-padR, ih=Hh-padT-padB;
    const params=[
        {label:"Solar PV capacity",   run:f=>runModel(solar*f,wind,elec,price,scen).lcoh},
        {label:"Wind capacity",       run:f=>runModel(solar,wind*f,elec,price,scen).lcoh},
        {label:"Stack capacity",      run:f=>runModel(solar,wind,elec*f,price,scen).lcoh},
        {label:"Localization factor", run:f=>baseLcoh*f},
    ];
    const rows=params.map(p=>{
        const lo=p.run(0.85)-baseLcoh, hi=p.run(1.15)-baseLcoh;
        return {label:p.label,lo,hi,span:Math.max(Math.abs(lo),Math.abs(hi))};
    }).sort((a,b)=>b.span-a.span);
    const maxAbs=Math.max(...rows.map(r=>r.span),0.01);
    const cx=padL+iw/2, scale=(iw/2-6)/maxAbs;
    const rowH=ih/rows.length;
    svg.appendChild(el("line",{x1:cx,x2:cx,y1:padT,y2:padT+ih,stroke:"#D8E1EC","stroke-width":1.4}));
    rows.forEach((r,i)=>{
        const y=padT+i*rowH+rowH/2, bh=Math.min(18,rowH*0.42);
        svg.appendChild(txt(padL-8,y+4,r.label,10.5,"#64798F","end"));
        const seg=(v,color)=>{
            if(!isFinite(v))return;
            const w=Math.abs(v)*scale;
            svg.appendChild(el("rect",{x:v<0?cx-w:cx,y:y-bh/2,width:Math.max(w,0.5),height:bh,rx:3,fill:color,opacity:.92}));
            svg.appendChild(txt(v<0?cx-w-5:cx+w+5,y+4,(v>=0?"+":"")+v.toFixed(2),9,"#64798F",v<0?"end":"start"));
        };
        seg(r.lo,"#1FB2D5"); seg(r.hi,"#0D2B4F");
    });
    svg.appendChild(txt(cx,Hh-6,"Δ LCOH ($/kg)",9.5,"#8FA3B8","middle"));
}

/* ---------- Scenario table ---------- */
function fillTable(solar, wind, elec, price, activeScen){
    const tb=$id("scenTable"); tb.innerHTML="";
    for(const key of ["base","aggressive","pessimistic"]){
        const s=scenarios[key];
        const r=runModel(solar, wind, elec, s.price, key);
        const ok=r.netProfitMargin>20, watch=r.netProfitMargin>0&&r.netProfitMargin<=20;
        const badge=ok?'<span class="badge ok">Bankable</span>':watch?'<span class="badge watch">Marginal</span>':'<span class="badge risk">At risk</span>';
        const tr=document.createElement("tr");
        if(key===activeScen)tr.style.background="#F4F8FC";
        tr.innerHTML=`<td style="font-weight:600;color:var(--navy)">${s.name}${key===activeScen?' <span style="font-size:10px;color:var(--cyan-dk);font-weight:600;letter-spacing:.08em">· ACTIVE</span>':''}</td>
            <td class="num">${fmt(r.lcoh)}</td>
            <td class="num">${fmt(r.annualH2Produced/1000,0)}</td>
            <td class="num">${fmt(r.capacityFactor*100,1)}%</td>
            <td class="num">${fmt(r.mac,2)}</td>
            <td class="num" style="color:${r.netProfitMargin>=0?'var(--good)':'var(--bad)'}">${fmt(r.netProfitMargin,1)}</td>
            <td style="text-align:right;padding-right:18px">${badge}</td>`;
        tb.appendChild(tr);
    }
}

/* ---------- Insight icons ---------- */
const ICONS = {
    ok: '<svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 11.08V12a10 10 0 11-5.93-9.14"/><path d="M22 4L12 14.01l-3-3"/></svg>',
    watch: '<svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M10.29 3.86L1.82 18a2 2 0 001.71 3h16.94a2 2 0 001.71-3L13.71 3.86a2 2 0 00-3.42 0z"/><path d="M12 9v4M12 17h.01"/></svg>',
    risk: '<svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><circle cx="12" cy="12" r="10"/><path d="M15 9l-6 6M9 9l6 6"/></svg>'
};

/* ---------- Main render ---------- */
function calculatePlatform() {
    const solar = parseFloat($id("solarInput").value) || 0;
    const wind = parseFloat($id("windInput").value) || 0;
    const electrolyzer = parseFloat($id("electrolyzerSize").value) || 1;
    const marketPrice = parseFloat($id("marketPrice").value) || 0;
    const scenKey = $id("scenario").value;

    const r = runModel(solar, wind, electrolyzer, marketPrice, scenKey);

    $id("h2Output").innerHTML = fmt(r.annualH2Produced/1000,1) + "<small>t/yr</small>";
    $id("capacityFactor").innerHTML = fmt(r.capacityFactor*100,1) + "<small>%</small>";
    $id("lcohValue").innerHTML = "$" + fmt(r.lcoh) + "<small>/kg</small>";
    const pm = $id("profitMargin");
    pm.innerHTML = fmt(r.netProfitMargin,1) + "<small>%</small>";
    pm.className = "value " + (r.netProfitMargin >= 20 ? "pos" : r.netProfitMargin >= 0 ? "warn" : "neg");
    $id("degradationRate").innerHTML = fmt(r.predictedDegradation) + "<small>%/yr</small>";
    $id("macValue").innerHTML = "$" + fmt(r.mac) + "<small>/tCO₂</small>";

    const panel = $id("strategicInsight");
    let insightText = "", cls = "", icon = "";
    if (r.netProfitMargin > 20) {
        cls = "ok"; icon = ICONS.ok;
        insightText = `<strong>Strong investment case</strong>The hybrid configuration achieves a healthy capacity factor of ${(r.capacityFactor*100).toFixed(0)}%, robustly absorbing market volatility. Financial risk profile is effectively mitigated.`;
    } else if (r.netProfitMargin > 0) {
        cls = "watch"; icon = ICONS.watch;
        insightText = `<strong>Marginal viability</strong>Tight commercial margin discovered. Advise optimizing the solar-to-wind capacity ratio to stabilize input currents and reduce the ML-predicted degradation rate of ${fmt(r.predictedDegradation)}%/yr.`;
    } else {
        cls = "risk"; icon = ICONS.risk;
        insightText = `<strong>Strategic rejection</strong>LCOH of $${fmt(r.lcoh)}/kg exceeds the target selling price of $${fmt(marketPrice)}/kg. Financial restructuring or localized technology subsidies are required to bridge the feasibility gap.`;
    }
    panel.className = "alert-panel " + cls;
    panel.innerHTML = icon + "<div>" + insightText + "</div>";

    drawPower(solar, wind, electrolyzer);
    drawDeg(r.predictedDegradation);
    drawTornado(solar, wind, electrolyzer, marketPrice, scenKey, r.lcoh);
    fillTable(solar, wind, electrolyzer, marketPrice, scenKey);
}

function applyScenario() {
    const selected = $id("scenario").value;
    $id("solarInput").value = scenarios[selected].solar;
    $id("windInput").value = scenarios[selected].wind;
    $id("marketPrice").value = scenarios[selected].price;
    calculatePlatform();
}

/* Live mode: update on any input change */
$id("scenario").addEventListener("change", applyScenario);
["solarInput","windInput","electrolyzerSize","marketPrice"].forEach(id=>
    $id(id).addEventListener("input", calculatePlatform));

calculatePlatform();
</script>

</body>
</html>
