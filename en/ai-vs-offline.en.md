---
title: AI vs. Offline Recommendation Philosophy – Coffee Rings
permalink: /en/ai-vs-offline/
---

<p align="center">
  <img src="/assets/coffeerings.png" alt="Coffee Rings" width="100">
</p>

<h1 align="center">AI vs. Offline Recommendation Philosophy</h1>

<p align="center"><em>Two paths, one goal: better espresso through insight and balance.</em></p>

Coffee Rings offers two complementary recommendation engines – both powered by real espresso science.  
Whether you prefer the **deterministic Offline Engine** (built into the app) or the **context-adaptive AI Engine** (via your own API key), both follow the same philosophy:  
**Keep your espresso balanced, consistent, and grounded in physics.**

---

## Comparison Overview

| Dimension | AI Engine | Offline Engine | What this means |
|------------|----------------------------------------|-----------------------------------------------|----------------|
| **Primary goal** | Context-adaptive re-balancing based on roast × drink × milk × taste deltas. | Deterministic, rule-bound corrections with validated plan. | AI flexes per context; Offline guarantees predictable, guardrailed moves. |
| **Inputs considered** | Full shot state, previous shot, equipment, drink, milk, roast, taste. | Same core inputs plus “foundation” layer for extreme cases. | Both read the same data; Offline adds a safety net for outliers. |
| **Action cap & priority** | Max 3 adjustments, enforced priorities P1–P3. | Same limit and priority validation. | You’ll only ever see up to 3 actionable levers. |
| **Temperature policy** | Roast micro-clamps, allows justified deviations (esp. with milk/taste). | Roast-aware, conservative cooling on bitterness. | Both avoid wild swings; Offline slightly more reserved. |
| **Yield (ratio)** | High precision (0.1 g), context-driven; stronger gate on meaningful changes. | Roast/style-aware step sizes with ratio guardrails. | Both lengthen or shorten logically by roast and drink type. |
| **Grind guidance** | Based on physics first; yield/time/taste interplay. | Nearly identical; slightly more conservative logic. | Prevents contradictions (e.g. finer + higher yield). |
| **Shot time** | Derived from grind/yield; never adjusted directly. | Same; time informs grind and validation only. | Time is an *outcome*, not a control. |
| **Pre-infusion** | Integer values only; policy-driven (enabled/disabled). | Adds/removes PI to smooth acidity or reduce harshness. | Offline may proactively add 2 s for better balance. |
| **Extremes** | “Extreme Case Mode” (up to 5 actions, incl. P0 must-fix). | `foundationNudges` (max 2) for safe correction. | AI can act wider; Offline stays surgical. |
| **Language & UX** | Units and summaries auto-localized; JSON contract ensures format. | Identical phrasing and labels; accessibility-ready. | Users see a consistent experience whichever engine they choose. |

---

## Which should you choose?

| If you value... | Go with... |
|------------------|------------|
| Full privacy, no cloud, no API keys | **Offline Engine (default)** |
| Context-aware nuance (milk, roast, taste memory) | **AI Engine** |
| Predictable, repeatable outcomes | **Offline Engine** |
| Exploratory insights and adaptive tweaks | **AI Engine** |

---

### Philosophy in one line

> The AI engine learns from your context.  
> The Offline engine guards your consistency.  
> Both share the same craft-based core.

---

<p align="center">
  <a href="/">Home</a>
</p>
