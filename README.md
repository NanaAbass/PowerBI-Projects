# 💧 Maji Ndogo Water Survey — Power BI Dashboard

## Overview

This Power BI report (`Maji_Ndogo_VIZ_3.pbix`) presents the results of a **national water access survey** for the fictional region of Maji Ndogo. It provides data-driven insights into the current state of water sources, the population served, and the improvements needed — broken down at both national and provincial levels.

The dashboard is designed to support decision-makers, analysts, and stakeholders in understanding where water infrastructure gaps exist and what it will cost to address them.

---

## 📊 Report Pages

| Page | Description |
|------|-------------|
| **National** | High-level summary of water survey results across all provinces |

> Additional pages may be accessible via toggle/navigation buttons embedded in the report layout.

---

## 🗂️ Data Fields

The report draws on the following key fields:

| Field | Description |
|-------|-------------|
| `province_name` / `province` | Geographic grouping at the provincial level |
| `location_type` | Urban or rural classification of the water source |
| `type_of_water_source` | Category of water source (e.g., tap, well, river) |
| `number_of_people_served` | Population count served by each source |
| `people_with_water_access` | Count of people with reliable water access |
| `improvement` / `Aggregated_improvements` | Recommended infrastructure improvement actions |
| `Formatted_change` | Human-readable description of proposed change |
| `budget` / `Budgeted_improvement_cost` | Estimated cost for each improvement |
| `Total Cost of Update` | Aggregate cost measure across all improvements |
| `quantity` | Volume or capacity metric for water sources |
| `results` | Survey result records |

---

## 📈 Visualisations Used

The dashboard includes the following visual components:

- **Shape Map** — Geographic distribution of water sources across provinces
- **Clustered Bar & Column Charts** — Comparison of source types and improvement counts by province
- **Bar Chart** — Breakdown of population served or improvements needed
- **Pie Chart** — Proportional view of source types or location types
- **Cards & Multi-Row Cards** — KPI summaries (e.g., total people served, total budget)
- **Table** — Detailed tabular view of survey records or improvement plans
- **Slicers** — Interactive filters (province, location type, source type)
- **Images & Custom Map** — Provincial map overlay with custom PNG assets
- **Toggle Buttons** — Navigation between report views (province-level / improvement-level)

---

## 🛠️ Tools & Requirements

| Requirement | Detail |
|-------------|--------|
| **Tool** | Microsoft Power BI Desktop |
| **File format** | `.pbix` |
| **Report version** | Power BI 2026.02 |
| **Data source** | Embedded model (no live connection required) |
| **Custom visuals** | None — all standard Power BI visuals |
| **Custom assets** | Provincial map image, toggle button PNGs (embedded) |

---

## 🚀 Getting Started

1. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free).
2. Open `Maji_Ndogo_VIZ_3.pbix` in Power BI Desktop.
3. Use the **slicer panels** to filter by province, location type, or water source type.
4. Use the **toggle buttons** to switch between the national view and province/improvement-level breakdowns.
5. Hover over any visual for detailed tooltips and drill-down options.

---

## 📌 Key Metrics at a Glance

- **Scope:** National-level water survey with provincial breakdowns
- **Focus areas:** Source type distribution, population coverage, improvement planning, budget estimation
- **Primary use case:** Infrastructure gap analysis and water access improvement prioritisation

---

## 📁 Project Context

This dashboard is part of the **Maji Ndogo** data analytics project — a case study exploring water access challenges in a developing-world context. It combines geospatial mapping, population data, and cost modelling to produce actionable infrastructure recommendations.

> Related project assets (SQL scripts, Python notebooks, or Streamlit apps) may be found in the parent repository.

---

*Built with Power BI Desktop · Maji Ndogo Water Initiative*
