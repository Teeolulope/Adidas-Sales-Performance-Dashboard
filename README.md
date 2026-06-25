# Adidas-Sales-Performance-Dashboard
An interactive Power BI dashboard analysing $120 million in Adidas sales data across 2020 and 2021, covering six product categories, five US regions, six major retail partners, and three sales channels. Built to answer key strategic questions about where Adidas is generating revenue, where growth is happening, and where corrective action is needed.

**📌 Project Goal**

Design an analytical dashboard for Adidas sales and commercial leadership to understand which product categories, regions, retailers, and sales channels are driving revenue and profit — and to identify growth opportunities and underperforming areas that require strategic intervention.📌 Project Goal

**🗂️ Dataset**

The dataset contains transactional sales records for Adidas across US retail partners from 2020 to 2021.

Columns included:

Retailer- Name of the retail partner (Foot Locker, West Gear, etc.), Retailer ID- Unique identifier for each retailer, Invoice Date- Date of the sales transaction, Region- US region (Northeast, Southeast, South, Midwest, West), State- State where the transaction occurred, City- City where the transaction occurred, Product- Product category sold, Price per Unit- Selling price per unit, Units Sold- Number of units in the transaction, Total Sales- Total revenue generated, Operating Profit- Profit after operating costs, Operating Margin- Profit as a percentage of revenue, Sales Method- Channel used (Online, Outlet, In-store)

<img width="1641" height="730" alt="Screenshot 2026-06-24 101255" src="https://github.com/user-attachments/assets/58693167-4e5d-4f91-bea9-213db5ee383b" />

**📊 Dashboard Views**

**Overview — Total Sales (All Years)**
Adidas performance across both years combined
<img width="1136" height="640" alt="Screenshot 2026-06-24 104326" src="https://github.com/user-attachments/assets/58c08133-74da-4e84-bba8-70dcd904cd7c" />

**Profit View (All Years)**
Same dashboard filtered to Profit — revealing where high revenue does not always mean high profit
<img width="1131" height="640" alt="Screenshot 2026-06-24 104429" src="https://github.com/user-attachments/assets/a188ad50-5ea1-40f3-a7e3-b1be74762746" />

**2020 View — COVID-Impacted Year**
Baseline year showing suppressed performance across all categories and regions
<img width="1135" height="640" alt="Screenshot 2026-06-24 104150" src="https://github.com/user-attachments/assets/0227a749-e683-4268-8c68-fd7e21a5e972" />

**2021 View — Recovery Year**
Strong rebound year showing which categories and retailers led the recovery
<img width="1134" height="640" alt="Screenshot 2026-06-24 104108" src="https://github.com/user-attachments/assets/6f45190a-aed6-4d4d-af93-d7efc48c902b" />

**⚙️ Technical Approach & Methodology**

**Data Cleaning & Preparation**

. Removed duplicate records and handled missing values across customer and transaction fields
. Standardised date formats and ensured consistency across all regional and product records
. Reordered and renamed columns for clarity using Power Query's advanced editor
. Verified data types for all numeric and date fields before loading into the data model


**DAX Measures Development**

Created the following dynamic measures to support KPI tracking and the Metric Selector feature:

. daxTotal Sales = SUM('Adidas'[Total Sales])

. Total Profit = SUM('Adidas'[Operating Profit])

. Operating Margin = DIVIDE([Total Profit], [Total Sales])

. Units Sold = SUM('Adidas'[Units Sold])

. Avg Price per Unit = AVERAGE('Adidas'[Price per Unit])

. Selected Metric = 
IF(
    SELECTEDVALUE('MetricSelector'[Metric]) = "Profit",
    [Total Profit],
    [Total Sales]
)

The Selected Metric measure powers all bar charts and the region matrix simultaneously — allowing the viewer to switch between Total Sales and Profit across every visual with one click.


**❓ Business Questions Answered**

. Which product category drives the most revenue?
. Which retailer is Adidas' strongest partner?
. Which product performs best in each region?
. Which product categories grew the most year over year?
. When does Adidas sell the most and least?
. Which sales channel contributes most to revenue?


**🔍 Key Findings**

**Product Performance**
Men's Street Footwear leads all categories at $28M in total sales — nearly double the lowest performing category. It held its top position in both 2020 and 2021, confirming it is a structurally strong category rather than a one-year anomaly. Women's Apparel showed the strongest proportional growth year over year, suggesting rising demand worth investing in.

**Regional Performance**
The West region dominates at $36.44M — more than the South ($20.60M) and Midwest ($16.67M) combined. The product-by-region matrix reveals the West consistently leads across every single product category. The Midwest is the weakest region across all categories and all metrics.

**Retailer Performance**
West Gear leads total sales at $32M overall but its dominance was more concentrated in 2020 ($12M out of $24M total — a 50% share). In 2021, Foot Locker and Sports Direct both reached $23M each, overtaking West Gear's proportional contribution and signalling a shift in retail momentum. Amazon and Walmart consistently underperform at $10M and $11M respectively.

**Sales Channel Performance**
Online leads at 37.42% of total revenue, outperforming both Outlet (32.9%) and In-store (29.68%). Importantly, Online maintained its leadership position even in 2021 when physical retail had fully reopened — confirming the shift to digital purchasing is structural, not a temporary COVID behaviour.

**Seasonal Trends**
Sales follow a consistent seasonal pattern: January to April declining (post-holiday slowdown), April to August climbing to peak ($12.6M in July, $12.3M in August), August to November gradually declining, then recovering in December ($11.4M) driven by holiday gifting. This pattern directly informs when inventory should be stocked and when promotions should be scheduled.

**Year-over-Year Growth**
Every category showed dramatic growth from 2020 to 2021. Men's Street Footwear had the largest absolute jump (from $5M to $23M). Women's Athletic Footwear and Women's Street Footwear showed the smallest proportional growth, suggesting less momentum in the Women's footwear segment compared to Men's.

**Revenue vs Profit**
Switching the Metric Selector from Total Sales to Profit reveals that the category ranking stays consistent — Electronics and top performers maintain their positions. No category shows inflated revenue with suppressed profit, indicating discounting is not distorting the business unevenly across segments.


**✅ Business Recommendations**

**Product Strategy**
Men's Street Footwear should be protected and grown through expanded ranges and targeted marketing timed around the July–August peak. Women's Apparel shows the strongest growth momentum and warrants increased inventory allocation and dedicated marketing in the next cycle.

**Channel Optimisation**
Online is the top revenue channel and structurally dominant — continued investment in digital infrastructure is justified. Outlet contributes nearly a third of sales and should be curated to move excess inventory without cannibalising full-price channels.

**Regional Focus**
The West model should be studied and applied to underperforming regions. The Midwest requires investigation — its weakness is consistent across every category and every metric, suggesting a distribution or marketing coverage gap rather than a demand problem.

**Demand Forecasting**
2020 data is COVID-distorted and should be excluded or heavily discounted when building forward inventory plans. Inventory orders should be placed 6–8 weeks before the July–August peak. February and April are the natural windows for promotional campaigns to clear slow-moving stock.

**Retailer and Partner Management**
Foot Locker's 2021 momentum ($23M) warrants deeper strategic investment. Amazon and Walmart are significantly underperforming relative to other partners and should be assessed on whether further investment is warranted or whether they serve primarily as volume-clearing channels.

**🛠️ Tools Used**

Power Query — Data cleaning, transformation, and column standardisation

Power BI Desktop — Data modelling, DAX measures, and dashboard development

DAX — Custom measures for KPI tracking and dynamic metric selection
