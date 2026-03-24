# Medtech & Pharma Sales Intelligence Dashboard

**The Hook:** Sales data alone doesn't drive decisions — context does. This Power BI dashboard transforms raw medtech and pharma transactional data into a multi-dimensional commercial performance system, tracking sales across local and international markets, segmented by product category, customer age bracket, geography, and star rating. The "so what?" is simple: by combining MoM momentum signals with location-level drill-down and customer sentiment in one report, commercial managers can move from "here are the numbers" to "here is where to act."

---

## The Problem & Context

Medtech and pharmaceutical sales teams operate across complex, multi-channel environments — local distributors, international accounts, diverse product lines, and customers who leave ratings and reviews that signal future churn long before it shows up in revenue. Most teams track these signals in siloed spreadsheets: sales in one file, shipping costs in another, customer feedback in a third.

The result? Leaders spend the first 20 minutes of every review meeting reconciling numbers instead of making decisions.

This project consolidates five data domains — sales transactions, product catalogue, customer demographics, location data, and shipping records — into a single Power BI report. It is designed for a **Sales Director or Commercial Manager** who needs to assess overall health, identify underperforming territories, and understand which product categories are driving volume vs. which are generating complaints.

---

## Approach & Methodology (The Conflict)

* **The Data:** Five dimension and fact tables were modelled in Power BI: `Sales-facts` (transactional records with buyer gender, age bracket, rating star, and review text), `Products_dim` (product ID and category), `Location_dim` (order location), `Date_Table` (calendar with Month No and Year Month fields for time intelligence), and a `Shipping` lookup. A dedicated `Analysis` measures table and a `Time_intelligence` table hold all DAX calculations, keeping the model clean and reusable.

* **The Brains:** The report is structured across two purpose-built pages. Page 1 is the **commercial overview**: headline KPIs (Total Sales, Qty Sold, Total Orders, Total Shipping, Average Rating) anchored by MoM delta cards and a Sale Type slicer (Local vs. International). A wide area chart traces the local/international revenue split over time — the core narrative visual. Two clustered bar charts break performance down by age bracket and product category. A location table with sparklines provides territory-level depth. Page 2 is the **customer and product lens**: gender breakdown, ratings distribution, shipping cost trends by product category, and a raw review table for qualitative signal. Two custom tooltip pages add contextual pop-ups on hover, keeping the canvas uncluttered.

* **The Battle Scars:** Building time intelligence in Power BI without a clean date spine is a reliable source of pain — and this project was no exception. The `Date_Table` needed to expose both `Month No` (for sparkline ordering) and `Year Month` (for the main area chart) as separate fields, otherwise the time axis either sorted alphabetically ("Apr, Aug, Dec...") or collapsed months across years. The fix — creating an explicit numeric `Month No` sort column mapped to the `Year Month` display field — is one of those Power BI lessons that costs you a morning the first time and takes 90 seconds ever after. The `Dynamic Month Text` measure was then layered on top to surface a human-readable period label directly on the KPI cards, so viewers always know which month's delta they are reading.

---

## Key Results (The Evidence)

*(Using the Pyramid Principle)*

* **The dashboard surfaces commercial performance across 5 KPIs with MoM momentum for every headline metric.**
  * Data Point 1: Four KPI card clusters each display a primary measure (Sales, Qty, Orders, Shipping), an embedded area sparkline, a dynamic month label, and a MoM delta — giving viewers trend direction alongside the absolute number without any additional filtering.
  * Data Point 2: The location table on Page 1 combines Total Orders, Total Qty, Total Sales, MoM Sales, and an in-cell sparkline for every territory row, enabling a Sales Director to rank and compare regions in a single view.

* **Customer sentiment is quantified and cross-referenced against product and gender dimensions on Page 2.**
  * Data Point 1: The average rating card is paired with a distribution bar chart of orders by rating star and a secondary bar chart of orders by product category — connecting "how satisfied?" with "which product?" in two adjacent visuals.
  * Data Point 2: A raw review table with Total Orders and Star Rating allows qualitative scanning of customer language alongside volume context, bridging the gap between quantitative scores and the reasons behind them.

* **Local vs. international segmentation runs as a thread across both pages via a Sale Type slicer.**
  * Data Point 1: The Page 1 area chart, both clustered bar charts, and the location table all respond to the Sale Type slicer, enabling a single filter action to reframe the entire commercial overview from global to local-only or international-only.

*(Note: Visualizations can be found in the Power BI report file. Export page visuals to `/images` for GitHub display.)*

---

## Actionable Conclusion (1 Clear Takeaway)

A sales dashboard's job is not to display data — it is to shorten the distance between a number and a decision. The next version of this dashboard should add three things that turn observation into action: **(1)** sales quota targets surfaced as a variance % on every KPI card and as a reference line on the area chart; **(2)** conditional formatting on the location table to flag territories below a MoM threshold in red, so the one territory that needs attention today is immediately visible; **(3)** a rolling 12-month view option on the area chart to separate seasonal patterns from genuine trend shifts — critical in healthcare procurement, which spikes at fiscal year-end. With those three additions, this dashboard stops being a reporting artefact and becomes a decision engine.

---

## Tech Stack & Replication

* **Tools:** Microsoft Power BI Desktop, DAX (Data Analysis Expressions), Power Query (M language)
* **Data Model:** Star schema — one central `Sales-facts` fact table joined to `Products_dim`, `Location_dim`, `Date_Table`, and `Shipping` dimension tables. Separate `Analysis` and `Time_intelligence` measure tables.
* **Key DAX Measures:** `Total Sales`, `Total Qty sold`, `Total Orders`, `Total Shipping`, `Avvg rating`, `Local Sales`, `Int'l Sales`, `MoM Sales`, `MoM Qty sold`, `MoM Orders`, `MoM Shipping`, `Dynamic Month Text`, `Now timestamp`

* **To Run:**
  ```bash
  # 1. Clone or download this repository
  git clone https://github.com/your-username/medtech-sales.git

  # 2. Open the report in Power BI Desktop (free download from Microsoft)
  #    File → Open → Medtech_pharma_project.pbix

  # 3. Connect to your data source
  #    Home → Transform Data → Data Source Settings → update connection string

  # 4. Refresh the data model
  #    Home → Refresh

  # 5. Publish to Power BI Service (optional)
  #    Home → Publish → select your workspace
  ```

* **Requirements:** Power BI Desktop (March 2026+ recommended)
* **Background assets:** Two background images and social profile assets are bundled in `assets` — replace with your own branding before publishing.
