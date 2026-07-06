# 🚛 Fleet Efficiency & Delay Cost Dashboard

![Status](https://img.shields.io/badge/Project-Capstone-blue)
![Data](https://img.shields.io/badge/Data-Synthetic%20%7C%20AI%20Generated-lightgrey)
![Focus](https://img.shields.io/badge/Focus-Cost%20Reduction%20%7C%20No%20Labor%20Increase-red)

---

## The Business Problem

Every day, trucks roll out with loads that should turn a profit. But somewhere between the dock and the destination, money leaks out. Not from bad drivers. Not from bad customers. From invisible friction in the operation—inefficient lanes, idle trucks at loading bays, deadhead miles driven for no revenue, and delays that cascade into missed appointments and penalty fees.

**The question from leadership was clear:** *Where are we losing money, and how do we stop it without adding more people, more trucks, or more shipments?*

We let the data answer. No assumptions. No bias. Just the numbers.

---

## Executive Summary

This analysis was built on a synthetic operational dataset representing **1,000 shipments across 260 trucks and 10 carriers**. Using Excel, Power Query, SQL, and AI-assisted analytics, we followed the data where it led—and what we found was sobering.

**The fleet is burning margin on preventable friction.**

- **171 shipments arrived late** out of 1,000. That is not a capacity problem. That is a workflow problem.
- **Detention—time wasted at docks—dominates delays**, accounting for nearly half of all documented delay reasons.
- **Severe delays (&gt;300 minutes)** hit 12 shipments. These are not minor hiccups. These are catastrophic failures that destroy customer trust and contract profitability.
- **Cost-per-mile and utilization variances** reveal that some lanes and truck types are silently eroding revenue before the invoice is ever sent.

**The bottom line:** We do not need more labor. We need less friction.

---

## What the Data Revealed

We approached this analysis without preconceptions. The goal was not to validate a hypothesis, but to discover the truth hidden in the operational noise. Here is what the unbiased analysis uncovered:

### 1. Detention Is the Silent Killer

- **63 of 129 documented delays** were caused by detention—waiting at docks.
- That is **48.8%** of all delay reasons. Not weather. Not traffic. Not mechanical failure. Waiting.
- Every minute a truck sits idle, the cost-per-mile climbs, and the driver clock runs out on the next load.

### 2. The On-Time Gap Is a Revenue Gap

- Fleet-wide on-time rate: **82.9%**
- That means **171 shipments** triggered late penalties, re-scheduling costs, or customer churn.
- Carrier performance ranges from **80.5% to 86.1%**. The gap between best and worst is not talent—it is process.

### 3. Lanes and Truck Types Are Not Created Equal

- Analysis of empty miles, deadhead miles, and utilization rates shows that certain lane assignments and truck-type pairings operate at a structural disadvantage.
- Some lanes are burning fuel and hours for loads that do not justify the round-trip cost.
- Load factor inconsistencies suggest dispatch and routing workflows are leaving money on the table.

### 4. Severe Delays Are Predictable—and Preventable

- **12 shipments (1.2%)** experienced severe delays exceeding 300 minutes.
- These are not random acts of nature. They are systemic failures in scheduling, routing, or dock coordination that can be flagged before dispatch.

---

## The Cost of Inaction

If these patterns hold true in live operations, the cost is not theoretical. It is:

- **Driver frustration** leading to turnover (your most expensive recruitment problem).
- **Customer penalties** and lost contract renewals.
- **Fuel and maintenance costs** on miles that generate zero revenue.
- **Dispatch overtime** managing chaos that should have been prevented.

This is not about working harder. It is about removing the friction that makes the work harder than it needs to be.

---

## Action Items

| Priority | Action | Expected Impact | Owner |
|----------|--------|-----------------|-------|
| 🔴 **CRITICAL** | Implement dock scheduling optimization to eliminate detention waste | Reduce delay-related costs by up to 15% | Operations |
| 🔴 **CRITICAL** | Audit lowest-performing lanes and truck-type pairings for profitability | Increase on-time delivery by 5%; reduce deadhead waste | Regional Manager |
| 🟡 **HIGH** | Standardize top-performing carrier workflows across the fleet | Increase fleet-wide on-time rate by 3% | Fleet Manager |
| 🟡 **HIGH** | Deploy pre-dispatch risk scoring for severe delay probability | Protect margin on high-value, time-sensitive loads | Analytics / Dispatch |
| 🟢 **MEDIUM** | Review empty-mile policy and backhaul lane planning | Reduce fuel and maintenance spend with no volume increase | Logistics Planning |

---

## 📸 Dashboard

![Fleet Efficiency & Delay Cost Dashboard](https://drive.google.com/file/d/109x60nwib1d0o0Ts5-KMEMV7bCN_2B1R/view?usp=drive_link,Screenshot 2026-06-28 214833.png)

*Dashboard components include: On-Time vs. Late Shipments, Carrier Performance Ranking, Documented Delay Reasons, and Actionable Recommendations.*

---

## How to Navigate This Repository

If you are reviewing this project, here is where everything lives and why it matters:

| Location | What You Will Find | Why It Matters |
|----------|-------------------|----------------|
| **Root** | `README.md` (this file) | The full story, from business problem to action items |
| `/data` | `dim_fleet_260.csv` | The fleet dimension table—truck specs, insurance, safety, maintenance |
| `/data` | `fact_orders_1000.xlsx` | The clean operational data—1,000 shipments with timing, costs, delays, and performance flags |
| `/data` | `fact_orders_1000_dirty.csv` | The raw data with intentional quality issues—used to validate data cleaning and ETL logic |
| `/docs` | `dashboard_screenshot.png` | The visual summary of findings for executive review |
| *(implied)* | Excel / Power Query / SQL | The analysis stack used to transform, query, and visualize the data |

**Quick Start for Reviewers:**

1. Read the **Executive Summary** and **Key Insights** above for the narrative.
2. Open the **Dashboard Screenshot** in `/docs` for the visual story.
3. Reference the **Data Used** table below for file context.
4. Download the clean data (`fact_orders_1000.xlsx`,`dim_fleet_260.cvs`) to validate the metrics independently.

---

## Data Used

| File | Description | Records |
|------|-------------|---------|
| `dim_fleet_260.xlsx` | Fleet dimension table. Truck specs, insurance, safety scores, maintenance schedules, compliance flags. | 260 trucks |
| `fact_orders_1000.xlsx` | Clean operational fact table. Shipment details, timing, delays, costs, mileage, utilization, and performance flags. | 1,000 shipments |
| `fact_orders_1000_dirty.csv` | Raw data with intentional quality issues (negative mileage, decimal errors, invalid truck types) used for ETL validation and data quality testing. | 1,000+ records |

**Key Fields Analyzed:**

- `delay_minutes`, `detention_minutes`, `Delay Reason`
- `cost_per_mile`, `variable_cost_per_mile`
- `empty_miles`, `deadhead_miles`, `loaded_miles`, `utilization_rate`
- `on_time_flag`, `late_flag`, `carrier_name`, `truck_type`, `region`

---

## Why This Data

This dataset was chosen specifically because it mirrors the operational reality of a mid-to-large scale trucking fleet without exposing proprietary company information.

**The criteria:**

- **Structurally authentic:** Real-world schema (fleet dimensions, order facts, delay categorization, cost allocation).
- **Analytically rich:** Contains the exact levers executives care about—cost per mile, utilization, delay drivers, and carrier variance.
- **Capstone appropriate:** As AI-generated synthetic data, it provides a sandbox for rigorous, unbiased analysis while demonstrating enterprise-grade business intelligence.
- **Constraint-aligned:** The data naturally supports the core strategic question: *How do we cut costs without increasing headcount or load volume?*

---

## Tools & Methodology

We used a modern, accessible stack to ensure the analysis is reproducible and transparent:

| Tool | Purpose |
|------|---------|
| **Excel** | Primary data exploration, pivot analysis, and dashboard visualization |
| **Power Query** | Data transformation, cleaning, and ETL preparation |
| **SQL** | Structured querying, metric calculation, and view creation for reproducible analysis |
| **AI** | Assisted in pattern recognition, insight synthesis, and executive narrative framing |

**Analytical Approach:**

- **Descriptive:** What happened? (On-time rates, delay counts, cost averages)
- **Diagnostic:** Why did it happen? (Root-cause delay analysis, lane/truck-type variance)
- **Prescriptive:** What do we do? (Prioritized action items with estimated impact)

---

## About This Analysis

This project was completed as a **Capstone Project**. The analysis was conducted with deliberate neutrality—no stakeholder pressure, no pre-existing bias, and no hypothesis to prove. The data was allowed to speak for itself.

**The insights were discovered, not manufactured.**

---

## Future State

- **Predictive Analytics:** Deploy pre-dispatch delay risk scoring using historical lane and carrier performance.
- **Real-Time Integration:** Connect live GPS and telematics to move from retrospective reporting to operational alerts.
- **Lane Profitability Scoring:** Build a lane-level P&L view to guide sales and dispatch toward the most efficient freight.
- **Driver Retention Link:** Correlate delay and detention patterns with driver turnover to quantify the human cost of operational friction.

---

## Project Details

- **Report Date:** June 28, 2026
- **Data Period:** January 2025 – December 2025
- **Version:** v2.0 Restored
- **Type:** Capstone / Executive Analytics

---

## 🎯 Executive Briefing: Copy & Paste

**Use this for emails, presentations, or elevator conversations:**

&gt; *Our fleet is losing margin to invisible friction. We analyzed 1,000 shipments across 260 trucks with no bias, no assumptions, and no agenda—and the data revealed a clear pattern. We are not late because we lack capacity. We are late because we are waiting. Detention at docks accounts for nearly half of all delays. Our on-time rate sits at 82.9%, but the gap between our best and worst carriers is pure process, not people. The good news: these are fixable problems. We do not need more trucks, more drivers, or more loads. We need tighter dock scheduling, smarter lane assignments, and a standardized workflow that already works for our top performers. The cost of doing nothing is driver turnover, customer penalties, and fuel burned on empty miles. The opportunity is margin recovery hiding in plain sight.*

---

*This analysis exists to turn operational noise into executive clarity. The trucks are already running. The question is whether they are running profitably.*
