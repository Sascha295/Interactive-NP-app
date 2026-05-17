# 0/1 Knapsack — Interactive NP-Completeness & Algorithm Visualizer

An interactive educational tool that walks through the NP-completeness proof for the 0/1 Knapsack decision problem, then visualizes three algorithms solving it step by step — with animated pseudocode, live complexity analysis, and a Subset Sum reduction diagram.

🔗 **[Live Demo](https://fatemeh-najafi1.github.io/Interactive-NP-app/)**

---

## What It Does

Most algorithm visualizers show *how* an algorithm runs. This one also shows *why* the problem is hard — starting from the formal NP-completeness proof and working down to the concrete trade-offs between brute-force, dynamic programming, and greedy.

---

## Features

### Page 1 — NP-Completeness
**Interactive Verifier (Step 1: showing Knapsack is in NP)**
- Build any candidate certificate (subset) by toggling item bits
- Watch the verifier check it step by step, counting operations
- Demonstrates that verification is O(n) — exactly what "in NP" requires
- Preset certificates: empty set, all items, DP-optimal subset, single item

**Subset Sum → Knapsack Reduction Diagram (Step 2: showing NP-hardness)**
- Enter any Subset Sum instance; the corresponding Knapsack instance updates live
- Toggle elements to explore the forward (⇒) and backward (⇐) proof directions
- "Show ⇒" auto-finds a valid summing subset and highlights both sides simultaneously
- "Use on Algorithms page" loads the reduced instance directly into the algorithm visualizer
- Pseudo-polynomial discussion: explains why O(nW) DP doesn't contradict NP-completeness, with a table showing how operations explode as W grows

### Page 2 — Algorithms & Complexity
**Three fully animated algorithms**
- Brute-Force — enumerates all 2ⁿ subsets; always correct; exponential
- Dynamic Programming — fills an SVG table with dependency arrows; always correct; pseudo-polynomial
- Greedy (value-to-weight ratio) — fast; detects and flags counterexamples automatically

**For each algorithm:**
- Step / Play / Pause / Speed controls
- Plain-English explanation for every step
- Pseudocode panel with live line highlighting and hover tooltips
- Step history table — click any row to jump back to that step

**Analysis panels**
- Growth curve chart — log-scale SVG comparing n·2ⁿ vs n·W vs n log n as n grows, with a live marker for your current input
- Side-by-side comparison — runs all three algorithms on the same input and flags when greedy disagrees with DP
- Algorithm verdict table — when to use each approach and why

---

## Tech Stack

| Category | Detail |
|---|---|
| Language | HTML, CSS, JavaScript (vanilla — no frameworks) |
| Rendering | SVG (DP table, growth curves, dependency arrows) |
| Layout | CSS Grid, custom design tokens |
| Fonts | JetBrains Mono, Fraunces, Inter (Google Fonts) |
| Deployment | GitHub Pages |

---

## How to Run Locally

No build step needed — it's a single HTML file.

```bash
git clone https://github.com/Fatemeh-Najafi1/Interactive-NP-app.git
cd Interactive-NP-app
open index.html   # or just double-click it
```

Or visit the **[live demo](https://fatemeh-najafi1.github.io/Interactive-NP-app/)** directly.

---

## Algorithms Implemented

| Algorithm | Time Complexity | Always Correct? | Notes |
|---|---|---|---|
| Brute-Force | O(n · 2ⁿ) | Yes | Checks every subset; capped at n ≤ 22 in the visualizer |
| Dynamic Programming | O(n · W) | Yes | Pseudo-polynomial; full SVG table with traceback |
| Greedy (v/w ratio) | O(n log n) | No | Counterexample detection built in |

---

## Key Concepts Covered

- Decision vs. optimization formulations of NP problems
- What it means for a problem to be "in NP" — certificates and polynomial-time verifiers
- Polynomial-time reductions and why Subset Sum reduces to Knapsack
- Why O(nW) DP is pseudo-polynomial, not truly polynomial
- Optimal substructure and why it enables DP
- Why the greedy-choice property fails for 0/1 Knapsack (but holds for Fractional Knapsack)

---

## Background

Built as a final project for Algorithms (BCS 309) at Canadian University Dubai — Spring 2026.

---

## Author

**Fatemeh Najafi** — [GitHub](https://github.com/Fatemeh-Najafi1) · [LinkedIn](https://www.linkedin.com/in/fatemeh-najafi-797555382)
