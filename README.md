<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>H₂ Quant — Green Hydrogen De-Risking Platform</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Archivo:wght@500;600;700;800&family=Inter:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
:root{
  --ink:#081C36; --navy:#0D2B4F; --navy2:#16406F;
  --paper:#FFFFFF; --cloud:#EEF2F7; --line:#D8E1EC;
  --steel:#64798F; --steel2:#8FA3B8;
  --cyan:#1FB2D5; --cyan-dk:#0E85A3;
  --good:#1B9E77; --bad:#C0392B;
  --radius:10px;
}
*{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth}
body{font-family:'Inter',sans-serif;background:var(--cloud);color:var(--ink);font-size:14px;line-height:1.5}
.mono{font-family:'IBM Plex Mono',monospace}

/* ---------- Shell ---------- */
.shell{display:grid;grid-template-columns:220px 1fr;min-height:100vh}
.rail{background:var(--ink);color:#C7D5E5;padding:26px 0;position:sticky;top:0;height:100vh;display:flex;flex-direction:column}
.brand{display:flex;align-items:center;gap:10px;padding:0 22px 24px;border-bottom:1px solid rgba(255,255,255,.08)}
.brand svg{flex:none}
.brand-name{font-family:'Archivo',sans-serif;font-weight:700;font-size:15px;color:#fff;letter-spacing:.02em}
.brand-sub{font-size:10px;letter-spacing:.14em;text-transform:uppercase;color:var(--steel2)}
.nav{margin-top:18px;flex:1}
.nav a{display:flex;align-items:center;gap:12px;padding:11px 22px;color:#AFC2D6;text-decoration:none;font-size:13px;font-weight:500;border-left:3px solid transparent;transition:.15s}
.nav a:hover,.nav a.active{color:#fff;background:rgba(255,255,255,.05);border-left-color:var(--cyan)}
.nav svg{stroke:currentColor;flex:none}
.rail-foot{padding:18px 22px;font-size:10.5px;color:var(--steel);border-top:1px solid rgba(255,255,255,.08);line-height:1.6}

/* ---------- Header ---------- */
.main{padding:0 34px 60px}
.hero{background:linear-gradient(115deg,var(--ink) 0%,var(--navy) 55%,var(--navy2) 100%);color:#fff;margin:0 -34px;padding:34px 34px 30px;position:relative;overflow:hidden}
.hero::after{content:"";position:absolute;right:-60px;top:-80px;width:420px;height:420px;border:1px solid rgba(255,255,255,.07);border-radius:50%}
.hero::before{content:"";position:absolute;right:40px;top:-140px;width:420px;height:420px;border:1px solid rgba(31,178,213,.18);border-radius:50%}
.eyebrow{font-size:10.5px;letter-spacing:.22em;text-transform:uppercase;color:var(--cyan);font-weight:600;margin-bottom:10px}
.hero h1{font-family:'Archivo',sans-serif;font-weight:800;font-size:29px;letter-spacing:-.01em;max-width:640px;line-height:1.2}
.hero p{margin-top:10px;color:#B9C9DB;max-width:560px;font-size:13.5px}
.hero-meta{display:flex;gap:28px;margin-top:22px;position:relative;z-index:1}
.hero-meta div{font-size:11px;color:var(--steel2);text-transform:uppercase;letter-spacing:.1em}
.hero-meta b{display:block;font-family:'IBM Plex Mono',monospace;font-size:15px;color:#fff;font-weight:600;letter-spacing:0;text-transform:none;margin-top:3px}

/* ---------- Scenario bar ---------- */
.scen-bar{display:flex;align-items:center;gap:14px;background:var(--paper);border:1px solid var(--line);border-radius:var(--radius);padding:14px 18px;margin-top:-24px;position:relative;z-index:2;box-shadow:0 8px 24px rgba(8,28,54,.08)}
.scen-label{font-size:11px;font-weight:600;letter-spacing:.12em;text-transform:uppercase;color:var(--steel)}
.scen-group{display:flex;background:var(--cloud);border-radius:8px;padding:4px;gap:4px}
.scen-btn{border:none;background:transparent;padding:8px 16px;border-radius:6px;font-family:'Inter',sans-serif;font-size:13px;font-weight:600;color:var(--steel);cursor:pointer;transition:.15s}
.scen-btn.active{background:var(--ink);color:#fff}
.scen-note{margin-left:auto;font-size:12px;color:var(--steel);display:flex;align-items:center;gap:8px}
.scen-note svg{stroke:var(--cyan-dk)}

/* ---------- Sections ---------- */
.section{margin-top:34px}
.sec-head{display:flex;align-items:baseline;gap:14px;margin-bottom:16px}
.sec-head h2{font-family:'Archivo',sans-serif;font-weight:700;font-size:18px;letter-spacing:-.01em}
.sec-head span{font-size:12px;color:var(--steel)}

/* ---------- KPI cards ---------- */
.kpis{display:grid;grid-template-columns:repeat(5,1fr);gap:14px}
.kpi{background:var(--paper);border:1px solid var(--line);border-radius:var(--radius);padding:18px 18px 16px;position:relative}
.kpi .k-ic{position:absolute;top:16px;right:16px;color:var(--steel2)}
.kpi .k-label{font-size:11px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:var(--steel)}
.kpi .k-val{font-family:'IBM Plex Mono',monospace;font-size:26px;font-weight:600;margin-top:8px;letter-spacing:-.02em}
.kpi .k-unit{font-size:12px;color:var(--steel);font-weight:400;margin-left:3px}
.kpi .k-delta{margin-top:6px;font-size:11.5px;font-weight:500;display:flex;align-items:center;gap:5px}
.k-delta.up{color:var(--good)} .k-delta.down{color:var(--bad)} .k-delta.flat{color:var(--steel)}
.kpi.hl{background:var(--ink);border-color:var(--ink);color:#fff}
.kpi.hl .k-label{color:var(--steel2)} .kpi.hl .k-val{color:var(--cyan)} .kpi.hl .k-unit{color:var(--steel2)} .kpi.hl .k-ic{color:var(--cyan-dk)}

/* ---------- Layout grid ---------- */
.grid{display:grid;grid-template-columns:340px 1fr;gap:20px;align-items:start}
.card{background:var(--paper);border:1px solid var(--line);border-radius:var(--radius);padding:22px}
.card h3{font-family:'Archivo',sans-serif;font-size:14.5px;font-weight:700;display:flex;align-items:center;gap:9px;margin-bottom:4px}
.card h3 svg{stroke:var(--navy2)}
.card .sub{font-size:12px;color:var(--steel);margin-bottom:18px}

/* ---------- Sliders ---------- */
.ctl{margin-bottom:18px}
.ctl-row{display:flex;justify-content:space-between;align-items:baseline;margin-bottom:7px}
.ctl-row label{font-size:12.5px;font-weight:600;color:var(--navy)}
.ctl-row output{font-family:'IBM Plex Mono',monospace;font-size:13px;font-weight:600;color:var(--ink);background:var(--cloud);padding:2px 9px;border-radius:5px}
input[type=range]{width:100%;height:4px;-webkit-appearance:none;appearance:none;background:linear-gradient(to right,var(--navy2) var(--fill,50%),var(--line) var(--fill,50%));border-radius:99px;outline:none;cursor:pointer}
input[type=range]::-webkit-slider-thumb{-webkit-appearance:none;width:16px;height:16px;border-radius:50%;background:var(--paper);border:3px solid var(--navy2);box-shadow:0 1px 4px rgba(8,28,54,.25);transition:.12s}
input[type=range]::-webkit-slider-thumb:hover{transform:scale(1.15)}
input[type=range]:focus-visible{outline:2px solid var(--cyan);outline-offset:4px}
.ctl-hint{font-size:10.5px;color:var(--steel2);margin-top:5px}
.divider{border:none;border-top:1px solid var(--line);margin:20px 0}

/* ---------- Charts ---------- */
.chart-wrap{width:100%}
.chart-wrap svg{width:100%;height:auto;display:block}
.legend{display:flex;gap:18px;margin-top:12px;flex-wrap:wrap}
.legend span{display:flex;align-items:center;gap:7px;font-size:11.5px;color:var(--steel);font-weight:500}
.dot{width:10px;height:10px;border-radius:3px;flex:none}
.two-col{display:grid;grid-template-columns:1fr 1fr;gap:20px}

/* ---------- Table ---------- */
table{width:100%;border-collapse:collapse;font-size:13px}
th{font-size:10.5px;text-transform:uppercase;letter-spacing:.1em;color:var(--steel);font-weight:600;text-align:left;padding:9px 12px;border-bottom:1px solid var(--line)}
td{padding:11px 12px;border-bottom:1px solid var(--cloud)}
td.num{font-family:'IBM Plex Mono',monospace;font-weight:500;text-align:right}
th.num{text-align:right}
tr:last-child td{border-bottom:none}
.badge{display:inline-flex;align-items:center;gap:6px;padding:3px 10px;border-radius:99px;font-size:11px;font-weight:600}
.badge.ok{background:#E4F4EE;color:var(--good)}
.badge.risk{background:#FBEAE7;color:var(--bad)}
.badge.watch{background:#FFF4DE;color:#9A6B00}

/* ---------- Verdict ---------- */
.verdict{display:grid;grid-template-columns:1fr auto;gap:20px;align-items:center;background:var(--ink);color:#fff;border-radius:var(--radius);padding:24px 26px}
.verdict h3{font-family:'Archivo',sans-serif;font-size:16px;font-weight:700;margin-bottom:6px}
.verdict p{color:#B9C9DB;font-size:13px;max-width:640px}
.verdict .big{font-family:'IBM Plex Mono',monospace;font-size:34px;font-weight:600;text-align:right}
.verdict .big small{display:block;font-family:'Inter',sans-serif;font-size:11px;letter-spacing:.12em;text-transform:uppercase;color:var(--steel2);margin-top:4px}

@media(max-width:1080px){.kpis{grid-template-columns:repeat(2,1fr)}.grid,.two-col{grid-template-columns:1fr}.shell{grid-template-columns:1fr}.rail{position:relative;height:auto;flex-direction:row;align-items:center;padding:12px 16px}.nav{display:flex;margin:0;flex:1;justify-content:flex-end}.nav a{border-left:none;padding:8px 10px}.nav a span{display:none}.rail-foot,.brand-sub{display:none}}
@media(prefers-reduced-motion:reduce){*{transition:none!important}}
</style>
</head>
<body>
<div class="shell">

<!-- ============ SIDE RAIL ============ -->
<aside class="rail">
  <div class="brand">
    <svg width="30" height="30" viewBox="0 0 30 30" fill="none"><rect x="1.5" y="1.5" width="27" height="27" rx="7" stroke="#1FB2D5" stroke-width="2"/><path d="M9 8v14M21 8v14M9 15h12" stroke="#fff" stroke-width="2.4" stroke-linecap="round"/></svg>
    <div>
      <div class="brand-name">H₂ QUANT</div>
      <div class="brand-sub">De-Risking Platform</div>
    </div>
  </div>
  <nav class="nav">
    <a href="#config" class="active"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><path d="M4 21v-7M4 10V3M12 21v-9M12 8V3M20 21v-5M20 12V3M1 14h6M9 8h6M17 16h6"/></svg><span>Asset Configuration</span></a>
    <a href="#engineering"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/></svg><span>Power &amp; Electrolysis</span></a>
    <a href="#ml"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 12h-4l-3 9L9 3l-3 9H2"/></svg><span>Degradation Forecast</span></a>
    <a href="#economics"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><path d="M12 1v22M17 5H9.5a3.5 3.5 0 000 7h5a3.5 3.5 0 010 7H6"/></svg><span>LCOH &amp; Sensitivity</span></a>
    <a href="#viability"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg><span>Commercial Viability</span></a>
  </nav>
  <div class="rail-foot">Asset-level techno-economic engine · KSA energy transition portfolio · v2.1</div>
</aside>

<!-- ============ MAIN ============ -->
<main class="main">

<header class="hero">
  <div class="eyebrow">Quantitative Simulation Framework</div>
  <h1>De-Risking Green Hydrogen Infrastructure</h1>
  <p>Asset-level decision framework integrating hybrid renewable intermittency, PEM electrolyzer engineering, predictive cell degradation, and discounted cash-flow economics under shifting market scenarios.</p>
  <div class="hero-meta">
    <div>Simulation horizon<b>8,760 h × 20 yr</b></div>
    <div>Discount rate (WACC)<b>8.0 %</b></div>
    <div>Grey H₂ benchmark<b>$1.50 /kg</b></div>
    <div>CO₂ avoided factor<b>10.0 kg / kg H₂</b></div>
  </div>
</header>

<!-- Scenario switcher -->
<div class="scen-bar" id="config">
  <span class="scen-label">Scenario</span>
  <div class="scen-group" role="tablist">
    <button class="scen-btn active" data-scen="base" role="tab">Base Case</button>
    <button class="scen-btn" data-scen="aggressive" role="tab">Aggressive Transformation</button>
    <button class="scen-btn" data-scen="pessimistic" role="tab">Pessimistic</button>
  </div>
  <span class="scen-note"><svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><circle cx="12" cy="12" r="10"/><path d="M12 16v-4M12 8h.01"/></svg><span id="scenDesc">Standard diversification trajectory — reference CAPEX and learning rates.</span></span>
</div>

<!-- KPI row -->
<section class="section">
  <div class="kpis" id="kpiRow">
    <div class="kpi hl">
      <div class="k-ic"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><path d="M12 1v22M17 5H9.5a3.5 3.5 0 000 7h5a3.5 3.5 0 010 7H6"/></svg></div>
      <div class="k-label">Levelized Cost of H₂</div>
      <div class="k-val"><span id="kLcoh">—</span><span class="k-unit">$/kg</span></div>
      <div class="k-delta flat" id="kLcohD">vs. market target</div>
    </div>
    <div class="kpi">
      <div class="k-ic"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2v6M12 22a7 7 0 007-7c0-2-1-3.9-3-5.5S12 2 12 2s-2 5.9-4 7.5-3 3.5-3 5.5a7 7 0 007 7z"/></svg></div>
      <div class="k-label">Annual H₂ Output</div>
      <div class="k-val"><span id="kH2">—</span><span class="k-unit">t/yr</span></div>
      <div class="k-delta flat" id="kH2D">year-1 production</div>
    </div>
    <div class="kpi">
      <div class="k-ic"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg></div>
      <div class="k-label">Electrolyzer Load Factor</div>
      <div class="k-val"><span id="kCF">—</span><span class="k-unit">%</span></div>
      <div class="k-delta flat" id="kCFD">utilization of stack</div>
    </div>
    <div class="kpi">
      <div class="k-ic"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M2 22c1.25-1.67 2.5-2.5 5-2.5s3.75 1.67 5 1.67 2.5-1.67 5-1.67 3.75.83 5 2.5M2 17c1.25-1.67 2.5-2.5 5-2.5s3.75 1.67 5 1.67 2.5-1.67 5-1.67 3.75.83 5 2.5M12 2v8M9 7l3 3 3-3"/></svg></div>
      <div class="k-label">Marginal Abatement Cost</div>
      <div class="k-val"><span id="kMac">—</span><span class="k-unit">$/tCO₂</span></div>
      <div class="k-delta flat" id="kMacD">vs. grey hydrogen route</div>
    </div>
    <div class="kpi">
      <div class="k-ic"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M23 6l-9.5 9.5-5-5L1 18"/><path d="M17 6h6v6"/></svg></div>
      <div class="k-label">Net Margin @ Market</div>
      <div class="k-val"><span id="kMargin">—</span><span class="k-unit">%</span></div>
      <div class="k-delta flat" id="kMarginD">against target price</div>
    </div>
  </div>
</section>

<!-- Config + Power chart -->
<section class="section grid" id="engineering">
  <div class="card">
    <h3><svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><path d="M4 21v-7M4 10V3M12 21v-9M12 8V3M20 21v-5M20 12V3M1 14h6M9 8h6M17 16h6"/></svg>Asset Configuration</h3>
    <div class="sub">Hybrid intermittency blending against fixed stack capacity.</div>

    <div class="ctl"><div class="ctl-row"><label for="sSolar">Solar PV capacity</label><output id="oSolar">120 MW</output></div>
      <input type="range" id="sSolar" min="0" max="400" step="5" value="120">
      <div class="ctl-hint">Diurnal profile · DNI-calibrated for northwest KSA</div></div>

    <div class="ctl"><div class="ctl-row"><label for="sWind">Wind capacity</label><output id="oWind">80 MW</output></div>
      <input type="range" id="sWind" min="0" max="400" step="5" value="80">
      <div class="ctl-hint">Stochastic Weibull draw · nocturnal complementarity</div></div>

    <div class="ctl"><div class="ctl-row"><label for="sElec">PEM electrolyzer capacity</label><output id="oElec">100 MW</output></div>
      <input type="range" id="sElec" min="10" max="400" step="5" value="100">
      <div class="ctl-hint">Min. turndown 10% · SEC 55 kWh/kg at BOL</div></div>

    <hr class="divider">

    <div class="ctl"><div class="ctl-row"><label for="sCapex">Electrolyzer CAPEX</label><output id="oCapex">$900 /kW</output></div>
      <input type="range" id="sCapex" min="400" max="1600" step="25" value="900"></div>

    <div class="ctl"><div class="ctl-row"><label for="sWacc">Discount rate (WACC)</label><output id="oWacc">8.0 %</output></div>
      <input type="range" id="sWacc" min="4" max="14" step="0.5" value="8"></div>

    <div class="ctl" style="margin-bottom:4px"><div class="ctl-row"><label for="sPrice">Target market price</label><output id="oPrice">$4.50 /kg</output></div>
      <input type="range" id="sPrice" min="1.5" max="8" step="0.1" value="4.5"></div>
  </div>

  <div>
    <div class="card">
      <h3><svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/></svg>Hybrid Power Blend &amp; Stack Intake — Representative 72 h</h3>
      <div class="sub">Simulated co-located generation vs. electrolyzer absorption ceiling. Curtailed energy shown as the gap above the stack line.</div>
      <div class="chart-wrap"><svg id="powerChart" viewBox="0 0 900 300" preserveAspectRatio="xMidYMid meet" role="img" aria-label="72 hour power blend chart"></svg></div>
      <div class="legend">
        <span><i class="dot" style="background:#F0B429"></i>Solar PV</span>
        <span><i class="dot" style="background:#1FB2D5"></i>Wind</span>
        <span><i class="dot" style="background:#0D2B4F"></i>Stack intake</span>
        <span><i class="dot" style="background:#D8E1EC"></i>Curtailment</span>
      </div>
    </div>

    <div class="two-col" style="margin-top:20px" id="ml">
      <div class="card">
        <h3><svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 12h-4l-3 9L9 3l-3 9H2"/></svg>Predictive Cell Degradation — 10 yr</h3>
        <div class="sub">Voltage-decay forecast driven by measured power ramp volatility. Higher intermittency accelerates stack fade.</div>
        <div class="chart-wrap"><svg id="degChart" viewBox="0 0 440 260" role="img" aria-label="Degradation forecast chart"></svg></div>
        <div class="legend">
          <span><i class="dot" style="background:#0D2B4F"></i>Current configuration</span>
          <span><i class="dot" style="background:#C0392B"></i>EOL threshold (85%)</span>
        </div>
      </div>
      <div class="card">
        <h3><svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><path d="M12 3v18M3 12h18M5.6 5.6l12.8 12.8M18.4 5.6L5.6 18.4"/></svg>LCOH Sensitivity — ±15% Parameter Shock</h3>
        <div class="sub">One-at-a-time perturbation around the live configuration. Bar length = Δ LCOH in $/kg.</div>
        <div class="chart-wrap"><svg id="tornado" viewBox="0 0 440 260" role="img" aria-label="Sensitivity tornado chart"></svg></div>
        <div class="legend">
          <span><i class="dot" style="background:#1FB2D5"></i>−15% shock</span>
          <span><i class="dot" style="background:#0D2B4F"></i>+15% shock</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- Economics table -->
<section class="section" id="economics">
  <div class="sec-head"><h2>Scenario Comparison</h2><span>All three structural baselines evaluated against the live asset configuration</span></div>
  <div class="card" style="padding:8px 6px">
    <table>
      <thead><tr>
        <th>Scenario</th><th class="num">LCOH $/kg</th><th class="num">H₂ t/yr</th><th class="num">Stack fade @10yr</th><th class="num">MAC $/tCO₂</th><th class="num">Margin %</th><th style="text-align:right;padding-right:18px">Status</th>
      </tr></thead>
      <tbody id="scenTable"></tbody>
    </table>
  </div>
</section>

<!-- Verdict -->
<section class="section" id="viability">
  <div class="verdict">
    <div>
      <h3 id="vTitle">Commercial verdict</h3>
      <p id="vText">—</p>
    </div>
    <div class="big"><span id="vNum">—</span><small id="vLabel">Break-even price $/kg</small></div>
  </div>
</section>

</main>
</div>

<script>
"use strict";
/* ================================================================
   Deterministic techno-economic engine
   ================================================================ */
const H = 8760, LIFE = 20, SEC_BOL = 55;          // kWh per kg at beginning of life
const GREY_COST = 1.50, CO2_PER_KG = 10;          // kg CO2 avoided per kg H2 (vs SMR)
const OPEX_PCT = 0.035, RE_SOLAR_CAPEX = 550, RE_WIND_CAPEX = 1150; // $/kW
const WATER_ELEC_OTHER = 0.25;                     // $/kg variable

const SCEN = {
  base:       {name:"Base Case",                capexMul:1.00, secMul:1.00, degMul:1.00, availability:0.97,
               desc:"Standard diversification trajectory — reference CAPEX and learning rates."},
  aggressive: {name:"Aggressive Transformation", capexMul:0.72, secMul:0.93, degMul:0.75, availability:0.98,
               desc:"Accelerated technology learning, high-capacity scaling, optimized balance-of-plant."},
  pessimistic:{name:"Pessimistic Case",          capexMul:1.30, secMul:1.06, degMul:1.45, availability:0.93,
               desc:"Supply-chain shocks, sub-optimal resource realization, elevated financing friction."}
};
let activeScen = "base";

/* Seeded PRNG → reproducible wind stochastics */
function mulberry(seed){return function(){seed|=0;seed=seed+0x6D2B79F5|0;let t=Math.imul(seed^seed>>>15,1|seed);t=t+Math.imul(t^t>>>7,61|t)^t;return((t^t>>>14)>>>0)/4294967296}}

/* Hourly capacity-factor profiles (built once) */
const solarCF = new Float64Array(H), windCF = new Float64Array(H);
(function build(){
  const rnd = mulberry(20260720);
  let w = 0.35;
  for(let h=0;h<H;h++){
    const day = Math.floor(h/24), hod = h%24;
    const season = 0.88 + 0.12*Math.cos(2*Math.PI*(day-172)/365);        // summer peak
    const sun = Math.max(0, Math.sin(Math.PI*(hod-6)/12));               // 06→18
    const cloud = 1 - 0.12*rnd()*rnd();
    solarCF[h] = Math.min(1, 0.98*season*Math.pow(sun,1.15)*cloud);
    // wind: mean-reverting walk with nocturnal bias
    const nightBias = hod>=19||hod<=6 ? 0.06 : -0.02;
    w += 0.18*(0.38-w) + 0.14*(rnd()-0.5) + nightBias*0.3;
    w = Math.min(0.95, Math.max(0.02, w));
    windCF[h] = w;
  }
})();

/* Core simulation for a given config + scenario */
function simulate(cfg, s){
  const {solar, wind, elec} = cfg;
  const minLoad = 0.10*elec;
  let e_in=0, e_avail=0, hoursOn=0, prev=0, volAcc=0;
  const sec = SEC_BOL*s.secMul;
  for(let h=0;h<H;h++){
    const gen = solar*solarCF[h] + wind*windCF[h];
    e_avail += gen;
    let p = Math.min(gen, elec);
    if(p < minLoad) p = 0; else hoursOn++;
    p *= s.availability;
    e_in += p;
    volAcc += Math.abs(p-prev); prev = p;
  }
  const h2kg = e_in*1000/sec;                                  // kWh→kg
  const loadFactor = e_in/(elec*H);
  const rampVol = volAcc/(H*elec);                             // normalized MW ramp per hour
  // Degradation: base 0.55%/yr scaled by volatility & cycling, scenario multiplier
  const cycles = 1 - hoursOn/H;
  const degRate = (0.45 + 3.2*rampVol + 1.1*cycles) * s.degMul; // %/yr efficiency fade
  // Economics
  const capex = elec*1000*cfg.capex*s.capexMul + solar*1000*RE_SOLAR_CAPEX + wind*1000*RE_WIND_CAPEX;
  const r = cfg.wacc/100;
  const crf = r*Math.pow(1+r,LIFE)/(Math.pow(1+r,LIFE)-1);
  const opex = capex*OPEX_PCT;
  // Lifetime-average output haircut from degradation (efficiency fade raises SEC)
  let lifeH2=0; for(let y=0;y<LIFE;y++){ lifeH2 += h2kg/(1+degRate/100*Math.min(y,10)); }
  const avgH2 = lifeH2/LIFE;
  const lcoh = avgH2>0 ? (capex*crf + opex)/avgH2 + WATER_ELEC_OTHER : Infinity;
  const mac = (lcoh-GREY_COST)/(CO2_PER_KG/1000);              // $/t CO2
  const margin = cfg.price>0 ? (cfg.price-lcoh)/cfg.price*100 : 0;
  const fade10 = Math.min(40, degRate*10);
  return {h2kg, loadFactor, lcoh, mac, margin, degRate, fade10, curtail:1-e_in/Math.max(1,e_avail), breakeven:lcoh};
}

/* ================================================================
   DOM wiring
   ================================================================ */
const $ = id => document.getElementById(id);
const sliders = {solar:$("sSolar"), wind:$("sWind"), elec:$("sElec"), capex:$("sCapex"), wacc:$("sWacc"), price:$("sPrice")};
const outs = {solar:$("oSolar"), wind:$("oWind"), elec:$("oElec"), capex:$("oCapex"), wacc:$("oWacc"), price:$("oPrice")};

function cfgNow(){
  return {solar:+sliders.solar.value, wind:+sliders.wind.value, elec:+sliders.elec.value,
          capex:+sliders.capex.value, wacc:+sliders.wacc.value, price:+sliders.price.value};
}
function paintFill(el){ const p=(el.value-el.min)/(el.max-el.min)*100; el.style.setProperty("--fill",p+"%"); }

const fmt = (v,d=2)=> isFinite(v)? v.toLocaleString("en-US",{minimumFractionDigits:d,maximumFractionDigits:d}) : "—";

function render(){
  const cfg = cfgNow(), s = SCEN[activeScen];
  outs.solar.textContent = cfg.solar+" MW"; outs.wind.textContent = cfg.wind+" MW";
  outs.elec.textContent = cfg.elec+" MW";  outs.capex.textContent = "$"+cfg.capex+" /kW";
  outs.wacc.textContent = fmt(cfg.wacc,1)+" %"; outs.price.textContent = "$"+fmt(cfg.price,2)+" /kg";
  Object.values(sliders).forEach(paintFill);

  const r = simulate(cfg, s);
  $("kLcoh").textContent = fmt(r.lcoh);
  $("kH2").textContent  = fmt(r.h2kg/1000,0);
  $("kCF").textContent  = fmt(r.loadFactor*100,1);
  $("kMac").textContent = fmt(r.mac,0);
  $("kMargin").textContent = fmt(r.margin,1);

  setDelta($("kLcohD"), cfg.price-r.lcoh, v=> v>=0 ? fmt(v)+" $/kg headroom vs. target" : fmt(-v)+" $/kg above target", true);
  setDelta($("kMarginD"), r.margin, v=> v>=0 ? "profitable at target price" : "loss-making at target price");
  $("kH2D").textContent = fmt(r.curtail*100,1)+"% energy curtailed";
  $("kH2D").className = "k-delta "+(r.curtail>0.25?"down":"flat");
  $("kCFD").textContent = r.loadFactor<0.35 ? "under-utilized stack" : r.loadFactor>0.6 ? "well-utilized stack" : "moderate utilization";
  $("kCFD").className = "k-delta "+(r.loadFactor<0.35?"down":r.loadFactor>0.6?"up":"flat");
  $("kMacD").textContent = r.mac<150 ? "competitive abatement" : r.mac<300 ? "mid-range abatement" : "high-cost abatement";
  $("kMacD").className = "k-delta "+(r.mac<150?"up":r.mac<300?"flat":"down");

  drawPower(cfg);
  drawDeg(r, s);
  drawTornado(cfg, s, r.lcoh);
  fillTable(cfg);
  verdict(cfg, r);
}
function setDelta(el, v, msg, useSign){
  el.textContent = msg(v);
  el.className = "k-delta "+(v>=0?"up":"down");
}

/* ---------- SVG helpers ---------- */
const NS="http://www.w3.org/2000/svg";
function el(tag,attrs){const e=document.createElementNS(NS,tag);for(const k in attrs)e.setAttribute(k,attrs[k]);return e;}
function txt(x,y,str,size,fill,anchor,weight){const t=el("text",{x,y,"font-size":size,fill,"text-anchor":anchor||"start","font-family":"'IBM Plex Mono',monospace","font-weight":weight||400});t.textContent=str;return t;}

/* ---------- Chart: power blend (72h stacked area) ---------- */
function drawPower(cfg){
  const svg=$("powerChart"); svg.innerHTML="";
  const W=900,Hh=300,padL=54,padR=12,padT=16,padB=32;
  const n=72,start=24*181;                       // three summer days
  const iw=W-padL-padR, ih=Hh-padT-padB;
  let peak=0; const sol=[],wnd=[];
  for(let i=0;i<n;i++){const h=start+i;
    sol.push(cfg.solar*solarCF[h]); wnd.push(cfg.wind*windCF[h]);
    peak=Math.max(peak, sol[i]+wnd[i], cfg.elec);}
  peak=Math.max(peak*1.08, 10);
  const X=i=>padL+i/(n-1)*iw, Y=v=>padT+ih-(v/peak)*ih;

  // grid + y labels
  for(let g=0;g<=4;g++){const v=peak*g/4, y=Y(v);
    svg.appendChild(el("line",{x1:padL,x2:W-padR,y1:y,y2:y,stroke:"#EEF2F7","stroke-width":1}));
    svg.appendChild(txt(padL-8,y+4,Math.round(v)+"",10,"#8FA3B8","end"));}
  svg.appendChild(txt(14,padT+10,"MW",10,"#8FA3B8"));

  // total generation area (curtailment backdrop)
  let dTot="M"+X(0)+" "+Y(sol[0]+wnd[0]);
  for(let i=1;i<n;i++)dTot+=" L"+X(i)+" "+Y(sol[i]+wnd[i]);
  dTot+=" L"+X(n-1)+" "+Y(0)+" L"+X(0)+" "+Y(0)+" Z";
  svg.appendChild(el("path",{d:dTot,fill:"#D8E1EC",opacity:.55}));

  // wind area (stacked base)
  let dW="M"+X(0)+" "+Y(wnd[0]);
  for(let i=1;i<n;i++)dW+=" L"+X(i)+" "+Y(wnd[i]);
  dW+=" L"+X(n-1)+" "+Y(0)+" L"+X(0)+" "+Y(0)+" Z";
  svg.appendChild(el("path",{d:dW,fill:"#1FB2D5",opacity:.75}));

  // solar stacked on wind
  let dS="M"+X(0)+" "+Y(wnd[0]+sol[0]);
  for(let i=1;i<n;i++)dS+=" L"+X(i)+" "+Y(wnd[i]+sol[i]);
  for(let i=n-1;i>=0;i--)dS+=" L"+X(i)+" "+Y(wnd[i]);
  dS+=" Z";
  svg.appendChild(el("path",{d:dS,fill:"#F0B429",opacity:.85}));

  // stack intake line = min(total, elec)
  let dI="";
  for(let i=0;i<n;i++){const v=Math.min(sol[i]+wnd[i],cfg.elec);dI+=(i?" L":"M")+X(i)+" "+Y(v);}
  svg.appendChild(el("path",{d:dI,fill:"none",stroke:"#0D2B4F","stroke-width":2.4,"stroke-linejoin":"round"}));

  // electrolyzer ceiling
  svg.appendChild(el("line",{x1:padL,x2:W-padR,y1:Y(cfg.elec),y2:Y(cfg.elec),stroke:"#0D2B4F","stroke-width":1,"stroke-dasharray":"5 4",opacity:.55}));
  svg.appendChild(txt(W-padR,Y(cfg.elec)-6,"stack ceiling "+cfg.elec+" MW",10,"#64798F","end"));

  // x labels
  for(let d=0;d<3;d++){const x=X(d*24+12);
    svg.appendChild(txt(x,Hh-8,"Day "+(d+1),10.5,"#8FA3B8","middle"));
    if(d)svg.appendChild(el("line",{x1:X(d*24),x2:X(d*24),y1:padT,y2:padT+ih,stroke:"#EEF2F7"}));}
}

/* ---------- Chart: degradation forecast ---------- */
function drawDeg(r,s){
  const svg=$("degChart"); svg.innerHTML="";
  const W=440,Hh=260,padL=46,padR=14,padT=14,padB=30;
  const iw=W-padL-padR, ih=Hh-padT-padB;
  const yMin=78,yMax=100;
  const X=y=>padL+y/10*iw, Y=v=>padT+ih-(v-yMin)/(yMax-yMin)*ih;
  for(let g=0;g<=4;g++){const v=yMin+(yMax-yMin)*g/4, y=Y(v);
    svg.appendChild(el("line",{x1:padL,x2:W-padR,y1:y,y2:y,stroke:"#EEF2F7"}));
    svg.appendChild(txt(padL-7,y+4,v.toFixed(0)+"%",9.5,"#8FA3B8","end"));}
  // EOL threshold
  svg.appendChild(el("line",{x1:padL,x2:W-padR,y1:Y(85),y2:Y(85),stroke:"#C0392B","stroke-width":1.4,"stroke-dasharray":"5 4"}));
  // curve with uncertainty band (±20% on degradation rate)
  let dC="",up="",lo="";
  for(let y=0;y<=10;y+=0.25){const c=100/(1+r.degRate/100*y);
    dC+=(y?" L":"M")+X(y)+" "+Y(c);
    up+=(y?" L":"M")+X(y)+" "+Y(100/(1+r.degRate*0.8/100*y));}
  for(let y=10;y>=0;y-=0.25){lo+=" L"+X(y)+" "+Y(100/(1+r.degRate*1.2/100*y));}
  svg.appendChild(el("path",{d:up+lo+" Z",fill:"#0D2B4F",opacity:.08}));
  svg.appendChild(el("path",{d:dC,fill:"none",stroke:"#0D2B4F","stroke-width":2.4}));
  // x labels
  for(let y=0;y<=10;y+=2)svg.appendChild(txt(X(y),Hh-8,"Y"+y,9.5,"#8FA3B8","middle"));
  // annotation
  const f10=100/(1+r.degRate/100*10);
  svg.appendChild(el("circle",{cx:X(10),cy:Y(f10),r:4,fill:"#1FB2D5",stroke:"#fff","stroke-width":1.5}));
  svg.appendChild(txt(X(10)-6,Y(f10)-9,f10.toFixed(1)+"% @Y10",10,"#0D2B4F","end",600));
  svg.appendChild(txt(padL+4,Y(85)-6,"EOL replacement trigger",9.5,"#C0392B"));
}

/* ---------- Chart: sensitivity tornado ---------- */
function drawTornado(cfg,s,baseLcoh){
  const svg=$("tornado"); svg.innerHTML="";
  const W=440,Hh=260,padL=118,padR=44,padT=18,padB=26;
  const iw=W-padL-padR, ih=Hh-padT-padB;
  const params=[
    {label:"Electrolyzer CAPEX",mut:(c,f)=>({...c,capex:c.capex*f})},
    {label:"WACC",mut:(c,f)=>({...c,wacc:c.wacc*f})},
    {label:"Solar capacity",mut:(c,f)=>({...c,solar:c.solar*f})},
    {label:"Wind capacity",mut:(c,f)=>({...c,wind:c.wind*f})},
    {label:"Stack capacity",mut:(c,f)=>({...c,elec:c.elec*f})},
  ];
  const rows=params.map(p=>{
    const lo=simulate(p.mut(cfg,0.85),s).lcoh-baseLcoh;
    const hi=simulate(p.mut(cfg,1.15),s).lcoh-baseLcoh;
    return {label:p.label,lo,hi,span:Math.max(Math.abs(lo),Math.abs(hi))};
  }).sort((a,b)=>b.span-a.span);
  const maxAbs=Math.max(...rows.map(r=>r.span),0.01);
  const cx=padL+iw/2, scale=(iw/2-6)/maxAbs;
  const rowH=ih/rows.length;
  svg.appendChild(el("line",{x1:cx,x2:cx,y1:padT,y2:padT+ih,stroke:"#D8E1EC","stroke-width":1.4}));
  rows.forEach((r,i)=>{
    const y=padT+i*rowH+rowH/2, bh=Math.min(16,rowH*0.42);
    svg.appendChild(txt(padL-8,y+4,r.label,10.5,"#64798F","end"));
    const seg=(v,color)=>{
      const w=Math.abs(v)*scale;
      svg.appendChild(el("rect",{x:v<0?cx-w:cx,y:y-bh/2,width:Math.max(w,0.5),height:bh,rx:3,fill:color,opacity:.92}));
      svg.appendChild(txt(v<0?cx-w-5:cx+w+5,y+4,(v>=0?"+":"")+v.toFixed(2),9,"#64798F",v<0?"end":"start"));
    };
    seg(r.lo,"#1FB2D5"); seg(r.hi,"#0D2B4F");
  });
  svg.appendChild(txt(cx,Hh-6,"Δ LCOH ($/kg)",9.5,"#8FA3B8","middle"));
}

/* ---------- Scenario table ---------- */
function fillTable(cfg){
  const tb=$("scenTable"); tb.innerHTML="";
  for(const key of ["base","aggressive","pessimistic"]){
    const s=SCEN[key], r=simulate(cfg,s);
    const ok=r.margin>=15, watch=r.margin>=0&&r.margin<15;
    const badge=ok?'<span class="badge ok">Bankable</span>':watch?'<span class="badge watch">Marginal</span>':'<span class="badge risk">At risk</span>';
    const tr=document.createElement("tr");
    if(key===activeScen)tr.style.background="#F4F8FC";
    tr.innerHTML=`<td style="font-weight:600;color:var(--navy)">${s.name}${key===activeScen?' <span style="font-size:10px;color:var(--cyan-dk);font-weight:600;letter-spacing:.08em">· ACTIVE</span>':''}</td>
      <td class="num">${fmt(r.lcoh)}</td><td class="num">${fmt(r.h2kg/1000,0)}</td>
      <td class="num">${fmt(100-100/(1+r.degRate/100*10),1)}%</td>
      <td class="num">${fmt(r.mac,0)}</td>
      <td class="num" style="color:${r.margin>=0?'var(--good)':'var(--bad)'}">${fmt(r.margin,1)}</td>
      <td style="text-align:right;padding-right:18px">${badge}</td>`;
    tb.appendChild(tr);
  }
}

/* ---------- Executive verdict ---------- */
function verdict(cfg,r){
  $("vNum").textContent="$"+fmt(r.breakeven);
  const gap=cfg.price-r.lcoh;
  let title,text;
  if(r.margin>=15){title="Proceed — configuration clears bankability threshold";
    text=`At a target price of $${fmt(cfg.price)}/kg the asset yields a ${fmt(r.margin,1)}% net margin with ${fmt(gap)} $/kg of headroom. Curtailment of ${fmt(r.curtail*100,1)}% suggests residual optimization value in stack sizing; abatement cost of $${fmt(r.mac,0)}/tCO₂ is defensible against carbon-contract benchmarks.`;}
  else if(r.margin>=0){title="Conditional — margin is thin under current assumptions";
    text=`Margin of ${fmt(r.margin,1)}% leaves limited buffer against the pessimistic baseline. Prioritize CAPEX compression or offtake indexation before FID. Sensitivity ranking above identifies the dominant de-risking lever.`;}
  else{title="Hold — configuration is loss-making at target price";
    text=`LCOH of $${fmt(r.lcoh)}/kg exceeds the $${fmt(cfg.price)}/kg target by ${fmt(-gap)} $/kg. Re-balance the renewables-to-stack ratio (current load factor ${fmt(r.loadFactor*100,1)}%) or defer until electrolyzer CAPEX crosses the tornado's break-even band.`;}
  $("vTitle").textContent=title; $("vText").textContent=text;
}

/* ---------- Events ---------- */
Object.values(sliders).forEach(sl=>sl.addEventListener("input",render));
document.querySelectorAll(".scen-btn").forEach(b=>b.addEventListener("click",()=>{
  document.querySelectorAll(".scen-btn").forEach(x=>x.classList.remove("active"));
  b.classList.add("active"); activeScen=b.dataset.scen;
  $("scenDesc").textContent=SCEN[activeScen].desc; render();
}));
document.querySelectorAll(".nav a").forEach(a=>a.addEventListener("click",()=>{
  document.querySelectorAll(".nav a").forEach(x=>x.classList.remove("active"));a.classList.add("active");
}));
render();
</script>
</body>
</html>
