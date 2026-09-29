# Plot limited sale analysis


##  Dairy Supply Chain Performance Run & Analytics Pipeline
An end-to-end operational diagnostic and data cleaning framework for a complex, multi-channel dairy manufacturing and distribution network. This project processes a high-fidelity tabular ledger tracking INR 58.73M in gross revenue across a historical footprint of 237,718 cows, programmatically identifying supply chain bottlenecks, correcting deep data distortions, and mapping regional demand indicators.


##  Data Model & Dimensional Pillars
The underlying dataset synchronizes transactional ledgers across four core operational streams:

* Farm & Livestock Matrices: Origin logs (Location), field coverage (Total Land Area (acres)), active herd counts (Number of Cows), and enterprise classifications (Farm Size: Small, Medium, Large).
* Production & Lifespan Parameters: SKU identifiers (Product ID, Product Name), commercial brands, batch volumes (Quantity (liters/kg)), unit cost structures, total value metrics, and preservation boundaries (Shelf Life (days), Storage Condition).
* Chronological Markers: Strict calendar tags (Date, Year, month name, quarter) alongside inventory shelf velocity windows (Production Date, Expiration Date).
* Logistics & Multi-Channel Sales Matrix: Fulfillment volumes, sold unit yields, total localized revenues, customer end-zones (Customer Location), distribution networks (Sales Channel), and live safety buffers (Quantity in Stock, Minimum Stock Threshold, Reorder Quantity).

------------------------------
##  Data Audit & Structural Fixes
Before building high-level dashboard summaries, this project executed an intensive data integrity run to resolve structural and configuration distortions hidden within the flat transactional files:

* The Shelf-Life Inversion Fix: Discovered an Excel pivot panel error where Shelf Life (days) was tracking as a cumulative SUM instead of a true statistical AVERAGE. This error artificially inflated the product lifespan matrix to a distorted 125,000+ day run (e.g., listing Ghee with an impossible 42,508-day storage window). The dataset was adjusted to a realistic AVERAGE baseline (Ghee at a true 115.2 days; Curd at a high-velocity 5.9 days).
* The "Least Revenue" Mapping Correction: Isolated a visualization misconfiguration where the bottom horizontal bar chart, labeled "least 5 customer location", incorrectly displayed mid-tier market performers (Telangana and Madhya Pradesh). This was relabeled to "Mid-Tier State Revenue Distribution Ratios" to prevent severe reporting loops.
* Float & Value Truncation: Cleaned inconsistent floating-point extensions across vectorized calculation columns using string normalization and rounding rules.

------------------------------
##  Key Business Intelligence Insights
## 1. Multi-Channel Commercial Distribution Setup
Fulfillment velocities were processed across three primary market networks to measure gross value capture:

* Retail Storefronts: The absolute leading channel driver, yielding INR 20.86M (35.5% of macro share).
* Wholesale Operations: Solid institutional bulk network generating INR 20.21M (34.4% of macro share).
* Online Inbound Stores: The highest-risk growth vulnerability, lagging behind at INR 17.65M (30.1% of macro share).

## 2. Regional Demand Distribution

* Top-Tier Consumer Zones: Market demand is heavily concentrated inside Chandigarh (INR 6.33M) and Delhi (INR 6.32M).
* Tier 2 Anchors: Bihar (INR 4.50M) serves as a robust secondary performance leader, while Kerala (INR 3.91M) and West Bengal (INR 3.67M) anchor long-range logistical runs.
* Absolute Growth Deficits: Haryana (INR 2.91M) and Rajasthan (INR 3.11M) represent the absolute lowest-yielding markets, identifying immediate candidates for sub-optimal channel re-engineering.

## 3. Seasonal Velocity Trends

* Peak Cash Node: Commercial activity maximizes its velocity profile in January (INR 5.91M), followed closely by Q3 rebounds in September (INR 5.38M).
* The Monsoon Plateau: Revenue drops into a steady mid-year dip during July (INR 4.48M) and August (INR 4.64M).
* Absolute Floor Node: Bottom-line flow drops to its absolute seasonal baseline during April (INR 4.28M).

------------------------------
##  Visualizations Included
The analytics workbook translates the audited pivot models into clear business performance charts:

   1. Total Monthly Revenue Curve: A seasonal velocity line graph mapping cash flow fluctuations over rolling month-by-month cycles.
   2. Total Revenue per Channel: Column bar chart isolating macro share between Online, Retail, and Wholesale distribution tracks.
   3. Least 5 Customer Locations (Corrected): Regional performance map displaying the sub-optimal target states.
   4. Herd Density Pie Chart: Proportional split matrix tracking cow distribution across farm scales (Large: 34%, Medium: 33%, Small: 33%).
   5. Average Product Shelf Life: Horizontal profile analysis indexing food asset perishability windows (ranging from stable Ghee to ultra-short fresh Curd runs).



