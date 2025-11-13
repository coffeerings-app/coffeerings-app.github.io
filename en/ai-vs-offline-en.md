---
title: AI vs Offline – Recommendation Philosophy
permalink: /en/ai-vs-offline/
layout: default
---

<style>
:root{
  --fg:#222; --muted:#5f6772; --bg:#fff; --stripe:#f6f7f8; --accent:#c9a227;
  --radius:14px; --space:14px; --space-lg:24px; --border:1px solid #e6e7ea;
  --maxw:980px;
}
.page-wrap{max-width:var(--maxw); margin:0 auto; padding:var(--space-lg) var(--space);}
.lede{font-size:1.05rem; color:var(--muted);}
.kicker{display:inline-block; font-weight:600; color:var(--accent); letter-spacing:.02em;}
h1{margin:.25rem 0 1rem;}
hr{border:none; height:1px; background:#eceef1; margin:var(--space-lg) 0;}

.table-wrap{background:var(--bg); border-radius:var(--radius); border:var(--border); overflow:hidden;}
table.cmp{width:100%; border-collapse:collapse;}
table.cmp thead th{font-weight:700; text-align:left; background:var(--stripe); padding:12px 14px; border-bottom:var(--border);}
table.cmp tbody th{font-weight:600; width:24%; vertical-align:top;}
table.cmp td, table.cmp th{padding:14px; border-bottom:var(--border); vertical-align:top;}
table.cmp td small{color:var(--muted);}
table.cmp tr:nth-child(even) td, table.cmp tr:nth-child(even) th{background: #fafbfc;}

/* Mobile: turn each row into a card */
@media (max-width: 740px){
  .table-wrap{border:none; background:transparent;}
  table.cmp{display:block;}
  table.cmp thead{display:none;}
  table.cmp tbody{display:grid; gap:12px;}
  table.cmp tr{display:grid; border:var(--border); border-radius:12px; background:#fff;}
  table.cmp tr > *{display:block; border:none; padding:12px 14px;}
  table.cmp tr > th{
    border-bottom:1px solid #edf0f3;
    background:#fff; width:auto;
  }
  /* show column labels for each cell */
  table.cmp td[data-label]::before{
    content: attr(data-label);
    display:block; font-size:.82rem; color:var(--muted); margin-bottom:4px;
    font-weight:600; letter-spacing:.01em;
  }
}

/* callouts */
.note{background:#fffbeb; border:1px solid #f3e7b6; border-radius:12px; padding:12px 14px; margin-top:8px;}
</style>

<div class="page-wrap">

<p align="center">
  <img src="/assets/coffeerings.png" alt="Coffee Rings" width="90"><br>
<a href="/en/support/">Support</a> · <a href="/en/privacy/">Privacy</a> · <a href="/">Home</a>
</p>

<h1>AI vs Offline Recommendation Philosophy</h1>

<p class="lede">
Coffee Rings offers two complementary recommendation engines – both grounded in espresso physics.
Whether you prefer the <strong>deterministic Offline Engine</strong> (built into the app) or the
<strong>context-adaptive AI Engine</strong> (via your own API key), the goal is the same:
<strong>balanced, consistent extractions with clear, testable guidance.</strong>
</p>

<hr>

<h2>Comparison Overview</h2>

<div class="table-wrap">
<table class="cmp">
  <thead>
    <tr>
      <th>Dimension</th>
      <th>AI Engine</th>
      <th>Offline Engine</th>
      <th>What this means</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Primary goal</th>
      <td data-label="AI Engine">Context-adaptive re-balancing based on roast × drink × milk × taste deltas.</td>
      <td data-label="Offline Engine">Deterministic, rule-bound corrections with validated plan.</td>
      <td data-label="What this means">AI flexes per context; Offline guarantees predictable, guardrailed moves.</td>
    </tr>
    <tr>
      <th>Inputs considered</th>
      <td data-label="AI Engine">Full shot state, previous shot (optional), equipment, drink, milk, roast, taste.</td>
      <td data-label="Offline Engine">Same core inputs plus a “foundation” layer for extreme cases.</td>
      <td data-label="What this means">Both read the same data; Offline adds a safety net for outliers.</td>
    </tr>
    <tr>
      <th>Action cap & priority</th>
      <td data-label="AI Engine">Max 3 adjustments, enforced contiguous priorities P1–P3.</td>
      <td data-label="Offline Engine">Same limit with priority validation.</td>
      <td data-label="What this means">You’ll only ever see up to 3 actionable levers.</td>
    </tr>
    <tr>
      <th>Temperature policy</th>
      <td data-label="AI Engine">Roast micro-clamps; allows justified deviations (esp. with milk/taste).</td>
      <td data-label="Offline Engine">Roast-aware steps; conservative cooling on bitterness.</td>
      <td data-label="What this means">Both avoid wild swings; Offline is slightly more reserved.</td>
    </tr>
    <tr>
      <th>Yield (ratio)</th>
      <td data-label="AI Engine">High precision (0.1 g) and stronger gate on “meaningful” changes.</td>
      <td data-label="Offline Engine">Roast/style-aware step sizes with ratio guardrails.</td>
      <td data-label="What this means">Both lengthen for clarity or shorten for body; step size differs by context.</td>
    </tr>
    <tr>
      <th>Grind guidance</th>
      <td data-label="AI Engine">Physics first: ↑ yield ⇒ coarser; ↓ yield ⇒ finer. Time-band overrides (≤ 22 s ⇒ finer, ≥ 32 s ⇒ coarser).</td>
      <td data-label="Offline Engine">Nearly identical: time first, taste in neutral band, then yield pairing.</td>
      <td data-label="What this means">Prevents contradictions like “finer + more yield”.</td>
    </tr>
    <tr>
      <th>Shot time handling</th>
      <td data-label="AI Engine">Never adjusted directly; derived from grind/yield. Accounts for Pre-Infusion credit.</td>
      <td data-label="Offline Engine">Same principle; time informs grind guardrails.</td>
      <td data-label="What this means">Time is an <em>outcome</em>, not a knob.</td>
    </tr>
    <tr>
      <th>Pre-infusion policy</th>
      <td data-label="AI Engine">Allowed/disabled by policy; JSON schema restricts to integers (0, 3–8 s).</td>
      <td data-label="Offline Engine">Enables/steps Pre-Infusion when acidity is high & time not long; removes for bitter short shots.</td>
      <td data-label="What this means">Offline is more proactive as a taste smoother.</td>
    </tr>
    <tr>
      <th>Extremes handling</th>
      <td data-label="AI Engine">“Extreme Mode” focusses on Priority-0 must-fixes to get on track.</td>
      <td data-label="Offline Engine">Also here, a maximum of 2 changes for temp/ratio/time are applied before any taste tweaks.</td>
      <td data-label="What this means">Both approaches help you get started with a first-aid approach.</td>
    </tr>
  </tbody>
</table>
</div>

<div class="note">
  Prefer privacy / no network or costs? Use the built-in Offline Engine.  
  <p></p>
  Want context-aware nuance? Add your own OpenAI API key in the app to enable AI recommendations.
</div>
<p></p>
<p align="center">
  <a href="/en/support/">Support</a> · <a href="/en/privacy/">Privacy</a> · <a href="/">Home</a>
</p>

</div>
