---
title: KI vs. Offline – Empfehlungs-Philosophie
permalink: /de/ai-vs-offline/
layout: default
---

<!-- styles are identical to EN page -->
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

@media (max-width: 740px){
  .table-wrap{border:none; background:transparent;}
  table.cmp{display:block;}
  table.cmp thead{display:none;}
  table.cmp tbody{display:grid; gap:12px;}
  table.cmp tr{display:grid; border:var(--border); border-radius:12px; background:#fff;}
  table.cmp tr > *{display:block; border:none; padding:12px 14px;}
  table.cmp tr > th{border-bottom:1px solid #edf0f3; background:#fff; width:auto;}
  table.cmp td[data-label]::before{
    content: attr(data-label);
    display:block; font-size:.82rem; color:var(--muted); margin-bottom:4px;
    font-weight:600; letter-spacing:.01em;
  }
}

.note{background:#fffbeb; border:1px solid #f3e7b6; border-radius:12px; padding:12px 14px; margin-top:8px;}
</style>

<div class="page-wrap">

<p align="center">
  <img src="/assets/coffeerings.png" alt="Coffee Rings" width="90"><br>
<a href="/de/support/">Support</a> · <a href="/de/privacy/">Privacy</a> · <a href="/">Home</a>
</p>

<h1>KI vs. Offline – Empfehlungs-Philosophie</h1>

<p class="lede">
Coffee Rings bietet zwei sich ergänzende Empfehlungs-Engines – beide basieren auf echter Espresso-Physik.
Ob du die <strong>deterministische Offline-Engine</strong> (in der App) oder die
<strong>kontext-adaptive KI-Engine</strong> (mit eigenem API-Schlüssel) bevorzugst:
Ziel ist stets <strong>Ausgewogenheit, Konsistenz und nachvollziehbare Hinweise.</strong>
</p>

<hr>

<h2>Vergleich im Überblick</h2>

<div class="table-wrap">
<table class="cmp">
  <thead>
    <tr>
      <th>Dimension</th>
      <th>KI-Engine</th>
      <th>Offline-Engine</th>
      <th>Bedeutung</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Primäres Ziel</th>
      <td data-label="KI-Engine">Kontext-adaptive Neu-Balance auf Basis von Röstung × Getränk × Milch × Geschmacks-Deltas.</td>
      <td data-label="Offline-Engine">Deterministische, regelgebundene Korrekturen mit validiertem Plan.</td>
      <td data-label="Bedeutung">KI passt sich an; Offline garantiert vorhersehbare, abgesicherte Schritte.</td>
    </tr>
    <tr>
      <th>Berücksichtigte Eingaben</th>
      <td data-label="KI-Engine">Kompletter Shot-Zustand, optional Vor-Shot, Equipment, Getränk, Milch, Röstung, Geschmack.</td>
      <td data-label="Offline-Engine">Gleiche Kerndaten plus „Foundation“-Schicht für Extreme.</td>
      <td data-label="Bedeutung">Beide lesen dieselbe Welt; Offline fügt ein Sicherheitsnetz für Ausreißer hinzu.</td>
    </tr>
    <tr>
      <th>Aktions-Limit & Priorität</th>
      <td data-label="KI-Engine">Max. 3 Anpassungen, zusammenhängende Prioritäten P1–P3.</td>
      <td data-label="Offline-Engine">Gleiches Limit mit Prioritäts-Validierung.</td>
      <td data-label="Bedeutung">Maximal drei umsetzbare Hebel in der UI.</td>
    </tr>
    <tr>
      <th>Temperatur-Policy</th>
      <td data-label="KI-Engine">Röstungs-Mikro-Klammern; begründete Abweichungen möglich (v. a. bei Milch/Geschmack).</td>
      <td data-label="Offline-Engine">Röstungs-bewusste Schritte; konservatives Kühlen bei Bitterkeit.</td>
      <td data-label="Bedeutung">Keine wilden Sprünge; Offline etwas zurückhaltender.</td>
    </tr>
    <tr>
      <th>Output (Ratio)</th>
      <td data-label="KI-Engine">Hohe Präzision (0,1 g) und strengeres Tor für „sinnvolle“ Änderungen.</td>
      <td data-label="Offline-Engine">Röstungs/Style-abhängige Schrittweiten mit Ratio-Leitplanken.</td>
      <td data-label="Bedeutung">Verlängern für Klarheit, verkürzen für Körper; Schrittgröße variiert.</td>
    </tr>
    <tr>
      <th>Mahlgrad-Hinweise</th>
      <td data-label="KI-Engine">Physik zuerst: ↑ Output ⇒ gröber, ↓ Output ⇒ feiner. Zeit-Bänder übersteuern (≤ 22 s ⇒ feiner, ≥ 32 s ⇒ gröber).</td>
      <td data-label="Offline-Engine">Nahezu identisch: Zeit zuerst, im Neutralband Geschmack, dann Output-Paarung.</td>
      <td data-label="Bedeutung">Verhindert Widersprüche wie „feiner + mehr Output“.</td>
    </tr>
    <tr>
      <th>Behandlung der Shot-Zeit</th>
      <td data-label="KI-Engine">Nie direkt eingestellt; ergibt sich aus Mahlgrad / Output Berücksichtigt PI-Gutschrift.</td>
      <td data-label="Offline-Engine">Gleiches Prinzip; Zeit steuert nur Leitplanken.</td>
      <td data-label="Bedeutung">Zeit ist ein <em>Ergebnis</em>, kein Drehknopf.</td>
    </tr>
    <tr>
      <th>Pre-Infusion-Policy</th>
      <td data-label="KI-Engine">Durch Policy erlaubt/deaktiviert; Schema erlaubt Ganzzahlen (0, 3–8 s).</td>
      <td data-label="Offline-Engine">Aktiviert/erhöht PI bei hoher Säure & nicht langer Zeit; entfernt bei bitter-kurzen Shots.</td>
      <td data-label="Bedeutung">Offline nutzt PI aktiver als Geschmacksglätter.</td>
    </tr>
    <tr>
      <th>Umgang mit Extremen</th>
      <td data-label="KI-Engine">„Extreme Mode“ kann bis zu 5 Aktionen inkl. Priorität-0 Must-Fix ausgeben.</td>
      <td data-label="Offline-Engine"><code>foundationNudges</code> (max. 2) für Temp/Ratio/Zeit vor Geschmack.</td>
      <td data-label="Bedeutung">KI kann mehr Must-Fixes listen; Offline bleibt klein & sicher.</td>
    </tr>
    <tr>
      <th>Sprache & UX</th>
      <td data-label="KI-Engine">Einheiten/Schritte erzwungen; lokalisierte Zusammenfassungen; DE-Glossar.</td>
      <td data-label="Offline-Engine">Spiegelt Zielwerte; starke Accessibility-Labels.</td>
      <td data-label="Bedeutung">Konsistente Formulierungen in beiden Pfaden.</td>
    </tr>
  </tbody>
</table>
</div>

<div class="note">
  Privat, ohne Netzwerk oder Kosten? Nutze die integrierte Offline-Engine.  
    <p></p>
  Mehr Kontext-Nuance gewünscht? Hinterlege in der App deinen OpenAI API-Schlüssel für KI-Empfehlungen.
</div>
<p></p>
  
<p align="center">
  <a href="/de/support/">Support</a> · <a href="/de/privacy/">Privacy</a> · <a href="/">Home</a>
</p>


</div>
