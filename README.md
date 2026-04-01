# Going Beyond the Numbers

A market-context approach to dynamic pricing portfolio management for short-term rentals. This project analyzes 20 STR properties across 6 international markets, combining platform health diagnostics with occupancy matrices and lead-time classification to deliver actionable base price recommendations.

## Live Dashboard

**[View Interactive Dashboard](https://agrisigabriel.github.io/going-beyond-the-numbers/)**

---

## Assignment #1 — Portfolio Analysis & Booking Review

### Deliverables

| File | Description |
|------|-------------|
| [`index.html`](./index.html) | Interactive dashboard — filterable portfolio table, market overview, and full methodology documentation |
| [`assets/BP_Portfolio_Analysis.xlsx`](./assets/BP_Portfolio_Analysis.xlsx) | Spreadsheet with original data, calculated fields (Adjusted Occupancy, Min/Base Ratio, Lead Time Classification), and base price recommendations with reasoning |
| [`assets/BP_Analysis_Document.docx`](./assets/BP_Analysis_Document.docx) | Project description — approach, key findings, and market-by-market verdict |

### Approach

#### 1. Understanding the Platform
Before analyzing any data, I completed both the Host and Manager Bootcamps, the 3-Step Quickstart Guide, Charts Guide, and Market Insights documentation. Key takeaways:

- **Base Price** is the annual average anchor — dynamic pricing fluctuates above and below it based on demand
- **Health Score** measures how close occupancy is to optimal neighborhood occupancy — not absolute occupancy
- **Minimum Price** is the algorithm's floor — setting it too close to base effectively disables dynamic pricing
- The platform is designed to be monitored every 2 weeks, not "set and forget"

#### 2. Viable Approaches Considered

**Intervention Score (0–100)** — A weighted composite score combining Health (35pts), 30d Occupancy (25pts), % at Min (20pts), Staleness (10pts), and % Blocked (10pts). Useful for quick triage, but a single number can't distinguish a ski resort in normal off-season from a listing that's genuinely failing.

**Market-Context Approach (selected)** — Uses a 30d/90d occupancy decision matrix crossed with lead-time classification and market type to determine whether weak metrics are *expected* or *alarming*. Prevents false positives and avoids unnecessary base price cuts during seasonal dips.

#### 3. Key Analytical Dimensions

| Dimension | What It Reveals |
|-----------|-----------------|
| **30d/90d Occupancy Matrix** | Cross-referencing near-term and forward occupancy to classify each property as Strong, Short Window, Seasonal, or Intervention |
| **Min/Base Price Ratio** | How much room the dynamic pricing algorithm has to flex — ratios above 85% effectively disable dynamic pricing |
| **Adjusted Occupancy** | True utilization after removing host-blocked nights — reveals properties where available inventory IS booking despite low headline occupancy |
| **Lead Time Classification** | Market demand pattern (Last-Minute, Short Window, Standard, Advance, Far-Out) — determines how urgently low occupancy should be treated |
| **% Nights at Minimum** | Whether the algorithm is actively optimizing or has flatlined at the price floor |

#### 4. Key Findings

- **3 properties** flagged as host behavior issues (85–100% blocked) — these need coaching conversations, not pricing changes
- **5 properties** with Min/Base ratio > 80% — the dynamic pricing algorithm is effectively handcuffed
- **2 properties** (866 Bachelor Ridge, Picasso 4.4) have algorithms that are completely frozen — 100% and 96% of nights at minimum price
- **3 properties** are clearly underpriced — 100% occupancy in both windows (Deer Park, Picasso 3.1, Costa Brava)
- **Same neighborhood, opposite results** in Barcelona: Picasso 2.1 (health 89) vs Picasso 4.4 (health 20) in Dreta de l'Eixample — confirms the issue is property-level base price calibration, not market conditions

#### 5. Recommendation Summary

| Signal | Count | Action |
|--------|-------|--------|
| **Intervention** | 6 | Base price reduction required (range: -5% to -22%) |
| **Host Issue** | 3 | Calendar unblocking / host coaching before any pricing change |
| **Monitor** | 3 | Seasonal or new — hold and reassess in 2–3 weeks |
| **Strong** | 8 | Maintain or raise base price (range: +5% to +12%) |

### Spreadsheet Details

The Excel file preserves the original data (white background) and adds the following calculated columns:

| Column | Description | Logic |
|--------|-------------|-------|
| **Min/Base Ratio** | `Minimum Price / Base Price` — percentage of base that the minimum represents | Formula |
| **Adjusted Occ 30d** | `(Occ30d × 30) / (30 × (1 - %Blocked))` — booked nights over available nights | Formula |
| **Lead Time Class** | Last-Minute / Short Window / Standard / Advance / Far-Out | Derived from lead time days |
| **Signal** | Market-context verdict using 30d/90d matrix, health, and blocked % | Analyst determination |
| **Recommended %** | Specific base price change recommendation | Analyst determination |
| **Comments/Insights** | Detailed reasoning for each recommendation | Analyst narrative |

Color coding follows financial modeling conventions:
- **Blue text** — hardcoded inputs / analyst inputs
- **Black text** — formulas and calculations
- **Green background** — strong / raise opportunity
- **Yellow background** — monitor / seasonal
- **Red background** — intervention required
- **Purple background** — host behavior issue

---

## Assignment #2

*Coming soon — will be added after the live review session.*

---

## About

This analysis was completed as part of a Senior Revenue Manager selection process. The goal was to demonstrate analytical depth, platform understanding, and the ability to translate data into actionable revenue management recommendations.

**Author:** Gabriel Agrisi Paigel
