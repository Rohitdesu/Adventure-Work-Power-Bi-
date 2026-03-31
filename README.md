# AdventureWorks Sales Dashboard - Power BI

This is my first Power BI project where I built a full sales analytics dashboard using the AdventureWorks dataset. The report has 4 main pages plus a custom tooltip page, with navigation buttons, bookmarks, slicers, and a bunch of DAX measures I wrote from scratch.

---

## What's inside

The data model follows a star schema with Sales Data and Returns Data as the two fact tables, connected to lookup tables for customers, products, categories, subcategories, calendar dates, and territory/geography.

**Tables I used:**
- Sales Data (main fact table)
- Returns Data
- Customer Lookup
- Product Lookup
- Product Subcategories Lookup
- Product Categories Lookup
- Calendar Lookup
- Territory Lookup
- Product Category Sales (Unpivot Demo)
- Measure table (where all my DAX measures live)
- Price Adjustment % (what-if parameter)
- Product Metric Selection (field parameter)
- Customer Metric Selection (field parameter)

---

## DAX Measures

All measures are in a separate Measure table to keep things clean.

- Total Revenue
- Total Profit
- Total Orders
- Total Returns
- Return Rate
- Total Customers
- Average Revenue Per Customer
- Previous Month Revenue
- Previous Month Orders
- Previous Month Returns
- Adjusted Profit (uses the price adjustment what-if parameter)
- Order Target
- Revenue Target
- Profit Target

---

## Report Pages

### Executive Dashboard
Main page. Has 4 KPI cards at the top showing revenue, profit, orders and return rate. Below that there's a line chart for revenue trending over time, a clustered bar chart for orders by product category, and a matrix table breaking down products by orders, revenue and return rate. At the bottom there are 3 KPI tiles showing current month vs previous month for revenue, orders, and returns.

### Map
Just a map visual showing total orders by country, sized by bubbles. Has a continent slicer at the top to filter by region.

### Product Detail
Has 3 gauge charts comparing monthly orders, revenue, and profit against targets. There's a line chart showing total profit vs adjusted profit (the adjusted profit changes based on the price adjustment slicer). Also an area chart for product metric trending that switches dynamically based on which metric you pick from the slicer.

### Customer Detail
Shows total customers and average revenue per customer as KPI cards. Has a line chart trending both metrics over time, two donut charts for orders by income level and by occupation, and a table with the top 100 customers. When you click a customer in the table, the cards on the right update to show that customer's name, orders, and revenue.

### Category Tooltip (hidden page)
This is a custom tooltip page, size 350x225. It shows a multi-row card with revenue, profit, orders, returns, and return rate, plus a small area chart. This pops up when you hover over category visuals on other pages.

---

## Navigation and UI

Built a custom navigation sidebar using action buttons with icon images. Each button has two versions of the icon - a white one for default state and a blue one for hover/selected state. There's also a slide-out slicer panel that can be toggled using bookmarks.

**Bookmarks I set up:**
- clear all filters in exec
- customer insight
- clear all filters customer
- Hide Slicer Panel
- Show Slicer Panel

---

## Tools used

- Power BI Desktop (Cloud release, October 2024)
- DAX for all measures
- Power Query for data loading and transformation
- What-if parameters for the price adjustment scenario
- Field parameters for dynamic metric switching
- Custom PNG icons embedded in the report (AdventureWorks logo + nav icons)

---

## How to open

Just download the .pbix file and the resource files open it in Power BI Desktop. Make sure you have the October 2024 version or later otherwise some features might not load correctly.

---

## Notes

This was built as a learning project to practice data modeling, DAX, and report design in Power BI. The AdventureWorks dataset is a sample dataset provided by Microsoft.
